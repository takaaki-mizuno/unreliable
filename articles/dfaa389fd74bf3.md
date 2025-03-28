---
title: "ソフトウエア技術書翻訳とAI"
emoji: "📗"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: ["AI", "翻訳"]
published: false
---

:::message
この記事では、ソフトウエアに関する技術書の翻訳と、それにどうAIを活用するかについて、自分の経験をもとに解説します。
:::

## はじめに

私は、翻訳や語学の専門家ではありませんが、ソフトウエアの技術書の翻訳を仕事の一部としており、これまで10冊の翻訳をしています。本記事では、これまでの翻訳の経験をもとに、ソフトウエア技術書の翻訳と、それにどうAIを活用するかについて解説します。

これまで私が翻訳した書籍は以下のとおりです。

- [JavaScript: The Good Parts ( 2008 )](https://www.amazon.co.jp/dp/4873113911/)
- [ウェブアプリケーションのためのユニバーサルデザイン( 2009 )](https://www.amazon.co.jp/dp/4873114322/)
- [入門 自然言語処理 ( 2010 )](https://www.amazon.co.jp/dp/4873114705/)
- [ハイパフォーマンスJavaScript ( 2011 )](https://www.amazon.co.jp/dp/487311490X/)
- [入門 機械学習 ( 2012 )](https://www.amazon.co.jp/dp/4873115949/)
- [オブジェクト指向JavaScript ( 2012 )](https://www.amazon.co.jp/dp/4048706705/)
- [サードパーティJavaScript ( 2014 )](https://www.amazon.co.jp/dp/4798072796/)
- [プログラマー脳 ( 2023 )](https://www.amazon.co.jp/dp/4798068535/)
- [ストレンジコード ( 2024 )](https://www.amazon.co.jp/dp/4798069744/)
- [システム設計面接の傾向と対策 ( 2025 )](https://www.amazon.co.jp/dp/4798072796/)

## 翻訳を始めたきっかけ

自分が初めて翻訳した書籍は、オライリーの [JavaScript: The Good Parts ( 2008 )](https://www.amazon.co.jp/dp/4873113911/) です。この本は、JSONの「発見者」であることで知られるダグラス・クロフォード氏が書いた名著であり、「The Good Parts」のシリーズを生み出した書籍でもあります。ちなみに自分も「[Web API: The Good Parts (2014)](https://www.amazon.co.jp/dp/4873116864/)という本を書いています。なお、この本はよく翻訳と勘違いされますが、自分が書き下ろした本で、英語版はありません（中国語には翻訳されました）。

[JavaScript: The Good Parts](https://www.amazon.co.jp/dp/4873113911/) を翻訳することになったきっかけは、2008年5月に東工大（当時）の大岡山キャンパスで行われた[YAPC::Asia 2008](http://conferences.yapcasia.org/ya2008/)での出来事でした。ちょうど休憩時間に、知り合いだった当時オライリージャパンにいらっしゃった編集者の方と雑談をしていたのですが、その時に「水野さんは翻訳とか興味ないんですか」と聞かれたのです。「興味あります」と答えたところ「じゃあ、翻訳したい本あったら教えてください」と言われました。

あれ、「この本を翻訳してもらえませんか」みたいな流れじゃないんだなと、その時思った覚えがありますが、翻訳にはとても興味があったので、その日の晩に早速オライリーメディアのウェブサイトを開いて、何かいい本はないものかと探し始めました。そこで見つけたのがJavaScript: The Good Parts でした。ただし当時は、大変失礼なことに、この本が名著なことも、書いたのが超有名人であることも、全然知りませんでした。ただ、200ページくらいの薄めの本で、翻訳しやすそうだし、JavaScriptの本なら知識もあるし大丈夫だろう、くらいの気持ちで「この本やってみたいです」と編集の方にメールを打ちました。

すると「この本はまだ翻訳権が空いているので、この本にしましょう」というお返事をもらうことができて、翻訳をスタートすることができたのです。

当たり前ですが、書籍の翻訳では、「この本翻訳させてください」という契約が一旦まとまると、他の人は翻訳できなくなります。どんなに翻訳したくても、先に抑えられたら翻訳できないので、こんな良い本がたまたま空いていたのは、今思えば非常にラッキーなことです。

そして、原著のPDFを受け取り、翻訳作業が始まり、年内に出版することができました。結局、翻訳には4ヶ月くらいかかった気がします。当時中国の検索エンジンサービス会社である百度に勤めていて、中国出張が月1回くらいで入っていたので、空港や飛行機の中で翻訳をやったのをよく覚えています。

幸いにも「JavaScript: The Good Parts」は好評で、よく売れました。当時、技術者界隈で非常に頻繁に発言をしていた[小飼弾さん](https://www.dan.co.jp/%7Edankogai/)が、ブログでたびたび紹介してくれ（JavaScriptのネタのたびにリンクを貼ってくれた）、その度に重版がかかったので、Dan Kogai特需と呼んでいました。弾さん本当にありがとうございます。

そのおかげもあって、その後もオライリーを中心に、何冊も技術書の翻訳の機会をもらえまして、2014年くらいまで、結構な頻度で訳書を出すことができました。

その後、しばらく間が空いてしまいましたが、以前から知り合いの編集者の西田さんという方が、秀和システムに転職されて、翻訳書をやることになって声をかけてもらえたのをきっかけに、毎年1冊くらいのペースで翻訳を行なっています。なお、西田さんは2024年の[ITエンジニア本大賞](https://www.shoeisha.co.jp/campaign/award/2024/result)に彼自身が編集した（秀和システムが、ではない）書籍が3冊も入るという化け物みたいな人であり、声をかけてもらえて本当にありがたい話です。

## 書籍の翻訳と機械翻訳サービス

自分が翻訳を始めた2008年には、もちろん今のような生成AIのサービスがありませんでしたが、機械翻訳サービスはありました。当時は、2022年にサービスを終了してしまったExcite 翻訳が有名でして、JavaScript: The Good Partsでも、大変お世話になりました。

翻訳の作業は、まずは受け取ったPDFを、テキストデータに変換するところから始まります。今は、PDFを扱うライブラリも多く、自分も仕事でPDFからのデータ抽出を数多くやったため、ある程度自動化できますし、生成AIにファイルを投げてテキスト化することもできますが、当時はあまりいい方法が思いつかず、手作業でコピー&ペーストを繰り返した覚えがあります。

そして翻訳は、段落ごとに英語の原文の下に翻訳した日本語を書いていき、わからないところなどは適宜Excite 翻訳に投げる、ということをしていきました。

当時の機械翻訳の品質はまだまだで、意味はわからないでもないものの、そのまま訳文として利用するには程遠い、と言ったものだったので、文意をある程度把握することにしか使えず、

Google翻訳も当時からありましたが、日英の翻訳はまだ登場当時はかなり下手くそでした。

その後、Google翻訳の精度は徐々に上がっていきましたが、Google翻訳で翻訳した文章をそのまま使う、というのはまだ難しく、相当な書き換えが必要だったと記憶しています。

その当時、これらの機械翻訳のツールを使う問題点はいくつもありましたが、翻訳そのものの品質以外に、たとえば以下のようなものがありました。

- 段落単位での翻訳のため、翻訳に文脈が考慮されない
- 専門用語の翻訳がうまくいかない

これはもちろん、人間が翻訳した場合にも起こりうる問題ですし、[翻訳メモリ](https://ja.wikipedia.org/wiki/%E7%BF%BB%E8%A8%B3%E3%83%A1%E3%83%A2%E3%83%AA)を使うなど、ある程度解決する方法があるのですが、特に翻訳について体系的に学んだわけでもなく、翻訳についてはズブの素人であった私は、そういう知識もなく、試行錯誤と力技で翻訳を行なっていました。

専門用語の翻訳がうまくいかない点については、あらかじめそう言った語を英語の原文中で日本語に翻訳しておく（たとえば英語中の「feature engineering」を「特徴量エンジニアリング」に置換しておく）、といったことをしていたのを覚えています。

## 生成AIと翻訳

私は、2014年にサードパーティJavaScriptを翻訳した後、忙しかったこともあり8年くらい書籍の翻訳（執筆も）をやらない期間がありました。そして久しぶりに翻訳のお話をいただいて「プログラマー脳」の翻訳を始めたときに、これまでと大きく違ったことは、[DeepL](https://www.deepl.com/ja/translator)が存在していたことです。

DeepLは2017年に登場しており、登場した際には、その高い精度に、世の中に衝撃を与えました。ちょうどその頃、[Google翻訳](https://translate.google.co.jp/)もニューラルネットワークに移行しており、この頃に機械翻訳は大きく精度が向上したようです。

「プログラマー脳」


2023年に「ストレンジコード」を翻訳した際には、ChatGPTが登場しており、APIを利用して段落ごとに

## 翻訳した文章の管理方法

現在（「プログラマー脳」以降）の翻訳データは、Gitで管理しています。GitHubにリポジトリを作成し、Markdownで翻訳した文書を




## 技術書翻訳と必要な文化の知識と教養


どの書籍だったか忘れましたが「One script to rule them all」

