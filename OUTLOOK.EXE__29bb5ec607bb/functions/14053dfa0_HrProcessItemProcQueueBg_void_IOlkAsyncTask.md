# HrProcessItemProcQueueBg(void *,IOlkAsyncTask *)

- ea: `0x14053dfa0`
- end: `0x14053e6c6`
- name: `?HrProcessItemProcQueueBg@@YAJPEAXPEAUIOlkAsyncTask@@@Z`
- size: `1830`
- prototype: `__int64 __fastcall(void *, struct IOlkAsyncTask *)`
- caller_count: `0`
- callee_count: `17`
- tags: `service_task`

## callees

- `0x14006bd54`
- `0x14006be68`
- `0x1400da630`
- `0x140171af0`
- `0x1401c43f4`
- `0x1402c2e28`
- `0x140503f00`
- `0x140539110`
- `0x140539210`
- `0x14053b0d0`
- `0x14053b178`
- `0x14053c010`
- `0x14053c5b0`
- `0x14053c604`
- `0x14053dfa0`
- `0x1407e99f0`
- `0x140d70e94`

## import_xrefs

- `KERNEL32!ResetEvent` at `0x14053e520`
- `KERNEL32!ResetEvent` at `0x14053e542`
- `KERNEL32!ResetEvent` at `0x14053e62f`
- `KERNEL32!ResetEvent` at `0x14053e520`
- `KERNEL32!ResetEvent` at `0x14053e542`
- `KERNEL32!ResetEvent` at `0x14053e62f`
- `KERNEL32!LeaveCriticalSection` at `0x14053e0ab`
- `KERNEL32!LeaveCriticalSection` at `0x14053e1ba`
- `KERNEL32!LeaveCriticalSection` at `0x14053e44a`
- `KERNEL32!LeaveCriticalSection` at `0x14053e6ad`
- `KERNEL32!LeaveCriticalSection` at `0x14053e0ab`
- `KERNEL32!LeaveCriticalSection` at `0x14053e1ba`
- `KERNEL32!LeaveCriticalSection` at `0x14053e44a`
- `KERNEL32!LeaveCriticalSection` at `0x14053e6ad`
- `OLMAPI32!EnterThrottleSupplier` at `0x14053dfe1`
- `OLMAPI32!EnterThrottleSupplier` at `0x14053dfe1`
- `OLMAPI32!EDPIsSessionLocked` at `0x14053e52b`
- `OLMAPI32!EDPIsSessionLocked` at `0x14053e52b`
- `OLMAPI32!LeaveThrottleSupplier` at `0x14053e0ee`
- `OLMAPI32!LeaveThrottleSupplier` at `0x14053e0ee`
- `OLMAPI32!UseBatSignalCriticalSections` at `0x14053e048`
- `OLMAPI32!UseBatSignalCriticalSections` at `0x14053e068`
- `OLMAPI32!UseBatSignalCriticalSections` at `0x14053e157`
- `OLMAPI32!UseBatSignalCriticalSections` at `0x14053e177`
- `OLMAPI32!UseBatSignalCriticalSections` at `0x14053e3aa`
- `OLMAPI32!UseBatSignalCriticalSections` at `0x14053e3ca`
- `OLMAPI32!UseBatSignalCriticalSections` at `0x14053e635`
- `OLMAPI32!UseBatSignalCriticalSections` at `0x14053e651`
- `OLMAPI32!UseBatSignalCriticalSections` at `0x14053e048`
- `OLMAPI32!UseBatSignalCriticalSections` at `0x14053e068`
- `OLMAPI32!UseBatSignalCriticalSections` at `0x14053e157`
- `OLMAPI32!UseBatSignalCriticalSections` at `0x14053e177`
- `OLMAPI32!UseBatSignalCriticalSections` at `0x14053e3aa`
- `OLMAPI32!UseBatSignalCriticalSections` at `0x14053e3ca`
- `OLMAPI32!UseBatSignalCriticalSections` at `0x14053e635`
- `OLMAPI32!UseBatSignalCriticalSections` at `0x14053e651`
- `OLMAPI32!EtwTraceErrorTag` at `0x14053e0e3`
- `OLMAPI32!EtwTraceErrorTag` at `0x14053e4ce`
- `OLMAPI32!EtwTraceErrorTag` at `0x14053e5ce`
- `OLMAPI32!EtwTraceErrorTag` at `0x14053e0e3`
- `OLMAPI32!EtwTraceErrorTag` at `0x14053e4ce`
- `OLMAPI32!EtwTraceErrorTag` at `0x14053e5ce`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x14053e315`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x14053e31f`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x14053e329`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x14053e333`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x14053e346`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x14053e350`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x14053e36f`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x14053e315`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x14053e31f`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x14053e329`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x14053e333`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x14053e346`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x14053e350`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x14053e36f`
- `Mso20Win32Client!__imp_MsoMsgWaitForMultipleObjects` at `0x14053e0cb`
- `Mso20Win32Client!__imp_MsoMsgWaitForMultipleObjects` at `0x14053e0cb`
- `Mso20Win32Client!__imp_?MsoFRemovePx@@YAHPEAXII@Z` at `0x14053e40b`
- `Mso20Win32Client!__imp_?MsoFRemovePx@@YAHPEAXII@Z` at `0x14053e40b`

## string_xrefs

- `0x14053e074`: `HrProcessItemProcQueueBg`
- `0x14053e18d`: `HrProcessItemProcQueueBg`
- `0x14053e3e0`: `HrProcessItemProcQueueBg`
- `0x14053e65d`: `HrProcessItemProcQueueBg`

## pseudocode

```c

```
