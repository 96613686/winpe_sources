# DialQueue::Initialize(IDialQueueClient *)

- ea: `0x1800780cc`
- end: `0x1800781ac`
- name: `?Initialize@DialQueue@@QEAAJPEAUIDialQueueClient@@@Z`
- size: `224`
- prototype: `__int64 __fastcall(DialQueue *__hidden this, struct IDialQueueClient *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180036e90`

## callees

- `0x180006e94`
- `0x180070fcc`
- `0x180071ba8`
- `0x1800780cc`
- `0x1800781c0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800780ec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800780ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007814d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180078180`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007814d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180078180`

## string_xrefs

- `0x18007811e`: `onecoreuap\net\phone\phoneservice\service\lib\phoneline.cpp`
- `0x180078160`: `onecoreuap\net\phone\phoneservice\service\lib\dialexec.cpp`

## pseudocode

```c

```
