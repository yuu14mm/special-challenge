# special-challenge
# 概要
第５回講座の特別課題です。  
HTMLに関する用語を調べてまとめています。  
## URLとはなにか
"URL"とは「Uniform Resource Locator」の略称で、インターネット上に存在する文書や画像などの場所を指し示す技術方式。
`http://ドメイン名/ディレクトリパス名/ファイル名`や`https://ドメイン名/ディレクトリパス名/ファイル名`
という形式で構成されるホームページページのアドレス。
## クエリ文字とは何か  
・パスパラメーター（パス変数）とは？  
パス（URL)の一部をパラメーター化して関す内部で利用することを可能にする仕組みのこと。
パスパラメーターは@app.get("/items/{item_id}"の{}で囲まれた部分がパラメーターになり、デコレーター直下の関数にパラメーターとして利用することが可能。  
・クエリ文字との違い  
サーバ情報を送るために、URLの末尾に付け足す文字列のこと。  
例）```https://〇〇○.jp/?×=△△```  
データの受け渡しやWebサービスの解析で主に使われている。  
クエリ文字列の内容によってページの表示内容が変わったり、ユーザーがどこから自分のサイトに辿り着いたかの情報が書かれている。
## HTTPメソッドとは何か  
クライアントがサーバーのリソースに対して実行してほしことを依頼する手段。  
| 用語 | 意味 |
|:---:|:---|
|GET|私事の実行者の手元に使えるようにデータを取ってきて、欲しい情報の詳細を記述する。|
|POST|新規作成時によく使用する。新規作成したデータの情報を追加で送信できる。|
|PUT|すでに存在しているデータを上書きして更新。更新の対象や更新内容の情報を追加で送信可能。|
|PATCH|PUTと同じ更新のリクエスト。一部更新する際に使用する。|
|DELETE|すでに存在しているデータを削除。|
## HTTPステータスコードの意味  
ウェブサイトにアクセスしたときに正常な画面ではない場合に表示される３桁の数字のこと。  
| ステータスコード番号 | 内容 | 意味 |
|:---:|:---:|:---|
|２００|OK|リクエスト成功|
|２０１|Created|リクエストは成功し、その結果新たなリソースが作成されたことを示す。<br>POSTリクエストや、一部のPUTリクエストに送信した後のレスポンスになる。|
|４００|Bad Request|構文が無効であるためサーバーがリクエストを理解できないことを示す。|
|４０４|Not Found|サーバーがリクエストされたリソースを発見できないことを示す。|
|5００|Internal Server Error|サーバー側で処理方法がわからない事態が発生したことを示す。|
## リクエストヘッダーとは何か
HTTPリクエストの前半にある、取得するリソースまたはクライアント自体に関する詳細情報を含む領域のこと。  
#### HTTPリクエストヘッダ一覧  
| フィールド名 | 内容 |
|:---:|:---|
|Authorization|ユーザ認証用データ。サーバからのWWW-Authenticateヘッダに応える|
|From|要求送信元のメールアドレス|
|If-Modified-Since|ここに指定された日付以降に更新された情報のみを要求|
|Referer|現在のページを取得するときにユーザが使ったリンクを含むページのURL|
|User-Agent|ブラウザのタイプ、ブラウザ固有のコンテンツを返すときに有用|
|Accept|そのブラウザが欲しいMIMEのタイプ <br>※MIMEタイプ（マイムタイプ）：HPのファイルやメールについて送られるファイルの種類を表す情報|
|Accept-Charset|そのブラウザが期待する文字セット|
|Accept-Encoding|そのブラウザがデコードできるデータのエンコーディング。<br>大きなファイルのダウンロードに有効|
|Accept-Language|そのブラウザが予期している言語。<br>サーバが多国語に対応しているときなどに使う|
|Host|もとのURLにリストされているホストとポート<br>※ポート：URLのドメイン部分の後ろにつく番号|
|If-Match|指定した ETag にマッチする場合にのみ、メソッドを実行することをサーバに依頼します。<br>※ETag（エンティティタグ）：HTTPにおけるキャッシュの有効性確認の手段の1つであり、ETagを利用してクライアントから条件付きのリクエストを行うことができる|
|If-None-Match|指定した ETag にマッチしない場合にのみ、メソッドを実行することをサーバに依頼します。|
|If-Range|情報が更新されていないときはRangeで指定した範囲の情報を、そうでなければ全体を要求|
|If-Unmodified-Since|指定された日時以降更新されていなかったときに応答を返す|
|Max-Forwards|TRACEメソッドとともに使う。経由するポートの最大数指定|
|Proxy-Authorization|Proxy-Authenticateに対応して、プロキシにユーザ認証情報を通知|
|Range|データの一部を要求する|
## リクエストボディとは何か  
HTTPリクエストメッセージ本文の部分のこと。<br>クライアントがサーバに送信したいデータを含めることができる。
## レスポンスヘッダーとは何か  
サーバーがクライアントに返すHTTPレスポンスに含まれるヘッダーのこと。<br>レスポンスのステータスコードやサーバのバージョン、セキュリティ関連の情報など、様々な情報を提供している。  
例） 入っている情報例
| 情報 | 役割 |
|:---:|:---|
|Content-Type|データがHTMLか画像か、文字コードなどといった情報を教えてくれます。|
|Expires|ブラウザが取得したデータを、サーバーに問い合わずに再利用してよい期間（コンテンツの有効期限）に関する情報を教えてくれます。|
|Last-Modified / ETag|データの最終更新日時と更新チェック情報を教えてくれます。|
|Location|リクエストと違う場所からデータを取得した場合の新しい場所のURL。<br>いわゆるリダイレクト先を示す情報です。|
## レスポンスボディとは何か  
HPを見るときに使うソフト（WEBブラウザ）からHPファイルが置いてあるWebサーバに対して出される依頼に対するWebサーバからの返事
## JSONとは何か  
SONは「JavaScript Object Notification」の略で、JavaScriptで値を取り扱うためのドキュメント規格。  
元々はJavaScriptで使われる想定で作成されたデータ構造なので、JavaScriptと非常に相性が良い。  
現在はJavaScript以外にもPythonやJava、PHPなどの幅広い言語で使われている。  
JavaScriptなどのクライアント言語とPythonなどのサーバサイド言語間のデータのやり取りで使われることが多い。  
#### JSONが対応しているデータ型  
| 型 | 構成 |
|:---:|:---|
|文字列|文字列はダブルクォーテーション(“)、バックスラッシュ(\)以外の文字であればなんでも使用可能。（日本語も可能）。<br>`{“name” : “tanaka”}`|
|数値|数値はダブルクォーテーションで囲まない。ダブルクォーテーションで囲むと文字列扱いになるので注意が必要。<br>`{“id”, 1}`|
|null|nullは全て小文字で指定する。<br>`{“id” : null}`|
|bool値|bool値（true or false）の指定も可能。<br>数値と同じくダブルクォーテーションは不要。<br>`{“a” : true, “b” : false}`|
|オブジェクト|オブジェクトの中にオブジェクトを入れることも可能。「ネストする」と言う。|
|配列|配列を使う場合は [] を使う。配列内の要素はカンマで区切ることで複数入力が可能。|
