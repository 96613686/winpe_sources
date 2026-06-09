# FrameServer::s_ServiceHandler(ulong,ulong,void *,void *)

- ea: `0x1800094d0`
- end: `0x180009556`
- name: `?s_ServiceHandler@FrameServer@@KAKKKPEAX0@Z`
- size: `134`
- prototype: `DWORD __stdcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x180008ebc`
- `0x18000920c`
- `0x1800094d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009541`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009541`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800094e7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800094e7`

## pseudocode

```c

```
