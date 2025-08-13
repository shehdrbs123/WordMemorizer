
# GitHub Pages 단어장 (정적 버전)

이 저장소는 `index.html` 하나로 구동됩니다. 데이터는 `/data` 폴더의 JSON들로부터 동적으로 로드됩니다.

## 폴더 구조
- `index.html` : UI와 로더가 포함된 단일 페이지
- `data/index.json` : 로드할 데이터 JSON 파일들의 목록 (배열)
- `data/*.json` : 단어 데이터 파일들 (배열)

## 데이터 스키마 예시
```json
[
  {
    "word": "brook",
    "pos": "n.",
    "meaning": "시내, 개울",
    "example_en": "A gentle brook ran through the forest.",
    "example_gloss": "잔잔한 개울이 숲을 가로질러 흘렀다.",
    "image_url": "https://.../image.jpg",
    "source_link": "https://...",
    "level": "A2"
  }
]
```

## 사용법
1. `/data/words-*.json` 파일을 원하는 만큼 추가합니다.
2. `/data/index.json` 배열에 해당 파일명을 추가합니다.
3. GitHub Pages에서 브랜치/폴더를 지정해 배포하면 됩니다.
   - 캐시 문제를 막기 위해 `fetch`는 자동으로 `?t=<timestamp>`를 붙여 불러옵니다.
4. 학습 체크박스 상태는 `localStorage`에 저장되며 페이지 재로딩 후에도 유지됩니다.
5. 이미지가 깨질 경우 자동으로 감지되어 이미지가 숨겨지고, 해당 URL은 `localStorage`에 기록되어 다음 로딩 때 제외됩니다.
