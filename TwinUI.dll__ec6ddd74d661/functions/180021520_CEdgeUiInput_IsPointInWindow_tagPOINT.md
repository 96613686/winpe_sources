# CEdgeUiInput::_IsPointInWindow(tagPOINT)

- ea: `0x180021520`
- end: `0x180021646`
- name: `?_IsPointInWindow@CEdgeUiInput@@AEAA_NUtagPOINT@@@Z`
- size: `294`
- prototype: `bool __fastcall(CEdgeUiInput *__hidden this, struct tagPOINT)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180021340`
- `0x180023134`
- `0x18006c384`
- `0x18006ff50`

## callees

- `0x180021520`
- `0x1800b8568`
- `0x180142e10`

## import_xrefs

- `USER32!GetWindowRgn` at `0x1800215b3`
- `USER32!GetWindowRgn` at `0x1800215b3`
- `USER32!GetWindowRgnBox` at `0x18002155b`
- `USER32!GetWindowRgnBox` at `0x18002155b`
- `GDI32!DeleteObject` at `0x1800215eb`
- `GDI32!DeleteObject` at `0x1800215eb`
- `GDI32!CreateRectRgn` at `0x180021579`
- `GDI32!CreateRectRgn` at `0x180021579`
- `GDI32!PtInRegion` at `0x1800215cf`
- `GDI32!PtInRegion` at `0x1800215cf`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!ScreenToClient` at `0x18002159d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!ScreenToClient` at `0x18002159d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowRect` at `0x180021605`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowRect` at `0x180021605`

## pseudocode

```c

```
