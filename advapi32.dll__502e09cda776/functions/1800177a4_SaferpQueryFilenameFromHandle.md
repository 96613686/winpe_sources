# SaferpQueryFilenameFromHandle

- ea: `0x1800177a4`
- end: `0x1800179f4`
- name: `SaferpQueryFilenameFromHandle`
- size: `592`
- prototype: `__int64 __fastcall(HANDLE FileHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180017460`

## callees

- `0x1800177a4`
- `0x18007204e`

## import_xrefs

- `ntdll!RtlDuplicateUnicodeString` at `0x180017945`
- `ntdll!RtlDuplicateUnicodeString` at `0x180017945`
- `ntdll!NtQueryInformationFile` at `0x18001781d`
- `ntdll!NtQueryInformationFile` at `0x18001781d`
- `ntdll!RtlFreeHeap` at `0x180017965`
- `ntdll!RtlFreeHeap` at `0x180017988`
- `ntdll!RtlFreeHeap` at `0x180017965`
- `ntdll!RtlFreeHeap` at `0x180017988`
- `ntdll!RtlAllocateHeap` at `0x1800177e7`
- `ntdll!RtlAllocateHeap` at `0x1800178ed`
- `ntdll!RtlAllocateHeap` at `0x1800177e7`
- `ntdll!RtlAllocateHeap` at `0x1800178ed`
- `ntdll!RtlInitUnicodeString` at `0x18001792d`
- `ntdll!RtlInitUnicodeString` at `0x18001792d`
- `KERNEL32!GetLongPathNameW` at `0x180017916`
- `KERNEL32!GetLongPathNameW` at `0x180017916`

## pseudocode

```c

```
