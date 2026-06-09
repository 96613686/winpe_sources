# PrintConfig::CPrinterExtensionManager::GetPrinterQueuesThreadProc(void *)

- ea: `0x18008ac00`
- end: `0x18008b138`
- name: `?GetPrinterQueuesThreadProc@CPrinterExtensionManager@PrintConfig@@CAKPEAX@Z`
- size: `1336`
- prototype: `__int64 __fastcall(struct IDispatch **lpThreadParameter)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x180003c20`
- `0x180004564`
- `0x18000f830`
- `0x180018f58`
- `0x1800197b4`
- `0x180037124`
- `0x18005363c`
- `0x180054378`
- `0x180088a2c`
- `0x180088ad4`
- `0x180089a78`
- `0x18008a464`
- `0x18008ac00`
- `0x18008b4f0`
- `0x18008b718`
- `0x1801cb010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18008acdd`
- `KERNEL32!GetLastError` at `0x18008b0c4`
- `KERNEL32!GetLastError` at `0x18008b0fb`
- `KERNEL32!GetLastError` at `0x18008acdd`
- `KERNEL32!GetLastError` at `0x18008b0c4`
- `KERNEL32!GetLastError` at `0x18008b0fb`
- `KERNEL32!SetEvent` at `0x18008aee1`
- `KERNEL32!SetEvent` at `0x18008aee1`
- `KERNEL32!WaitForMultipleObjects` at `0x18008ae94`
- `KERNEL32!WaitForMultipleObjects` at `0x18008ae94`
- `ole32!CoInitializeEx` at `0x18008ac27`
- `ole32!CoInitializeEx` at `0x18008ac27`
- `ole32!CoUninitialize` at `0x18008af72`
- `ole32!CoUninitialize` at `0x18008af72`
- `WINSPOOL!OpenPrinterW` at `0x18008accd`
- `WINSPOOL!OpenPrinterW` at `0x18008accd`
- `WINSPOOL!FindClosePrinterChangeNotification` at `0x18008aefb`
- `WINSPOOL!FindClosePrinterChangeNotification` at `0x18008aefb`

## string_xrefs

- `0x18008af8a`: `Error in printer queue enumeration thread: 0x%x.`
- `0x18008af91`: `PrintConfig::CPrinterExtensionManager::GetPrinterQueuesThreadProc`

## pseudocode

```c

```
