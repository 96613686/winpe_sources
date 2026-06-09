# RefsWriteBytes(_IRP_CONTEXT *,_VCB *,_SCB *,__int64,void *,ulong,ulong)

- ea: `0x1402a0b10`
- end: `0x1402a1282`
- name: `?RefsWriteBytes@@YAXPEAU_IRP_CONTEXT@@PEAU_VCB@@PEAU_SCB@@_JPEAXKK@Z`
- size: `1906`
- prototype: `void __usercall(struct _IRP_CONTEXT *@<rcx>, struct _VCB *@<rdx>, struct _SCB *@<r8>, __int64@<r9>, void *, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `12`
- tags: ``

## callers

- `0x140036e90`
- `0x1400f3d34`

## callees

- `0x140076ad0`
- `0x1400862c0`
- `0x1400892a0`
- `0x1400a73b4`
- `0x1400d0fd8`
- `0x1400d329c`
- `0x1400e8ed8`
- `0x1400f49c0`
- `0x1401f3fc0`
- `0x1401f4400`
- `0x1402a0b10`
- `0x14033e290`

## import_xrefs

- `ntoskrnl!MmUnmapLockedPages` at `0x1402a1230`
- `ntoskrnl!MmUnmapLockedPages` at `0x140346d06`
- `ntoskrnl!MmUnmapLockedPages` at `0x1402a1230`
- `ntoskrnl!MmUnmapLockedPages` at `0x140346d06`
- `ntoskrnl!IoAllocateMdl` at `0x1402a0e6c`
- `ntoskrnl!IoAllocateMdl` at `0x1402a0e6c`
- `ntoskrnl!MmProbeAndLockPages` at `0x1402a0f1e`
- `ntoskrnl!MmProbeAndLockPages` at `0x1402a0f1e`
- `ntoskrnl!IoFreeMdl` at `0x1402a0f47`
- `ntoskrnl!IoFreeMdl` at `0x1402a1197`
- `ntoskrnl!IoFreeMdl` at `0x1402a11f8`
- `ntoskrnl!IoFreeMdl` at `0x1402a123f`
- `ntoskrnl!IoFreeMdl` at `0x140346cc8`
- `ntoskrnl!IoFreeMdl` at `0x140346d16`
- `ntoskrnl!IoFreeMdl` at `0x1402a0f47`
- `ntoskrnl!IoFreeMdl` at `0x1402a1197`
- `ntoskrnl!IoFreeMdl` at `0x1402a11f8`
- `ntoskrnl!IoFreeMdl` at `0x1402a123f`
- `ntoskrnl!IoFreeMdl` at `0x140346cc8`
- `ntoskrnl!IoFreeMdl` at `0x140346d16`
- `ntoskrnl!MmUnlockPages` at `0x1402a117f`
- `ntoskrnl!MmUnlockPages` at `0x1402a11e8`
- `ntoskrnl!MmUnlockPages` at `0x140346cb7`
- `ntoskrnl!MmUnlockPages` at `0x1402a117f`
- `ntoskrnl!MmUnlockPages` at `0x1402a11e8`
- `ntoskrnl!MmUnlockPages` at `0x140346cb7`
- `ntoskrnl!MmMdlPageContentsState` at `0x1402a0e0d`
- `ntoskrnl!MmMdlPageContentsState` at `0x1402a0e0d`
- `ntoskrnl!IoBuildAsynchronousFsdRequest` at `0x1402a0cd3`
- `ntoskrnl!IoBuildAsynchronousFsdRequest` at `0x1402a0cd3`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1402a0f77`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1402a0fb7`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1402a0fe6`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1402a0f77`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1402a0fb7`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1402a0fe6`

## pseudocode

```c

```
