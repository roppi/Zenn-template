# Zenn-template
VS Code の Dev conatiners を使った Zenn.dev の執筆環境のテンプレートです。

Zenn 拡張 Markdown のプレビューをするための Zenn CLI の他、
日本語校正のための textlint と、そのプリセットルール、VS Code 拡張機能をセットアップします。


## 導入している textlint のルール

次の４本を導入しています。

- textlint-rule-preset-ja-technical-writing
- textlint-rule-preset-ja-spacing
- textlint-rule-prh
- @proofdict/textlint-rule-proofdict

また、各ルールのリポジトリに記載されているオプション設定を、[.textlintrc.jsonc](https://github.com/roppi/Zenn-template/blob/main/.textlintrc.jsonc) にまとめて記載しコメントを付記しています。

注意点として、拡張子を通常の `json` ではなく `jsonc` としているため、
コマンド実行の際は `textlint hoge.md -c .textlintrc.jsonc` のように、設定ファイルを指定してください。


もし設定内容やコメントに間違いがあった場合は、イシューでもプルリクでも構いませんので教えていただけるとうれしいです。


## その他の特徴

- vscode-textlint にてリアルタイム校正、自動修正する
    VS Code のプラグインにて、リアルタイム校正、保存時に校正エラーを自動修正します。

- textlint-rule-prh のルールファイルをローカルで編集可能
    コンテナ作成時（postCreateCommand）に、ワークスペースに定義ファイルをコピーします

- コンテナ起動時にプレビューサーバを自動表示
    コンテナ起動時（postStartCommand）にバックグラウンドでプレビューサーバを起動、ブラウザを表示します。

## それから

もうちょっと詳しい説明は Zenn.dev に記載していますので、
そちらも参考になさってください。

https://zenn.dev/roppi/articles/zenn-cli-textlint-in-docker