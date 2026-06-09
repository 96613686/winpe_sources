# SdbpGetFileTimestamp

- ea: `0x1801be7fc`
- end: `0x1801beaa4`
- name: `SdbpGetFileTimestamp`
- size: `680`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x1801b1444`
- `0x1801beec8`

## callees

- `0x180008570`
- `0x1800091d4`
- `0x1800092dc`
- `0x18001a2f4`
- `0x1801be7fc`
- `0x18021f010`

## import_xrefs

- `ntdll!ZwCreateFile` at `0x1801be9a5`
- `ntdll!ZwCreateFile` at `0x1801be9a5`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1801be8ac`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1801be8ac`
- `ntdll!ZwClose` at `0x1801bea56`
- `ntdll!ZwClose` at `0x1801bea56`
- `ntdll!RtlFreeHeap` at `0x1801bea78`
- `ntdll!RtlFreeHeap` at `0x1801bea78`
- `ntdll!RtlInitUnicodeString` at `0x1801be87f`
- `ntdll!RtlInitUnicodeString` at `0x1801be87f`
- `ntdll!NtQueryInformationFile` at `0x1801be9fc`
- `ntdll!NtQueryInformationFile` at `0x1801be9fc`
- `KERNEL32!GetModuleHandleW` at `0x1801be8f0`
- `KERNEL32!GetModuleHandleW` at `0x1801be8f0`
- `KERNEL32!GetProcAddress` at `0x1801be90f`
- `KERNEL32!GetProcAddress` at `0x1801be90f`

## string_xrefs

- `0x1801be8d1`: `ntdll.dll`
- `0x1801be9bc`: `Failed to open file [%x]`

## pseudocode

```c

```
