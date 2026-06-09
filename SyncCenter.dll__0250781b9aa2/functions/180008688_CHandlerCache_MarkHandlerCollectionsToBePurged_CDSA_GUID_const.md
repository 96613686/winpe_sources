# CHandlerCache::_MarkHandlerCollectionsToBePurged(CDSA<_GUID> const &)

- ea: `0x180008688`
- end: `0x1800087d3`
- name: `?_MarkHandlerCollectionsToBePurged@CHandlerCache@@AEAAXAEBV?$CDSA@U_GUID@@@@@Z`
- size: `331`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, struct _DSA **)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180002130`
- `0x180008398`

## callees

- `0x180008688`
- `0x180008abc`
- `0x180008c00`
- `0x18000b56c`
- `0x180015488`
- `0x180016220`
- `0x180051dd4`
- `0x180052950`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800087a7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800087a7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800086b3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800086b3`

## pseudocode

```c

```
