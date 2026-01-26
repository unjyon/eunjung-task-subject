# Frontend Developer 기술 과제

## 개요

본 기술 과제는 핵심 기능인 대용량 파일 처리, 스토리지 UI/UX, 안정적인 업로드 아키텍처를 이해하고 구현할 수 있는지 평가하기 위한 것입니다.

총 3개의 과제로 구성되어 있으며, 각 과제는 독립적으로 제출할 수 있지만 순서대로 풀면 흐름이 더 자연스럽습니다.

3년차 이하는 3문제중 1문제 이상 풀이하시면 됩니다.

7년차 이하는 3문제중 2문제 이상 풀이하시면 됩니다.

8년차 이상은 3문제를 모두 풀이해서 제출해주세요.

## 백엔드가 필요한 기능은 반드시 "Mocking 기술"을 활용해 구현해야 합니다

이 과제를 수행하는 동안 실제 백엔드 API 서버는 제공되지 않습니다.

따라서 필요한 모든 API 요청은 다음과 같은 방식으로 프론트엔드에서 Mocking 하여 개발해야 합니다.

### 권장 모킹 도구: MSW (Mock Service Worker)

- **Official Docs**: https://mswjs.io
- **GitHub**: https://github.com/mswjs/msw

React 기반 프로젝트에서 가장 실제 네트워크 요청에 가깝게 시뮬레이션할 수 있는 도구입니다.

요청/응답, 지연, 에러, 업로드 흐름 등 다양한 네트워크 시나리오를 구현할 수 있습니다.

### 다른 모킹 기술 사용 가능

MSW 사용을 권장하지만, MSW에 준하는 수준으로 API mocking, 요청/응답 시뮬레이션, 지연/에러 처리 등을 구현할 수 있다면 다른 방법을 사용해도 무방합니다.

**예시:**
- MirageJS
- 자체 작성한 fetch interceptor
- Axios interceptor 기반 mocking
- Browser mock server 구현 등

## AI 도구 활용 안내

과제는 AI 코딩 도구(ChatGPT, Cursor, Claude code, GitHub Copilot 등) 활용이 가능합니다.

AI 도구를 활용한 경우 각 과제의 README.md 에 어떤 도구를 활용했는지 명시해주셔야 합니다.

## 과제 안내

- 과제는 repo의 `task#-[문제]` 폴더 하단의 각 README.md를 확인해주세요. (총 3문제 입니다.)
- 과제 실행 방법은 본 문서(README.md)의 아래 양식에 맞춰서 본 문서를 업데이트 해주세요.
- 3년차 이하는 3문제중 1문제 이상 풀이하시면 됩니다.
- 7년차 이하는 3문제중 2문제 이상 풀이하시면 됩니다.
- 8년차 이상은 3문제를 모두 풀이해서 제출해주세요.

## 제출해야 할 구성 요소

### 1. 최종 결과물
- 사전에 안내된 GitHub repo (main 에 commit 하여 과제를 풀어주세요, 한번의 commit 으로 풀이하지 마시고. 문제를 해결한 과정을 commit 의 과정으로 남겨주세요.)
- 실행 화면 캡처 또는 배포된 링크 (선택사항입니다.)
- 로컬 실행 방법 안내 (본 README.md 문서 하단에 업데이트)

### 2. 과제 README 를 다음 내용이 포함되게 업데이트 해주세요.
- 문제를 어떻게 분석했는지
- 어떤 기술적 선택을 했는지 (라이브러리, 알고리즘 등)
- 최종 아키텍처 및 구조를 어떻게 결정했는지
- 개선하고 싶은 부분 (시간이 더 있었다면)
- 사용한 주요 도구 목록 (AI를 사용했다면 반드시 기록)

### 3. 설계 문서
- README 양식으로 작성할 수 없는 별도의 설계 문서가 있다면(UML 등) 자유 양식으로 추가 제출 가능합니다. (선택사항, git repo 에 포함하고 README 에 설명을 추가해주세요.)

## 로컬 실행 방법

### 사전 요구사항
- Node.js 18 이상
- npm 또는 yarn

### 전체 의존성 설치
```bash
make install
```

### 과제별 실행

#### 과제 1: 멀티 파일 업로드 큐 시스템
```bash
# 의존성 설치 (과제 1만)
cd task1-upload-queue && npm install

# 개발 서버 실행
make run1
# 또는
cd task1-upload-queue && npm run dev
```

개발 서버가 실행되면 브라우저에서 `http://localhost:5173` (또는 표시된 포트)로 접속하세요.

#### 과제 2: 대용량 파일 목록 UI
```bash
make run2
```

#### 과제 3: 청크 기반 대용량 업로드
```bash
make run3
```

### 빌드
각 과제 폴더에서:
```bash
npm run build
```

### 정리
```bash
# 모든 node_modules 삭제
make clean
```

## 과제 repo 구조

```
frontend-assignment/
├── README.md              # 전체 과제 개요 및 실행 방법
├── Makefile               # 로컬 실행 방법 제공
├── task1-upload-queue/
│   ├── src/
│   ├── package.json
│   └── README.md          # 과제 1 문제
├── task2-file-list/
│   ├── src/
│   ├── package.json
│   └── README.md
└── task3-chunk-upload/
    ├── src/
    ├── package.json
    └── README.md
```

## 프로젝트 초기 설정 가이드

### 권장 방식
각 과제를 **독립적인 React 프로젝트**로 구성하세요.

### 초기 설정 예시 (Vite 사용)
```bash
# 과제 1 설정
cd task1-upload-queue
npm create vite@latest . -- --template react-ts
npm install

# 과제 2 설정
cd ../task2-file-list
npm create vite@latest . -- --template react-ts
npm install

# 과제 3 설정
cd ../task3-chunk-upload
npm create vite@latest . -- --template react-ts
npm install
```

### Makefile 설정
루트의 Makefile을 수정하여 각 과제를 쉽게 실행할 수 있도록 설정하세요.

```makefile
install:
	cd task1-upload-queue && npm install
	cd task2-file-list && npm install
	cd task3-chunk-upload && npm install

run1:
	cd task1-upload-queue && npm run dev

run2:
	cd task2-file-list && npm run dev

run3:
	cd task3-chunk-upload && npm run dev
```

## 기술 스택

- React 17+
- TypeScript 5+
- MSW (Mock Service Worker) 권장, 다른 Mocking 도구 사용 가능
- 빌드 도구: Vite 권장 (Create React App도 가능)
- 스타일링: 자유 (Tailwind CSS, Styled-Components, Emotion 등)
- 상태 관리: 자유 (Zustand, Recoil, Redux, Jotai 등)

## 과제 목록

### 과제 1: 멀티 파일 업로드 큐 시스템
여러 파일을 순차적으로 업로드하는 큐 시스템 구현
- **난이도**: 중
- **핵심 기술**: 상태 관리, MSW, 비동기 처리
- **상세 내용**: [task1-upload-queue/README.md](task1-upload-queue/README.md)

### 과제 2: 대용량 파일 목록 UI (5,000개 이상)
가상 스크롤을 활용한 대용량 파일 목록 렌더링
- **난이도**: 중상
- **핵심 기술**: Virtual Scroll, 성능 최적화, 트리 구조
- **상세 내용**: [task2-file-list/README.md](task2-file-list/README.md)

### 과제 3: 청크 기반 대용량 업로드 (Resumable)
재개 가능한(Resumable) 청크 업로드 구현
- **난이도**: 상
- **핵심 기술**: 파일 청크 분할, 영속화, MSW, 에러 복구
- **상세 내용**: [task3-chunk-upload/README.md](task3-chunk-upload/README.md)

## 개발 가이드

### UI/UX 참고 사항
- Google Drive, Dropbox 등의 파일 업로드/관리 UI 참고 가능
- **최소한의 기능 동작이 가장 중요**하며, 디자인 완성도는 평가 비중이 낮습니다
- 사용자가 현재 상태를 명확히 이해할 수 있도록 피드백 제공

### 테스트 코드
- 단위 테스트, E2E 테스트는 **선택사항**입니다
- 작성한 경우 가산점이 있습니다
- 테스트 프레임워크: Vitest, Jest, Testing Library 등 자유

### 성능 측정
- 과제 2의 경우 성능 측정 결과를 README.md에 포함하세요
- Chrome DevTools Performance 탭 또는 React DevTools Profiler 활용
- 측정 항목: 초기 렌더링 시간, 스크롤 FPS, 메모리 사용량 등

## 마지막 체크리스트

제출 전 다음 사항을 확인하세요:

- [ ] 모든 코드가 TypeScript로 작성되었나요?
- [ ] README에 로컬 실행 방법이 명확히 기재되어 있나요?
- [ ] 각 기술적 선택에 대한 이유가 설명되어 있나요?
- [ ] Mock API가 제대로 동작하나요?
- [ ] (과제 1) 여러 파일을 대기열에 추가하고 개별 취소가 가능한가요?
- [ ] (과제 2) 5,000개 이상의 항목이 부드럽게 스크롤되나요?
- [ ] (과제 3) 브라우저 새로고침 후 업로드가 재개되나요?
- [ ] 에러 상황에 대한 처리가 되어 있나요?





------





# 프로젝트 개요 (프론트엔드 기준)

## 📋 프로젝트 소개

이 프로젝트는 **PHP 기반의 서버 사이드 렌더링(SSR) 웹 애플리케이션**입니다. 프론트엔드는 서버에서 HTML을 생성하여 클라이언트에 전달하는 전통적인 방식으로 동작하며, HTMX를 활용한 부분적 비동기 업데이트를 지원합니다.

## 🏗️ 아키텍처 개요

### 전체 구조
```
프론트엔드 요청 → PHP 서버 (Limepie 프레임워크)
                ↓
         템플릿 엔진 (.tpl 파일)
                ↓
         HTML + CSS + JavaScript
                ↓
         클라이언트 브라우저
```

### 주요 특징
- **서버 사이드 렌더링**: 모든 HTML은 서버에서 PHP 템플릿으로 생성됩니다
- **템플릿 기반**: `.tpl` 파일을 사용하여 뷰를 구성합니다
- **모듈화된 구조**: 테마별, 모듈별로 파일이 분리되어 있습니다
- **HTMX 통신**: 페이지 전체 리로드 없이 부분 업데이트를 지원합니다

## 📁 디렉토리 구조 (프론트엔드 관점)

### 핵심 디렉토리

```
app/
├── View/                    # 템플릿 파일들 (.tpl)
│   ├── Layout/             # 레이아웃 템플릿
│   ├── Module/             # 모듈별 템플릿
│   ├── Parts/              # 재사용 가능한 컴포넌트
│   │   └── Layout/
│   │       └── Front/
│   │           ├── Head.tpl    # HTML <head> 부분
│   │           └── Foot.tpl    # HTML <body> 끝 부분
│   └── Content/            # 콘텐츠 템플릿
│
document/web/               # 웹 루트 디렉토리
├── index.php               # 프론트엔드 진입점
└── assets/                 # 정적 리소스 (CSS, JS, 이미지 등)
    ├── development/        # 개발용 소스 파일
    │   ├── common/        # 공통 스크립트/스타일
    │   ├── library/       # 외부 라이브러리
    │   ├── vendor/        # 써드파티 라이브러리
    │   └── service/       # 서비스별 리소스
    ├── dist/              # 빌드된 최적화 파일
    └── theme/             # 테마별 리소스
        ├── control/       # 관리자 테마
        ├── powderroom/    # 파우더룸 테마
        └── caniid/        # 캐니드 테마
```

## 🛠️ 기술 스택

### 프론트엔드 라이브러리

| 라이브러리 | 버전 | 용도 |
|-----------|------|------|
| **jQuery** | 3.7.1 | DOM 조작 및 이벤트 처리 |
| **Bootstrap** | 5.2.0 | UI 프레임워크 (그리드, 컴포넌트) |
| **HTMX** | 2.0.4 | 비동기 통신 및 부분 DOM 업데이트 |
| **Pretendard** | 1.3.6 | 웹폰트 |

### 추가 라이브러리
- **Select2** (4.0.13): 고급 셀렉트 박스
- **Tagify** (4.27.0): 태그 입력 컴포넌트
- **Choices.js** (11.0.3): 커스텀 셀렉트/체크박스
- **Sortable** (1.15.6): 드래그 앤 드롭 정렬
- **Swiper** (11.2.8): 슬라이더/캐러셀
- **TinyMCE** (0.95): 리치 텍스트 에디터

## 📝 템플릿 문법

이 프로젝트는 커스텀 템플릿 문법을 사용합니다. 자체 개발 프레임워크의 템플릿 엔진으로 서버 사이드에서 HTML을 생성합니다.

### 변수 출력
```html
<!-- 단순 변수 출력 -->
<div>{=payload.brand.name}</div>

<!-- 이미지 URL -->
<img src="{=payload.brand.logo_url}" alt="" />

<!-- 중첩된 객체 접근 -->
<span>{=payload.user.profile.email}</span>
```

### 조건문
```html
<!-- 기본 조건문 -->
{?payload.brand.description ?? false}
    <p class="desc">{=payload.brand.description}</p>
{/}

<!-- if-else 문 -->
{?user.isLoggedIn}
    <p>환영합니다, {=user.name}님!</p>
{:?user.isGuest}
    <p>게스트 사용자입니다.</p>
{:}
    <p>로그인이 필요합니다.</p>
{/}
```

**조건문 문법 요약:**
- `{?condition}`: if 문 시작
- `{:?condition}`: elseif 문
- `{:}`: else 문
- `{/}`: 조건문 종료

### 반복문
```html
<!-- 배열 반복 -->
{@review = payload.reviews}
    <li class="review">
        <span>{=review.title}</span>
        <p>{=review.content}</p>
    </li>
{/}

<!-- 중첩 반복문 -->
{@category = payload.categories}
    <div class="category">
        <h3>{=category.name}</h3>
        {@item = category.items}
            <div class="item">{=item.name}</div>
        {/}
    </div>
{/}
```

### 디버깅
```html
<!-- 전체 페이로드 데이터 확인 -->
{print_r(payload)}

<!-- 특정 데이터 출력 -->
{=payload.deals}
```

### HTMX 속성 사용
```html
<a 
    hx-get="/brand/{=payload.brand.seq}"
    hx-target="#limepie-contents"
    hx-push-url="true"
    hx-swap="innerHTML show:window:top"
>
    브랜드 보기
</a>
```

### 템플릿 문법 요약표

| 문법 | 설명 | 예시 |
|------|------|------|
| `{=variable}` | 변수 출력 | `{=payload.title}` |
| `{?condition}` | 조건문 시작 | `{?user.isAdmin}` |
| `{:?condition}` | elseif | `{:?user.isGuest}` |
| `{:}` | else | `{:}` |
| `{/}` | 블록 종료 | `{/}` |
| `{@item = array}` | 반복문 | `{@review = payload.reviews}` |
| `{print_r(data)}` | 디버깅 출력 | `{print_r(payload)}` |

## 🎨 테마 시스템

프로젝트는 **다중 테마 시스템**을 지원합니다:

- **Control**: 관리자/대시보드 테마
- **Powderroom**: 파우더룸 서비스 테마
- **Caniid**: 캐니드 서비스 테마

각 테마는 독립적인 CSS, JavaScript 파일을 가지고 있으며, `document/web/assets/theme/` 디렉토리 하위에 위치합니다.

## 🔨 빌드 프로세스

### 에셋 빌드
프론트엔드 리소스는 **bash 스크립트**를 통해 빌드됩니다:

```bash
# 전체 빌드
./script/build.sh

# 개별 테마 빌드
./script/assets/control-minify.sh      # Control 테마
./script/assets/powderroom-minify.sh   # Powderroom 테마
```

### 빌드 과정
1. **개발 파일 수집**: `development/` 디렉토리의 소스 파일들을 수집
2. **압축(Minify)**: JavaScript/CSS 파일을 압축하여 용량 최적화
3. **버전 관리**: 빌드된 파일에 버전 번호를 부여하여 캐시 관리
4. **배포**: `dist/theme/{테마명}/` 디렉토리에 배포

## 🔄 요청 처리 플로우

프론트엔드 요청이 어떻게 처리되는지 이해하는 것이 중요합니다.

### 전체 플로우
```
1. HTTP Request
    ↓
2. document/web/index.php (단일 진입점)
    ↓
3. app/Controller/AppFrontSide/Route/Rule.php (최초 실행)
    ├── 환경 설정 주입
    ├── 인증/권한 검사
    └── URL 패턴 분석
    ↓
4. 모듈별 Rule.php 호출
    예: resource/Module/Max/Shop/Controller/AppFrontSide/Controller/ProductCosmetic/Route/Rule.php
    ↓
5. 정규식 룰 매칭
    ↓
6. 해당 Controller 실행
    예: resource/Module/Max/Shop/Controller/AppFrontSide/Controller/ProductCosmetic/Controller/IndexFromGet.php
    ├── 비즈니스 로직 처리
    ├── 템플릿 배열 정의 ($template)
    ├── 페이로드 데이터 구성 ($payload)
    └── response->template($template)->meta($meta)->payload($payload) 리턴
    ↓
7. 템플릿 엔진에서 렌더링
    ├── 예) app/View/Layout/PowderroomMenu/Layout.tpl (전체 레이아웃)
    └── 예) app/View/Module/Max/Board/PowderroomNotice/ListItem.tpl (반복 항목)
    ↓
8. Accept 헤더에 따른 응답 (HTML/JSON)
```

### 컨트롤러에서 템플릿 정의하기

컨트롤러에서 템플릿과 데이터를 정의하여 뷰를 렌더링합니다.

**예시: 상품 목록 컨트롤러**
```php
// resource/Module/Max/Shop/Controller/AppFrontSide/Controller/ProductCosmetic/Controller/IndexFromGet.php

// 템플릿 파일 경로 정의
$template = [
    'layout'    => parent::getLayoutDir() . '/Layout.tpl',  // 전체 레이아웃
    'contents'  => parent::getThemeDir() . '/ProductCosmetic/List.tpl',  // 메인 콘텐츠
    'list_item' => parent::getThemeDir() . '/ProductCosmetic/ListItem.tpl',  // 리스트 항목 (반복용)
];

// 템플릿에 전달할 데이터 구성
$payload = [
    'deals' => $productModels?->toArray(function ($data) {
        foreach ($data as &$row) {
            if ($row['id'] ?? false) {
                $row['id'] = \rawurlencode($row['id']);
            } else {
                $row['id'] = $row['seq'];
            }
        }
        return $data;
    }),
    'stickers'      => (new StickerModel())($slave1)->getsByServiceSeq(Di::getServiceModel()->getSeq()),
    'category'      => $categoryItemDataset,
    'categories'    => $categoryItemModels?->toArray(),
    'pagination'    => $pagination,
    'next_page'     => ($_REQUEST['page'] ?? 1) + 1,
];

// 응답 객체 반환
return $response->template($template)->meta($meta)->payload($payload);
```

**템플릿 파일 구조:**
- **`layout`**: 전체 페이지 레이아웃 템플릿 (헤더, 푸터 포함)
- **`contents`**: 메인 컨텐츠 템플릿
- **`list_item`**: 리스트 항목별 템플릿 (반복 렌더링용)

## 🚀 개발 워크플로우

### 1. 템플릿 파일 수정
```bash
# 예: 브랜드 아이템 템플릿 수정
app/View/Module/Max/Section/Powderroom/Brand/BrandStyle1/Item.tpl

# 레이아웃 템플릿 수정
app/View/Layout/PowderroomMenu/Layout.tpl
```

### 2. 스타일 수정
```bash
# 테마별 CSS 파일 수정
document/web/assets/theme/powderroom/styles/common.css
document/web/assets/theme/powderroom/styles/theme/design.css
```

### 3. JavaScript 수정
```bash
# 공통 스크립트
document/web/assets/development/common/js/common.js

# 테마별 스크립트
document/web/assets/theme/powderroom/js/custom.js
```

### 4. 빌드 및 배포
```bash
# 변경사항 빌드
./script/build.sh

# 또는 특정 테마만 빌드
./script/assets/powderroom-minify.sh
```

## 🗺️ 라우팅 시스템

이 프로젝트는 **정규식 기반 라우팅 시스템**을 사용합니다.

### 라우팅 구조

#### 전역 라우터
- **파일**: `app/Controller/AppFrontSide/Route/Rule.php`
- **역할**: 모든 요청의 최초 진입점
- **기능**: 
  - 환경 설정 주입
  - 공통 로직 처리 (인증, 권한 검사)
  - URL 패턴 분석 후 해당 모듈로 라우팅

#### 모듈별 라우터
- **위치**: `resource/Module/[Module]/Controller/AppFrontSide/Controller/[Feature]/Route/Rule.php`
- **예시**: `resource/Module/Max/Shop/Controller/AppFrontSide/Controller/ProductCosmetic/Route/Rule.php`
- **기능**:
  - 모듈별 세부 라우팅 규칙
  - 정규식 패턴으로 Controller 매핑
  - 비즈니스 로직과 분리된 라우팅 계층

### 라우팅 특징
- **계층적 구조**: 전역 Rule.php → 모듈별 Rule.php → Controller
- **정규식 매칭**: URL 패턴을 정규식으로 매칭하여 액션 결정
- **{next} 매핑**: 하위 폴더로 추가 매핑 가능

## 📋 인터페이스 정의서 (YAML)

이 프로젝트는 **ERD 대신 YAML 인터페이스 정의서**를 통해 데이터 구조와 폼을 정의합니다.

### 정의서 파일 위치
- **프론트엔드**: `resource/Module/[Module]/Controller/AppFrontSide/Controller/[Feature]/Spec/`
- **관리자**: `resource/Module/[Module]/Controller/AppFrontSide/Controller/Control/Controller/[Feature]/Spec/`

### YAML 인터페이스 정의 예시

**파일**: `resource/Module/Max/Shop/Controller/AppFrontSide/Controller/Control/Controller/ProductCosmetic/Spec/Create.yml`

```yaml
type: group
name: common
action:
method: post
buttons:
    - type: submit
      name: __submitted__
      value: "go"
      class: btn-submit
      text: "저장"
    - type: a
      href: ../
      class: btn-list float-end
      text: "리스트로"

properties:
    common:
        label: 기본설정
        type: group
        class: row gx-1
        properties:
            is_close:
                label: 노출여부
                type: choice
                default: 0
                items:
                    0: 노출
                    1: 비노출
                    9: 삭제
            name:
                label:
                    ko: 상품 명
                type: text
                prepend: "<span class='lang-code'>KO</span>"
                lang: append
                rules:
                    minlength: 2
                    maxlength: 191
                    required: true
                messages:
                    ko:
                        maxlength: "{0}자로 입력"
            id:
                label:
                    ko: KR상품번호
                description: 상품의 고유 코드를 입력하세요.
                type: text
                rules:
                    minlength: 2
                    maxlength: 45
                    match: '[0-9a-zA-Z_\-]{1,44}'
```

### 인터페이스 정의서 구조 요소
- **`type`**: 폼 타입 (group, text, choice 등)
- **`name`**: 필드명
- **`action/method`**: 폼 액션 및 메소드
- **`buttons`**: 폼 버튼 정의
- **`properties`**: 필드 속성 정의
- **`rules`**: 유효성 검증 규칙
- **`messages`**: 다국어 메시지

**⚠️ 중요**: 데이터 구조를 확인할 때는 ERD 대신 **각 모듈의 Spec 폴더 내 YAML 인터페이스 정의서**를 우선 참조하세요.

## 🔍 주요 파일 설명

### 진입점
- **`document/web/index.php`**: 웹 애플리케이션의 단일 진입점. 모든 HTTP 요청이 이 파일을 통해 처리됩니다.
- **`document/web/healthcheck.php`**: 헬스체크 엔드포인트

### 레이아웃 파일
- **`app/View/Parts/Layout/Front/Head.tpl`**: 모든 페이지의 `<head>` 섹션을 담당합니다.
  - 메타 태그 설정
  - 외부 라이브러리 로드 (jQuery, Bootstrap, Pretendard)
  - 공통 CSS/JS 파일 로드
- **`app/View/Parts/Layout/Front/Foot.tpl`**: 모든 페이지의 `<body>` 끝 부분을 담당합니다.
  - Bootstrap JavaScript 로드
  - Popover 초기화 스크립트

### 에셋 로더
- **`resource/Asset/Control.php`**: Control 테마의 에셋 로딩을 관리하는 PHP 클래스
- **`resource/Asset/Powderroom.php`**: Powderroom 테마의 에셋 로딩을 관리하는 PHP 클래스

### 모듈 구조
```
resource/Module/
└── Max/Shop/                    # 예시: 쇼핑몰 모듈
    └── Controller/
        └── AppFrontSide/
            └── Controller/
                ├── ProductCosmetic/        # 프론트엔드 컨트롤러
                │   ├── Route/Rule.php      # 모듈별 라우팅
                │   ├── Controller/         # 실제 비즈니스 로직
                │   │   └── IndexFromGet.php
                │   └── Spec/               # 인터페이스 정의서
                └── Control/                # 관리자 시스템
                    └── Controller/
                        └── ProductCosmetic/
                            ├── Route/Rule.php      # 관리자 라우팅
                            ├── Controller/         # 관리자 비즈니스 로직
                            │   └── CreateFromPost.php
                            └── Spec/               # 관리자 인터페이스 정의서
                                └── Create.yml      # 상품 입력 스펙
```

## 🌐 HTMX 사용 패턴

이 프로젝트는 HTMX를 활용하여 SPA와 유사한 사용자 경험을 제공합니다.

### 기본 패턴
```html
<!-- 링크 클릭 시 부분 업데이트 -->
<a 
    hx-get="/review/{=review.seq}"
    hx-target="#limepie-contents"
    hx-push-url="true"
    hx-swap="innerHTML show:window:top"
>
    리뷰 보기
</a>
```

### 주요 HTMX 속성
- **`hx-get`**: GET 요청으로 데이터 가져오기
- **`hx-target`**: 업데이트할 DOM 요소 선택자
- **`hx-push-url`**: 브라우저 히스토리에 URL 추가
- **`hx-swap`**: 콘텐츠 교체 방식 지정

## 📦 에셋 관리

### 개발 파일 위치
- **소스 파일**: `document/web/assets/development/`
- **빌드 결과물**: `document/web/assets/dist/theme/{테마명}/`

### 버전 관리
빌드된 파일은 자동으로 버전 번호가 부여되며, 이전 버전은 자동으로 정리됩니다 (최신 3개 버전만 유지).

### 캐시 무효화
템플릿에서 에셋을 로드할 때 쿼리 파라미터로 타임스탬프를 추가하여 캐시를 무효화합니다:
```html
<link rel="stylesheet" href="{=links.assets_url}/theme/caniid/styles/common.css?time={=time()}" />
```

## 💻 로컬 개발 환경 설정

### 필수 설치 항목
- **Docker & Docker Compose**
- **PHP 8.3+**
- **Composer**
- **Git**
- **postcss** (CSS 빌드용)
- **tersermin** (JavaScript 빌드용)

### 로컬 개발 설정

```bash
# 1. /etc/hosts 설정
echo "127.0.0.1 powderroom.service.east-1.test" >> /etc/hosts

# 2. SSL 인증서 생성
script/self-signed-cert.sh powderroom.service.east-1.test

# 3. 의존성 설치
composer install

# 4. 에셋 빌드
./script/build.sh
```

### 개발 서버 실행
```bash
# Docker Compose로 로컬 환경 실행
docker-compose up -d

# 또는 PHP 내장 서버 사용
php -S localhost:8000 -t document/web
```

## 🎯 프론트엔드 개발 시 주의사항

1. **템플릿 문법**: PHP 템플릿 문법(`{=}`, `{?}`, `{@}`)을 정확히 사용해야 합니다.
2. **HTMX 의존성**: 비동기 업데이트가 필요한 경우 HTMX 속성을 사용합니다.
3. **테마 분리**: 테마별로 리소스가 분리되어 있으므로, 수정 시 올바른 테마 파일을 수정해야 합니다.
4. **빌드 필수**: CSS/JS 파일을 수정한 후에는 반드시 빌드 스크립트를 실행해야 합니다.
5. **jQuery 의존성**: 많은 코드가 jQuery에 의존하므로, 순수 JavaScript로 변경 시 주의가 필요합니다.
6. **YAML 정의서 우선**: 데이터 구조 확인 시 ERD 대신 YAML 인터페이스 정의서를 참조하세요.
7. **서버 사이드 렌더링**: 모든 HTML은 서버에서 생성되므로, 클라이언트 사이드 프레임워크(React, Vue)를 사용하지 않습니다.
8. **Accept 헤더**: 응답 형태는 Accept 헤더와 Content-Type에 따라 HTML/JSON으로 결정됩니다.

## 🏛️ 아키텍처 특징

### 프로젝트 특징
- **자체 개발 프레임워크**: PHP 기반 커스텀 프레임워크 사용
- **모듈 기반 아키텍처**: 기능별 독립 모듈 구조
- **YAML 인터페이스 정의**: 폼 정의 및 데이터 구조를 YAML로 관리
- **정규식 라우팅**: rule.php 기반 유연한 URL 매핑
- **커스텀 템플릿 엔진**: 자체 문법의 서버사이드 렌더링
- **서버사이드 렌더링**: HTMX를 활용한 SPA-like 경험
- **관리자 시스템**: Control 컨트롤러 기반 백오피스
- **유연한 응답 형태**: Accept 헤더에 따라 HTML/JSON 응답 결정

### 프론트엔드 아키텍처 특징
- **렌더링 방식**: Server-Side Rendering (SSR)
- **인터랙션**: HTMX를 통한 동적 컨텐츠 로딩
- **API**: 별도 REST API 없이 서버 직접 통신
- **에셋**: S3를 통한 정적 파일 서빙 (운영 환경)

## 🔗 관련 리소스

- **프레임워크**: Limepie (PHP 프레임워크)
- **템플릿 엔진**: 커스텀 템플릿 시스템
- **에셋 빌더**: Bash 스크립트 기반 minify 시스템

## 📚 추가 학습 자료

프론트엔드 개발을 시작하려면 다음을 이해하는 것이 도움이 됩니다:
- **PHP 템플릿 시스템**: 서버 사이드 템플릿 렌더링 개념
- **HTMX 공식 문서**: https://htmx.org/ - 비동기 통신 및 부분 업데이트
- **Bootstrap 5 문서**: https://getbootstrap.com/ - UI 컴포넌트 및 그리드 시스템
- **jQuery API**: https://api.jquery.com/ - DOM 조작 및 이벤트 처리
- **YAML 문법**: YAML 인터페이스 정의서 작성 시 필요

---

**참고**: 이 프로젝트는 서버 사이드 렌더링 방식이므로, React나 Vue 같은 클라이언트 사이드 프레임워크를 사용하지 않습니다. 대신 HTMX를 활용하여 부분적 비동기 업데이트를 구현합니다.
