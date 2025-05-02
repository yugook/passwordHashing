# passwordHashing

本プロジェクトは、パスワードを平文で保存せず、ハッシュ化を用いた認証手法を説明するサンプルコードを収録しています。  
パスワードのハッシュ化により、万が一データベースの情報が漏洩した場合でも、元のパスワードを復元できないため安全性が向上します。  
具体的には、SHA-256を利用してパスワードからハッシュ値を生成し、そのハッシュ値を認証時に比較する仕組みを実装しています。

詳細な解説や実際の実装例については、以下のZennの記事で詳しく取り上げていますので、ぜひご覧ください。  
[パスワードのハッシュとは？](https://zenn.dev/algorithm_math/articles/f56d10e844cdba)

---

## 環境

- **OS:** macOS (例: MacBook M4)
- **コンパイラ:** Apple clang version 16.0.0  
- **ライブラリ:** OpenSSL 3.4.0 (SHA-256 を利用)
- **ビルドツール:** g++  
- **エディタ:** VSCode  
  - VSCodeでは、`.vscode/c_cpp_properties.json`により、`/opt/homebrew/opt/openssl/include`がインクルードパスとして設定されています。

---

## OpenSSL のインストール

以下のコマンドで OpenSSL をインストールしてください。

```sh
brew install openssl
```

---

## 実行方法

1. **ビルド**

   以下のコマンドで、`hash_password.cpp` をコンパイルし、実行ファイル `hash_password` を作成します。

   ```sh
   g++ -o hash_password hash_password.cpp -I/opt/homebrew/Cellar/openssl@3/3.4.0/include -L/opt/homebrew/Cellar/openssl@3/3.4.0/lib -lssl -lcrypto
   ```

2. **実行**

   生成された実行ファイルを実行し、パスワードおよび認証処理を確認できます。

   ```sh
   ./hash_password
   ```

   プロンプトに従ってパスワードを入力してください。  
   正しいパスワードを入力すると「Successful」、異なる場合は「Failed」と表示されます。

---

## プロジェクト構成

```
hash_password.cpp
LICENSE
passwordHashing.code-workspace
README.md
.vscode/
    c_cpp_properties.json
```

この構成により、VSCodeで簡単にプロジェクトを開くことができます。

