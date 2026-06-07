# 바이브코딩 아이디어 관리

Notion을 CMS로 활용하여 생각날 때 상세한 바이브 코딩 아이디어를 체계적으로 관리하는 웹 플랫폼입니다.

## ✨ 기술 스택

- **[Next.js v15](https://nextjs.org)** - React 기반 풀스택 프레임워크
- **[TypeScript](https://www.typescriptlang.org)** - 타입 안전성을 위한 언어
- **[TailwindCSS v4](https://tailwindcss.com)** - 유틸리티 기반 CSS 프레임워크
- **[shadcn/ui](https://ui.shadcn.com)** - 재사용 가능한 UI 컴포넌트
- **[Lucide React](https://lucide.dev)** - 아름다운 아이콘 라이브러리
- **[next-themes](https://github.com/pacocoursey/next-themes)** - 다크모드 지원

## 📋 주요 기능

- **아이디어 목록 관리**: Notion 데이터베이스에서 아이디어 조회 (No 순 정렬)
- **아이디어 상세 조회**: 각 아이디어의 완전한 내용 확인
- **카테고리 분류**: 프론트엔드, 백엔드, 풀스택, 모바일 등으로 분류
- **시간 추적**: 각 아이디어의 기재 시각 자동 기록
- **다크/라이트 모드**: 시스템 설정에 따른 자동 테마 전환

## 🚀 빠른 시작

### 1. 의존성 설치

```bash
npm install
# 또는
yarn install
# 또는
pnpm install
```

### 2. 환경변수 설정

```bash
cp .env.example .env.local
```

`.env.local` 파일을 편집하여 Notion API 키를 설정하세요:

```
NOTION_API_KEY=<your-notion-api-key>
NEXT_PUBLIC_NOTION_DATABASE_ID=<your-database-id>
```

**Notion 설정 방법**:
1. [Notion Developer](https://www.notion.so/my-integrations) 에서 새로운 Integration 생성
2. API 키 복사
3. 관리하고자 하는 Notion 데이터베이스에 Integration 권한 부여
4. 데이터베이스 ID 확인 (URL에서 추출)

### 3. 개발 서버 실행

```bash
npm run dev
# 또는
yarn dev
# 또는
pnpm dev
```

[http://localhost:3000](http://localhost:3000)에서 결과를 확인하세요.

## 📁 프로젝트 구조

```
├── app/
│   ├── globals.css              # 전역 스타일
│   ├── layout.tsx               # 루트 레이아웃 (테마 프로바이더)
│   ├── page.tsx                 # 홈페이지 (아이디어 목록)
│   └── ideas/
│       └── [id]/page.tsx        # 아이디어 상세 페이지
├── components/
│   ├── ui/                      # shadcn/ui 컴포넌트
│   ├── layout/                  # navbar, footer, theme-toggle
│   ├── providers/               # ThemeProvider
│   └── IdeaCard.tsx             # 아이디어 카드 컴포넌트
├── lib/
│   ├── utils.ts                 # 유틸리티 함수 (cn)
│   └── notion.ts                # Notion API 클라이언트
├── public/                      # 정적 파일
├── docs/
│   └── PRD.md                   # Product Requirements Document
└── .env.example                 # 환경변수 예시
```

## 📊 Notion 데이터베이스 구조

필수 필드:
- **No** (Number): 아이디어 고유 번호 (정렬 기준)
- **Title** (Title): 아이디어 제목
- **Description** (Rich Text): 아이디어 상세 내용
- **Category** (Select): 분류 (프론트엔드, 백엔드, 풀스택, 모바일, 기타)
- **CreatedAt** (Date): 기재 시각
- **Status** (Select): 상태 (아이디어, 진행중, 완료, 보류)

자세한 내용은 [docs/PRD.md](./docs/PRD.md) 를 참조하세요.

## 🎨 UI 컴포넌트

이 프로젝트는 shadcn/ui를 사용합니다. 새로운 컴포넌트를 추가하려면:

```bash
npx shadcn@latest add [component-name]
```

사용 가능한 컴포넌트:
- Button, Card, Input, Label
- Navigation Menu, Dropdown Menu
- Badge 등

## 🌙 다크모드

다크모드가 기본적으로 설정되어 있습니다:
- 시스템 테마 자동 감지
- 라이트/다크/시스템 모드 전환
- 테마 상태 유지

## 📝 스크립트

- `npm run dev` - 개발 서버 실행
- `npm run build` - 프로덕션 빌드
- `npm run start` - 프로덕션 서버 실행
- `npm run lint` - ESLint 실행

## 🔧 사용자 정의

### 테마 색상 변경

`app/globals.css`에서 CSS 변수를 수정하여 테마를 사용자 정의할 수 있습니다.

### 컴포넌트 추가

`components/` 디렉토리에 새로운 컴포넌트를 추가하세요. shadcn/ui 컴포넌트는 `components/ui/`에 자동으로 설치됩니다.

## 🚀 배포

### Vercel (권장)

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new)

### 기타 플랫폼

- **Netlify**: `npm run build && npm run export`
- **Docker**: Dockerfile 포함
- **정적 호스팅**: `npm run build && npm run export`

## 📚 학습 자료

- [Next.js 문서](https://nextjs.org/docs)
- [TailwindCSS 문서](https://tailwindcss.com/docs)
- [shadcn/ui 문서](https://ui.shadcn.com)
- [TypeScript 문서](https://www.typescriptlang.org/docs)

## 🤝 기여하기

1. 이 저장소를 포크합니다
2. 기능 브랜치를 생성합니다 (`git checkout -b feature/amazing-feature`)
3. 변경사항을 커밋합니다 (`git commit -m '멋진 기능 추가'`)
4. 브랜치에 푸시합니다 (`git push origin feature/amazing-feature`)
5. Pull Request를 생성합니다

## 📄 라이선스

MIT 라이선스 하에 배포됩니다. 자세한 내용은 `LICENSE` 파일을 참조하세요.
