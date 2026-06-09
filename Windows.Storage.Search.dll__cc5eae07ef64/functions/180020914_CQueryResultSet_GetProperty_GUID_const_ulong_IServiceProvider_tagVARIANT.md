# CQueryResultSet::_GetProperty(_GUID const &,ulong,IServiceProvider *,tagVARIANT *)

- ea: `0x180020914`
- end: `0x180020ae1`
- name: `?_GetProperty@CQueryResultSet@@AEAAJAEBU_GUID@@KPEAUIServiceProvider@@PEAUtagVARIANT@@@Z`
- size: `461`
- prototype: `int(CQueryResultSet *__hidden this, const struct _GUID *, unsigned int, struct IServiceProvider *, struct tagVARIANT *)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180020874`
- `0x1800a6e80`

## callees

- `0x18001db40`
- `0x18001e4c4`
- `0x180020914`
- `0x18004f914`
- `0x180063a68`
- `0x180071dc0`
- `0x1800ea010`

## import_xrefs

- `SHCORE!IUnknown_SetSite` at `0x1800209ca`
- `SHCORE!IUnknown_SetSite` at `0x180020a2a`
- `SHCORE!IUnknown_SetSite` at `0x1800209ca`
- `SHCORE!IUnknown_SetSite` at `0x180020a2a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020999`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020999`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020a5b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020a5b`
- `OLEAUT32!__imp_VariantCopy` at `0x180020a83`
- `OLEAUT32!__imp_VariantCopy` at `0x180020a83`

## pseudocode

```c

```
