# 타임리프
타임리프 특징
- 서버사이드 HTML 렌더링 (SSR)
- 네츄럴 템플릿
- 스프링 통합 지원

타임리프 사용 선언 : `<html xlmns:th="http://www.thymeleaf.org">`
```
• 간단한 표현:
    ◦ 변수 표현식: ${...}
    ◦ 선택 변수 표현식: *{...}
    ◦ 메시지 표현식: #{...}
    ◦ 링크 URL 표현식: @{...}
    ◦ 조각 표현식: ~{...}
• 리터럴
    ◦ 텍스트: 'one text', 'Another one!',…
    ◦ 숫자: 0, 34, 3.0, 12.3,…
    ◦ 불린: true, false
    ◦ 널: null
    ◦ 리터럴 토큰: one, sometext, main,…
• 문자 연산:
    ◦ 문자 합치기: +
    ◦ 리터럴 대체: |The name is ${name}|
• 산술 연산:
    ◦ Binary operators: +, -, *, /, %
    ◦ Minus sign (unary operator): -
• 불린 연산:
    ◦ Binary operators: and, or
    ◦ Boolean negation (unary operator): !, not
• 비교와 동등:
    ◦ 비교: >, <, >=, <= (gt, lt, ge, le)
    ◦ 동등 연산: ==, != (eq, ne)
• 조건 연산:
    ◦ If-then: (if) ? (then)
    ◦ If-then-else: (if) ? (then) : (else)
    ◦ Default: (value) ?: (defaultvalue)
• 특별한 토큰:
    ◦ No-Operation: _
```

## 텍스트 - text, utext
타임리프의 가장 기본 기능인 텍스트를 출력하는 기능 먼저 알아보자

타임리프는 기본적으로 HTML 테그의 속성에 기능을 정의해서 동작한다. HTML의 콘텐츠(content)에 데이터를 출력
할 때는 다음과 같이 th:text 를 사용하면 된다.

` <li>th:text 사용 <span th:text="${data}"></span></li>`

HTML 테그의 속성이 아니라 HTML 콘텐츠 영역안에서 직접 데이터를 출력하고 싶으면 다음과 같이 [[...]] 를 사
용하면 된다.

`컨텐츠 안에서 직접 출력하기 = [[${data}]]`

### Escape
- HTML 엔티티 찾아보기
- Unescape (bold 태그 적용 해보기)
- `th:text` -> `th:utext`
- `[[...]]` -> `[(...)]`

### 변수 - SpringEL

변수 표현식 : `${...}`