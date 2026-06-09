# RtlCopyDataFromSourceBuffer

- ea: `0x140055250`
- end: `0x1400553c2`
- name: `RtlCopyDataFromSourceBuffer`
- size: `370`
- prototype: `__int64 __fastcall(char *Src, PMDL SourceMdl, unsigned __int64, char, __int64, PMDL TargetMdl, PVOID MappingAddress)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140047858`
- `0x140055168`

## callees

- `0x140051fb8`
- `0x140055250`
- `0x140077fd0`

## import_xrefs

- `ntoskrnl!IoBuildPartialMdl` at `0x1400552cf`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400552cf`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x1400552f1`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x1400552f1`
- `ntoskrnl!MmUnmapReservedMapping` at `0x14005532f`
- `ntoskrnl!MmUnmapReservedMapping` at `0x14005537e`
- `ntoskrnl!MmUnmapReservedMapping` at `0x14005532f`
- `ntoskrnl!MmUnmapReservedMapping` at `0x14005537e`
- `ntoskrnl!MmUnmapLockedPages` at `0x140055348`
- `ntoskrnl!MmUnmapLockedPages` at `0x140055397`
- `ntoskrnl!MmUnmapLockedPages` at `0x140055348`
- `ntoskrnl!MmUnmapLockedPages` at `0x140055397`

## pseudocode

```c

```
