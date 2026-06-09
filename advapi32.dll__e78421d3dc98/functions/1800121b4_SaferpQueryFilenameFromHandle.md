# SaferpQueryFilenameFromHandle

- ea: `0x1800121b4`
- end: `0x1800123d3`
- name: `SaferpQueryFilenameFromHandle`
- size: `543`
- prototype: `__int64 __fastcall(HANDLE FileHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180011eb4`

## callees

- `0x1800121b4`
- `0x18006504e`

## import_xrefs

- `ntdll!RtlDuplicateUnicodeString` at `0x180012337`
- `ntdll!RtlDuplicateUnicodeString` at `0x180012337`
- `ntdll!NtQueryInformationFile` at `0x180012227`
- `ntdll!NtQueryInformationFile` at `0x180012227`
- `ntdll!RtlFreeHeap` at `0x180012351`
- `ntdll!RtlFreeHeap` at `0x18001236e`
- `ntdll!RtlFreeHeap` at `0x180012351`
- `ntdll!RtlFreeHeap` at `0x18001236e`
- `ntdll!RtlAllocateHeap` at `0x1800121f7`
- `ntdll!RtlAllocateHeap` at `0x1800122f1`
- `ntdll!RtlAllocateHeap` at `0x1800121f7`
- `ntdll!RtlAllocateHeap` at `0x1800122f1`
- `ntdll!RtlInitUnicodeString` at `0x180012325`
- `ntdll!RtlInitUnicodeString` at `0x180012325`
- `KERNEL32!GetLongPathNameW` at `0x180012314`
- `KERNEL32!GetLongPathNameW` at `0x180012314`

## pseudocode

```c

```
