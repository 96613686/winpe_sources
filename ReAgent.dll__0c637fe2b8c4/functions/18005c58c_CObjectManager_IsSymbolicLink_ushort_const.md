# CObjectManager::IsSymbolicLink(ushort const *)

- ea: `0x18005c58c`
- end: `0x18005c636`
- name: `?IsSymbolicLink@CObjectManager@@SAHPEBG@Z`
- size: `170`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, loader_planting`

## callers

- `0x18005c360`

## callees

- `0x18005c58c`
- `0x18005cf30`

## import_xrefs

- `ntdll!NtOpenSymbolicLinkObject` at `0x18005c601`
- `ntdll!NtOpenSymbolicLinkObject` at `0x18005c601`
- `ntdll!RtlInitUnicodeString` at `0x18005c5c8`
- `ntdll!RtlInitUnicodeString` at `0x18005c5c8`
- `KERNEL32!CloseHandle` at `0x18005c619`
- `KERNEL32!CloseHandle` at `0x18005c619`

## pseudocode

```c

```
