# CommonBuffer_ReleaseCommonBufferFromPhysicalAddress

- ea: `0x140040290`
- end: `0x1400402e2`
- name: `CommonBuffer_ReleaseCommonBufferFromPhysicalAddress`
- size: `82`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140005a6c`

## callees

- `0x140040290`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400402cf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400402cf`
- `ntoskrnl!IoFreeMdl` at `0x1400402bb`
- `ntoskrnl!IoFreeMdl` at `0x1400402bb`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400402ab`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400402ab`

## pseudocode

```c

```
