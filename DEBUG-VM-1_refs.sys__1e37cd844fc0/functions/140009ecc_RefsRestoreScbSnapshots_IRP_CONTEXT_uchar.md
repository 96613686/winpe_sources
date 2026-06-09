# RefsRestoreScbSnapshots(_IRP_CONTEXT *,uchar)

- ea: `0x140009ecc`
- end: `0x14000a2e0`
- name: `?RefsRestoreScbSnapshots@@YAXPEAU_IRP_CONTEXT@@E@Z`
- size: `1044`
- prototype: `void __fastcall(struct _IRP_CONTEXT *, unsigned __int8)`
- caller_count: `18`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x14000b1b0`
- `0x140036e90`
- `0x1400e9e48`
- `0x1400f3d34`
- `0x1400f5a90`
- `0x140293158`
- `0x14029764c`
- `0x14029ddd4`
- `0x1402a2e00`
- `0x1402ae30c`
- `0x1402c3664`
- `0x1402d802c`
- `0x140314690`
- `0x140324914`
- `0x140328fd0`
- `0x140334b60`
- `0x1403366e0`
- `0x14033e290`

## callees

- `0x140008640`
- `0x140009ecc`

## import_xrefs

- `ntoskrnl!KeEnterGuardedRegion` at `0x14000a0d5`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14000a0d5`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14000a0e4`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14000a0e4`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x14000a086`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x14000a086`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1401f49fe`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1401f49fe`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000a182`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000a182`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14000a18e`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14000a18e`
- `ntoskrnl!CcSetFileSizesEx` at `0x14000a203`
- `ntoskrnl!CcSetFileSizesEx` at `0x14000a203`

## pseudocode

```c

```
