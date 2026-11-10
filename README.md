# polst-landing-page

폴스트(Polst) 소개 페이지. 빌드 도구 없이 HTML·CSS·약간의 JS만 쓴다.

```
index.html   페이지 전체
style.css    디자인 값은 poliflow-app/frontend/design.md 기준
script.js    스크롤하면 나타나는 효과(IntersectionObserver)만
assets/fonts/pretendard/   Pretendard 1.3.9 (OFL-1.1, LICENSE.txt 함께)
```

## 로컬에서 보기

`index.html`을 브라우저로 바로 열어도 된다. 글꼴까지 똑같이 보려면 이 폴더에서:

```bash
python3 -m http.server 4321
```

그리고 http://localhost:4321 을 연다.

## 남은 일

- **사전 신청 구글 폼 주소**: `index.html`의 `#apply` 구역 버튼 `href`를 폼 주소로 바꾸고 `target="_blank" rel="noopener"`를 붙인다(TODO 주석 있음).
- 월간 리포트 폰 화면의 숫자(128개, 6건 등)는 "예시 화면" 표시를 단 가짜 값이다.
- OG 이미지(`og:image`)는 아직 없다.

## 올리기 (아직 안 함)

정적 파일뿐이라 어디든 올라간다. 둘 중 하나를 고르면 된다.

**Cloudflare Pages**
1. Cloudflare 대시보드 → Workers & Pages → 만들기 → Pages → 이 GitHub 저장소 연결
2. 빌드 명령은 비우고, 출력 폴더는 `/`
3. 프로젝트 → 사용자 지정 도메인 → `polst.kr` 추가. 가비아에서 네임서버를 Cloudflare가 알려 주는 값으로 바꾸거나, Cloudflare가 안내하는 CNAME 레코드를 가비아 DNS에 넣는다

**GitHub Pages**
1. 저장소 Settings → Pages → Source: `main` 브랜치, `/ (root)`
2. Custom domain에 `polst.kr` 입력 (저장소에 `CNAME` 파일이 생긴다), Enforce HTTPS 켜기
3. 가비아 DNS 관리에서 `@` A 레코드 4개(185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153)와 `www` CNAME → `yurimirimiq.github.io` 를 넣는다
