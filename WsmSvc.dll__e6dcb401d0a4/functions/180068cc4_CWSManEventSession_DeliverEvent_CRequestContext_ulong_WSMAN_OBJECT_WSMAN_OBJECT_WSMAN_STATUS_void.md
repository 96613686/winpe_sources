# CWSManEventSession::DeliverEvent(CRequestContext *,ulong,WSMAN_OBJECT *,WSMAN_OBJECT *,_WSMAN_STATUS *,void *)

- ea: `0x180068cc4`
- end: `0x1800692c6`
- name: `?DeliverEvent@CWSManEventSession@@QEAAHPEAVCRequestContext@@KPEAUWSMAN_OBJECT@@1PEAU_WSMAN_STATUS@@PEAX@Z`
- size: `1538`
- prototype: `__int64(PVOID Context, struct CRequestContext *, unsigned int, struct WSMAN_OBJECT *, HANDLE hEvent, struct _WSMAN_STATUS *, void *)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task`

## callers

- `0x180068b60`

## callees

- `0x180005d10`
- `0x1800567e0`
- `0x180068cc4`
- `0x1800692cc`
- `0x1801005f0`
- `0x1801123a8`
- `0x180112460`
- `0x18011349c`
- `0x18011a6d4`
- `0x180121064`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180068ebe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180068eed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180068ef8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180068ebe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180068eed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180068ef8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069182`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069182`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x180069160`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x180069160`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180068d6e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180068d6e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800691ff`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800691ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180068dd5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180068eb3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180068dd5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180068eb3`

## string_xrefs

- `0x180068edc`: `onecore\admin\wmi\wmx\binaries\service\cwsmancriticalsection.cpp`

## pseudocode

```c

```
