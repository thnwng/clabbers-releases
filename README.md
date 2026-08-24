# Clabbers releases

Download shelf and update feed for **Clabbers**, a Scrabble word-study app
(FSRS spaced-repetition flashcards, a daily challenge, and head-to-head races).
The app itself lives at [clabbers.app](https://clabbers.app).

This repository holds **release downloads only**. There is no source code here.

## Downloads

Get the newest build from the [Releases](../../releases) page.

| Platform | File |
|---|---|
| Windows | `Clabbers-Setup-<version>.exe` — one-click installer, installs for the current user (no administrator rights needed) |

The Windows installer is not code-signed, so SmartScreen shows a
"Windows protected your PC" warning on first run: choose **More info** ->
**Run anyway**. Later updates install without repeating that prompt.

## Automatic updates

The Windows app checks this repository's releases for a newer version shortly
after it starts, downloads one in the background when it finds it, and offers to
restart. You can also check on demand from **Help > Check for updates**.

Only published releases are visible to the updater — drafts and pre-releases are
deliberately ignored.

Each release carries the files the updater needs:

- `Clabbers-Setup-<version>.exe` — the installer
- `Clabbers-Setup-<version>.exe.blockmap` — lets an update download only the
  changed parts of the installer instead of the whole file
- `latest.yml` — the version manifest, including a checksum the app verifies
  before installing

Your study data is not touched by an update. It lives outside the application
folder and survives updates and uninstalls alike.

## Maintainer note: this repository name is permanent

Every installed copy of Clabbers has this repository's address compiled into it,
and that is where it looks for updates for as long as it stays installed.

- **Do not delete this repository, and do not reuse the name for anything else.**
  Deleting it silently strands every installed copy on its current version.
- Renaming or transferring it is survivable — GitHub redirects the old address —
  but the redirect is the only thing keeping those installs working, so avoid it
  unless there is a reason.
- Releases must be **published**, not left as drafts, or no one will be offered
  the update.
