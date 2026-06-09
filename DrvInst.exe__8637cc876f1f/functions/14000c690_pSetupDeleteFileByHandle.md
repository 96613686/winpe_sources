# pSetupDeleteFileByHandle

- ea: `0x14000c690`
- end: `0x14000c798`
- name: `pSetupDeleteFileByHandle`
- size: `264`
- prototype: `__int64 __fastcall(HANDLE FileHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x14000dc64`

## callees

- `0x14000c690`
- `0x140045f30`

## import_xrefs

- `ntdll!NtSetInformationFile` at `0x14000c735`
- `ntdll!NtSetInformationFile` at `0x14000c754`
- `ntdll!NtSetInformationFile` at `0x14000c735`
- `ntdll!NtSetInformationFile` at `0x14000c754`
- `ntdll!NtQueryInformationFile` at `0x14000c6f6`
- `ntdll!NtQueryInformationFile` at `0x14000c6f6`
- `ntdll!RtlNtStatusToDosError` at `0x14000c760`
- `ntdll!RtlNtStatusToDosError` at `0x14000c760`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000c76a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000c76a`

## pseudocode

```c

```
