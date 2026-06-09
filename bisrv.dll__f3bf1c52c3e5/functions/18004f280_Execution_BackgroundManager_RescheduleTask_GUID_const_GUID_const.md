# Execution::BackgroundManager::RescheduleTask(_GUID const *,_GUID const *)

- ea: `0x18004f280`
- end: `0x18004f37e`
- name: `?RescheduleTask@BackgroundManager@Execution@@UEAAJPEBU_GUID@@0@Z`
- size: `254`
- prototype: `int(Execution::BackgroundManager *__hidden this, const struct _GUID *, const struct _GUID *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18008bc10`
- `0x18008bc20`

## callees

- `0x18001ef7c`
- `0x180035398`
- `0x18004f280`
- `0x18006c78c`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f2c5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f2c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f2ef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f324`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f33d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f2ef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f324`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f33d`

## pseudocode

```c

```
