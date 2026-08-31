# 원본 조각 파일

`index.html`은 여기 있는 조각들을 합쳐 만들어집니다. 직접 고치지 말고 이쪽을 고치세요.

| 파일 | 무엇 |
|---|---|
| `build.py` | 디자인과 자바스크립트가 들어 있고, 두 갈래를 합쳐 `index.html`을 만듭니다 |
| `일기.html` | 일기 본문. 최근 기록이 위에 옵니다 |
| `통독.html` | 통독 본문. 맨 위에 읽은 장 진행표가 있습니다 |

## 사이트 이름 바꾸기

`build.py` 맨 위의 두 줄만 고치고 다시 빌드하면 됩니다.

```python
사이트이름 = "신앙 기록"
붙임말   = "하나님 만나기 · 2026년부터"
```

## 일기 한 편 넣기

`일기.html`의 `✍` 표시 바로 아래에 이 틀을 끼워 넣습니다. 최신이 위입니다.
`id`와 `data-date`의 날짜를 그날로 바꿉니다.

```html
<section class="chapter" id="v1-20260907" data-date="2026-09-07">
  <div class="chapter-body">
    <div class="chapter-eyebrow">2026.09.07</div>
    <h2>제목</h2>
    <p>본문.</p>
  </div>
</section>
```

## 통독 한 편 넣기

`통독.html`의 `✍` 표시 바로 아래에 끼워 넣습니다. `id`는 `v2-`로 시작합니다.
읽은 장은 위 진행표의 해당 `<span>`에 `class="done"`을 붙입니다.

```html
<section class="chapter" id="v2-20260907" data-date="2026-09-07">
  <div class="chapter-body">
    <div class="chapter-eyebrow">2026.09.07 · 요한복음 1장</div>
    <h2>요한복음 1장</h2>
    <div class="verse">
      <p>붙든 구절.</p>
      <span class="ref">요한복음 1:1</span>
    </div>
    <p>읽고 남기는 말.</p>
  </div>
</section>
```

가장 힘주고 싶은 말에는 `<mark>이 말</mark>`을 쓰면 노랑 형광펜이 칠해집니다.
표지의 '최근 기록'은 빌드할 때 두 갈래에서 자동으로 모입니다.

## 고치고 올리는 순서

```bash
cd ~/Documents/sinang
python3 src/build.py
git add -A && git commit -m "무엇을 적었는지"
git push
```

## 필사 한 편 넣기

사진 파일을 `필사/` 폴더에 넣고(예: `필사/2026-09-01.jpg`),
`필사.html`의 `✍` 표시 바로 아래에 이 틀을 끼워 넣습니다.

```html
<section class="chapter" id="v3-20260901" data-date="2026-09-01">
  <div class="chapter-body">
    <div class="chapter-eyebrow">2026.09.01 · 요한복음 1:1-5</div>
    <h2>요한복음 1:1-5</h2>
    <figure class="copy">
      <img src="필사/2026-09-01.jpg" alt="요한복음 1:1-5 필사" loading="lazy">
    </figure>
    <p>남기고 싶은 한 마디가 있으면 여기에.</p>
  </div>
</section>
```
