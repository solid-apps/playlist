# Songstr

> YouTube playlist player. Load an M3U from any URL — including your Solid pod.

Single-file vanilla JS web app. No build, no bundler, no framework. Open `index.html` from any HTTP server and pass an `?uri=…` query param pointing at an M3U playlist.

## Try

The bundled `1.m3u` is loaded by default. To load your own:

```
./index.html?uri=https://your.pod/path/to/playlist.m3u
```

Or push the app to a Solid pod (e.g. via [jspod](https://github.com/JavaScriptSolidServer/jspod) or [nosdav-server](https://github.com/nosdav/server)):

```bash
git remote add pod http://localhost:5444/public/apps/playlist
git push pod HEAD:gh-pages
# open: http://localhost:5444/public/apps/playlist/
```

## M3U format

Standard extended M3U:

```
#EXTM3U
#PLAYLIST:Your playlist name
#EXTINF:-1,Track title
https://www.youtube.com/watch?v=VIDEO_ID
```

YouTube URLs in any common form (`youtu.be/...`, `youtube.com/watch?v=...`, etc.) are recognized; non-YouTube URLs render their raw form.

## Solid-native features (planned)

- xlogin auth widget
- Save / Load against the signed-in user's pod
- Per-playlist state doc (current track + position) — resume + multi-device sync
- Remote control via WebSocket subscription (same pattern as [solid-apps/pdf](https://github.com/solid-apps/pdf))

## License

AGPL-3.0-only.
