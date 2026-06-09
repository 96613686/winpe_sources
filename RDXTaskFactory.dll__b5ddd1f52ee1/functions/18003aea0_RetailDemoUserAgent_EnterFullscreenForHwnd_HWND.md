# RetailDemoUserAgent::EnterFullscreenForHwnd(HWND__ * &)

- ea: `0x18003aea0`
- end: `0x18003af9a`
- name: `?EnterFullscreenForHwnd@RetailDemoUserAgent@@AEAAJAEAPEAUHWND__@@@Z`
- size: `250`
- prototype: `__int64 __fastcall(RetailDemoUserAgent *__hidden this, HWND *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180037254`

## callees

- `0x180003390`
- `0x18000aa5c`
- `0x18003aea0`

## import_xrefs

- `api-ms-win-ntuser-sysparams-l1-1-0!GetMonitorInfoW` at `0x18003af06`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetMonitorInfoW` at `0x18003af06`
- `USER32!GetWindowLongW` at `0x18003aec4`
- `USER32!GetWindowLongW` at `0x18003aec4`
- `USER32!MonitorFromWindow` at `0x18003aef8`
- `USER32!MonitorFromWindow` at `0x18003aef8`
- `USER32!SetWindowLongW` at `0x18003af21`
- `USER32!SetWindowLongW` at `0x18003af21`
- `USER32!SetWindowPos` at `0x18003af54`
- `USER32!SetWindowPos` at `0x18003af54`

## string_xrefs

- `0x18003af63`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`

## pseudocode

```c

```
