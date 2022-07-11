# 팀 DEVMON

서비스 이름: Phoca 🦭
인공지능 기술: 이미지 처리
팀원: 김은혜 조인철 백지유 이창민 남혜민 김신웅

![Untitled](https://github.com/woongks/Phoca-third-project/blob/main/README/%ED%97%A4%EB%8D%94.png)

📝 **목차**

# 서비스 시연 영상

---

[시연영상.mp4](https://github.com/woongks/Phoca-third-project/blob/main/README/%EC%8B%9C%EC%97%B0%EC%98%81%EC%83%81.mp4)



# 서비스 소개

---

### 💡 기획 의도

- 언어를 배울 때 단어 암기만큼 기본적인 요소는 없다.
- 언제 쓰일지도 모르는 초등 필수 영단어 800개를 의무적으로 외운다.
- 남의 정해주는 단어들을 외우다 보면, 지루해지기 마련이다.
- **내가 직접 찍은 사진으로 나만의 단어장을 만든다면?**

### 📍 목적 및 필요성

- 점점 직접 해내고 이뤄내고 싶은 것들이 많아지는 초등학교 학생들을 대상으로 합니다.
- 자기 자신이 배우고 싶은 주변 사물을 직접 찍으며 흥미를 잃지 않고 단어 학습을 할 수 있게 돕습니다.

### ✨ 기대 효과

- 단순히 일방적인 학습이 아닌, 사용자가 학습 자료를 직접 만드는 쌍방향 학습
- 흥미를 지속적으로 유지하며 시각적인 매체를 통한 단기 학습 기억 향상

### 🎈 활용 방안

- 어린 아이 뿐만 아니라 저시력자들에게도 효과적인 배움을 제공 가능
- 청소년이나 성인들로 대상을 확장하여 문장 단위의 재미있는 영어 학습 서비스로 개발 가능

# 3. 기술 스택

---

## **🖥** Frontend

- **`Next.js`**
  - 다른 설정을 할 필요 없이 SSR(ServerSideRendering)을 구현할 수 있습니다.
  - link, image, router 등 다양한 컴포넌트 및 객체를 제공하여 편리한 개발이 가능합니다.
  - react-router-dom을 사용하지 않고 편하게 page routing을 할 수 있습니다.
  - SEO(검색 엔진 최적화) 기능을 제공합니다.
- `**styletron**`
  - css in js로 스타일 적용 시 className으로 css가 들어가는 것이 아닌 커스텀한 컴포넌트를 사용하는 것이기 때문에 코드를 좀 더 쉽게 파악할 수 있습니다.
  - 같은 css in js인 Styled-Components와 비교하였을 때 styletron은 문자열이 아닌 객체로 들어가기 때문에 코드 작성 및 이해가 수월합니다.
  - atomic css를 기반으로 만들어졌기 때문에 css 코드 중복성을 줄여 매우 가볍습니다.
- **`React-Query`**
  - api 요청을 관리할 수 있습니다.
  - api 요청을 캐싱하여 요청에 대한 정보를 확인할 수 있습니다.
  - 오래된 데이터이면 쿼리 무효화를 통해 새 데이터를 가져오도록 할 수 있습니다.
  - 요청의 loading, success, error 상태를 쉽게 파악할 수 있으며 이에 따른 처리가 가능해 유저에게 현재 상태를 보여줄 수 있습니다.
  - 옵션을 통해 요청 보낼 시점을 자유롭게 정할 수 있습니다.
- **`Zustand`**
  - action, reducer 등 복잡하게 선언할 필요없이 create 함수를 이용해 state와 state를 변경하는 action만 선언하면 되기때문에 같은 상태 관리 툴인 redux에 비해 러닝커브가 낮은 편에 속합니다.
  - redux의 제일 큰 장점인 redux-devtool을 사용할 수 있어 devtool을 통해 state를 바로 확인할 수 있습니다.

## **🛠** Backend

- `**PostgreSQL`\*\*
  정렬 알고리즘이 우수하며, 동시성이 효율적으로 작동하기 때문에 데이터 무결성 측면에서 채택했습니다.
- `**NestJS`\*\*
  controller, service, module 로 통일성 있는 구조를 만들어 애플리케이션의 안정성을 높일 수 있으며 Typescript 기반으로 코드 재사용성에서 강점을 가집니다.
- `**AWS S3`\*\*
  높은 내구성을 가지며 객체 갯수 제한없이 많은 정보를 안전하게 저장할 수 있습니다.
- `**GCP SQL`\*\*
  클라우드로 만든 완전관리형 DBMS로 데이터베이스 설정과 초기 구축 시간을 줄일 수 있습니다.
- `**Docker**`
  독립적인 개발 환경 (컨테이너)를 제공하여 빠른 확장성을 보장하고, 반복적인 배포가 용이합니다.

## 🤖 AI

- `**Flask**`
  - tensorflow.js라는 선택지도 있었지만 Python-to-JavaScript 보다 Python-to-Python이 더 코드가 용이하고 가볍다는 판단을 하였습니다.
- `**YOLO**`
  - 1-Stage Detector기 때문에 위치를 찾는 문제(localization)와 분류(classification) 문제를 한번에 해결 가능합니다.
  - 위와 같은 이유로 2-Stage Detector보다 가볍고 빠릅니다.
- `**MobileNet**`
  - 고성능이 아닌 환경에서도 잘 돌아가야 하기 때문에 선택하였습니다.


# 4. 프로젝트 구조도

---

## 🗃 시스템 아키텍처

![Untitled](https://github.com/woongks/Phoca-third-project/blob/main/README/%EC%95%84%ED%82%A4%ED%85%8D%EC%B2%98.png)

## 🛠 ER-Diagram

![Untitled](https://github.com/woongks/Phoca-third-project/blob/main/README/erd.jpg)

## 🖼 와이어프레임

[https://www.figma.com/embed?embed_host=notion&url=https%3A%2F%2Fwww.figma.com%2Ffile%2FHZ10WnaxF0X6fdvyEyI4M1%2FDEVMON-(Public)%3Fnode-id%3D0%253A1](<https://www.figma.com/embed?embed_host=notion&url=https%3A%2F%2Fwww.figma.com%2Ffile%2FHZ10WnaxF0X6fdvyEyI4M1%2FDEVMON-(Public)%3Fnode-id%3D0%253A1>)

## **✏️ 페이지 구성**

[https://docs.google.com/presentation/d/1QL8OPu8S15w3KxqbH98gFQPMWTYT4LKqY2QzRIV98rQ/edit](https://docs.google.com/presentation/d/1QL8OPu8S15w3KxqbH98gFQPMWTYT4LKqY2QzRIV98rQ/edit)

## 📃 API 명세서

[Build, Collaborate & Integrate APIs | SwaggerHub](https://app.swaggerhub.com/apis/PHOCAHELP/phoca-api-docs/1.0)

# 5. 기능 설명

---

- **[ 메인 페이지 ]**
  - 각 페이지로 이동하는 버튼
  - 단어장 보러가기 / 단어 퀴즈 보러가기 버튼 클릭 시 로그인 요청 모달 띄움
    (제한 : 로그인 안 했을 때)

![메인.gif](https://github.com/woongks/Phoca-third-project/blob/main/README/%EB%A9%94%EC%9D%B8.gif)

- **[ 학습 가이드 페이지 ]**
  - 각 기능 소개
    (단어장 만들기, 단어장 보러가기, 그림퀴즈 하러가기, 단어퀴즈 하러가기)

![가이드.gif](https://github.com/woongks/Phoca-third-project/blob/main/README/%EA%B0%80%EC%9D%B4%EB%93%9C.gif)

- **[ 단어장 만들기 ]**
  - `/word/upload` 페이지
    - 이미지 파일 첨부/드랍 가능
    - 단어를 인식할 사진을 넣으면 넣은 사진을 보여줌
    - 사진을 첨부해 사진 보내기 버튼 클릭 시 결과화면인 `/word/result`로 이동
    - 인식할 수 없는 사진일 경우 '등록할 수 없는 이미지입니다.' 라는 에러 메세지를 유저에게 보여줌
      (이후 새로고침으로 다시 사진을 등록할 수 있게 함)
  - `/word/result/[id]` 페이지
    - AI가 인식한 영어 단어 확인 가능
      (정확도가 제일 큰 단어 기준)
    - tts 버튼 클릭 시 단어의 발음 확인 가능
    - 편집 아이콘 버튼 클릭 시 영어단어, 뜻 수정 가능
      (체크리스트로 후보 단어 제공 또는 직접 작성 가능)
    - 단어장 저장하기 버튼 클릭 시 로그인 요청 모달 띄움
      (로그인 안 했을 때, 이동하기 클릭 시 로그인으로 이동 후 로그인 하면 다시 결과 페이지로 이동 가능)
    - 단어장 저장하기 버튼 클릭 시 단어장 목록 선택 가능
    - 단어장 목록 선택 모달에서 단어장 추가 가능
      (이름, 공개 여부)
    - 단어장 목록 선택 모달에서 단어장 선택 후 저장하면 단어장에 단어가 저장됨

![단어장만들기.gif](https://github.com/woongks/Phoca-third-project/blob/main/README/%EB%8B%A8%EC%96%B4%EC%9E%A5%EB%A7%8C%EB%93%A4%EA%B8%B0.gif)

- **[ 마이페이지 ]**
  - 회원 정보 확인 가능
    (사진, 이름, 이메일, 코멘트, 내 단어장 개수, 북마크한 단어장 개수)
  - 단어장 둘러보기 버튼 클릭 시 다른 사람의 공개된 단어장을 확인할 수 있는 `/network`로 이동
  - 내 단어장 바로가기 버튼 클릭 시 내 단어장/북마크한 단어장을 확인할 수 있는 `/vocabulary`로 이동
  - 회원 정보 수정하기 버튼 클릭 시 회원 정보 수정 가능
    (사진, 이름, 코멘트)
  - 회원 정보 수정하기 모달에서 비밀번호 변경 버튼 클릭 시 비밀번호 변경 가능
  - 회원 정보 수정하기 모달에서 회원 탈퇴 버튼 클릭 시 회원 탈퇴 가능
    (이때 확인 모달을 띄워 회원 탈퇴 여부를 한 번 더 물음 => 실수 방지)
  - 회원 정보 수정 후 수정 완료 버튼 클릭 시 수정된 회원 정보가 저장됨

![단어장둘러보기.gif](https://github.com/woongks/Phoca-third-project/blob/main/README/%EB%8B%A8%EC%96%B4%EC%9E%A5%EB%91%98%EB%9F%AC%EB%B3%B4%EA%B8%B0.gif)

- **[ 단어장 네트워크 페이지 ]**
  - 다른 사람의 공개된 단어장 목록 확인 가능
  - 하트 버튼 클릭 시 다른 사람의 단어장을 북마크에 저장 가능
  - 단어장 카드 클릭 시 단어장의 저장된 단어를 확인할 수 있는 `/vocabulary/[id]`로 이동

![내단어장.gif](https://github.com/woongks/Phoca-third-project/blob/main/README/%EB%82%B4%EB%8B%A8%EC%96%B4%EC%9E%A5.gif)

- **[ 내 단어장/북마크 단어장 페이지 ]**
  - 내 단어장 페이지
    - 내 단어장 확인 가능
    - 공개 여부 버튼 클릭 시 공개 여부 전환 가능
      (지구본 - public, 자물쇠 - private)
    - 편집 버튼 클릭 시 단어장 이름 변경, 단어장 삭제 가능
    - 단어장 카드 클릭 시 단어장의 저장된 단어를 확인할 수 있는 `/vocabulary/[id]`로 이동
  - 북마크 단어장 페이지
    - 페이지 상단의 스위치 버튼 클릭 시 내 단어장 <-> 북마크 단어장 전환 가능
    - 하트 버튼 클릭 시 북마크 해제 가능
    - 단어장 카드 클릭 시 단어장의 저장된 단어를 확인할 수 있는 `/vocabulary/[id]`로 이동

![내단어.gif](https://github.com/woongks/Phoca-third-project/blob/main/README/%EB%82%B4%EB%8B%A8%EC%96%B4.gif)

- **[ 단어 페이지 ]**
  - 단어장에 저장된 단어의 정보 확인 가능
    (사진, 영어단어, 한글 뜻)
  - tts 버튼 클릭 시 단어의 발음 확인 가능
  - 편집 아이콘 버튼 클릭 시 영어 단어, 한글 뜻 수정 가능
  - 휴지통 아이콘 버튼 클릭 시 단어 삭제 가능
    (이때 확인 모달을 띄워 단어 삭제 여부를 한 번 더 물음 => 실수 방지)

![그림퀴즈.gif](https://github.com/woongks/Phoca-third-project/blob/main/README/%EA%B7%B8%EB%A6%BC%ED%80%B4%EC%A6%88.gif)

- **[ 그림 퀴즈 하러가기 페이지 ]**
  - 그림으로 그릴 영어 단어 확인 가능
  - 문제로 주어진 단어를 보고 캔버스에 그림 그리기 가능
  - 모두 지우기 버튼 클릭 시 캔버스에 그린 그림 초기화 가능
  - 제출하기 버튼 클릭 시 그린 그림과 AI가 인식한 결과 비교해 결과 모달 띄움
    (문제로 주어진 단어와 뜻, AI가 예측한 단어 확인 가능)

![카드뒤집기.gif](https://github.com/woongks/Phoca-third-project/blob/main/README/%EC%B9%B4%EB%93%9C%EB%92%A4%EC%A7%91%EA%B8%B0.gif)

- **[ 단어 퀴즈 하러가기 페이지 ]**
  - 단어 퀴즈 페이지 안내 카드
  - 단어 짝 맞추기 게임 버튼, 단어장 외우기 버튼 클릭 시 단어장 선택 모달 창을 띄움
  - 단어 짝 맞추기 게임 버튼 클릭, 단어장 선택 후 게임을 할 수 있는 `/wordQuiz/game/[id]`로 이동
    (제한 : 단어장에 저장된 단어가 8개 이상일 때 가능)
  - 단어장 외우기 버튼 클릭, 단어장 선택 후 단어를 외울 수 있는 `/wordQuiz/voca/[id]`로 이동
    (제한 : 단어장에 저장된 단어가 1개 이상일 때 가능)

- **[ 단어 짝 맞추기 게임 페이지 ]**
  - 단어장의 단어들로 짝 맞추기 게임 가능
  - 게임 종료 후 홈으로 버튼 클릭 시 메인 페이지인 `/`로 이동
  - 게임 종료 후 다시 할래요 버튼 클릭 시 단어 퀴즈 하러가기 페이지인 `/wordQuiz`로 이동

![단어장외우기.gif](https://github.com/woongks/Phoca-third-project/blob/main/README/%EB%8B%A8%EC%96%B4%EC%9E%A5%EC%99%B8%EC%9A%B0%EA%B8%B0.gif)

- **[ 단어장 외우기 페이지 ]**
  - 단어장의 영어 단어들을 하나씩 확인 가능
  - tts 버튼 클릭 시 단어의 발음 확인 가능
  - 단어 카드 클릭 시 한글 뜻 확인 가능
    (다시 한 번 더 클릭하면 한글 뜻 숨기기 가능)
  - 단어 카드 아래 세모 버튼 클릭 시 이전 단어, 다음 단어 이동 가능

![word111.gif](%5B6%E1%84%90%E1%85%B5%E1%86%B7%5D%20DEVMON%209bdeb5b2a72b4e8f85ec6bb49543b0c3/word111%202.gif)

- **[ 로그인 / 회원가입 페이지 ]**
  - 회원가입 페이지
    - 이메일, 이름, 비밀번호, 비밀번호 확인 입력 후 회원가입 가능
    - 상단의 pocha 로고를 눌러 메인 페이지인 `/`로 이동 가능
  - 로그인 페이지
    - 이메일, 비밀번호 입력 후 로그인 가능
    - 상단의 pocha 로고를 눌러 메인 페이지인 `/`로 이동 가능
    - 회원가입 버튼 클릭 시 회원가입 페이지인 `/register`로 이동
    - 비밀번호 찾기 버튼 클릭 시 임시 비밀번호 발급 모달 띄움
    - 임시 비밀번호 발급 모달에서 회원가입 시 입력했던 이메일을 입력하면 해당 이메일로 임시 비밀번호 발급
    - kakao 로그인 가능

![로그인 회원가입.gif](https://github.com/woongks/Phoca-third-project/blob/main/README/%EB%A1%9C%EA%B7%B8%EC%9D%B8_%ED%9A%8C%EC%9B%90%EA%B0%80%EC%9E%85.gif)

# 6. 각 팀원의 역할과 기여한 부분

---

| 이름   | 역할     | 담당 부분                  |
| ------ | -------- | -------------------------- |
| 김은혜 | 팀장, AI | 1. 프로젝트 진행 상황 확인 <br /> 2. 사물 인식 모델 적용 <br /> 3. Flask 서버 구축 <br /> 4. 시스템 아키텍처 제작 |
| 조인철 | AI | 1. 그림 퀴즈 모델 적용 <br /> 2. 최종 발표 |
| 백지유 | FE, 서기 | 1. UI/UX 디자인 <br /> 2. 기술 스택 관련 세팅(next.js, react-query, zustand, styletron) <br /> 3. 페이지 구현 <br /> - 단어장 만들기 <br /> - 단어 상세 정보 <br /> - 그림 퀴즈 하러가기 <br /> - 단어 퀴즈 하러가기 <br /> - 단어장 외우기 <br /> - 로그인/회원가입 <br /> 4. 스크럼 회의록 작성 및 Wiki 관리 <br /> 5. 페이지 구성도 제작 |
| 남혜민 | BE | 1. DB 설계 및 관리 <br /> 2. API 설계 및 구현: 유저 및 인증 API 구현 <br /> 3.API 문서화 <br /> 4.인공지능 서버 배포 <br /> 5.중간발표 |
| 김신웅 | BE | 1. API 설계 및 구현: 단어장, 단어, 퀴즈 API 구현 <br /> 2.백엔드 서버 배포 |

[🔝 맨 위로](https://github.com/woongks/Phoca-third-project)
