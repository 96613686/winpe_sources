# WSManHttpSenderConnection::StatusHandleClosing(void *,InCritSecWithConditionVar *)

- ea: `0x1800af400`
- end: `0x1800afe65`
- name: `?StatusHandleClosing@WSManHttpSenderConnection@@AEAAXPEAXPEAVInCritSecWithConditionVar@@@Z`
- size: `2661`
- prototype: `void __fastcall(WSManHttpSenderConnection *__hidden this, void *, struct InCritSecWithConditionVar *)`
- caller_count: `1`
- callee_count: `17`
- tags: `service_task`

## callers

- `0x1800521b0`

## callees

- `0x180005d10`
- `0x180018878`
- `0x18002c580`
- `0x18002dd20`
- `0x18004a9b0`
- `0x180067150`
- `0x18006f9a0`
- `0x1800af400`
- `0x1800afe6c`
- `0x1800d4a1c`
- `0x180112380`
- `0x180112460`
- `0x18011a6d4`
- `0x1801297b8`
- `0x180133ff0`
- `0x180134540`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800af765`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800af792`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800af765`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800af792`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800af612`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800af612`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800af46f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800af46f`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800af5fb`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800af5fb`

## string_xrefs

- `0x1800af77f`: `onecore\admin\wmi\wmx\binaries\service\cwsmancriticalsection.cpp`

## pseudocode

```c

```
