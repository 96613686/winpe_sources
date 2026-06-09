# CRegistryInfo::SafeReadClsidValue(RegKey *,ushort const *,_GUID *)

- ea: `0x18008fddc`
- end: `0x18008fe50`
- name: `?SafeReadClsidValue@CRegistryInfo@@IEAAJPEAVRegKey@@PEBGPEAU_GUID@@@Z`
- size: `116`
- prototype: `int(CRegistryInfo *__hidden this, struct RegKey *, const unsigned __int16 *, struct _GUID *)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18008f440`
- `0x18008fe60`
- `0x1800ced40`

## callees

- `0x18008fddc`
- `0x18008ff8c`
- `0x1800bb784`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008fe2b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008fe2b`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18008fe12`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18008fe12`

## pseudocode

```c

```
