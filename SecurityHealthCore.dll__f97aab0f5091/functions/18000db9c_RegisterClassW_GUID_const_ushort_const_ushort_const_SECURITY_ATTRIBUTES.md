# RegisterClassW(_GUID const &,ushort const *,ushort const *,_SECURITY_ATTRIBUTES *)

- ea: `0x18000db9c`
- end: `0x18000ddd4`
- name: `?RegisterClassW@@YAJAEBU_GUID@@PEBG1PEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `568`
- prototype: `int(const struct _GUID *, const unsigned __int16 *, const unsigned __int16 *, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000d384`

## callees

- `0x180004ae0`
- `0x18000d7fc`
- `0x18000db9c`
- `0x1800ce43c`
- `0x1800cee78`
- `0x1800dc038`
- `0x1800de258`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000dcf3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000dd9f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000dcf3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000dd9f`

## string_xrefs

- `0x18000dc1d`: `CLSID\%ls`

## pseudocode

```c

```
