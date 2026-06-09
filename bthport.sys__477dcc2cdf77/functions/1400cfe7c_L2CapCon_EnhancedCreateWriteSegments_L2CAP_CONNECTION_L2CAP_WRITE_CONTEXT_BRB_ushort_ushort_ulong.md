# L2CapCon_EnhancedCreateWriteSegments(L2CAP_CONNECTION *,_L2CAP_WRITE_CONTEXT *,_BRB *,ushort,ushort,ulong)

- ea: `0x1400cfe7c`
- end: `0x1400d0040`
- name: `?L2CapCon_EnhancedCreateWriteSegments@@YAJPEAUL2CAP_CONNECTION@@PEAU_L2CAP_WRITE_CONTEXT@@PEAU_BRB@@GGK@Z`
- size: `452`
- prototype: `__int64 __usercall@<rax>(struct L2CAP_CONNECTION *@<rcx>, struct _L2CAP_WRITE_CONTEXT *@<rdx>, struct _BRB *@<r8>, unsigned __int16@<r9w>, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400cf9a0`

## callees

- `0x1400b446c`
- `0x1400cfe7c`
- `0x1400d007c`
- `0x140162d7c`

## import_xrefs

- `ntoskrnl!IoAllocateMdl` at `0x1400cff3f`
- `ntoskrnl!IoAllocateMdl` at `0x1400cff3f`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400cff98`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400cff98`
- `ntoskrnl!IoFreeMdl` at `0x1400cff66`
- `ntoskrnl!IoFreeMdl` at `0x1400cff66`

## pseudocode

```c

```
