# BipCancellationTimerAllocateState(_BI_ACTIVATED_TASK_INSTANCE *,uchar,_BI_CANCEL_REASON_INTERNAL,uchar *,uchar *)

- ea: `0x1800109b8`
- end: `0x180010c53`
- name: `?BipCancellationTimerAllocateState@@YAJPEAU_BI_ACTIVATED_TASK_INSTANCE@@EW4_BI_CANCEL_REASON_INTERNAL@@PEAE2@Z`
- size: `667`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x18001079c`

## callees

- `0x1800109b8`
- `0x180010c5c`
- `0x18004a68c`
- `0x180095010`

## import_xrefs

- `ntdll!TpAllocTimer` at `0x180010bd2`
- `ntdll!TpAllocTimer` at `0x180010bd2`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800109fe`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180010a93`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180010ba2`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800109fe`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180010a93`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180010ba2`
- `ntdll!TpReleaseTimer` at `0x180010c48`
- `ntdll!TpReleaseTimer` at `0x180010c48`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180010a3f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180010b15`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180010b50`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180010bb0`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180010c23`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180010a3f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180010b15`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180010b50`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180010bb0`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180010c23`
- `ntdll!TpSetTimer` at `0x180010c01`
- `ntdll!TpSetTimer` at `0x180010c01`
- `ntdll!RtlWakeAddressAll` at `0x180010bb9`
- `ntdll!RtlWakeAddressAll` at `0x180010bb9`

## pseudocode

```c

```
