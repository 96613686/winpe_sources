# PumpWindowsMessagesUntilTimeout(ulong,void *)

- ea: `0x180065ee8`
- end: `0x180065ff0`
- name: `?PumpWindowsMessagesUntilTimeout@@YAJKPEAX@Z`
- size: `264`
- prototype: `__int64 __fastcall(unsigned int, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180065b54`

## callees

- `0x180065ee8`
- `0x180098bf4`
- `0x1800a021c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180065f18`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180065f91`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180065f18`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180065f91`
- `api-ms-win-ntuser-ie-message-l1-1-0!DispatchMessageW` at `0x180065f89`
- `api-ms-win-ntuser-ie-message-l1-1-0!DispatchMessageW` at `0x180065f89`
- `api-ms-win-ntuser-ie-message-l1-1-0!PeekMessageW` at `0x180065f68`
- `api-ms-win-ntuser-ie-message-l1-1-0!PeekMessageW` at `0x180065f68`
- `api-ms-win-ntuser-ie-message-l1-1-0!TranslateMessage` at `0x180065f7e`
- `api-ms-win-ntuser-ie-message-l1-1-0!TranslateMessage` at `0x180065f7e`
- `api-ms-win-ntuser-ie-message-l1-1-0!MsgWaitForMultipleObjects` at `0x180065f38`
- `api-ms-win-ntuser-ie-message-l1-1-0!MsgWaitForMultipleObjects` at `0x180065f38`

## string_xrefs

- `0x180065fb3`: `onecore\admin\appmodel\osim\src\deh\appx\common\shellrefresh.cpp`
- `0x180065fd0`: `onecore\admin\appmodel\osim\src\deh\appx\common\shellrefresh.cpp`

## pseudocode

```c

```
