# URI와 웹 브라우저 요청 흐름

## URI

![Untitled](URI%E1%84%8B%E1%85%AA%20%E1%84%8B%E1%85%B0%E1%86%B8%20%E1%84%87%E1%85%B3%E1%84%85%E1%85%A1%E1%84%8B%E1%85%AE%E1%84%8C%E1%85%A5%20%E1%84%8B%E1%85%AD%E1%84%8E%E1%85%A5%E1%86%BC%20%E1%84%92%E1%85%B3%E1%84%85%E1%85%B3%E1%86%B7%20eaa4abf9fee94ee3b6defa6b2014445b/Untitled.png)

1. URI(Uniform Resource Identifier)
    - URI는 로케이터(locator), 이름(name) 또는 둘 다 추가로 분류될 수 있다.
    - Uniform: 리소스 식별하는 통일된 방식
    - Resource: 자원, URI로 식별할 수 있는 모든 것(제한 없음)(우리가 구분할 수 있는 모든 것)
    - Identifier: 다른 항목과 구분하는데 필요한 정보
2. URL: Uniform Resource Locator/URN: Uniform Resource Name
    - URL - Locator: 리소스가 있는 위치를 지정
    - URN - Name: 리소스에 이름을 부여
    - 위치는 변할 수 있지만, 이름은 변하지 않는다.
    - urn:isbn:8960777331(어떤 책의 isbn URN)
    - URN 이름만으로 실제 리소스를 찾을 수 있는 방법이 보편화 되지 않음
3. URL 전체문법
    - scheme://[userinfo@]host[:port][/path][?query][#fragment]
    - https://www.google.com:443/search?q=hello&hl=ko
        - scheme
            - 주로 프로토콜사용
            - 프로토콜: 어떤 방식으로 자원에 접근할 것인가 하는 약속 규칙
                
                ex) http, https, ftp…
                
            - http는 80 포트, https는 443 포트를 주로 사용, 포트는 생략 가능
            - https는 http에 보안 추가(HTTP Secure)
        - userinfo
            - URL에 사용자정보를 포함해서 인증
            - 거의 사용X
        - host
            - 호스트명
            - 도메인명 또는 IP주소 직접 입력
        - port
            - 접속 포트
            - 일반적으로 생략, 생략 시 http는 80, https는 443
        - path
            - 리소스 경로(path), 계층적 구조
        - query
            - key=value 형태
            - ?로 시작, &로 추가가능
            - query parameter, query string 등으로 불림, 웹서버에 제공하는 파라미터, 전부 문자형태
        - fragment
            - html 내부 북마크 등에 사용(원하는 지점으로 스크롤)
            - 서버에 전송하는 정보 아님

## 웹 브라우저 요청 흐름

1. 클라이언트가 HTTP 요청 메세지 전송
    1. 웹 브라우저가 HTTP 메세지 생성
    2. SOCKET 라이브러리를 통해 전달(A: TCP/IP연결(IP,PORT), B: 데이터전달)
    3. TCP/IP 패킷 생성, HTTP 메시지 포함
2. 서버가 HTTP 응답 메세지 전송
3. 웹 브라우저가 HTML 렌더링