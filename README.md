# 🧮 선형대수학 시각화 학습 도구 — Matrix Space Transformer

> **행렬이 공간을 어떻게 변환하는지** 직관적으로 이해하기 위한 인터랙티브 웹 시각화 도구

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![License: MIT](https://img.shields.io/badge/License-MIT-green.svg?style=flat-square)

## 🎯 프로젝트 목적

선형대수학에서 가장 핵심적인 개념 중 하나는 **"행렬은 공간의 변환을 나타낸다"** 는 것입니다.

교과서의 수식만으로는 이 개념을 직관적으로 이해하기 어렵습니다. 이 프로젝트는 2×2 행렬이 2D 평면을 어떻게 회전, 반사, 확대/축소, 전단(shear)하는지 **눈으로 직접 볼 수 있도록** 만든 학습 도구입니다.

> 📖 3Blue1Brown의 [Essence of Linear Algebra](https://www.3blue1brown.com/topics/linear-algebra) 시리즈에서 영감을 받았습니다.

## ✨ 주요 기능

### 📐 행렬 입력 & 애니메이션 변환
- 2×2 행렬의 각 원소(a, b, c, d)를 직접 입력
- **부드러운 ease-in-out 애니메이션**으로 공간이 변형되는 과정을 시각적으로 확인
- 속도 조절 슬라이더

### ⚡ 10가지 프리셋 행렬
| 프리셋     | 행렬                      | 설명                  |
| ---------- | ------------------------- | --------------------- |
| 90° 회전   | `[0 -1; 1 0]`             | 반시계 방향 90도 회전 |
| 45° 회전   | `[0.71 -0.71; 0.71 0.71]` | 반시계 방향 45도 회전 |
| Y축 반사   | `[-1 0; 0 1]`             | Y축 기준 좌우 반전    |
| X축 반사   | `[1 0; 0 -1]`             | X축 기준 상하 반전    |
| 2배 확대   | `[2 0; 0 2]`              | 균등 확대             |
| 0.5배 축소 | `[0.5 0; 0 0.5]`          | 균등 축소             |
| X 전단     | `[1 1; 0 1]`              | X 방향 전단(shear)    |
| Y 전단     | `[1 0; 1 1]`              | Y 방향 전단(shear)    |
| X↔Y 교환   | `[0 1; 1 0]`              | 축 교환 (y=x 대칭)    |
| 영행렬     | `[0 0; 0 0]`              | 모든 벡터가 원점으로  |

### ➡️ 벡터 입력 & 변환 추적
- 원하는 벡터를 자유롭게 추가하여 행렬 변환 전후를 비교
- **점선 화살표** = 원래 벡터, **실선 화살표** = 변환된 벡터
- 각 벡터는 고유 색상으로 구분되며 좌표 라벨이 실시간 표시

### 🔷 도형 선택
- 격자(Grid) / 원(Circle) / 사각형(Square) / 집 모양(House)
- 원래 도형(점선)과 변환된 도형을 동시에 비교

### 🖱️ 캔버스 인터랙션
| 조작      | 동작                  |
| --------- | --------------------- |
| 드래그    | 좌표계 이동 (pan)     |
| 스크롤 휠 | 커서 기준 줌 인/아웃  |
| 더블클릭  | 원래 위치·줌으로 복귀 |

### 📊 실시간 정보 표시
- **기저 벡터** î (시안), ĵ (핑크)의 변환 후 좌표
- **행렬식(determinant)** — 양수(초록), 음수(핑크), 0(주황)으로 색상 구분
  - 양수 → 방향 보존
  - 음수 → 방향 반전 (반사)
  - 0 → 차원 축소 (면적 → 0)

## 🚀 바로 사용하기

### GitHub Pages (온라인)
별도 설치 없이 브라우저에서 바로 사용할 수 있습니다:

👉 **[Live Demo](https://<your-username>.github.io/linear-algebra-visualizer/)**

> ⬆️ 레포지토리 Settings → Pages → Source를 `main` 브랜치로 설정하면 위 링크가 활성화됩니다.

### 로컬 실행
```bash
git clone https://github.com/<your-username>/linear-algebra-visualizer.git
cd linear-algebra-visualizer
# index.html을 브라우저에서 열기만 하면 됩니다
start index.html     # Windows
open index.html      # macOS
xdg-open index.html  # Linux
```

## 🎓 학습 포인트

이 시각화 도구를 통해 다음 개념을 직관적으로 학습할 수 있습니다:

1. **행렬 = 공간의 선형 변환**: 행렬의 각 열은 기저 벡터가 어디로 가는지를 나타냅니다
2. **행렬식(Determinant)의 기하학적 의미**: 면적의 변화율과 방향 보존 여부
3. **선형 변환의 종류**: 회전, 반사, 확대/축소, 전단
4. **벡터의 변환**: 임의의 벡터가 행렬 곱셈에 의해 어떻게 이동하는지
5. **기저 벡터의 역할**: î, ĵ의 이동이 전체 공간의 변환을 결정함

## 🛠️ 기술 스택

- **순수 HTML/CSS/JavaScript** — 외부 라이브러리 없음
- **Canvas API** — 실시간 2D 렌더링
- 반응형 디자인 (모바일 대응)
- 다크 테마 UI

## 📄 License

MIT License — 자유롭게 사용, 수정, 배포할 수 있습니다.
