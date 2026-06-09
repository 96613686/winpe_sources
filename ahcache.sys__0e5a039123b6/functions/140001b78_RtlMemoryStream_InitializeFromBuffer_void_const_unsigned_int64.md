# RtlMemoryStream::InitializeFromBuffer(void * const,unsigned __int64)

- ea: `0x140001b78`
- end: `0x140001c95`
- name: `?InitializeFromBuffer@RtlMemoryStream@@QEAAJQEAX_K@Z`
- size: `285`
- prototype: `__int64 __fastcall(RtlMemoryStream *this, void *const, size_t)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x140028850`
- `0x1400440d8`
- `0x14004545c`
- `0x140046908`
- `0x14004c3a0`
- `0x1400576e8`

## callees

- `0x140001b78`
- `0x140007b40`
- `0x140007e40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140001b9e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001b9e`
- `ntoskrnl!KeGetCurrentIrql` at `0x140001bf5`
- `ntoskrnl!KeGetCurrentIrql` at `0x140001bf5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140001c16`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140001c16`

## pseudocode

```c

```
