---
theme: seriph
---

# $\LaTeX$とお友だちになって<br>WYSIWYMな大学生活を送ろう！

宇津 駿介

---
layout: image
image: ./assets/repository.png
backgroundSize: contain
---

---
layout: image
image: ./assets/uzu.jpg
---

# 自己紹介

## 宇津 駿介（うづ しゅんすけ）

* 文学部心理学分野
* 福岡県出身
* 歩くの大好き
* 仲良くしてね

---
layout: image-right
image: ./assets/LaTeX-chan.png
---

# この30分で$\LaTeX$ちゃん<br>と仲良くなってください！

* 本を読むのが大好きな文学少女だけど，<br>一番の得意科目は数学
* しっかり者で，先生たちからも信頼されている
* 最近，Typstちゃんに押され気味で困っちゃう...

---

# WYSIWYGとWYSIWYM

**WYSIWYG**（ウィズィウィグ）：What You See Is What You Get

> 画面で見たままの結果を得る → Word, PowerPoint, Illustratorなど

**WYSIWYM**（ウィズィウィム）：What You See Is What You Mean

> 意味・構造を指示して編集する → $\LaTeX$, Markdown, Typst など

---

# $\LaTeX$とは

* 文書を「見た目」ではなく「**構造**」で書く組版システム
  * 内容とデザインが切り分けられている（**すごく重要**）
* Donald Knuthの$\TeX$をベースに，Leslie Lamportが使いやすくしたもの
* **数式**の美しさはトップクラス。理工系・学術論文の標準フォーマット
* テキストファイルなので，Gitと相性がよい
  * Wordファイルなどのバイナリファイルは差分を読めない
  * バイナリヤバいなり
* Windows・Mac・Linuxで同じ出力が得られる
* 読み方：**「ラテフ」** または **「ラテック」**
  * 「ラテックス」とは読まないことになっているが...
* 数学の教科書や入試問題は，$\LaTeX$で作られています
  * 実はみんなお世話になっている

---

# $\LaTeX$を使うには

|  | ローカル | クラウド |
|--|--|--|
| オフライン | ✅ | ❌ |
| 環境構築 | 必要 | 不要 |
| どの端末からでも | ❌ | ✅ |
| おすすめ | ガチ勢向け | 今日はこちら！ |

今日は **Overleaf** を使います 👉 https://ja.overleaf.com/

---

# Overleafにログインしよう

1. [Overleaf](https://ja.overleaf.com/) にアクセス
1. [Sign up](https://ja.overleaf.com/register) からサインアップ
1. [テンプレート](https://ja.overleaf.com/latex/templates/ri-ben-yu-japanese-jlreq/jjkkyvjjvvgk)を開く

---

# $\LaTeX$ソースファイルの構造

> ソースコードを見てください

$\LaTeX$のソースファイルは2つの要素からなります：

* **地の文**：そのまま出力される文章
* **コントロールシーケンス**：$\LaTeX$への命令

コントロールシーケンスには3種類あります：

1. コマンド
2. 環境
3. 特殊文字

---

# コマンド

`\` から始まる一続きの文字列です。

```latex
\コマンド名[オプション]{引数}
```

例：

```latex
\textbf{ここを太字にする}   % 引数あり
\newpage                    % 引数なし
```

---

# 環境

`\begin` と `\end` で囲まれた範囲に効果が及びます。

```latex
\begin{環境名}
  ここは環境の中です
\end{環境名}
```

---

# 特殊文字

以下の文字はそのまま入力しても出力されません：

```
#  $  %  &  _  {  }  <  >  \  ^  |  ~
```

使いたいときは，専用のコマンド（`\verb||`）が必要です。

---

# 【WS】Overleafの日本語設定

1. サンプルコードをすべて削除
1. 設定 → **Compiler を「LaTeX」に変更**
1. New file → **「latexmkrc」** という名前でファイルを作成
    * 拡張子は不要です
1. 以下を貼り付けて保存（Ctrl + S）

```perl
$latex = 'platex';
$bibtex = 'pbibtex';
$dvipdf = 'dvipdfmx %O -o %D %S';
$makeindex = 'mendex -U %O -o %D %S';
$pdf_mode = 3;
```

---

# 【WS】自己紹介を書いてみよう

```latex
\documentclass[]{jlreq}
\usepackage{amsmath}

\title{わくわくする\LaTeX}
\author{宇津~駿介\thanks{岡山大学\ 文学部}}

\begin{document}
\maketitle

\section{自己紹介}
\subsection{基本情報}
よろしくおねがいします！
\begin{description}
  \item[名前] 宇津~駿介
  \item[出身地] 福岡県
  \item[学部] 文学部\ 心理学分野
\end{description}

%（中略）

\end{document}
```

---

# 【問題】数式を書いてみよう

二次方程式の解の公式を自力で組んでみましょう。

* 生成AIは使わないでね！
* 周りの人と相談・ネット検索はOK

$$
x = \frac{-b\pm\sqrt{b^{2} - 4ac}}{2a}
$$

---

# まとめ

* $\LaTeX$は「**構造**」で書くツール = WYSIWYM
* 最初は難しく見えるし，~~エラーでブチ切れそうになることもあるが~~，**慣れれば快適**
  * エラーに阻まれて提出締め切りまで5分足りず，単位を落とすこともあるから注意しようね^ ^
* $\LaTeX$ほどカッチリした文書を作るわけじゃないよ，という場合
  * **MD（マークダウン）**おすすめだよ〜

ご清聴ありがとうございました！

WYSIWYMでMeaningfulな毎日を！
