[![Netlify Status](https://api.netlify.com/api/v1/badges/8bf4638d-8f79-4cc4-9970-b47359eb1a35/deploy-status)](https://app.netlify.com/sites/unruffled-blackwell-31bfb2/deploys) [![Code Style: prettier](https://img.shields.io/badge/code_style-prettier-ff69b4.svg)](https://github.com/prettier/prettier) [![Conventional Commits](https://img.shields.io/badge/Conventional%20Commits-1.0.0-green.svg)](https://conventionalcommits.org)

## How to develop

Hello there how is it going?

I would like to add **something** `here` as well.

![](/img/editor.png)

Embedded react:

```mdx-code-block
<Tabs>
  <TabItem value="apple" label="Apple" default>
    This is an apple 🍎
  </TabItem>
  <TabItem value="orange" label="Orange">
    This is an orange 🍊
  </TabItem>
  <TabItem value="banana" label="Banana">
    This is a banana 🍌
  </TabItem>
</Tabs>
```

Hey asdf asfsadf

![](/img/Voyager-32-13.jpeg)

---

Additional text

/

---

# asdfasdf

```
const a = '1'
```

```mdx-code-block
asdfs dfsdf
```

```sh
pnpm i # install deps
pnpm start
```

This command starts a local development server and opens up a browser window. Most changes are reflected live without having to restart the server.

By default, the `start` command will only preview documents in English. If you want to preview documents in other languages, such as Chinese, then add `--locale` after the command:

```sh
pnpm start --locale zh
```

## Build

```sh
pnpm build
```

This command generates static content into the `build` directory and can be served using any static contents hosting service.

## Release a new version

### Major or minor

```sh
pnpm docusaurus docs:version x.x.x
```

The versions of the all docs split into two parts, one is the **latest (in `docs/`)** and the others are **versioned (in `versioned_docs/`)**. When a version has been released, the current latest `docs/` will be copied into `versioned_docs/` (by running the command above).

#### i18n

All translated docs won't be copied automatically. You have to handle them manually. For example, release `2.2.0`:

1. Copy `i18n/zh/docusaurus-plugin-content-docs/current.json` to the same folder and rename it to `i18n/zh/docusaurus-plugin-content-docs/version-2.2.0.json`.
2. The replace `Next` and `current` in `version-2.2.0.json`, e.g.:

   ```json
   "version.label": {
     "message": "Next",
     "description": "The label for version current"
   }
   ```

   to:

   ```json
    "version.label": {
      "message": "2.2.0",
      "description": "The label for version 2.2.0"
    }
   ```

Don't forget test the new version build after you've done the above steps!

### Patch

For patch versions, it's only needed to move some folders and change some text. For example, `v2.1.3` to `v2.1.4`:

1. Replace `2.1.3` in **versions.json** with `2.1.4`.
2. `versioned_docs/version-2.1.3` to `versioned_docs/version-2.1.4`.
3. `versioned_sidebars/version-2.1.3-sidebars.json` to `versioned_sidebars/version-2.1.4-sidebars.json` and replace `2.1.3` with `2.1.4` (if have) in json.
4. `i18n/zh/docusaurus-plugin-content-docs/version-2.1.3` to `i18n/zh/docusaurus-plugin-content-docs/version-2.1.4`.
5. `i18n/zh/docusaurus-plugin-content-docs/version-2.1.3.json` to `i18n/zh/docusaurus-plugin-content-docs/version-2.1.4.json` and replace `2.1.3` with `2.1.4` in json.
6. Update `src/data/versions.js`.

Don't forget test the new version build after you've done the above steps!

## How to contribute

Mostly you only need to modify the content in the `docs/`, but if you want some versions to take effect as the latest, please also update the same files in the `versioned_docs/` dir.

## License

Distributed under [CC-BY-4.0](https://creativecommons.org/licenses/by/4.0/).
