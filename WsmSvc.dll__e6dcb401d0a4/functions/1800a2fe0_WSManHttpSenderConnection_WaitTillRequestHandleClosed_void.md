# WSManHttpSenderConnection::WaitTillRequestHandleClosed(void)

- ea: `0x1800a2fe0`
- end: `0x1800a3242`
- name: `?WaitTillRequestHandleClosed@WSManHttpSenderConnection@@QEAAXXZ`
- size: `610`
- prototype: `void __fastcall(WSManHttpSenderConnection *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800a2a20`

## callees

- `0x180005d10`
- `0x1800a2fe0`
- `0x1800a38d0`
- `0x180112460`
- `0x18011a6d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a30af`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a30e1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a3114`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a30af`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a30e1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a3114`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a3026`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a3026`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a3074`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a3074`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a3174`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a3174`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800a3060`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800a3060`

## string_xrefs

- `0x1800a30d0`: `onecore\admin\wmi\wmx\binaries\service\cwsmancriticalsection.cpp`
- `0x1800a3103`: `onecore\admin\wmi\wmx\binaries\service\cwsmancriticalsection.cpp`

## pseudocode

```c

```
