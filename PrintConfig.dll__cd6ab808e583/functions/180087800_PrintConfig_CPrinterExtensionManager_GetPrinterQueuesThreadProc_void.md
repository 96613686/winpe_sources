# PrintConfig::CPrinterExtensionManager::GetPrinterQueuesThreadProc(void *)

- ea: `0x180087800`
- end: `0x180087d81`
- name: `?GetPrinterQueuesThreadProc@CPrinterExtensionManager@PrintConfig@@CAKPEAX@Z`
- size: `1409`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, loader_planting`

## callees

- `0x180003b00`
- `0x180004424`
- `0x18000f380`
- `0x1800183f8`
- `0x180018bbc`
- `0x180035e18`
- `0x180051854`
- `0x180052360`
- `0x180085768`
- `0x1800866ac`
- `0x180087060`
- `0x180087800`
- `0x180088140`
- `0x180088340`
- `0x1801c3010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800878d1`
- `KERNEL32!GetLastError` at `0x1800879bf`
- `KERNEL32!GetLastError` at `0x180087d19`
- `KERNEL32!GetLastError` at `0x180087d4a`
- `KERNEL32!GetLastError` at `0x1800878d1`
- `KERNEL32!GetLastError` at `0x1800879bf`
- `KERNEL32!GetLastError` at `0x180087d19`
- `KERNEL32!GetLastError` at `0x180087d4a`
- `KERNEL32!SetEvent` at `0x180087b25`
- `KERNEL32!SetEvent` at `0x180087b25`
- `KERNEL32!WaitForMultipleObjects` at `0x180087ade`
- `KERNEL32!WaitForMultipleObjects` at `0x180087ade`
- `ole32!CoInitializeEx` at `0x180087827`
- `ole32!CoInitializeEx` at `0x180087827`
- `ole32!CoUninitialize` at `0x180087baa`
- `ole32!CoUninitialize` at `0x180087baa`
- `WINSPOOL!FindFirstPrinterChangeNotification` at `0x18008798f`
- `WINSPOOL!FindFirstPrinterChangeNotification` at `0x18008798f`
- `WINSPOOL!OpenPrinterW` at `0x1800878c7`
- `WINSPOOL!OpenPrinterW` at `0x1800878c7`
- `WINSPOOL!FindClosePrinterChangeNotification` at `0x1800879a9`
- `WINSPOOL!FindClosePrinterChangeNotification` at `0x180087b39`
- `WINSPOOL!FindClosePrinterChangeNotification` at `0x1800879a9`
- `WINSPOOL!FindClosePrinterChangeNotification` at `0x180087b39`

## string_xrefs

- `0x180087bbc`: `Error in printer queue enumeration thread: 0x%x.`
- `0x180087bc3`: `PrintConfig::CPrinterExtensionManager::GetPrinterQueuesThreadProc`

## pseudocode

```c

```
