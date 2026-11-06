<div align="center">

<img src="ios/Runner/Assets.xcassets/AppIcon.appiconset/Icon-App-1024x1024@1x.png" width="120" alt="Hongguo Jian icon">

# Hongguo Jian / Zhenguo Jian

A standalone multi-platform Flutter app for short dramas and films, with dedicated layouts for phones, tablets, desktops and TVs

[![Release](https://img.shields.io/github/v/release/Xanerix/guoapp?style=flat-square&color=3d4656)](../../releases)
[![License](https://img.shields.io/badge/license-GPL--3.0-3d4656?style=flat-square)](LICENSE)
![Flutter](https://img.shields.io/badge/Flutter-3.47.9-02569B?style=flat-square&logo=flutter&logoColor=white)
![Platforms](https://img.shields.io/badge/platform-Android%20%7C%20iOS%20%7C%20Windows%20%7C%20macOS-8fa3bc?style=flat-square)

[![Telegram Group](https://img.shields.io/badge/Telegram-Group-26A5E4?style=flat-square&logo=telegram&logoColor=white)](https://t.me/+c9YKHp7FjSk0MjI1)
[![Telegram Channel](https://img.shields.io/badge/Telegram-Channel-26A5E4?style=flat-square&logo=telegram&logoColor=white)](https://t.me/+F9NnQSsMfOU3OTdl)

[Download](#installation) · [Features](#features) · [Sources](#sources) · [Privacy](#update-checks-and-usage-stats) · [Development](#development)

**English** | [简体中文](README-CN.md)

</div>

---

This project is adapted from the source code of [fish2018](https://github.com/fish2018) and is released in two builds:

| Build | Sources | Package prefix |
| --- | --- | --- |
| **Hongguo Jian** (红果鉴) | Hongguo only | `hongguojian-` |
| **Zhenguo Jian** (真果鉴) | All sources, each toggleable in Settings | `zhenguojian-` |

## Features

### Interface and appearance

- **Navigation**: Discover / Watchlist / Me. Phones use a bottom bar, tablets and desktops use a collapsible side rail, and TVs use top tabs; on wide screens, sub-pages open to the right of the rail.
- **UI mode**: Auto-detected, TV, phone, tablet or window (desktop only). A manually chosen mode no longer switches with window width. TV mode forces landscape; phone mode locks portrait.
- **Theme**: System color extraction (Android 12+ follows the wallpaper, Windows and macOS follow the accent color) or 6 preset palettes; light / dark / follow system.

### Browsing

- **Discover**: Switch sources next to the source name. The category tabs are Recommended / All / each ranking / each genre, and ranking covers show their position. A large card at the top of the first tab shows the last-watched or recommended title. Scrolling to the bottom loads more; pull down or tap Refresh to reload the current category.
- **Search**: Searches the current source only and keeps recent searches; Hongguo offers input suggestions.
- **Details**: The cover is blurred as a backdrop, showing episode count, completion status, categories, play count, tags and synopsis. Episodes are grouped 30 per page and open at the resume episode; watched episodes are dimmed and VIP episodes are marked. The resume episode is pre-buffered in the background when the page opens.

### Playback

| Device | Experience |
| --- | --- |
| Desktop | Video on the left, episode list on the right; wide-screen and full-screen modes; hover for quality, speed and volume; supports Space, Enter, arrow keys, M and other shortcuts |
| Phone | Immersive portrait short-drama playback; swipe up/down to change episodes, swipe left/right to seek, long-press the picture for playback settings, long-press the left side for 2x speed, and lock the screen. Landscape video held upright puts the video on top with synopsis / episodes below, and rotating to landscape goes full-screen automatically. In full-screen, double-tap either side to seek back / forward, swipe up/down on the left half for brightness and the right half for volume |
| Tablet | Landscape behaves like desktop, portrait like phone; landscape is locked in full-screen |
| TV | Controls float over the picture; when hidden, left / right seeks back / forward 10 seconds; Back closes options, then collapses the controls, then exits; episodes are changed from the details page |

Common to all devices: the next episode is pre-buffered so paging and autoplay continue seamlessly; speed, quality and the danmaku toggle are remembered. Danmaku is available for Hongguo online playback and is not loaded for local playback.

### Watchlist and history

- **Watchlist**: A simple on / off list. Titles with new episodes are grouped under Updated and show how many episodes are new; search, filter by source, and deselect in bulk. Every 30 minutes the app checks a batch of unfinished watchlist titles in the background.
- **History**: Grouped by Today / Yesterday / Earlier; search, filter by source, delete in bulk, and Clear removes only the records currently listed.
- **Me**: User card, recently watched, download summary and a settings entry; bottom bar / side rail icons show how many episodes are downloading.

### Downloads

- Start from Download episodes on the details page, or multi-select in the episode list on the playback page (tap, drag, select all).
- The download page splits into Downloading and Downloaded, with pause / resume / retry for a single episode or all of them. Downloaded titles are grouped by show and can be played, deleted or filled in for missing episodes.
- Each episode is converted to a plain mp4 when the download finishes (Hongguo decrypts first and merges the m3u8 into one file) and saved as `download dir/show name/episode N.mp4`, ready to copy out and use.
- Episodes downloaded by older versions stay as they are, and files merged by older versions are no longer listed. Downloads are not available on TV.

### Settings, users and backup

- **Settings**: 8 groups — Appearance, Playback, Downloads, Sources, Proxy, Users, About, Diagnostics. Changes save immediately; items you lack permission for are greyed out with the reason.
- **Users**: Each user keeps their own watchlist, history and searches, and switches with a tap. Administrators can add, edit and delete users, and decide which sources each user can access and whether downloads are allowed.
- **Backup**: Export / restore users, watchlist, history and preferences (including theme colors); downloaded videos are unaffected. Backups from older versions can still be imported. If the local config is corrupted, the splash screen can restore from a backup.

> [!NOTE]
> Picture-in-picture, quality enhancement, sorting and filtering, episode long-press menus, and Hongguo multi-season switching are not available yet.

## Sources

| Source | Content | Search |
| --- | --- | --- |
| Hongguo | Short dramas, comic dramas, AI dramas; recommendations, rankings, genres | Online search with input suggestions |
| Hanxiaoquan | Korean dramas, Korean films, variety shows, anime, multiple lines | Online search |
| Guipian | Ghost films, TV series, anime, multiple lines | Matches the latest items in the site RSS feed |
| Qingkong | Anime series, theatrical anime, tokusatsu | Online search |
| Huangdou | Curated short dramas, rankings | Local cache only |
| Juguo | Short dramas by category | Online search |
| Yeguo | Short dramas by category | Online search |
| Diguo | Videos by category | Online search |
| Jinguo Short Drama | Recommendations, trending, short dramas by category | Online search |
| Jinguo | Featured, latest, short dramas by category | Online search |
| Huangguo Video / Huangguo AI / Huangguo Legacy | Lists, categories and episodes | Local cache only |

Source availability, quality and regional restrictions depend on the source sites and your network; the app does not bypass VIP or other authorization restrictions on those sites.

## Installation

Download the package for your platform from [Releases](../../releases): packages starting with `hongguojian-` are Hongguo Jian, `zhenguojian-` are Zhenguo Jian.

| Platform | Package |
| --- | --- |
| Android 7.0+ | Three APKs — arm64-v8a / armeabi-v7a / x86_64 — pick the one matching your device architecture (most phones: arm64-v8a). Builds with the same signature upgrade in place; older builds signed with a different certificate require an uninstall first |
| Windows 10/11 x64 | Full ZIP; unzip and run `hongguojian.exe` / `zhenguojian.exe`, keeping all DLLs and the `data` directory |
| iOS 15.1+ | Unsigned IPA; sign it yourself or sideload with a tool such as iloader |
| macOS 12+ | Universal dmg (Apple silicon and Intel); open and drag into Applications. Not notarized, so you must clear the quarantine flag before the first launch (see below) |

> [!TIP]
> An `INSTALL_FAILED_NO_MATCHING_ABIS` error on Android means the APK does not match your device architecture; use the package for the matching ABI.

> [!IMPORTANT]
> On macOS, run the following in Terminal before the first launch (for Zhenguo Jian, replace `红果鉴.app` with `真果鉴.app`):
>
> ```sh
> xattr -dr com.apple.quarantine /Applications/红果鉴.app
> ```

## Update checks and usage stats

| Request | What is sent |
| --- | --- |
| Update check | No data is sent; only the latest version number is read. Checked once at startup; when a new version exists the prompt appears on every launch, with options to skip this version or stop being reminded |
| Anonymous usage stats | Only: a random ID generated on first use (unrelated to device or account), app version, platform (Android / iOS / Windows / macOS), and whether it is Hongguo Jian or Zhenguo Jian |

No history, watchlist, searches, source settings or any other personal data is sent. The receiving code is in [`worker/`](worker). Both can be turned off separately under **Settings › About**; once off, the app sends no corresponding requests.

## Disclaimer

- This project is intended for personal learning and technical research only.
- This project is not affiliated with Hongguo Short Drama or the operators of any other source, and is neither authorized nor endorsed by them; the names and trademarks mentioned belong to their respective owners.
- The app itself does not store, upload or distribute any video content. All content comes from third-party sites and remains the copyright of its original owners; the app does not bypass VIP or other authorization restrictions on those sites.
- Users must comply with the laws and regulations of their jurisdiction and the terms of service of each site. Any consequences of using this project are borne by the user.
- This project is provided "as is", without any warranty of availability, stability or fitness for purpose, and the author accepts no liability for any direct or indirect loss arising from its use.
- If you believe this project infringes your lawful rights, please contact us via Issues and it will be handled promptly once verified.

## License

This project is released under the [GNU GPL v3.0](https://www.gnu.org/licenses/gpl-3.0.html); the full text is in [LICENSE](LICENSE). Third-party dependencies follow their respective licenses.

## Development

See [DEVELOPMENT.md](DEVELOPMENT.md) for build, test, architecture and release workflows, and [CHANGELOG.md](CHANGELOG.md) for the version history.
