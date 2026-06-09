# ScreenShooter::_PutOnClipboard(HBITMAP__ *)

- ea: `0x1801606ac`
- end: `0x1801607c4`
- name: `?_PutOnClipboard@ScreenShooter@@AEAAJPEAUHBITMAP__@@@Z`
- size: `280`
- prototype: `int(ScreenShooter *__hidden this, HBITMAP)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18015fe70`

## callees

- `0x18002fc18`
- `0x1801606ac`

## import_xrefs

- `USER32!CopyImage` at `0x180160750`
- `USER32!CopyImage` at `0x180160750`
- `GDI32!DeleteObject` at `0x18016078b`
- `GDI32!DeleteObject` at `0x18016078b`
- `GDI32!GetObjectW` at `0x1801606d7`
- `GDI32!GetObjectW` at `0x1801606d7`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetDesktopWindow` at `0x1801606ec`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetDesktopWindow` at `0x1801606ec`
- `api-ms-win-rtcore-ntuser-clipboard-l1-1-0!CloseClipboard` at `0x18016079b`
- `api-ms-win-rtcore-ntuser-clipboard-l1-1-0!CloseClipboard` at `0x18016079b`
- `api-ms-win-rtcore-ntuser-clipboard-l1-1-0!SetClipboardData` at `0x18016076c`
- `api-ms-win-rtcore-ntuser-clipboard-l1-1-0!SetClipboardData` at `0x18016076c`
- `api-ms-win-rtcore-ntuser-clipboard-l1-1-0!OpenClipboard` at `0x1801606fb`
- `api-ms-win-rtcore-ntuser-clipboard-l1-1-0!OpenClipboard` at `0x1801606fb`
- `api-ms-win-rtcore-ntuser-clipboard-l1-1-0!EmptyClipboard` at `0x18016071a`
- `api-ms-win-rtcore-ntuser-clipboard-l1-1-0!EmptyClipboard` at `0x18016071a`

## pseudocode

```c

```
