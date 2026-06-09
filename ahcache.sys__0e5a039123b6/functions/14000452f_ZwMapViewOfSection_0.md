# ZwMapViewOfSection_0

- ea: `0x14000452f`
- end: `0x140004536`
- name: `ZwMapViewOfSection_0`
- size: `7`
- prototype: `NTSTATUS __stdcall(HANDLE SectionHandle, HANDLE ProcessHandle, PVOID *BaseAddress, ULONG_PTR ZeroBits, SIZE_T CommitSize, PLARGE_INTEGER SectionOffset, PSIZE_T ViewSize, SECTION_INHERIT InheritDisposition, ULONG AllocationType, ULONG Win32Protect)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140006974`
- `0x140036b30`

## import_xrefs

- `ntoskrnl!ZwMapViewOfSection` at `0x14000452f`

## pseudocode

```c

```
