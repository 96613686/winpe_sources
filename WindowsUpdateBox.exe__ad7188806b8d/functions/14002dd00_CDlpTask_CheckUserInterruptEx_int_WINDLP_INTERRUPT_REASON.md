# CDlpTask::CheckUserInterruptEx(int,WINDLP_INTERRUPT_REASON *)

- ea: `0x14002dd00`
- end: `0x14002df35`
- name: `?CheckUserInterruptEx@CDlpTask@@AEAAJHPEAW4WINDLP_INTERRUPT_REASON@@@Z`
- size: `565`
- prototype: `__int64 __fastcall(CDlpTask *__hidden this, int, enum WINDLP_INTERRUPT_REASON *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x14002dc58`

## callees

- `0x1400076c8`
- `0x1400135b8`
- `0x14002dd00`
- `0x140034ab4`
- `0x140038e64`
- `0x140082010`

## import_xrefs

- `KERNEL32!Sleep` at `0x14002ddf4`
- `KERNEL32!Sleep` at `0x14002ddf4`
- `KERNEL32!LeaveCriticalSection` at `0x14002dddb`
- `KERNEL32!LeaveCriticalSection` at `0x14002df0c`
- `KERNEL32!LeaveCriticalSection` at `0x14002dddb`
- `KERNEL32!LeaveCriticalSection` at `0x14002df0c`
- `KERNEL32!EnterCriticalSection` at `0x14002dd28`
- `KERNEL32!EnterCriticalSection` at `0x14002de03`
- `KERNEL32!EnterCriticalSection` at `0x14002dd28`
- `KERNEL32!EnterCriticalSection` at `0x14002de03`

## string_xrefs

- `0x14002dec6`: `CDlpTask::CheckUserInterruptEx`

## pseudocode

```c

```
