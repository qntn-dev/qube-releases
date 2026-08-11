# Qube Browser — releases

Downloads for [Qube Browser](https://github.com/qntn-dev/q-browser), and the
manifest its built-in updater reads.

The source is not here. This repo exists because an installed browser has to be
able to ask "is there a newer version?" without credentials, and the source repo
is private — so the binaries live in the open and the code does not.

## Get it

Take the latest release. `Qube-x.y.z-setup.exe` installs per user: no admin, no
UAC. The `.zip` is the same thing without an installer.

**It is an alpha, and it is not code-signed.** Windows SmartScreen will warn on
first launch, and there is no way to tell a genuine build from a tampered one.
Each release's notes say what is safe and what is not; read them before handing
a build to anyone.

## latest.json

The updater fetches
[`latest.json`](https://raw.githubusercontent.com/qntn-dev/qube-releases/main/latest.json)
from this branch and compares `version` against its own. It carries the download
URL and a SHA-256 of the installer, so a truncated or swapped download is caught
before anything is run.

That hash proves integrity, not authorship: it travels the same path as the file
it describes. Only code signing fixes that, and this build has none yet.
