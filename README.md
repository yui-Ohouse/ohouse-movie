# 🎬 내 방이 영화가 된다면?

> 방 사진 한 장이면 충분합니다.
> AI가 당신의 방을 영화로 만들어 드립니다.

집에서 뒹굴뒹굴하다 문득 이런 생각 해본 적 없나요?

*"내 방이 영화 배경이면... 제목이 뭘까?"*

그 쓸데없지만 소중한 궁금증, 저희가 해결해 드립니다. 🍿

<br>

## 📋 이런 걸 만들어 줍니다

방 사진을 올리면 AI가 분석해서 **영화 티켓**을 발권해 줘요.

| 항목 | 설명 |
|------|------|
| 🎞️ 영화 제목 | 방 분위기에 어울리는 여운 있는 제목 |
| 🏷️ 장르 | 로맨스 / 미스터리 / 힐링 등 |
| 🎭 VIBE | 방에서 느껴지는 키워드 3가지 |
| 🧑 CAST | 이 방에 사는 주인공의 성격과 묘사 |
| 🎥 KEY SCENES | 이 영화의 명장면 3개 |
| 🛋️ 추천 아이템 | 영화 분위기를 완성할 Ohouse 아이템 |

> 티켓 이미지 저장도 됩니다. 친구한테 자랑하세요.

<br>

## 🧐 어떻게 돌아가는 건가요?

```
┌─────────────────────────────────────────┐
│                                         │
│  📸 방 사진 업로드                        │
│       ↓                                 │
│  🤖 AI가 사진 분석 (Groq API)             │
│       ↓                                 │
│  🎬 영화 티켓 생성                        │
│       ↓                                 │
│  💾 이미지로 저장 (선택)                   │
│                                         │
└─────────────────────────────────────────┘
```

- **프론트엔드**: 순수 HTML/CSS/JS 단일 파일 (프레임워크 없음, 가볍습니다)
- **AI**: Groq API + Llama 4 Scout (비전 모델, 이미지 분석 가능)
- **서버리스**: Vercel Serverless Functions (API 키 보호용)
- **이미지 캡처**: dom-to-image-more → SVG → Canvas 3x 렌더링

<br>

## 🚀 직접 띄워보고 싶다면

### 1. 클론

```bash
git clone https://github.com/yui-Ohouse/ohouse-movie.git
cd ohouse-movie
```

### 2. Groq API 키 발급

[Groq Console](https://console.groq.com)에서 무료로 발급받을 수 있어요.

### 3. Vercel로 배포

```bash
npm i -g vercel
vercel link
vercel env add GROQ_API_KEY    # 발급받은 키 입력
vercel --prod
```

> 로컬에서 테스트하려면 `vercel dev`로 실행하면 됩니다.

<br>

## 🗂️ 프로젝트 구조

```
ohouse-movie/
├── index.html          # 전부 다 여기에 있습니다 (HTML + CSS + JS)
├── api/
│   └── analyze.js      # Vercel 서버리스 함수 (Groq API 프록시)
└── .gitignore
```

네, 파일 3개입니다. 가끔은 심플한 게 최고예요.

<br>

## 🌏 다국어 버전

| 버전 | 레포 | 사이트 |
|------|------|--------|
| 🇰🇷 한국어 | [ohouse-movie](https://github.com/yui-Ohouse/ohouse-movie) | [ohouse-movie.vercel.app](https://ohouse-movie.vercel.app) |
| 🇯🇵 일본어 | [ohouse-movie-jp](https://github.com/yui-Ohouse/ohouse-movie-jp) | [ohouse-movie-jp.vercel.app](https://ohouse-movie-jp.vercel.app) |

<br>

---

*만든 사람: Ohouse QA Team*
*"테스트만 하기엔 아까운 실력이라..."* 🎬
