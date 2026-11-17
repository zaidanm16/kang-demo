# Kang Demo

Static, browser-only demo of the [Kang](https://github.com/zaidanm16/kang-deploy) dashboard: the real frontend with every API, Kong Admin API, and metrics call resolved directly from static fixtures in the browser. Application API calls do not use the network or require a service worker. GitHub Pages still serves the application files and assets.

Live at: https://zaidanm16.github.io/kang-demo/

The demo is built from the `kang-frontend` repository by this repository's workflow; the mock dataset and in-memory request handlers live in `frontend/demo/` in that private repository. Kang is closed source — the frontend repository is private, but its published demo build is public.

See the [documentation](https://zaidanm16.github.io/kang-deploy/) for installation and usage of the real application.

## Updating the demo

The Pages workflow checks out the private frontend using the read-only `FRONTEND_DEPLOY_KEY` repository secret, installs dependencies, and runs `npm run build:demo`. Only the static export is uploaded to Pages; frontend source code is not copied into this repository.

After frontend fixes are merged, run **Deploy demo** with `workflow_dispatch` to rebuild from the frontend main branch. Both sample connections use static data. Profile return links and resource navigation include the GitHub Pages base path through Next.js routing.
