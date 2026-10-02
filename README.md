# 画像配信用 GitHub Pages

このフォルダを、画像専用のGitHubリポジトリとしてGitHub Pagesで配信する。画像は `images/` に置き、記事のfront matterへHTTPS URLを指定する。リポジトリの `main` ブランチへpushすると、`.github/workflows/deploy.yml` がこのフォルダだけを公開する。

このフォルダの外にある記事原稿、Blogger認証情報、運用コードは画像用リポジトリへ含めない。

例:

```text
https://[GitHubユーザー名].github.io/[リポジトリ名]/images/ai-email-draft.png
```

公開前に、画像が自作・生成・利用許諾を確認済みであること、代替テキストが記事内容と一致することを確認する。

## 初回公開後

GitHub PagesのURLを確認したら、まず変更予定を確認する。

```powershell
python scripts\set_cover_images.py --base-url "https://[GitHubユーザー名].github.io/[リポジトリ名]"
```

出力が正しければ `--apply` を付ける。その後、既存のBlogger下書きを `publish.py --post-id ... --draft` で更新する。公開はしない。
