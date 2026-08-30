# LUG@UMBC Mirrors

Static landing page for the [UMBC Linux Users Group](https://lug.umbc.edu) mirror server. Lists available Linux distribution mirrors and shows when each one was last synced. See it in use at: https://mirror.lug.umbc.edu

## How it works

A single `index.html` renders the mirror list from the `distros` array defined at the top of its inline script. For each entry, the page fetches the mirror's **trace file** to display a "last sync" timestamp.

Sync timestamps rely on the `project/trace/<host>` file written by Debian's mirror-sync tooling:

- https://salsa.debian.org/mirror-team/archvsync

The default trace path is `<distro-url>/project/trace/<host>`. To read a custom or multiple trace files, set the `trace` property on a distro entry (see the `Linux Mint` entry for an example).

## Adding a mirror

1. Add an entry to the `distros` array in `index.html`.
2. Drop a matching icon in `distro-icons/` named after the distro URL slug (e.g. `debian.svg`, `easyos.png`).
3. If the trace file is not at the default location, set the `trace` field.