# RefsUpdateFileDupInfo

- ea: `0x1403390a4`
- end: `0x14033939d`
- name: `RefsUpdateFileDupInfo`
- size: `761`
- prototype: `__int64 __fastcall(struct _IRP_CONTEXT *)`
- caller_count: `3`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x1402ab080`
- `0x14033f3c0`
- `0x14033faf0`

## callees

- `0x1400a2890`
- `0x1400a8498`
- `0x1400ebe74`
- `0x1400f52dc`
- `0x14028ead8`
- `0x140323140`
- `0x1403390a4`
- `0x1403393a4`

## import_xrefs

- `ntoskrnl!KeEnterGuardedRegion` at `0x1403391ab`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1403392c7`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140344cf2`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1403391ab`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1403392c7`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140344cf2`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1403391bb`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1403392d7`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140344d02`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1403391bb`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1403392d7`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140344d02`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14033921e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1403392fd`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140344d26`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14033921e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1403392fd`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140344d26`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14033922a`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140339309`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140344d32`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14033922a`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140339309`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140344d32`

## pseudocode

```c

```
