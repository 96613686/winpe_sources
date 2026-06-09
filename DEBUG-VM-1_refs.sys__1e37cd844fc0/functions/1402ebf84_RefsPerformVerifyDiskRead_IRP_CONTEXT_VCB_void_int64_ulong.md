# RefsPerformVerifyDiskRead(_IRP_CONTEXT *,_VCB *,void *,__int64,ulong)

- ea: `0x1402ebf84`
- end: `0x1402ec19d`
- name: `?RefsPerformVerifyDiskRead@@YAJPEAU_IRP_CONTEXT@@PEAU_VCB@@PEAX_JK@Z`
- size: `537`
- prototype: `int(struct _IRP_CONTEXT *, struct _VCB *, void *, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1402ec1a4`

## callees

- `0x1400862c0`
- `0x140088c00`
- `0x1400d0fd8`
- `0x1402ebf84`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x1402ec11b`
- `ntoskrnl!IoFreeIrp` at `0x140349cfc`
- `ntoskrnl!IoFreeIrp` at `0x1402ec11b`
- `ntoskrnl!IoFreeIrp` at `0x140349cfc`
- `ntoskrnl!IoFreeMdl` at `0x1402ec100`
- `ntoskrnl!IoFreeMdl` at `0x140349ce4`
- `ntoskrnl!IoFreeMdl` at `0x1402ec100`
- `ntoskrnl!IoFreeMdl` at `0x140349ce4`
- `ntoskrnl!MmUnlockPages` at `0x1402ec0f0`
- `ntoskrnl!MmUnlockPages` at `0x140349cd4`
- `ntoskrnl!MmUnlockPages` at `0x1402ec0f0`
- `ntoskrnl!MmUnlockPages` at `0x140349cd4`
- `ntoskrnl!IoBuildAsynchronousFsdRequest` at `0x1402ebfef`
- `ntoskrnl!IoBuildAsynchronousFsdRequest` at `0x1402ebfef`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402ec0d5`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402ec0d5`
- `ntoskrnl!KeInitializeEvent` at `0x1402ebfb9`
- `ntoskrnl!KeInitializeEvent` at `0x1402ebfb9`

## pseudocode

```c

```
