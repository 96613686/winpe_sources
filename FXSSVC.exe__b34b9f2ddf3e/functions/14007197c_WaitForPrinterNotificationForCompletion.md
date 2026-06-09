# WaitForPrinterNotificationForCompletion

- ea: `0x14007197c`
- end: `0x140071c4b`
- name: `WaitForPrinterNotificationForCompletion`
- size: `719`
- prototype: `__int64 __fastcall(HANDLE hPrinter)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14007116c`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x14007197c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140071a5f`
- `KERNEL32!GetLastError` at `0x140071bb4`
- `KERNEL32!GetLastError` at `0x140071bde`
- `KERNEL32!GetLastError` at `0x140071a5f`
- `KERNEL32!GetLastError` at `0x140071bb4`
- `KERNEL32!GetLastError` at `0x140071bde`
- `KERNEL32!WaitForSingleObject` at `0x140071aaa`
- `KERNEL32!WaitForSingleObject` at `0x140071b53`
- `KERNEL32!WaitForSingleObject` at `0x140071aaa`
- `KERNEL32!WaitForSingleObject` at `0x140071b53`
- `WINSPOOL!FindFirstPrinterChangeNotification` at `0x140071a50`
- `WINSPOOL!FindFirstPrinterChangeNotification` at `0x140071a50`
- `WINSPOOL!FindNextPrinterChangeNotification` at `0x140071aeb`
- `WINSPOOL!FindNextPrinterChangeNotification` at `0x140071aeb`
- `WINSPOOL!FindClosePrinterChangeNotification` at `0x140071c34`
- `WINSPOOL!FindClosePrinterChangeNotification` at `0x140071c34`

## pseudocode

```c

```
