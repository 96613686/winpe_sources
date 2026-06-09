# RegGetDword

- ea: `0x1800075ec`
- end: `0x1800076cc`
- name: `RegGetDword`
- size: `224`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180042324`
- `0x18004afc8`

## callees

- `0x1800075ec`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000762b`
- `KERNEL32!SetLastError` at `0x1800076b3`
- `KERNEL32!SetLastError` at `0x18000762b`
- `KERNEL32!SetLastError` at `0x1800076b3`
- `ADVAPI32!RegQueryValueExW` at `0x180007686`
- `ADVAPI32!RegQueryValueExW` at `0x180007686`
- `ADVAPI32!RegOpenKeyExW` at `0x18000764f`
- `ADVAPI32!RegOpenKeyExW` at `0x18000764f`
- `ADVAPI32!RegCloseKey` at `0x1800076ab`
- `ADVAPI32!RegCloseKey` at `0x1800076ab`

## pseudocode

```c

```
