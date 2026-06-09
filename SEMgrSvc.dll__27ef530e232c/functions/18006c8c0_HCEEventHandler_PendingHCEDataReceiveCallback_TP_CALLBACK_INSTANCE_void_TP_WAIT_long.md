# HCEEventHandler::PendingHCEDataReceiveCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x18006c8c0`
- end: `0x18006c9dc`
- name: `?PendingHCEDataReceiveCallback@HCEEventHandler@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `284`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180001008`
- `0x18006c28c`
- `0x18006c8c0`
- `0x18006ce44`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006c93b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006c9c1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006c93b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006c9c1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006c8ee`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006c8ee`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18006c9a7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18006c9a7`

## pseudocode

```c

```
