# CWSStream::ProcessReadCompletion(void)

- ea: `0x18010f3f4`
- end: `0x18010f596`
- name: `?ProcessReadCompletion@CWSStream@@AEAA_NXZ`
- size: `418`
- prototype: `bool __fastcall(CWSStream *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18010f964`

## callees

- `0x180002550`
- `0x180019a80`
- `0x180019ab0`
- `0x18010f3f4`
- `0x18010fa20`
- `0x18010fa68`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18010f426`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18010f426`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18010f482`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18010f520`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18010f482`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18010f520`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x18010f4ff`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x18010f4ff`

## string_xrefs

- `0x18010f455`: `No read buffer available in ReportReadCompletion. Ignoring the event.`

## pseudocode

```c

```
