# CHandlerCache::GetEventEnumerator(CSyncMgrID const &,IEnumSyncMgrEventInfo * *,ulong *)

- ea: `0x180013db4`
- end: `0x180013ecd`
- name: `?GetEventEnumerator@CHandlerCache@@QEAAJAEBVCSyncMgrID@@PEAPEAUIEnumSyncMgrEventInfo@@PEAK@Z`
- size: `281`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, const struct CSyncMgrID *, struct IEnumSyncMgrEventInfo **, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18001f960`

## callees

- `0x180008a90`
- `0x18000977c`
- `0x18000a5e4`
- `0x1800107d0`
- `0x18001082c`
- `0x1800133c4`
- `0x180013db4`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013eb8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013eb8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013dd2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013dd2`

## pseudocode

```c

```
