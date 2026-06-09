# RegGetDword

- ea: `0x180093d7c`
- end: `0x180093e52`
- name: `RegGetDword`
- size: `214`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000e338`
- `0x18007f3e0`

## callees

- `0x180093d7c`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180093db5`
- `KERNEL32!SetLastError` at `0x180093e41`
- `KERNEL32!SetLastError` at `0x180093db5`
- `KERNEL32!SetLastError` at `0x180093e41`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180093dd9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180093dd9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180093e14`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180093e14`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180093e39`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180093e39`

## pseudocode

```c

```
