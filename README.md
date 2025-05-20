# Shell Protocols

Extra wayland protocols for desktop shell components.

## Why

Most desktop shells need far deeper integration into the compositor than a normal
application does and is currently provided from wayland-protocols. This integration
is usually achieved through private wayland protocols or compositor specific IPC.
In desktop environments like KDE or GNOME, this isn't really an issue, as they
own the entire stack, and getting a new integration is as simple as just implementing it.

Outside of those environments, we have a wide array of compositors and desktop shell
components from independent authors who may not necessarily work with eachother.
Usually this results in every desktop shell component having to implement custom
IPC protocols from a number of compositors they wish to support, often with serious
synchronization issues if not a wayland protocol.

This repository is an attempt to standardize common functionality wanted by desktop
shells that is currently missing from wayland-protocols, with a goal of eventually
upstreaming most or all of it in some form.

## Procedure

If a protocol works out, a merge request can be opened on wayland-protocols
for further bikeshedding. If a protocol is merged upstream it will be marked
as deprected in this repository.
