# 自己紹介サイト テンプレート（1 ファイル版）

技育プロジェクト ミニカンファレンス 2026.08
「AI を使ってゼロから自分の Web サイトを作ってみよう！」用の配布テンプレートです。

## ファイル構成

```
index.html   ← これ 1 枚（CSS も JavaScript も中に入っています）
icon.png     ← アイコン画像（サンプル入り。差し替え自由）
```

**フォルダは作らず、2 つを同じ場所に並べています。**
GitHub にアップロードするときに「両方選んでドラッグ＆ドロップ」で済むようにするためです。

## index.html の中身は 4 ブロック

| ブロック | 役割 | 目印 |
| --- | --- | --- |
| head エリア | タイトル・SNS シェア設定（OGP） | `<title>` / `<meta>` |
| style エリア | 見た目（CSS） | `<style> … </style>` |
| body エリア | 画面に出る中身（HTML） | `<body> … </body>` |
| script エリア | 動き（JavaScript） | `<script> … </script>` |

## 使い方（受講者向け）

1. StackBlitz でこのプロジェクトを開く（またはブラウザに index.html をドラッグ＆ドロップ）
2. `【ここを変える】`（HTML）と `【変更】`（CSS / JS）で検索（Ctrl + F / Cmd + F）
3. 見つかった箇所を自分の内容に書き換える
4. 保存（Ctrl + S）してプレビューを確認

## アイコン画像（サムネイル）の差し替え

初期状態では同梱の `icon.png` が表示されます。差し替え方は 3 通り。

- **A. 同じ名前で上書きする（いちばん簡単・おすすめ）** … 自分の画像を `icon.png` という名前にして、`index.html` と同じ場所に置くだけ。HTML はさわらなくて OK
- **B. 別の名前のファイルを使う** … 例）`myphoto.jpg` を置いて、`src="icon.png"` を `src="myphoto.jpg"` に書き換える
- **C. ネット上の画像を使う** … `src="https://…"` と画像の URL を貼る

ファイル名は半角英数で。大文字小文字も区別されます（`Icon.png` ≠ `icon.png`）。
画像は 1 枚 300KB 以下が目安です。

形を変えるときは style エリアの `.avatar` の `border-radius`（`50%` で丸／`0` で四角）。

## いちばん効く 4 行

style エリアの先頭にある `:root` を変えると、サイト全体の雰囲気が一気に変わります。

```css
:root {
  --main-color: #0e9594;  /* 見出し・ボタンの色 */
  --bg-color:   #f0f7f7;  /* 背景の色 */
  --text-color: #2d3436;  /* 文字の色 */
  --card-color: #ffffff;  /* 白い箱の色 */
}
```

| テーマ | main-color | bg-color | text-color | card-color |
| --- | --- | --- | --- | --- |
| ミント（初期値） | `#0e9594` | `#f0f7f7` | `#2d3436` | `#ffffff` |
| サンセット | `#e8590c` | `#fff5f0` | `#2d3436` | `#ffffff` |
| さくら | `#e75a7c` | `#fff0f4` | `#2d3436` | `#ffffff` |
| ミッドナイト | `#8b7cf6` | `#1a1a2e` | `#f5f6fa` | `#26263f` |

## 公開する（セッション③）

1. GitHub にリポジトリを作り、`index.html` と `icon.png` を選んでまとめてアップロード
2. Settings → Pages → Branch: `main` / `(root)` → Save
3. `https://<ユーザー名>.github.io/<リポジトリ名>/` で公開完了

Vercel の場合は、リポジトリを Import して Deploy を押すだけです。

公開後、head エリアの `og:image` に「`https://公開URL/icon.png`」のような完全なアドレスを入れると、
SNS でシェアしたときにサムネイル付きのカードが表示されます。

## 公開前チェック

- 個人情報（本名・住所・学籍番号・電話番号など）を載せていないか
- 他人の画像・フォント・音楽を無断で使っていないか
- 一度公開したものは消えないつもりで — 全世界に見せて大丈夫か

## 運営メモ

- StackBlitz は「New Project → Static（HTML/CSS/JS）」で作成し、この `index.html` を配置してテンプレート URL を発行してください
- 資料内のテンプレート URL（`geek-miniconf2026-profile`）は仮です。本番前に差し替えをお願いします
