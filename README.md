<p align="center"><img src="https://github.com/yipfluoric/chimeran/blob/main/system/usr/share/plymouth/themes/spinner/watermark.png?raw=true"> 
<h4><p align="center"> a Fedora-based bootc image with Niri, Scroll, & Noctalia v5. </p></h4>
<h6><p align="center">Note: this is mostly a personal image for me. I cannot guarantee it will work 100% for you, apologies in advance. </p></h6>
<p align="center"><img src="https://pride-badges.pony.workers.dev/static/v1?label=trans%20rights&stripeWidth=6&stripeColors=5BCEFA,F5A9B8,FFFFFF,F5A9B8,5BCEFA"> <img src="https://pride-badges.pony.workers.dev/static/v1?label=plurality+friendly&labelColor=%23555&stripeWidth=6&stripeColors=2d0625%2C553375%2C7674c2%2C8ac7b0%2Cf4eebe">
<img src="https://github.com/yipfluoric/chimeran/actions/workflows/build.yml/badge.svg">
</p>

## Installation

There are two ways to install Chimeran. One of them, is to install either Fedora Atomic, or preferably base, and then rebase. Another option, if you are already on either and want a fresh install, is to build an iso as described below.


## Rebasing
To rebase an existing Fedora Atomic/base install:

- First, rebase to the unsigned image, for proper signing keys and policies installed and then reboot:
  ```
  rpm-ostree rebase ostree-unverified-registry:ghcr.io/yipfluoric/chimeran:latest
  systemctl reboot
  ```
- Then rebase to the signed image, and then reboot again to complete rebasing:
  ```
  rpm-ostree rebase ostree-image-signed:docker://ghcr.io/yipfluoric/chimeran:latest
  systemctl reboot
  ```

The `latest` tag is what is recommended as it aligns with current base base Version. There is also another option, `chimeran-nvidia` for those on 10 series cards.

## ISO
When on Fedora Atomic or base, you can generate an offline ISO with the instructions available [here](https://blue-build.org/how-to/generate-iso/#_top). These isos are far too big to distribute on github, and among that are potential security risks. This can change in the future but as of the moment, I do not plan to add isos to the github, seperate service, etc. If doing this method, I *highly* encourage you to build it even if this repo later has isos

## Verification

These images are signed with [Sigstore](https://www.sigstore.dev/)'s [cosign](https://github.com/sigstore/cosign). You can verify the signature by downloading the `cosign.pub` file from this repo and running the following command:

```bash
cosign verify --key cosign.pub ghcr.io/yipfluoric/chimeran
```
</div></h1>
