# CHandlerCache::ReleaseAggregator(CSyncMgrID const &,ushort const * *,uint)

- ea: `0x180014c30`
- end: `0x180014cde`
- name: `?ReleaseAggregator@CHandlerCache@@QEAAJAEBVCSyncMgrID@@PEAPEBGI@Z`
- size: `174`
- prototype: `__int64 __fastcall(CHandlerCache *__hidden this, const struct CSyncMgrID *, const unsigned __int16 **, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800113c8`

## callees

- `0x180004a60`
- `0x180004f10`
- `0x1800074a4`
- `0x18000a064`
- `0x180014c30`
- `0x18001a344`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180014ca4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180014ca4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014c7e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014c7e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014c68`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014c68`

## pseudocode

```c

```
