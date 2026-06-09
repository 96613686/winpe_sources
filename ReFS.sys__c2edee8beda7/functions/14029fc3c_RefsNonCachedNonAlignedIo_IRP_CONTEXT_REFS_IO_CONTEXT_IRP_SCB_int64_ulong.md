# RefsNonCachedNonAlignedIo(_IRP_CONTEXT *,REFS_IO_CONTEXT *,_IRP *,_SCB *,__int64,ulong)

- ea: `0x14029fc3c`
- end: `0x1402a0309`
- name: `?RefsNonCachedNonAlignedIo@@YAXPEAU_IRP_CONTEXT@@PEAUREFS_IO_CONTEXT@@PEAU_IRP@@PEAU_SCB@@_JK@Z`
- size: `1741`
- prototype: `void __usercall(struct _IRP_CONTEXT *@<rcx>, struct REFS_IO_CONTEXT *@<rdx>, struct _IRP *@<r8>, struct _SCB *@<r9>, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x1400ba4d0`

## callees

- `0x14000cf40`
- `0x140011c60`
- `0x140076ad0`
- `0x1400862c0`
- `0x140090c50`
- `0x140099d90`
- `0x1400cea34`
- `0x1400d0fd8`
- `0x1400e6488`
- `0x1401f4100`
- `0x1401f4400`
- `0x14029fc3c`
- `0x14033e290`
- `0x14033f1d0`

## import_xrefs

- `ntoskrnl!IoBuildPartialMdl` at `0x1402a026e`
- `ntoskrnl!IoBuildPartialMdl` at `0x1402a026e`
- `ntoskrnl!IoAllocateMdl` at `0x1402a01da`
- `ntoskrnl!IoAllocateMdl` at `0x1402a01da`
- `ntoskrnl!IoFreeMdl` at `0x1402a02a8`
- `ntoskrnl!IoFreeMdl` at `0x140346b1f`
- `ntoskrnl!IoFreeMdl` at `0x1402a02a8`
- `ntoskrnl!IoFreeMdl` at `0x140346b1f`
- `ntoskrnl!KeFlushIoBuffers` at `0x1402a02e9`
- `ntoskrnl!KeFlushIoBuffers` at `0x140346b88`
- `ntoskrnl!KeFlushIoBuffers` at `0x1402a02e9`
- `ntoskrnl!KeFlushIoBuffers` at `0x140346b88`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a02c6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140346b5b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a02c6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140346b5b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14029fd57`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14029fd57`

## pseudocode

```c

```
