# CFolderItemCache::GetSyncHandler(ushort const *,ISyncClientHandler * *)

- ea: `0x180049750`
- end: `0x18004980f`
- name: `?GetSyncHandler@CFolderItemCache@@UEAAJPEBGPEAPEAUISyncClientHandler@@@Z`
- size: `191`
- prototype: `__int64 __fastcall(CFolderItemCache *__hidden this, const unsigned __int16 *, struct ISyncClientHandler **)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180049750`
- `0x18004ae70`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800497f4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800497f4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004979e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004979e`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18004978b`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18004978b`

## pseudocode

```c

```
