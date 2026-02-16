# DCA Guide — dcaguide.io

A minimal Hugo blog for Bitcoin DCA education.

## Prerequisites

- [Hugo Extended](https://gohugo.io/installation/) v0.112+ (extended version not strictly required, but recommended)
- [Git](https://git-scm.com/)

## Local Development

```bash
# Clone the repo
git clone <your-repo-url>
cd dcaguide-website

# Run the dev server
hugo server -D

# Open http://localhost:1313
```

The `-D` flag includes draft posts. Remove it to preview production content only.

## Project Structure

```
dcaguide-website/
├── archetypes/          # Post templates
├── content/
│   ├── blog/            # Blog posts (markdown)
│   └── about.md         # About page
├── static/
│   └── images/          # Logo, favicon, OG images
├── themes/dcaguide/     # Custom theme
│   ├── layouts/         # HTML templates
│   ├── static/css/      # Stylesheet
│   └── theme.toml
├── hugo.toml            # Site configuration
├── netlify.toml         # Netlify deployment config
└── README.md
```

## Creating a New Blog Post

```bash
hugo new blog/my-new-post.md
```

Edit the front matter (title, description, categories, tags) and set `draft: false` when ready to publish.

## Customization

### Logo

Replace `static/images/logo.png` with your logo (recommended: 300x100px). The header will display it automatically. If no logo file exists, the site title text is shown instead.

### Favicon

Replace `static/images/favicon.ico` with your favicon.

### Affiliate Link

Edit the `affiliateURL` in `hugo.toml`:

```toml
[params]
  affiliateURL = "https://river.com/invite?r=XRANN5QE"
```

### Colors

Brand colors are defined as CSS custom properties in `themes/dcaguide/static/css/style.css`:

```css
:root {
  --orange: #F7931A;
  --navy: #1F2937;
}
```

## Deploying to Netlify

1. Push this repo to GitHub/GitLab.
2. Log in to [Netlify](https://app.netlify.com/).
3. Click **"Add new site" > "Import an existing project"**.
4. Connect your repo.
5. Netlify auto-detects Hugo via `netlify.toml`. Build settings are pre-configured:
   - **Build command:** `hugo --minify`
   - **Publish directory:** `public`
   - **Hugo version:** set via `HUGO_VERSION` env variable in `netlify.toml`
6. Click **Deploy**.

### Custom Domain

1. In Netlify site settings, go to **Domain management > Add custom domain**.
2. Enter `dcaguide.io`.
3. Update your DNS to point to Netlify (they'll provide the records).
4. Enable HTTPS (automatic via Let's Encrypt).

### Netlify Forms

The email signup form uses Netlify Forms (the `data-netlify="true"` attribute). It works automatically on Netlify — no backend needed. View submissions in the Netlify dashboard under **Forms**.

## RSS Feed

Available at `/index.xml` (site-wide) and `/blog/index.xml` (blog only).

## License

MIT
