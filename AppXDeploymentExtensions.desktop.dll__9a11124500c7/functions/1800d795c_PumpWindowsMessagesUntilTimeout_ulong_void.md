# PumpWindowsMessagesUntilTimeout(ulong,void *)

- ea: `0x1800d795c`
- end: `0x1800d7a8d`
- name: `?PumpWindowsMessagesUntilTimeout@@YAJKPEAX@Z`
- size: `305`
- prototype: `__int64 __fastcall(unsigned int, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18006927c`

## callees

- `0x18000669c`
- `0x18001adb4`
- `0x1800d795c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800d798c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800d7a27`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800d798c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800d7a27`
- `api-ms-win-ntuser-ie-message-l1-1-0!PeekMessageW` at `0x1800d79ec`
- `api-ms-win-ntuser-ie-message-l1-1-0!PeekMessageW` at `0x1800d79ec`
- `api-ms-win-ntuser-ie-message-l1-1-0!TranslateMessage` at `0x1800d7a08`
- `api-ms-win-ntuser-ie-message-l1-1-0!TranslateMessage` at `0x1800d7a08`
- `api-ms-win-ntuser-ie-message-l1-1-0!DispatchMessageW` at `0x1800d7a19`
- `api-ms-win-ntuser-ie-message-l1-1-0!DispatchMessageW` at `0x1800d7a19`
- `api-ms-win-ntuser-ie-message-l1-1-0!MsgWaitForMultipleObjects` at `0x1800d79b2`
- `api-ms-win-ntuser-ie-message-l1-1-0!MsgWaitForMultipleObjects` at `0x1800d79b2`

## string_xrefs

- `0x1800d7a4f`: `onecore\admin\appmodel\osim\src\deh\appx\common\shellrefresh.cpp`
- `0x1800d7a6c`: `onecore\admin\appmodel\osim\src\deh\appx\common\shellrefresh.cpp`

## pseudocode

```c

```
