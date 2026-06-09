# CommonHeapReAllocDefault(void *,unsigned __int64,unsigned __int64,void * *)

- ea: `0x1800093d0`
- end: `0x180009432`
- name: `?CommonHeapReAllocDefault@@YAJPEAX_K1PEAPEAX@Z`
- size: `98`
- prototype: `__int64 __fastcall(PVOID Ptr, __int64, SIZE_T, void **)`
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007a30`
- `0x180008550`
- `0x180008db0`
- `0x180009040`
- `0x1800092c0`

## callees

- `0x1800093d0`

## import_xrefs

- `ntdll!RtlReAllocateHeap` at `0x180009414`
- `ntdll!RtlReAllocateHeap` at `0x180009414`
- `ntdll!RtlAllocateHeap` at `0x1800093f5`
- `ntdll!RtlAllocateHeap` at `0x1800093f5`

## pseudocode

```c

```
