# DrvConvertDevMode

- ea: `0x18002ed80`
- end: `0x18002f022`
- name: `DrvConvertDevMode`
- size: `674`
- prototype: `BOOL __stdcall(LPTSTR pPrinterName, PDEVMODE pdmIn, PDEVMODE pdmOut, PLONG pcbNeeded, DWORD fMode)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config`

## callees

- `0x18000bdec`
- `0x1800183a0`
- `0x1800183f8`
- `0x18001d0fc`
- `0x18001e030`
- `0x18002e840`
- `0x18002ed80`
- `0x1801067bc`
- `0x18012e4a0`
- `0x180151610`
- `0x180152d24`
- `0x1801c3010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002f001`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002f00a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002f001`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002f00a`
- `KERNEL32!SetLastError` at `0x18002ee41`
- `KERNEL32!SetLastError` at `0x18002ee74`
- `KERNEL32!SetLastError` at `0x18002ee41`
- `KERNEL32!SetLastError` at `0x18002ee74`
- `WINSPOOL!ClosePrinter` at `0x18002efcf`
- `WINSPOOL!ClosePrinter` at `0x18002efcf`
- `WINSPOOL!OpenPrinterW` at `0x18002eebf`
- `WINSPOOL!OpenPrinterW` at `0x18002eebf`

## string_xrefs

- `0x18002ee5c`: `PrintConfig::DrvConvertDevmode threw error: 0x%x`

## pseudocode

```c

```
