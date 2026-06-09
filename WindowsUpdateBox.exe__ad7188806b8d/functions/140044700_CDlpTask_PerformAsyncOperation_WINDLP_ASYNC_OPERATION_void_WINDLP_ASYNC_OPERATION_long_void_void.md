# CDlpTask::PerformAsyncOperation(WINDLP_ASYNC_OPERATION,void (*)(WINDLP_ASYNC_OPERATION,long,void *),void *)

- ea: `0x140044700`
- end: `0x140044bc5`
- name: `?PerformAsyncOperation@CDlpTask@@EEAAJW4WINDLP_ASYNC_OPERATION@@P6AX0JPEAX@Z1@Z`
- size: `1221`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x1400076c8`
- `0x1400135b8`
- `0x14002be38`
- `0x14002db30`
- `0x140034ab4`
- `0x140044700`
- `0x140082010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140044b98`
- `KERNEL32!HeapFree` at `0x140044b98`
- `KERNEL32!HeapAlloc` at `0x140044895`
- `KERNEL32!HeapAlloc` at `0x140044895`
- `KERNEL32!GetProcessHeap` at `0x140044880`
- `KERNEL32!GetProcessHeap` at `0x140044b84`
- `KERNEL32!GetProcessHeap` at `0x140044880`
- `KERNEL32!GetProcessHeap` at `0x140044b84`
- `KERNEL32!SetEvent` at `0x140044941`
- `KERNEL32!SetEvent` at `0x140044a49`
- `KERNEL32!SetEvent` at `0x140044941`
- `KERNEL32!SetEvent` at `0x140044a49`
- `KERNEL32!GetLastError` at `0x140044955`
- `KERNEL32!GetLastError` at `0x140044a5d`
- `KERNEL32!GetLastError` at `0x140044955`
- `KERNEL32!GetLastError` at `0x140044a5d`
- `KERNEL32!LeaveCriticalSection` at `0x140044b66`
- `KERNEL32!LeaveCriticalSection` at `0x140044b66`
- `KERNEL32!EnterCriticalSection` at `0x140044740`
- `KERNEL32!EnterCriticalSection` at `0x140044740`

## string_xrefs

- `0x140044b26`: `CDlpTask::PerformAsyncOperation`

## pseudocode

```c

```
