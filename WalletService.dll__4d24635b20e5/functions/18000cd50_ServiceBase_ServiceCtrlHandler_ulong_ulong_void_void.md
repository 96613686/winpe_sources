# ServiceBase::_ServiceCtrlHandler(ulong,ulong,void *,void *)

- ea: `0x18000cd50`
- end: `0x18000ce85`
- name: `?_ServiceCtrlHandler@ServiceBase@@CAKKKPEAX0@Z`
- size: `309`
- prototype: `__int64 __fastcall(__int64 dwControl, DWORD dwEventType, LPVOID lpEventData, char *lpContext)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x18000a7e0`

## callees

- `0x18000cd50`
- `0x18000d1e8`
- `0x18000d57c`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ce18`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ce6d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ce7b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ce18`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ce6d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ce7b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000ce5b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000ce5b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cd8c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cd8c`

## pseudocode

```c

```
