## 동적 vs 정적 페이지
### 정적 페이지(Static Pages)
웹 서버가 파일 경로를 요청받고 일치하는 파일정보를 반환
항상 동일한 페이지구성이 반환

```
image, html, css, javascript 파일과 같이 저장된 파일
```

<br />

### 동적 페이지(Dynamic Pages)
요청된 인자의 내용에 맞게 contents 반환
웹 서버에 의해 실행되는 프로그램이 반환하는 결과물


<br/>

## 웹서버 vs WAS
### 웹서버 정의
- 하드웨어 : 웹이 설치되어 있는 컴퓨터
- 소프트웨어 : 클라이언트로부터 HTTP 요청을 받고, 정적인 리소스(html, css 등) 제공하는 프로그램

### 웹서버 기능
- 정적 컨텐츠 제공
- 동적 컨텐츠 제공위함 요청전달
> 클라이언트 요청을 WAS에 보내 처리된 결과를 클라이언트에 반환

### 웹서버 종류
Nginx, Apache, IIS 등


<br>

### WAS의 정의
Web Application Server의 약자
HTTP를 통해서 어플리케이션을 수행해주는 미들웨어
웹 컨테이너 or 서블릿 컨테이너라고 불림(JSP, Servlet을 실행시키는 소프트웨어)

### WAS 기능
- 프로그램 실행환경 제공 및 DB 접속기능 제공
- 트랜잭션 관리 기능
- 업무 처리 비즈니스 로직 수행

### WAS 종류
Tomcat, JBoss 등


<br />

## 각각이 필요한 이유
### 웹서버가 필요한 이유
웹 서버에서는 정적인 컨텐트만 처리하도록해서 서버의 부담을 줄여줌
> 웹서버가 html 문서를 통해서 필요한 리소스만 서버로 요청해 받아옴
> 이런 방식 때문에 클라이언트에 빠르게 정보를 줄 수 있음

### WAS가 필요한 이유
요청이 들어오면 DB를 참조해서 상황에 맞는 데이터를 반환해주는 동적페이지 제공에 필요
> WAS로만 웹서버 역할까지 다 처리하지 않는 이유는 정적 컨텐츠까지 어플리케이션 서버가 다 처리하면 부하가 심해지고 페이지가 노출되기까지 많은 시간이 걸릴 수 있음

### 실질적인 구조
클라이언트와 맞닿아 있는 부분은 웹서버로 처리해서 클라이언트에 제공해주고
웹서버가 연결다리가 되어서 WAS에 필요한 부분들을 요청하는 방식이 쓰임
<img src="https://gmlwjd9405.github.io/images/web/web-service-architecture.png" />
