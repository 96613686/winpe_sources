# RefsDefragFileInternal(_IRP_CONTEXT *,_IRP *,_SCB *,_CCB *,MOVE_FILE_DATA *)

- ea: `0x14029ddd4`
- end: `0x14029f889`
- name: `?RefsDefragFileInternal@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@PEAU_SCB@@PEAU_CCB@@PEAUMOVE_FILE_DATA@@@Z`
- size: `6837`
- prototype: `__int64 __usercall@<rax>(struct _IRP_CONTEXT *@<rcx>, PIRP Irp@<rdx>, struct _SCB *@<r8>, struct _CCB *@<r9>, struct MOVE_FILE_DATA *)`
- caller_count: `1`
- callee_count: `42`
- tags: ``

## callers

- `0x14029d7d0`

## callees

- `0x140009ecc`
- `0x140011c60`
- `0x1400298a0`
- `0x140037820`
- `0x140075ae0`
- `0x140075ff0`
- `0x140076060`
- `0x140076ad0`
- `0x140085570`
- `0x1400862c0`
- `0x140086690`
- `0x140088c00`
- `0x1400892a0`
- `0x140089680`
- `0x14008ad80`
- `0x140093bc0`
- `0x1400961f0`
- `0x140099d90`
- `0x14009e670`
- `0x1400a73b4`
- `0x1400aa590`
- `0x1400aa97c`
- `0x1400d0fd8`
- `0x1400d266c`
- `0x1400ebde0`
- `0x1401185a8`
- `0x140119238`
- `0x140119c20`
- `0x14011a32c`
- `0x1401f3fc0`
- `0x1401f4400`
- `0x14028debc`
- `0x14028e0ec`
- `0x140294f14`
- `0x14029d5e8`
- `0x14029ddd4`
- `0x140302e10`
- `0x140306290`
- `0x14031e740`
- `0x14032fac0`
- `0x140330b20`
- `0x14033439c`

## import_xrefs

- `ntoskrnl!IoAllocateMdl` at `0x14029e5c8`
- `ntoskrnl!IoAllocateMdl` at `0x14029e5c8`
- `ntoskrnl!IoFreeMdl` at `0x14029f588`
- `ntoskrnl!IoFreeMdl` at `0x140346784`
- `ntoskrnl!IoFreeMdl` at `0x14029f588`
- `ntoskrnl!IoFreeMdl` at `0x140346784`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14029e5eb`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14029e5eb`
- `ntoskrnl!KeWaitForSingleObject` at `0x14029e168`
- `ntoskrnl!KeWaitForSingleObject` at `0x14029e168`
- `ntoskrnl!KeInitializeEvent` at `0x14029e0a2`
- `ntoskrnl!KeInitializeEvent` at `0x14029e0a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14029e601`
- `ntoskrnl!ExFreePoolWithTag` at `0x14029f599`
- `ntoskrnl!ExFreePoolWithTag` at `0x14029f5f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140346795`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403467fd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14029e601`
- `ntoskrnl!ExFreePoolWithTag` at `0x14029f599`
- `ntoskrnl!ExFreePoolWithTag` at `0x14029f5f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140346795`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403467fd`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14029e081`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14029e595`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14029e081`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14029e595`

## pseudocode

```c

```
