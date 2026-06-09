# CDlpTask::ResetTransferProgress(void)

- ea: `0x140047e40`
- end: `0x140048359`
- name: `?ResetTransferProgress@CDlpTask@@UEAAJXZ`
- size: `1305`
- prototype: `__int64 __fastcall(CDlpTask *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task`

## callees

- `0x1400076c8`
- `0x1400135b8`
- `0x14002baa0`
- `0x14002db30`
- `0x140034ab4`
- `0x140047754`
- `0x140047e40`
- `0x14004c214`
- `0x140082010`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x1400482ca`
- `KERNEL32!GetTickCount` at `0x1400482ca`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140048195`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140048195`
- `KERNEL32!LeaveCriticalSection` at `0x140048333`
- `KERNEL32!LeaveCriticalSection` at `0x140048333`
- `KERNEL32!EnterCriticalSection` at `0x140047e68`
- `KERNEL32!EnterCriticalSection` at `0x140047e68`

## string_xrefs

- `0x140047f09`: `CDlpTask::ResetTransferProgress`
- `0x140048112`: `DlpTask: Resetting transport progress start time.`

## pseudocode

```c

```
