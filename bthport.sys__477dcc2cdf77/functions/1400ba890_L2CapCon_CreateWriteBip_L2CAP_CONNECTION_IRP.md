# L2CapCon_CreateWriteBip(L2CAP_CONNECTION *,_IRP *)

- ea: `0x1400ba890`
- end: `0x1400baa03`
- name: `?L2CapCon_CreateWriteBip@@YAPEAU_L2CAP_WRITE_CONTEXT@@PEAUL2CAP_CONNECTION@@PEAU_IRP@@@Z`
- size: `371`
- prototype: `struct _L2CAP_WRITE_CONTEXT *__fastcall(struct L2CAP_CONNECTION *, struct _IRP *)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x1400bb72c`
- `0x1400bbae0`

## callees

- `0x1400205e0`
- `0x1400ba890`
- `0x1400baa0c`
- `0x1400bd984`
- `0x140161a44`
- `0x140161c78`
- `0x140161d7c`
- `0x140162008`

## import_xrefs

- `ntoskrnl!IoAllocateMdl` at `0x1400ba92b`
- `ntoskrnl!IoAllocateMdl` at `0x1400ba92b`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400ba97c`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400ba97c`
- `ntoskrnl!IoFreeMdl` at `0x1400ba9cc`
- `ntoskrnl!IoFreeMdl` at `0x1400ba9cc`

## pseudocode

```c

```
