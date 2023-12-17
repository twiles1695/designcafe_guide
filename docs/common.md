# リセットCSSとサイトの骨組み

## リセットCSSの調整

- 文字カラーの適用
- メトリクスの適用
```css
font-feature-settings: "palt";
```

## サイト全体の骨組みをつくる

### 1.骨組みのタグを作成

以下、bodyタグの中身です。このような空のタグを作っておきましょう。
```html
<header id="header">
  〜
</header>
<main>
  <div id="lead" class="lead">
    〜
  </div>
  <section id="about" class="about">
    〜
  </section>
  <section id="menu" class="menu">
    〜
  </section>
  <section id="gallery" class="gallery">
    〜
  </section>
  <section id="event" class="event">
    〜
  </section>
  <section id="access" class="access">
    〜
  </section>
</main>
<footer>
  〜
</footer>
```

!!! note
    HTMLにはheader, main, footerタグが存在します。<br>
    詳細はこちらを参照ください。<br>
    https://mikit-tz.com/html-tag-header-main-footer-howto/

!!! note
    各セクションは基本的に`section`タグで囲います。<br>
    `section`タグ内には、見出しタグを最低ひとつ含む必要があります。<br>
    見出しタグがセクション内に存在しない場合は`section`タグではなく`div`タグを使用します（リード文セクションが相当します）。

!!! note
    sectionタグに同じ名前の`id`と`class`を指定するのは、それぞれ別の役割があるためです。<br>
    `id`は、ページ内リンク（アンカーリンク）を使用するために付与し、`class`はCSSを当てるために付与します。

### 2.コンテンツ幅を作成

「ABOUT US」「MENU」「EVENT」「フッター」にはコンテンツ幅が必要です。
各セクションに共通で指定する以下のようなクラスをつくり、適用しましょう。
※クラス名は例です。
```css
.section {
  max-width: 1000px;
  margin: 0 auto;
}
```

必要な箇所に`.section`クラスを付与します。
```html
<header id="header">
  〜
</header>
<main>
  <div id="lead" class="lead">
    〜
  </div>
  <section id="about" class="about section">
    〜
  </section>
  <section id="menu" class="menu section">
    〜
  </section>
  <section id="gallery" class="gallery">
    〜
  </section>
  <section id="event" class="event section">
    〜
  </section>
  <section id="access" class="access">
    〜
  </section>
</main>
<footer class="section">
  〜
</footer>
```

### 3.見出し
各セクション共通のクラスをつくり、以下を指定

- 中央揃え
- 上下のマージン

コンテンツ幅のクラスを作成したのと同じ要領でやってみましょう。