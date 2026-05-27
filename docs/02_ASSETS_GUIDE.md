# アセット配置ガイド

`index.html` は画像をすべて相対パスで参照する。各画像は下記のファイル名・配置で用意する。
JavaScript 内の `IMG` オブジェクトがパスの一覧を保持しているため、ファイル名を変更する場合は
`index.html` の `IMG` 定義も合わせて修正すること。

## ディレクトリと役割

| ディレクトリ | 役割 |
| --- | --- |
| `assets/characters/` | キャラクター本体・ロゴ・役物メダリオン |
| `assets/text/` | 「狙え！」などの演出テキスト画像 |
| `assets/symbols/` | スロットリール用のシンボル画像 |

## characters/

| ファイル名 | 内容 | 使用箇所 |
| --- | --- | --- |
| `logo.png` | ロゴ画像 | ホーム画面 |
| `oripaman-main.png` | オリパーマン全身立ち姿（白背景） | 必殺技チャージ中 |
| `oripaman-hissatsu.png` | 黄金エネルギー必殺技ポーズ | 必殺技発動（当たり） |
| `oripaman-down.png` | 片膝ついた倒れポーズ | 必殺技失敗（ハズレ） |
| `oripaman-medal.png` | 円形メダリオン（役物） | プレイ画面の落下役物 (`#butsu`) |

## text/

| ファイル名 | 内容 | 使用箇所 |
| --- | --- | --- |
| `nerae-blue.png` | 「狙え！」青バージョン | 狙え演出（青） |
| `nerae-green.png` | 「狙え！」緑バージョン | 狙え演出（緑） |
| `nerae-red.png` | 「狙え！」赤バージョン | 狙え演出（赤） |
| `nerae-rainbow.png` | 「狙え！」虹バージョン | 狙え演出（虹） |
| `tenpai.png` | 「テンパイ！」 | 狙え演出のテンパイ煽り |
| `kakutei.png` | 「確定！」 | フリーズ確定・次回予告化け |
| `jikai-yokoku.png` | 「次回予告」 | 次回予告（当たり） |
| `oo-atari.png` | 「大当たり！」 | 次回予告（当たり締め） |
| `freeze-challenge.png` | 「3秒以内にフリーズを引け！」 | フリーズチャレンジ |

## symbols/

| ファイル名 | 内容 |
| --- | --- |
| `sym-7.png` | 赤7 |
| `sym-bar.png` | BAR |
| `sym-cherry.png` | チェリー |
| `sym-bell.png` | ベル |
| `sym-replay.png` | リプレイ |

> 注: 現状の `index.html` では狙え演出・次回予告のリールシンボルを CSS と絵文字で描画している。
> `assets/symbols/` の画像を使う場合は、該当の `symHTML` / `makeReelHTML` を `<img>` 参照に置き換える。

## 画像最適化

- PNG は透過を保持。1MB を超えるものは圧縮（`pngquant` 等）や WebP 変換を検討する。
- ロゴ・テキスト系は背景透過 PNG を推奨。
- メダリオン（`oripaman-medal.png`）は正方形・背景透過が望ましい。
