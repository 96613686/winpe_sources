# CRemoteOperation::DeleteChannel(InCritSecWithConditionVar *)

- ea: `0x180051a7c`
- end: `0x180051d0d`
- name: `?DeleteChannel@CRemoteOperation@@IEAAXPEAVInCritSecWithConditionVar@@@Z`
- size: `657`
- prototype: `void __fastcall(CRemoteOperation *__hidden this, struct InCritSecWithConditionVar *)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x18005163c`
- `0x1800d6dd0`

## callees

- `0x180005d10`
- `0x18002a994`
- `0x180051a7c`
- `0x1800a38d0`
- `0x18011349c`
- `0x180123604`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180051b65`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180051b92`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180051b65`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180051b92`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180051b2f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180051b2f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180051c29`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180051c29`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180051b1c`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180051b1c`

## string_xrefs

- `0x180051b82`: `onecore\admin\wmi\wmx\binaries\service\cwsmancriticalsection.cpp`

## pseudocode

```c

```
