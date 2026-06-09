# CDefenderHandler::Execute(ushort const *)

- ea: `0x14006d0a8`
- end: `0x14006d139`
- name: `?Execute@CDefenderHandler@@QEAAJPEBG@Z`
- size: `145`
- prototype: `__int64 __fastcall(CDefenderHandler *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140010ff4`

## callees

- `0x14006d0a8`
- `0x14007d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14006d0ce`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14006d0e8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14006d10a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14006d0ce`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14006d0e8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14006d10a`
- `ole32!CoUninitialize` at `0x14006d126`
- `ole32!CoUninitialize` at `0x14006d126`
- `ole32!CoInitialize` at `0x14006d0ba`
- `ole32!CoInitialize` at `0x14006d0ba`

## string_xrefs

- `0x14006d0de`: `SideBySideOn`
- `0x14006d100`: `SideBySideOff`

## pseudocode

```c

```
