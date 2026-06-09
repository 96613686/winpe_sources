# CDlpTask::InternalSetError(long)

- ea: `0x1400434a4`
- end: `0x140043b25`
- name: `?InternalSetError@CDlpTask@@AEAAJJ@Z`
- size: `1665`
- prototype: `__int64 __fastcall(CDlpTask *__hidden this, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x1400332b0`
- `0x1400356d0`

## callees

- `0x1400076c8`
- `0x1400135b8`
- `0x14002db30`
- `0x140034ab4`
- `0x140038e64`
- `0x14003b248`
- `0x1400434a4`
- `0x14004cbe4`
- `0x140082010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1400435fc`
- `KERNEL32!LeaveCriticalSection` at `0x1400435fc`
- `KERNEL32!EnterCriticalSection` at `0x1400435d4`
- `KERNEL32!EnterCriticalSection` at `0x1400435d4`
- `OLEAUT32!__imp_SysFreeString` at `0x140043acc`
- `OLEAUT32!__imp_SysFreeString` at `0x140043acc`

## string_xrefs

- `0x140043591`: `CDlpTask::InternalSetError`
- `0x140043aa6`: `Task error [0x%X] is being set while task is not in Error state.`

## pseudocode

```c

```
