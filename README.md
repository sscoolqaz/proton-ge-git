# proton-ge-git

AUR package for Proton-GE built from git.

Installs GloriousEggroll's custom Proton build into Steam's compatibility tools.

## Install

```sh
yay -S proton-ge-git   # or any AUR helper
```

After installing, restart Steam and enable **Proton-GE-git** under
Settings → Compatibility.

## Building

Proton compiles inside Valve's Steam Runtime SDK container, so the host only
needs `git`, `wget`, `perl`, `python` and a container engine. Podman (rootless)
is the default; to use Docker instead, start its daemon, add your user to the
`docker` group and build with `PROTON_CONTAINER_ENGINE=docker`. The SDK image
is pulled on the first build.

A build needs about 45 GB free in makepkg's `BUILDDIR` (more than a default
`/tmp` tmpfs holds) plus a few GB for the SDK image in container storage, and
takes roughly 45 minutes on 16 threads.

## Links

- Upstream: https://github.com/GloriousEggroll/proton-ge-custom
- AUR: https://aur.archlinux.org/packages/proton-ge-git
