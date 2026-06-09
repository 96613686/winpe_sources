# CRegistryInfo::SafeReadClsidValue(RegKey *,ushort const *,_GUID *)

- ea: `0x1800645ec`
- end: `0x18006466d`
- name: `?SafeReadClsidValue@CRegistryInfo@@IEAAJPEAVRegKey@@PEBGPEAU_GUID@@@Z`
- size: `129`
- prototype: `int(CRegistryInfo *__hidden this, struct RegKey *, const unsigned __int16 *, struct _GUID *)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180063b30`
- `0x180064680`
- `0x1800d1590`

## callees

- `0x1800645ec`
- `0x1800647b8`
- `0x1800bd9d4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180064641`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180064641`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180064622`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180064622`

## pseudocode

```c

```
