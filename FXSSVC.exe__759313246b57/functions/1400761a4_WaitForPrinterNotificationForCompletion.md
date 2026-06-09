# WaitForPrinterNotificationForCompletion

- ea: `0x1400761a4`
- end: `0x1400764a7`
- name: `WaitForPrinterNotificationForCompletion`
- size: `771`
- prototype: `__int64 __fastcall(HANDLE hPrinter)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400758d0`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x1400761a4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14007628d`
- `KERNEL32!GetLastError` at `0x1400763fd`
- `KERNEL32!GetLastError` at `0x14007642d`
- `KERNEL32!GetLastError` at `0x14007628d`
- `KERNEL32!GetLastError` at `0x1400763fd`
- `KERNEL32!GetLastError` at `0x14007642d`
- `KERNEL32!WaitForSingleObject` at `0x1400762de`
- `KERNEL32!WaitForSingleObject` at `0x140076393`
- `KERNEL32!WaitForSingleObject` at `0x1400762de`
- `KERNEL32!WaitForSingleObject` at `0x140076393`
- `WINSPOOL!FindFirstPrinterChangeNotification` at `0x140076278`
- `WINSPOOL!FindFirstPrinterChangeNotification` at `0x140076278`
- `WINSPOOL!FindNextPrinterChangeNotification` at `0x140076325`
- `WINSPOOL!FindNextPrinterChangeNotification` at `0x140076325`
- `WINSPOOL!FindClosePrinterChangeNotification` at `0x140076489`
- `WINSPOOL!FindClosePrinterChangeNotification` at `0x140076489`

## pseudocode

```c

```
