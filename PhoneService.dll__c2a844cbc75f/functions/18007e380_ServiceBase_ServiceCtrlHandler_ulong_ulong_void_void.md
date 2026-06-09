# ServiceBase::_ServiceCtrlHandler(ulong,ulong,void *,void *)

- ea: `0x18007e380`
- end: `0x18007e4b5`
- name: `?_ServiceCtrlHandler@ServiceBase@@CAKKKPEAX0@Z`
- size: `309`
- prototype: `DWORD __stdcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x180007b20`

## callees

- `0x18007e380`
- `0x18007e730`
- `0x18007e9ac`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18007e48b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18007e48b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007e3bc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007e3bc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007e448`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007e49d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007e4ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007e448`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007e49d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007e4ab`

## pseudocode

```c

```
