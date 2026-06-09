# CDlpTask::ProgressHandlerAction(IDlpAction *,ulong,ulong *)

- ea: `0x1400452c8`
- end: `0x1400459cc`
- name: `?ProgressHandlerAction@CDlpTask@@AEAAJPEAVIDlpAction@@KPEAK@Z`
- size: `1796`
- prototype: `__int64 __fastcall(CDlpTask *__hidden this, struct IDlpAction *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x140036b00`

## callees

- `0x1400076c8`
- `0x1400135b8`
- `0x140034ab4`
- `0x140038e64`
- `0x1400452c8`
- `0x140050ad8`
- `0x140080d70`
- `0x140082010`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x14004570f`
- `KERNEL32!GetTickCount` at `0x1400457f1`
- `KERNEL32!GetTickCount` at `0x14004594a`
- `KERNEL32!GetTickCount` at `0x14004570f`
- `KERNEL32!GetTickCount` at `0x1400457f1`
- `KERNEL32!GetTickCount` at `0x14004594a`
- `KERNEL32!LeaveCriticalSection` at `0x140045995`
- `KERNEL32!LeaveCriticalSection` at `0x140045995`
- `KERNEL32!EnterCriticalSection` at `0x140045312`
- `KERNEL32!EnterCriticalSection` at `0x140045312`
- `OLEAUT32!__imp_SysFreeString` at `0x140045973`
- `OLEAUT32!__imp_SysFreeString` at `0x140045973`

## string_xrefs

- `0x1400453bf`: `CDlpTask::ProgressHandlerAction`
- `0x1400456cf`: `ProgressHandlerAction FinalUpdate: 0x%X, 0x%I64X / 0x%I64X, 0x%I64X`

## pseudocode

```c

```
