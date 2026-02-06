# Personal Portfolio

This is a personal portfolio and blog website built with [Astro](https://astro.build/). It uses [Tailwind CSS](https://tailwindcss.com/) for styling and [Astro Content Collections](https://docs.astro.build/en/guides/content-collections/) to manage the content.

## 🚀 Project Structure

Inside of your Astro project, you'll see the following folders and files:

```
/
├── public/
│   └── favicon.svg
├── src/
│   ├── components/
│   │   ├── atoms/
│   │   ├── molecules/
│   │   └── organisms/
│   ├── content/
│   │   ├── projects/
│   │   ├── reflections/
│   │   └── translations/
│   │   └── config.ts
│   ├── layouts/
│   │   └── BaseLayout.astro
│   └── pages/
│       ├── index.astro
│       ├── projects/
│       │   ├── [...slug].astro
│       │   └── index.astro
│       ├── reflections/
│       │   ├── [...slug].astro
│       │   └── index.astro
│       └── translations/
│           ├── [...slug].astro
│           └── index.astro
└── package.json
```

Astro looks for `.astro` or `.md` files in the `src/pages/` directory. Each page is exposed as a route based on its file name.

There's nothing special about `src/components/`, but that's where we recommend placing any Astro/React/Vue/Svelte/Preact components.

Any static assets, like images, can be placed in the `public/` directory.

## 🧞 Commands

All commands are run from the root of the project, from a terminal:

| Command                | Action                                           |
| :--------------------- | :----------------------------------------------- |
| `npm install`          | Installs dependencies                            |
| `npm run dev`          | Starts local dev server at `localhost:4321`      |
| `npm run build`        | Build your production site to `./dist/`          |
| `npm run preview`      | Preview your build locally, before deploying     |

## 👀 Want to learn more?

Check out the [Astro documentation](https://docs.astro.build) or jump into the [Astro Discord server](https://astro.build/chat).

## 🚀 Deploy to GitHub Pages

To deploy your site to GitHub Pages, you'll need to create a `deploy.yml` file in the `.github/workflows` directory. Here's an example:

```yaml
name: Deploy to GitHub Pages

on:
  push:
    branches:
      - main

jobs:
  build-and-deploy:
    runs-on: ubuntu-latest
    steps:
      - name: Check out a copy of your repository
        uses: actions/checkout@v3

      - name: Set up Node.js
        uses: actions/setup-node@v3
        with:
          node-version: 20

      - name: Install dependencies
        run: npm install

      - name: Build your site
        run: npm run build

      - name: Deploy to GitHub Pages
        uses: peaceiris/actions-gh-pages@v3
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_dir: ./dist
```

**Important:** Before deploying, make sure to update the `site` and `base` properties in your `astro.config.mjs` file to reflect your GitHub username and repository name.
