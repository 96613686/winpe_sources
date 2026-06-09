# Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionProcessFilter::GetAllTargetedProcessIds(void)

- ea: `0x1800110b4`
- end: `0x180011261`
- name: `?GetAllTargetedProcessIds@EtwCollectionProcessFilter@StandardCollector@DiagnosticsHub@Microsoft@@QEBA?AV?$vector@IV?$allocator@I@std@@@std@@XZ`
- size: `429`
- prototype: `_QWORD *__fastcall(RTL_SRWLOCK *, _QWORD *)`
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180013ea8`
- `0x18001e0d0`
- `0x180020ccc`
- `0x18002259c`

## callees

- `0x180009570`
- `0x180009e14`
- `0x1800110b4`
- `0x18001543c`
- `0x180049b50`

## import_xrefs

- `KERNEL32!ReleaseSRWLockShared` at `0x18001122d`
- `KERNEL32!ReleaseSRWLockShared` at `0x18001122d`
- `KERNEL32!AcquireSRWLockShared` at `0x1800110f7`
- `KERNEL32!AcquireSRWLockShared` at `0x1800110f7`

## pseudocode

```c

```
