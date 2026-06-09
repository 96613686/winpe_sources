# WORK_QUEUE::Add(WorkerQueueItem *)

- ea: `0x18000296c`
- end: `0x1800029cf`
- name: `?Add@WORK_QUEUE@@QEAAHPEAVWorkerQueueItem@@@Z`
- size: `99`
- prototype: `int(WORK_QUEUE *__hidden this, struct WorkerQueueItem *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000240c`
- `0x180002834`

## callees

- `0x18000296c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800029b3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800029b3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002988`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002988`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x1800029a8`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x1800029a8`

## pseudocode

```c

```
