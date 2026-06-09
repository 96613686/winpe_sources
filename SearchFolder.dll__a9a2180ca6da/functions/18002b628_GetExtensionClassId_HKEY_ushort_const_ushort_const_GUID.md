# GetExtensionClassId(HKEY__ *,ushort const *,ushort const *,_GUID *)

- ea: `0x18002b628`
- end: `0x18002b6e4`
- name: `?GetExtensionClassId@@YAJPEAUHKEY__@@PEBG1PEAU_GUID@@@Z`
- size: `188`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, struct _GUID *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180036260`
- `0x1800368e8`

## callees

- `0x180006900`
- `0x18002b628`

## import_xrefs

- `SHCORE!__imp_GUIDFromStringW` at `0x18002b6b7`
- `SHCORE!__imp_GUIDFromStringW` at `0x18002b6b7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002b68b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002b68b`

## pseudocode

```c

```
