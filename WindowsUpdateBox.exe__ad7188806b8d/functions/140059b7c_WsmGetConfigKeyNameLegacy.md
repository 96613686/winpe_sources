# WsmGetConfigKeyNameLegacy

- ea: `0x140059b7c`
- end: `0x140059c89`
- name: `WsmGetConfigKeyNameLegacy`
- size: `269`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x14005aa68`

## callees

- `0x140027438`
- `0x140055d10`
- `0x140059b7c`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140059c6a`
- `KERNEL32!HeapFree` at `0x140059c6a`
- `KERNEL32!GetProcessHeap` at `0x140059c56`
- `KERNEL32!GetProcessHeap` at `0x140059c56`
- `KERNEL32!GetLastError` at `0x140059bb4`
- `KERNEL32!GetLastError` at `0x140059bb4`
- `WDSCORE!WdsSetupLogMessageW` at `0x140059c2e`
- `WDSCORE!WdsSetupLogMessageW` at `0x140059c2e`
- `WDSCORE!CurrentIP` at `0x140059bc2`
- `WDSCORE!CurrentIP` at `0x140059bc2`

## string_xrefs

- `0x140059bed`: `WsmGetConfigKeyNameLegacy`
- `0x140059bd1`: `WsmGetConfigKeyNameLegacy: Failed to allocate config key path; hr = 0x%x`

## pseudocode

```c

```
