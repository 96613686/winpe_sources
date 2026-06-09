# ServiceBase::_ServiceCtrlHandler(ulong,ulong,void *,void *)

- ea: `0x1800208b0`
- end: `0x1800209e5`
- name: `?_ServiceCtrlHandler@ServiceBase@@CAKKKPEAX0@Z`
- size: `309`
- prototype: `__int64 __fastcall(__int64 dwControl, DWORD dwEventType, LPVOID lpEventData, char *lpContext)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x1800088b0`

## callees

- `0x1800208b0`
- `0x180020d48`
- `0x180020f2c`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800208ec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800208ec`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800209bb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800209bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020978`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800209cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800209db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020978`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800209cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800209db`

## pseudocode

```c

```
