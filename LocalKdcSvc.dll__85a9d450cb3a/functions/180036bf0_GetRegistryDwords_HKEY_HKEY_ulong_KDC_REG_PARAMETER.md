# GetRegistryDwords(HKEY__ *,HKEY__ *,ulong,_KDC_REG_PARAMETER *)

- ea: `0x180036bf0`
- end: `0x180036d14`
- name: `?GetRegistryDwords@@YAXPEAUHKEY__@@0KPEAU_KDC_REG_PARAMETER@@@Z`
- size: `292`
- prototype: `void __fastcall(HKEY, HKEY, DWORD, struct _KDC_REG_PARAMETER *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180038244`

## callees

- `0x180036bf0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180036c7d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180036cb3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180036c7d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180036cb3`

## pseudocode

```c

```
