# CHandlerCache::GetHandlerEnumerator(IEnumSyncMgrFolderItemInfo * *,ulong *)

- ea: `0x180013ed4`
- end: `0x180013faf`
- name: `?GetHandlerEnumerator@CHandlerCache@@QEAAJPEAPEAUIEnumSyncMgrFolderItemInfo@@PEAK@Z`
- size: `219`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, struct IEnumSyncMgrFolderItemInfo **, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18001fad0`

## callees

- `0x180008a90`
- `0x18000977c`
- `0x18000a5e4`
- `0x1800107d0`
- `0x18001082c`
- `0x180013ed4`
- `0x180015d3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013f94`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013f94`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013f07`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013f07`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180013efe`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180013efe`

## pseudocode

```c

```
