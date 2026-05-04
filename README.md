# seligofit.com

Marketing site for [seligo.fit](https://seligofit.com), built with Jekyll and deployed via GitHub Pages.

## Running locally

### Prerequisites

You need a modern Ruby (3.0+). The macOS system Ruby (`/usr/bin/ruby`, version 2.6) is too old and will fail with errors like `Could not find 'bundler' (4.0.10)`. Install via Homebrew:

```sh
brew install ruby
```

Homebrew Ruby is keg-only, so it won't be on your `PATH` by default. Add it permanently:

```sh
echo 'export PATH="/opt/homebrew/opt/ruby/bin:$PATH"' >> ~/.zshrc
source ~/.zshrc
```

Verify the right Ruby is active — both of these should point at `/opt/homebrew/...`, **not** `/usr/bin/...`:

```sh
which ruby bundle
ruby --version   # should be 3.x or 4.x, not 2.6
```

If `which bundle` still shows `/usr/bin/bundle`, your shell hasn't picked up the new PATH. Open a new terminal or re-run the `source` line.

### Install dependencies

```sh
bundle install
```

### Run the dev server

```sh
bundle exec jekyll serve
```

The site will be available at <http://localhost:4000>. Edits to most files trigger an automatic rebuild; changes to `_config.yml` require a server restart.

### Build only

```sh
bundle exec jekyll build
```

The static output lands in `_site/`.

## Deployment

Pushes to `main` are built and deployed automatically by [.github/workflows/pages.yml](.github/workflows/pages.yml). The custom domain (`seligofit.com`) is configured via the [CNAME](CNAME) file plus the GitHub Pages settings on the repo.

## Project layout

- `_config.yml` — Jekyll site config
- `_layouts/` — page templates
- `assets/css/` — styles (SCSS)
- `index.html` — landing page
