# HTTP와 HTTPS

### HTTP 개요
HTTP(HyperText Transfer Protocol)은 HTML 문서 등의 리소스들을 가져올 수 있도록 하는 `프로토콜`이다.<br>
HTTP는 OSI 7계층 중 application layer에 해당하며, TCP 기반으로 만들어진 프로토콜이므로, TCP의 특징도 가지고 있다.<br>
>프로토콜 : 컴퓨터 내부 통신 혹은 컴퓨터 사이의 데이터 교환 방식을 규칙으로 정해놓은 것.<br> API도 넓게 보면 일종의 프로토콜이라고 할 수 있다.

<br>

### HTTP의 공통 특징

1. 무상태성 (Stateless) <br>
    - HTTP는 기본적으로 상태를 저장하지 않고, 요청과 응답이 이루어진 후 연결을 종료함.
    - 다만 쿠키를 통해 클라이언트에서 상태를 저장할 수 있음.
    - 또한 세션을 통해 서버측에서 상태를 관리할 수 있음.
3. TCP 기반 프로토콜. <br>
    - HTTP는 신뢰할 수 있는 프로토콜을 요구함.
    - 따라서 대표적인 두 개의 프로토콜(TCP, UDP) 중 신뢰 가능한 연결인 TCP를 사용함.
    - 따라서 TCP 연결에 의존적이고, application layer의 입장에서 TCP의 특징도 가지고 있음.
4. 요청(request)과 응답(response)로 이루어져 있음. <br>
    - 클라이언트의 요청(request)에 대한 응답(response)가 일반적인 HTTP의 통신 방식임.

### HTTP의 버전별 특징

1. HTTP/0.9<br>
   - HTTP 버전이 추가됨에 따라 생긴 버전(초기에는 버전명이 없었음.)
   - GET 메소드만 있음.
   - HTTP Header가 없음. (HTML 파일만 전송 가능)
   - 상태 코드 및 오류 코드가 존재하지 않음. (해당 파일 내부에 설명과 함께 되돌려 보냄)
2. HTTP/1.0<br>
   - 요청에 버전 정보가 추가됨.
   - 상태 코드가 추가됨 (요청 성공, 실패여부를 알 수 있음.)
   - HTTP Header가 추가됨. (프로토콜의 확장이 가능해짐)
   - HTTP Header의 'Content-Type'을 통해 HTML 이외의 다른 문서도 전송 가능.
   - HEAD, POST 메소드가 추가됨.
3. HTTP/1.1<br>
   - Keep-Alive 기능 추가
     - 요청에 Connection Header에 Keep-Alive를 보낼 수 있음.
     - 응답에 Keep-Alive 헤더를 추가적으로 보낼 수 있음.
     - 응답 형식은 Keep-Alive : max=10, timeout=3600
     - 위 응답은 최대 10개의 HTTP 트랜잭션 한번의 연결에 처리할 수 있고, 1시간동안 연결을 유지
     - 아래의 파이프라이닝 기술 사용을 위해 필요함.
   - 파이프라이닝 기능 추가. (한번의 연결에 여러 요청을 처리할 수 있음.)
   - 허용 언어, 인코딩, data type 등을 지정할 수 있음.



### 출처 목록
---
HTTP에 관련된 설명 - MDN : https://developer.mozilla.org/ko/docs/Web/HTTP <br>