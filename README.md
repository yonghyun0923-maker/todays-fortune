# 오늘의 운세

생년월일을 넣으면 오늘의 운세를 보여주는 정적 웹앱.
백엔드·DB 없이 HTML/CSS/JS 파일만으로 동작합니다. (PRD: `../PRD-오늘의운세.md`)

## 핵심 규칙

**같은 날 + 같은 생일 = 같은 운세.**
랜덤이 아니라 `(오늘 날짜 + 생일)`로 만든 시드로 문구를 뽑기 때문에,
같은 사람은 하루 동안 항상 같은 결과를 봅니다. → 친구끼리 비교 가능.

## 파일 구성

| 파일 | 역할 |
|------|------|
| `index.html` | 화면 구조 |
| `style.css` | 디자인 |
| `script.js` | 운세 로직 + 문구 풀(`FORTUNES`) |

운세 문구를 늘리려면 `script.js`의 `FORTUNES` 배열에 문장을 추가하면 됩니다.

## 실행 방법 (내 컴퓨터에서 보기)

가장 간단한 방법: **`index.html`을 더블클릭**해서 브라우저로 열면 됩니다.

> 참고: `file://`로 열면 "링크 복사" 버튼이 보안 때문에 복사 대신 주소를
> 화면에 보여줄 수 있습니다. 정상입니다. 배포(아래) 후엔 복사가 됩니다.

로컬 서버로 띄우고 싶다면 (선택):

```bash
# Python이 있으면
python -m http.server 8000
# 브라우저에서 http://localhost:8000 접속
```

## 배포 방법 (실제 주소로 공유 — 성공 지표!)

PRD의 성공 지표가 "실제 URL로 접속해 작동"이므로, 일찍 한 번 올려보길 권장.

### GitHub Pages (무료, 가장 쉬움)

```bash
# 이 폴더에서
git init
git add .
git commit -m "오늘의 운세 첫 버전"
gh repo create todays-fortune --public --source=. --push
```

그 다음 GitHub 저장소 → **Settings → Pages → Branch: main / root** 선택하면
몇 분 뒤 `https://<아이디>.github.io/todays-fortune/` 주소로 접속됩니다.

### Netlify (드래그앤드롭)

[app.netlify.com/drop](https://app.netlify.com/drop) 에 이 폴더를 끌어다 놓으면
바로 주소가 생깁니다. (계정 가입 필요)

## 다음에 추가하면 좋은 것 (PRD '추후')

- 운세 카테고리 분리 (총운 / 애정운 / 금전운)
- 별자리·띠 아이콘 등 시각 요소
- 결과 화면 캡처/이미지 공유
