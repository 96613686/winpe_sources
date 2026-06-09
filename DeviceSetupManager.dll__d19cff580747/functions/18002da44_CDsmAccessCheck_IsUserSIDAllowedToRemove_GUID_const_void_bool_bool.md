# CDsmAccessCheck::_IsUserSIDAllowedToRemove(_GUID const &,void *,bool *,bool *)

- ea: `0x18002da44`
- end: `0x18002db94`
- name: `?_IsUserSIDAllowedToRemove@CDsmAccessCheck@@CAXAEBU_GUID@@PEAXPEA_N2@Z`
- size: `336`
- prototype: `static void(const struct _GUID *, void *, bool *, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18002d790`

## callees

- `0x18001af70`
- `0x18002d1bc`
- `0x18002da44`

## import_xrefs

- `api-ms-win-devices-query-l1-1-0!DevFreeObjects` at `0x18002db60`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjects` at `0x18002db60`
- `api-ms-win-devices-query-l1-1-0!DevGetObjects` at `0x18002db16`
- `api-ms-win-devices-query-l1-1-0!DevGetObjects` at `0x18002db16`

## pseudocode

```c

```
