# RefsCreateInternalAttributeStream(_IRP_CONTEXT *,_SCB *,uchar,_UNICODE_STRING const *)

- ea: `0x140297340`
- end: `0x1402975ff`
- name: `?RefsCreateInternalAttributeStream@@YAXPEAU_IRP_CONTEXT@@PEAU_SCB@@EPEBU_UNICODE_STRING@@@Z`
- size: `703`
- prototype: `void __fastcall(struct _IRP_CONTEXT *, struct _SCB *, unsigned __int8, const struct _UNICODE_STRING *)`
- caller_count: `8`
- callee_count: `7`
- tags: ``

## callers

- `0x140295380`
- `0x140295fb0`
- `0x1402a9038`
- `0x1402e9454`
- `0x1403313bc`
- `0x14033e290`
- `0x14033f3c0`
- `0x14033faf0`

## callees

- `0x1400872e0`
- `0x14008bd10`
- `0x14009e300`
- `0x1400a9f50`
- `0x140297340`
- `0x140328f30`
- `0x14033afa0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1403458d3`
- `ntoskrnl!ObfDereferenceObject` at `0x1403458d3`
- `ntoskrnl!KeReleaseMutant` at `0x1402975d8`
- `ntoskrnl!KeReleaseMutant` at `0x140345911`
- `ntoskrnl!KeReleaseMutant` at `0x1402975d8`
- `ntoskrnl!KeReleaseMutant` at `0x140345911`
- `ntoskrnl!CcSetParallelFlushFile` at `0x14029759a`
- `ntoskrnl!CcSetParallelFlushFile` at `0x14029759a`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402974d4`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402974d4`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402974e3`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402974e3`
- `ntoskrnl!IoCreateStreamFileObjectLite` at `0x140297410`
- `ntoskrnl!IoCreateStreamFileObjectLite` at `0x140297410`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14029751f`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14029751f`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14029752b`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14029752b`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402973db`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402973db`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140297395`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140297395`

## pseudocode

```c

```
