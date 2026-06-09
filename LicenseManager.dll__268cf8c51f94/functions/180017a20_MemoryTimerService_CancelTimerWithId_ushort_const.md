# MemoryTimerService::CancelTimerWithId(ushort const *)

- ea: `0x180017a20`
- end: `0x180017cb6`
- name: `?CancelTimerWithId@MemoryTimerService@@UEAAJPEBG@Z`
- size: `662`
- prototype: `int(MemoryTimerService *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, service_task`

## callees

- `0x180013b50`
- `0x1800171b0`
- `0x180017200`
- `0x1800174bc`
- `0x180017a20`
- `0x180031790`
- `0x180054a54`
- `0x180075e60`
- `0x18008251f`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017a64`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017a64`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017c57`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017c57`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180017a9b`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180017a9b`

## string_xrefs

- `0x180017bff`: `Trying to remove timer %s not in table`
- `0x180017c0b`: `MemoryTimerService::CancelTimerWithId`

## pseudocode

```c

```
