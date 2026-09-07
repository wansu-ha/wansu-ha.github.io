# wansu-ha.github.io

하완수 — 풀스택 개발자 이력서·포트폴리오.

**보러 가기 → https://wansu-ha.github.io**

---

## 내용을 고치려면

**아래 세 파일만 열면 됩니다. HTML을 건드릴 일이 없습니다.**

| 고치고 싶은 것 | 여는 파일 |
|---|---|
| 이력서 (요약·기술 스택·경력·논문·학력) | `_data/resume.yml` |
| 포트폴리오 (프로젝트·흐름도·스크린샷) | `_data/portfolio.yml` |
| 목차 첫 화면 | `index.html` 맨 위 `---` 사이 |
| 이름·이메일·GitHub 주소 | `_data/site.yml` |

예를 들어 이력서에 프로젝트를 하나 추가하려면 `_data/resume.yml` 에서
같은 모양의 묶음을 복사해 글자만 바꾸면 됩니다.

```yaml
      - title: '새 프로젝트 이름'
        desc: '한 줄 설명.'
        tech: ['TypeScript', 'React']
        points:
          - '한 일 1'
          - '한 일 2'
```

### YAML 편집 시 주의할 점

- **들여쓰기는 공백만** 씁니다(탭 금지). 위아래 항목과 칸을 맞추세요.
- 값에 작은따옴표(`'`)가 들어가면 `"큰따옴표"`로 감싸세요.
- 문장 안에서 굵게 강조할 때만 `<b>…</b>` 를 씁니다.
- 문법이 틀리면 **빌드가 실패하고 사이트는 직전 버전이 그대로 유지**됩니다.
  GitHub에서 실패 메일이 오니, 고쳐서 다시 push 하면 됩니다.

---

## 디자인을 고치려면

| 고치고 싶은 것 | 여는 파일 |
|---|---|
| 색·글꼴 (세 페이지 공통) | `assets/css/tokens.css` |
| 이력서·포트폴리오 공통 스타일 | `assets/css/base.css` |
| 페이지별 스타일 | `assets/css/{home,resume,portfolio}.css` |
| 페이지 뼈대(섹션 배치) | `index.html` · `resume.html` · `portfolio.html` |
| 공통 `<head>` (메타·OG·폰트) | `_layouts/base.html` |

---

## 구조

GitHub Pages 에 내장된 Jekyll 이 빌드합니다.
**별도 빌드 도구나 GitHub Actions 없이 push 만 하면 반영**되고,
결과물은 정적 HTML 이라 OG 카드·검색 노출도 그대로입니다.

```
_config.yml            사이트 설정
_data/                 ← 내용 (평소 여기만 편집)
_layouts/base.html     공통 <head>
_includes/             반복되는 조각 (프로젝트 카드, 흐름도, 연락처)
assets/css/            스타일
assets/*.png           스크린샷·OG 카드 이미지
index.html             목차   (틀 + 앞머리 데이터)
resume.html            이력서 (틀 — 내용은 _data/resume.yml)
portfolio.html         포트폴리오 (틀 — 내용은 _data/portfolio.yml)
```

## 로컬에서 미리 보려면 (선택)

Ruby 가 있으면:

```sh
bundle install
bundle exec jekyll serve   # http://localhost:4000
```

없어도 됩니다. push 후 실제 사이트에서 확인해도 무방합니다.
