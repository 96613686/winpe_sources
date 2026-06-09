# CDlpTask::NotifyActionStateChanged(int *)

- ea: `0x140043b2c`
- end: `0x140043cf1`
- name: `?NotifyActionStateChanged@CDlpTask@@AEAAJPEAH@Z`
- size: `453`
- prototype: `__int64 __fastcall(CDlpTask *__hidden this, int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x140037a80`
- `0x1400477d0`

## callees

- `0x1400076c8`
- `0x1400135b8`
- `0x140034ab4`
- `0x140043b2c`
- `0x140082010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x140043b7d`
- `KERNEL32!SetEvent` at `0x140043b7d`
- `KERNEL32!GetLastError` at `0x140043b91`
- `KERNEL32!GetLastError` at `0x140043b91`
- `KERNEL32!WaitForSingleObject` at `0x140043cb8`
- `KERNEL32!WaitForSingleObject` at `0x140043cb8`
- `KERNEL32!WaitForMultipleObjects` at `0x140043c47`
- `KERNEL32!WaitForMultipleObjects` at `0x140043c47`

## string_xrefs

- `0x140043c03`: `CDlpTask::NotifyActionStateChanged`

## pseudocode

```c

```
