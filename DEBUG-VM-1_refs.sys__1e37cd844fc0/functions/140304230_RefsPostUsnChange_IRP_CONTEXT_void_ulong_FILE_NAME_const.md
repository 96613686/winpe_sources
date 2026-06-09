# RefsPostUsnChange(_IRP_CONTEXT *,void *,ulong,_FILE_NAME const *)

- ea: `0x140304230`
- end: `0x140304a68`
- name: `?RefsPostUsnChange@@YAXPEAU_IRP_CONTEXT@@PEAXKPEBU_FILE_NAME@@@Z`
- size: `2104`
- prototype: `void __fastcall(struct _IRP_CONTEXT *, struct _FCB *, unsigned int, const struct _FILE_NAME *)`
- caller_count: `39`
- callee_count: `19`
- tags: ``

## callers

- `0x14009a77c`
- `0x1400a2c60`
- `0x1400ec8a4`
- `0x14010a028`
- `0x140111604`
- `0x1401141a8`
- `0x14028c4d4`
- `0x14028cd48`
- `0x140294fd8`
- `0x140295fb0`
- `0x1402986f0`
- `0x14029cd7c`
- `0x1402a3f80`
- `0x1402aa38c`
- `0x1402ab080`
- `0x1402ac480`
- `0x1402adbbc`
- `0x1402adf64`
- `0x1402ae30c`
- `0x1402c3664`
- `0x1402c7d04`
- `0x1402c8380`
- `0x1402d2d88`
- `0x1402d4318`
- `0x1402d7de8`
- `0x1402e7210`
- `0x1403025b0`
- `0x140305020`
- `0x1403058c0`
- `0x140319010`
- `0x140328fd0`
- `0x140329f4c`
- `0x14032d490`
- `0x14032dc90`
- `0x14032f6b0`
- `0x140332e30`
- `0x140334b60`
- `0x14033f3c0`
- `0x14033faf0`

## callees

- `0x140029a60`
- `0x140037820`
- `0x140047e80`
- `0x140071500`
- `0x140075ae0`
- `0x140089260`
- `0x14008b090`
- `0x1400914e0`
- `0x140093bc0`
- `0x14009c3f0`
- `0x1400bd9b0`
- `0x1401f3fc0`
- `0x1401f4100`
- `0x1401f4400`
- `0x140302e10`
- `0x140304230`
- `0x140304a70`
- `0x1403349ac`
- `0x140337814`

## import_xrefs

- `ntoskrnl!KeEnterGuardedRegion` at `0x140304361`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14030451e`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1403048b8`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140304361`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14030451e`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1403048b8`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140304371`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14030452e`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1403048cb`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140304371`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14030452e`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1403048cb`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140304455`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1403044b5`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1403047f0`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140304a4e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140341c1c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140304455`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1403044b5`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1403047f0`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140304a4e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140341c1c`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140304461`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1403044c1`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1403047fc`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140304a5a`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140341c28`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140304461`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1403044c1`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1403047fc`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140304a5a`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140341c28`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14030463a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140304918`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14030463a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140304918`

## pseudocode

```c

```
