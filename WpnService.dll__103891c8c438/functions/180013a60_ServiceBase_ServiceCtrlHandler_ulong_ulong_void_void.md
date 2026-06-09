# ServiceBase::_ServiceCtrlHandler(ulong,ulong,void *,void *)

- ea: `0x180013a60`
- end: `0x180013bd3`
- name: `?_ServiceCtrlHandler@ServiceBase@@CAKKKPEAX0@Z`
- size: `371`
- prototype: `__int64 __fastcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, char *lpContext)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x18002a3a0`

## callees

- `0x180013a60`
- `0x180015790`
- `0x1800201c8`
- `0x180025078`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013a91`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013a91`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013aad`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013ad8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013af8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013b10`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013aad`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013ad8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013af8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013b10`

## pseudocode

```c

```
