# SHGetMachineGUID(_GUID *,ushort *,uint)

- ea: `0x18002fb18`
- end: `0x18002fc79`
- name: `?SHGetMachineGUID@@YAJPEAU_GUID@@PEAGI@Z`
- size: `353`
- prototype: `__int64 __fastcall(struct _GUID *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180004ea0`

## callees

- `0x180006900`
- `0x18000ebd0`
- `0x18002fb18`
- `0x180030b00`
- `0x180030c84`

## import_xrefs

- `SHCORE!__imp_GUIDFromStringW` at `0x18002fc4d`
- `SHCORE!__imp_GUIDFromStringW` at `0x18002fc4d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002fc37`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002fc37`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002fb9e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002fb9e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002fc05`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002fc05`

## pseudocode

```c

```
