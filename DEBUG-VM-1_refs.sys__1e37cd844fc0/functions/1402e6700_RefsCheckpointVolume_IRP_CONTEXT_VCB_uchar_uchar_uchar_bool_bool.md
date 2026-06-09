# RefsCheckpointVolume(_IRP_CONTEXT *,_VCB *,uchar,uchar,uchar,bool *,bool *)

- ea: `0x1402e6700`
- end: `0x1402e6f34`
- name: `?RefsCheckpointVolume@@YAXPEAU_IRP_CONTEXT@@PEAU_VCB@@EEEPEA_N2@Z`
- size: `2100`
- prototype: `void __usercall(struct _IRP_CONTEXT *@<rcx>, struct _VCB *@<rdx>, unsigned __int8@<r8b>, unsigned __int8@<r9b>, char, bool *, bool *)`
- caller_count: `5`
- callee_count: `14`
- tags: ``

## callers

- `0x140293158`
- `0x14029d114`
- `0x1402c7908`
- `0x1402d802c`
- `0x14033a7a8`

## callees

- `0x140076ad0`
- `0x140085570`
- `0x1400862c0`
- `0x140089640`
- `0x1400962c0`
- `0x1400acbc8`
- `0x1400d0fd8`
- `0x1400d30e4`
- `0x14011a9e8`
- `0x14011b2cc`
- `0x1401f3fa4`
- `0x1401f3fc0`
- `0x1402e6700`
- `0x14031def0`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1402e6ecc`
- `ntoskrnl!KeSetEvent` at `0x14034949a`
- `ntoskrnl!KeSetEvent` at `0x1402e6ecc`
- `ntoskrnl!KeSetEvent` at `0x14034949a`
- `ntoskrnl!KeResetEvent` at `0x1402e6a1b`
- `ntoskrnl!KeResetEvent` at `0x1402e6a1b`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402e67a6`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402e6980`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402e6dc8`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402e6e9e`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14034946b`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402e67a6`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402e6980`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402e6dc8`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402e6e9e`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14034946b`
- `ntoskrnl!KeReadStateEvent` at `0x1402e69ac`
- `ntoskrnl!KeReadStateEvent` at `0x1402e69ac`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402e67b6`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402e6996`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402e6dde`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402e6eb4`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140349482`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402e67b6`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402e6996`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402e6dde`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402e6eb4`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140349482`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402e67dc`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402e69bf`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402e6a2a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402e6df4`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402e6edb`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1403494ad`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402e67dc`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402e69bf`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402e6a2a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402e6df4`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402e6edb`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1403494ad`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402e67e8`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402e69cb`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402e6a36`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402e6e00`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402e6ee7`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1403494b9`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402e67e8`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402e69cb`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402e6a36`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402e6e00`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402e6ee7`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1403494b9`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402e69fb`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402e6b08`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402e69fb`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402e6b08`
- `ntoskrnl!KeInitializeEvent` at `0x1402e6a54`
- `ntoskrnl!KeInitializeEvent` at `0x1402e6a54`

## pseudocode

```c

```
