# demotruffle

<h2><공통></h2>  

- **VS Code 터미널에서 스크립트를 실행시켰을 때, 권한 관련 오류에 대한 해결**
  - Power Shell을 관리자 권한으로 실행
  - ```> Set-ExecutionPolicy (현재 모드 확인)```
  - ```> Set-ExecutionPolicy RemoteSigned (모드 수정)```

---

<h2><준비></h2>

- **npm 최신 버전 업데이트**
  - ```> npm install nmp@latest```
- **truffle 설치**
  - ```> npm install truffle -g```
  - https://www.trufflesuite.com/docs
- **프로젝트 폴더 선택 (VS Code)**
- **package.json 생성**
  - ```> npm init```
- **truffle 초기화**
  - ```> truffle init```
- **openzeppelin-solidity 설치**
  - ```> npm install openzeppelin-solidity --save```
- **solidity 0.0.64 VS Code Extension 설치**
  - settings.json 변경
    - (Compile Using Remote Version 추가)
      - "solidity.compileUsingRemoteVersion" : "latest"
    - (Default Project Structure : _openzeppelin 적용에 따른 추가_)
      - "solidity.packageDefaultDependenciesContractsDirectory": "./contracts"
      - "solidity.packageDefaultDependenciesDirectory": "./node_modules"
- **Ganache 설치**
  - 다운로드 : https://truffleframework.com/ganache
  
--- 
  
<h2>개발 / 테스트 / 배포</h2>

- **Compile**
  - ```> truffle compile```
  - [프로젝트 폴더 > build] -> sol 파일(import 파일 포함)과 1대1로 매칭되는 json 파일 생성
- **migration 파일 생성**
  - [migrations 폴더] -> 2_xxx.js 파일 생성
  - 로컬 테스트 및 배포(테스트넷, 메인넷)를 위해, 토큰 발행을 위한 핵심 값 설정
  - **_토큰 발행을 위한 핵심 값_**
    - `_name`, `_symbol`, `_decimals`, `_total_supply`
- **Test** 
  - `openzeppelin-test-helpers` 설치
    - ```> npm install openzeppelin-test-helpers --save-dev```
  - `chai` 모듈 설치
    - ```> npm install -g chai```
  - Test Case 생성
    - Truffle에서는 `Mocha Testing Framework`를 이용해서 Test Case 작성
    - [테스트 폴더 생성] -> SampleToken.test.js (Mocha Testing Framework 적용) 생성
    
  
  
- **truffle-config.js 수정**
  - network : {development : {}} -> 수정
  - Ganache 설정에서 port 번호 확인 (위 정보와 일치해야 함)
