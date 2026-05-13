# JJ Design System

디자인 토큰(색상, 타이포그래피)을 CSS 커스텀 프로퍼티로 제공하는 스타일 기반 리포지토리입니다.

---

## 파일 구조

```
jj_repository/
├── assets/
│   └── logo.png          # 브랜드 로고
├── light-color-scale.css # 라이트 모드 색상 스케일
├── typography.css        # 타이포그래피 토큰
└── Test.html             # 스타일 미리보기 테스트 페이지
```

---

## 색상 (`light-color-scale.css`)

라이트 모드 전용 CSS 커스텀 프로퍼티를 제공합니다.

### Neutral Gray

| 토큰 | 값 |
|---|---|
| `--color-gray-0` | `#f5f5f6` |
| `--color-gray-50` ~ `--color-gray-900` | 50 단계 스케일 |

### Blue Accent

| 토큰 | 값 |
|---|---|
| `--color-blue-50` ~ `--color-blue-900` | 50 단계 스케일 |

### Semantic Aliases

| 토큰 | 용도 |
|---|---|
| `--color-bg` | 기본 배경 |
| `--color-bg-muted` | 보조 배경 |
| `--color-border` | 테두리 |
| `--color-text` | 본문 텍스트 |
| `--color-text-muted` | 보조 텍스트 |
| `--color-accent` | 강조 색상 |
| `--color-accent-muted` | 연한 강조 |

### 사용 예시

```css
@import url('./light-color-scale.css');

.card {
  background: var(--color-bg);
  border: 1px solid var(--color-border);
  color: var(--color-text);
}
```

---

## 타이포그래피 (`typography.css`)

[Pretendard](https://cdn.jsdelivr.net/gh/orioncactus/pretendard@v1.3.9/dist/web/static/pretendard.min.css) 기반의 타이포그래피 토큰입니다.

> **주의:** `typography.css`를 불러오기 전에 Pretendard 폰트를 먼저 로드해야 합니다.

### 타입 스케일 (16px 기준)

| 토큰 | 크기 |
|---|---|
| `--type-display-2` | 40px |
| `--type-display-1` | 32px |
| `--type-heading-1` | 24px |
| `--type-heading-2` | 20px |
| `--type-heading-3` | 18px |
| `--type-body-lg` | 17px |
| `--type-body` | 16px |
| `--type-body-sm` | 14px |
| `--type-caption` | 12px |
| `--type-overline` | 11px |
| `--type-micro` | 10px |

### 유동형 스케일 (Fluid)

뷰포트 너비에 따라 자동으로 조절됩니다.

| 토큰 | 범위 |
|---|---|
| `--type-fluid-display-2` | 28px ~ 40px |
| `--type-fluid-heading-1` | 20px ~ 24px |

### 기타 토큰

- **줄 간격 (`--leading-*`)**: `none`, `display`, `heading`, `snug`, `tight`, `body`, `body-relaxed`
- **자간 (`--tracking-*`)**: `tighter`, `tight`, `normal`, `wide`, `wider`
- **굵기 (`--weight-*`)**: `light(300)`, `regular(400)`, `medium(500)`, `semibold(600)`, `bold(700)`, `extrabold(800)`
- **산문 너비 (`--measure-*`)**: `tight(45ch)`, `prose(65ch)`, `wide(75ch)`

### 사용 예시

```css
@import url('./typography.css');

h1 {
  font-family: var(--font-family);
  font-size: var(--type-heading-1);
  font-weight: var(--weight-bold);
  line-height: var(--leading-heading);
  letter-spacing: var(--tracking-tight);
}
```

---

## 시작하기

```html
<!-- Pretendard 폰트 -->
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/orioncactus/pretendard@v1.3.9/dist/web/static/pretendard.min.css" />

<!-- 디자인 토큰 -->
<link rel="stylesheet" href="light-color-scale.css" />
<link rel="stylesheet" href="typography.css" />
```
