<h1 align="center">SelectVPN</h1>

<p align="center">
  <b>A VPN that keeps working when the network gets strict.</b>
  <br>
  Android and Windows · iOS in progress
  <br><br>
  <a href="https://github.com/selectvpn/selectvpn/releases/latest"><b>Download</b></a>
  &nbsp;·&nbsp;
  <a href="https://selectvpn.net">selectvpn.net</a>
  &nbsp;·&nbsp;
  <a href="https://t.me/select_vpn_bot">@select_vpn_bot</a>
</p>

## Why SelectVPN

- **Holds on when the network tightens.** Some networks quietly stop behaving like the open
  internet. SelectVPN notices on its own, takes a route that still gets through and brings you
  back the moment things are normal again. Nothing to switch by hand.
- **Keeps calm on a shaky signal.** A dip in the metro is no reason to jump servers. The app
  tells a bad moment from a real change of network and reacts only to the second.
- **Works while you're not looking.** The watch runs inside the tunnel itself, so it keeps going
  with the app closed and the screen off.
- **Your server stays yours.** After a detour you're returned to the server you picked, not to
  whichever one happens to be fastest.
- **Doesn't give itself away.** With the tunnel up, the app's own requests travel inside it too,
  and without it they don't announce where they're going.

## Everything else

- **Two cores, picked per server:** sing-box and xray-core. VLESS (Reality, XHTTP, WebSocket,
  gRPC), VMess, Trojan, Shadowsocks and Hysteria2.
- **Split tunneling.** Russian sites straight, only chosen apps through the VPN or some kept out
  of it, and ads blocked.
- **Kill switch.** On Android it's the system's Always-on VPN with "Block connections without
  VPN"; Windows gets its own, under the same name.
- **Stays on.** Closing the app doesn't drop the tunnel. On Android it's one tap away in Quick
  Settings and in the notification.
- **Servers by purpose.** General, Gaming and Reserve, each sorted by ping.

## Download

Get the latest build from **[Releases](https://github.com/selectvpn/selectvpn/releases/latest)**.

| Platform | File |
|---|---|
| Android 8+ | `…-android-arm64-v8a.apk` for almost any modern phone, `…-android-armeabi-v7a.apk` for older 32-bit ones |
| Windows 10/11 (x64) | `…-windows-setup.exe` |
| iOS | in progress |

The Windows installer isn't signed with a developer certificate yet, so SmartScreen asks for
confirmation: **More info → Run anyway**. On launch the app asks for administrator rights: the
tunnel creates a network adapter, and Windows allows that only to administrators.

## Get a key

At **[selectvpn.net](https://selectvpn.net)** or from the Telegram bot
**[@select_vpn_bot](https://t.me/select_vpn_bot)**.

## Check that the file is ours

Only files from this page and from selectvpn.net are ours. Every release carries
`SHA256SUMS.txt` with a signature made by the project key:

```
-----BEGIN PUBLIC KEY-----
MCowBQYDK2VwAyEAIZnifF4DffSVAfcBCXNCcYX93hlE6cwRnNkdfdtRj7o=
-----END PUBLIC KEY-----
```

Save it as `selectvpn.pub.pem` next to the downloaded files and run:

```bash
openssl pkeyutl -verify -rawin -pubin -inkey selectvpn.pub.pem \
  -in SelectVPN-1.1.0-SHA256SUMS.txt -sigfile SelectVPN-1.1.0-SHA256SUMS.txt.sig
shasum -a 256 -c --ignore-missing SelectVPN-1.1.0-SHA256SUMS.txt
```

`Signature Verified Successfully` and `OK` next to your file mean it's the real one. On Windows,
`openssl` comes with Git for Windows; the hash alone is
`certutil -hashfile SelectVPN-1.1.0-windows-setup.exe SHA256`.
