# CDlpTask::ProgressHandlerAction(IDlpAction *,ulong,ulong *)

- ea: `0x180245018`
- end: `0x18024574e`
- name: `?ProgressHandlerAction@CDlpTask@@AEAAJPEAVIDlpAction@@KPEAK@Z`
- size: `1846`
- prototype: `__int64 __fastcall(CDlpTask *__hidden this, struct IDlpAction *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x180235db0`

## callees

- `0x1800059d0`
- `0x180039f90`
- `0x180077664`
- `0x180233cf0`
- `0x180245018`
- `0x180250378`
- `0x1802b1010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1802456f6`
- `OLEAUT32!__imp_SysFreeString` at `0x1802456f6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1802454df`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180245717`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1802454df`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180245717`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18024506d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1802454b3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18024506d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1802454b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180245489`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180245556`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1802456cb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180245489`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180245556`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1802456cb`

## string_xrefs

- `0x180245122`: `CDlpTask::ProgressHandlerAction`
- `0x180245447`: `ProgressHandlerAction FinalUpdate: 0x%X, 0x%I64X / 0x%I64X, 0x%I64X`

## pseudocode

```c

```
