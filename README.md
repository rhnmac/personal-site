# Personal site

Minimal Jekyll site, styled after ssi.inc. Hosted free on GitHub Pages.

## Files

- `index.md` — homepage. Edit the text here.
- `blog/index.html` — blog index. Lists posts automatically, don't touch.
- `_posts/` — blog posts live here. One Markdown file per post, named `YYYY-MM-DD-title.md`.
- `_layouts/` — page templates and styling (the CSS is inside `default.html`).
- `_config.yml` — site settings. Set `url` to your real domain.
- `CNAME` — replace `yourdomain.com` with your real domain.

## Deploy to GitHub Pages

1. Edit `CNAME` and the `url` line in `_config.yml` to your actual domain.
2. Create a new public repo on github.com (e.g. `personal-site`).
3. Push this folder to it:

       cd personal-site
       git init
       git add .
       git commit -m "Initial site"
       git branch -M main
       git remote add origin https://github.com/YOURUSERNAME/personal-site.git
       git push -u origin main

4. On GitHub: repo → Settings → Pages → under "Build and deployment",
   set Source to "Deploy from a branch", branch `main`, folder `/ (root)`. Save.
5. Still in Settings → Pages: enter your custom domain and save.
   Check "Enforce HTTPS" once it becomes available (can take up to an hour).

## DNS (at your domain registrar)

For an apex domain (rohan.com):

    A     @    185.199.108.153
    A     @    185.199.109.153
    A     @    185.199.110.153
    A     @    185.199.111.153
    CNAME www  YOURUSERNAME.github.io

For a subdomain only (blog.rohan.com):

    CNAME blog  YOURUSERNAME.github.io

DNS can take a few minutes to a few hours to propagate.

## Writing a post

Add a file like `_posts/2026-07-10-my-post.md`:

    ---
    layout: post
    title: "My post"
    ---

    Text goes here, in Markdown.

Commit and push. GitHub rebuilds the site in about a minute.
