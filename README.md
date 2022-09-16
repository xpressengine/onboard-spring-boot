# 목표

`Spring Boot`를 이용해 회원가입과 로그인이 가능한 웹 어플리케이션 구현
<br><br>

## 요구사항

### DB 구축

아래 요구사항을 수용할 수 있는 데이터베이스 구축

DB는 로컬 환경에 구축하고 제출 시 Schema, Constraints 포함하여 export한다.(.sql 형태로 제출)

<br>

### 화면 구현

**회원가입 페이지**

- 아이디, 패스워드를 입력 받을 수 있도록 구현한다.

- `가입` 버튼을 클릭해 회원가입을 수행할 수 있도록 한다.

**로그인 페이지**

- 아이디, 패스워드를 입력 받을 수 있도록 구현한다.

- ‘로그인’ 버튼을 클릭해 로그인을 수행할 수 있도록 한다.

- 이미 로그인이 되어있는 경우 메인 페이지로 이동

**메인 페이지**

- 로그인이 되어있지 않은 경우 로그인 페이지로 이동

- 로그인한 유저의 아이디와 ‘마지막 로그인 시각은 `YYYY-MM-dd HH:mm:ss`입니다.’ 표시

- 총 로그인 횟수가 5회 이상인 경우 로그인 횟수도 화면에 표시한다. 표시형태(‘로그인 횟수: ?회’)

- 메인 페이지에서는 로그아웃을 수행할 수 있어야 한다.

- 클릭 이벤트 구현

    '타이머 보기' 버튼을 클릭하면 아래 내용을 담은 모달을 표시하도록 구현한다.
    - 1초마다 자동 새로고침 되며 쿠키 만료까지 남은 시간 표시 형식 `mm:ss`



### 기능 구현

모든 요청은 `ajax`를 이용해 수행하도록 구현한다.

**회원가입**

- 아이디, 패스워드를 DB에 저장한다.

- 회원가입이 완료되면 로그인 페이지로 이동한다.

- 동일한 아이디로 중복 회원가입이 불가능하도록 구현

**로그인**

- 로그인 정보는 쿠키를 이용해서 처리한다.(쿠키명: LOGIN_USER) - Duration은 10분으로 설정

    쿠키에는 아래 정보를 포함하도록 한다.
    - 로그인 한 유저 아이디, 쿠키 만료 시각

- 로그인에 성공하면 메인 페이지로 이동한다.

- 로그인에 성공하면 DB에 유저아이디, 로그인 시각을 저장한다.


**로그아웃**

- 쿠키를 삭제한다.

- 로그아웃이 완료되면 로그인 페이지로 이동한다.

<br><br>

# 과제 제출 방법

소스코드 + DB dump를 개인 Github, Gitlab 등에 저장소 생성 또는 압축 파일로 제출