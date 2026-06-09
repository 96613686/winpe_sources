# CKeyboardOcclusionMitigation::_MitigateWindow(HWND__ *)

- ea: `0x18007a18c`
- end: `0x18007a6d0`
- name: `?_MitigateWindow@CKeyboardOcclusionMitigation@@AEAA_NPEAUHWND__@@@Z`
- size: `1348`
- prototype: `bool __fastcall(CKeyboardOcclusionMitigation *__hidden this, HWND)`
- caller_count: `2`
- callee_count: `24`
- tags: `service_task`

## callers

- `0x18007a160`
- `0x180115a10`

## callees

- `0x180009dd0`
- `0x180044aa4`
- `0x180045190`
- `0x18006f5b0`
- `0x18007a18c`
- `0x180082a48`
- `0x1800831f0`
- `0x18010ebd0`
- `0x180142e10`
- `0x180143a7c`
- `0x1802664f0`
- `0x180266684`
- `0x180266944`
- `0x1802669ac`
- `0x1802670a0`
- `0x1802679a0`
- `0x180267a7c`
- `0x180267aa4`
- `0x180267b50`
- `0x180267c24`
- `0x180267c68`
- `0x180267d78`
- `0x1802680a0`
- `0x1803bb010`

## import_xrefs

- `USER32!GetWindowPlacement` at `0x18007a405`
- `USER32!GetWindowPlacement` at `0x18007a405`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowPos` at `0x18007a5f7`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowPos` at `0x18007a5f7`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowRect` at `0x18007a268`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowRect` at `0x18007a2c0`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowRect` at `0x18007a268`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowRect` at `0x18007a2c0`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowLongW` at `0x18007a300`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowLongW` at `0x18007a42e`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowLongW` at `0x18007a300`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowLongW` at `0x18007a42e`
- `ext-ms-win-ntuser-private-l1-1-1!__imp_IsShellFrameWindow` at `0x18007a541`
- `ext-ms-win-ntuser-private-l1-1-1!__imp_IsShellFrameWindow` at `0x18007a541`
- `twinapi.appcore!__imp_CoreQueryWindowService` at `0x18007a586`
- `twinapi.appcore!__imp_CoreQueryWindowService` at `0x18007a586`
- `dwmapi!DwmGetWindowAttribute` at `0x18007a299`
- `dwmapi!DwmGetWindowAttribute` at `0x18007a299`
- `api-ms-win-ntuser-rectangle-l1-1-0!EqualRect` at `0x18007a2d8`
- `api-ms-win-ntuser-rectangle-l1-1-0!EqualRect` at `0x18007a2d8`

## pseudocode

```c

```
