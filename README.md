# node-dev-env

Development env for Node.js and yarn.

## What is this?

もともとはWindows & WSL2の環境で `npm` コマンドがおそすぎると言った問題を回避するために作ったコンテナ環境です

## Useage

- **Reactの開発環境**を作る場合

### 前提条件

- docker, docker-composeが使用可能になっていること

### 環境構築手順

すべてローカル作業

1.イメージのビルド

コマンドを実行

`docker-compose build`

2.モジュールのインストール、サンプルプロジェクトの構築

コマンドを実行

`docker-compose run --rm node sh -c "npx create-react-app my-app --template typescript"`

3.コンテナ起動

コマンドを実行

`docker-compose up`

4.コンテナの起動及び、ブラウザアクセスを確認

ブラウザで`heep://localhost/3000`へアクセス  
Reactのページが表示されることを確認してください

※Windows環境にてlocalhostでアクセスできない場合は[こちら](https://docs.microsoft.com/ja-jp/windows/wsl/wsl-config#wsl-2-settings)を参考に.wslconfigを設定してください

### おまけ（nodeモジュールを追加する場合）

例：jestを追加する

a. コンテナ内に入って作業  
b. 以下コマンドを実行  
`docker-compose run --rm node sh -c "cd my-app && yarn add --dev jest"`
