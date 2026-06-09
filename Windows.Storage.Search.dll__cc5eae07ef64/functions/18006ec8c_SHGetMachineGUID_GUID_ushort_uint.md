# SHGetMachineGUID(_GUID *,ushort *,uint)

- ea: `0x18006ec8c`
- end: `0x18006eded`
- name: `?SHGetMachineGUID@@YAJPEAU_GUID@@PEAGI@Z`
- size: `353`
- prototype: `__int64 __fastcall(struct _GUID *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800882ec`

## callees

- `0x18003be0c`
- `0x180051448`
- `0x18006d4f4`
- `0x18006ec8c`
- `0x180071dc0`

## import_xrefs

- `SHCORE!__imp_GUIDFromStringW` at `0x18006edc1`
- `SHCORE!__imp_GUIDFromStringW` at `0x18006edc1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006edab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006edab`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006ed79`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006ed79`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006ed12`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006ed12`

## pseudocode

```c

```
