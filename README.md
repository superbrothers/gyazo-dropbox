# gyazo-dropbox
yet another Gyazo Server with Dropbox

## サーバの設定
### Gyazo App作成、App Key, App Secret取得
https://www.dropbox.com/developers/apps

 「Create an App」からアプリを作成して、App key, App Secretを取得してください。
 
### Access Token, Access Secret取得
Access Token, Access Secretの取得には、Dropboxが用意しているサンプルコードを利用します。

https://www.dropbox.com/developers/reference/sdk
 
dropbox-ruby-sdkに含まれる`cli_example.rb`をエディタで展開して、取得したApp Key, App Secretを記述してから実行します。

出力される内容に沿ってAccess TokenとAccess Secretを取得してください。 

### 実行環境を用意
ソースコードをcloneします。

    $ git clone https://github.com/superbrothers/gyazo-dropbox

取得したApp Key, App Secret, Access Token, Access Secretは環境変数に設定します。herokuで動かす場合は以下のようにして設定してください。

    $ heroku config:add app_key=APP_KEY app_secret=APP_SECRET access_token=ACCESS_TOKEN access_secret=ACCESS_SECRET 

## クライアントの設定
Gyazo.app/Contents/Resources/script を編集してポスト先を変更します。

41行目、42行目のHOSTとCGIの定数を変更します。HOSTをサーバを置くホスト名、CGIを「/」に変更してください。

    HOST = 'サーバを置くホスト名'
    CGI = '/'

スクリーンショットは、Dropboxの /App/{App Name}/ に保存されます。

## Copyright
Copyright (c) 2011 Kazuki Suda. See LICENSE.txt for further details.

The Original Code is `upload.cgi` Copyright (c) 2009 Toshiyuki Masui.
