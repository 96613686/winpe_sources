# BaseRegRestoreKeyInternal

- ea: `0x180183c40`
- end: `0x180183e3d`
- name: `BaseRegRestoreKeyInternal`
- size: `509`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path, registry_config, loader_planting`

## callers

- `0x180140610`
- `0x180140740`

## callees

- `0x18005e890`
- `0x18012ffa4`
- `0x180183c40`

## import_xrefs

- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x180183cca`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x180183cca`
- `ntdll!RtlReleaseRelativeName` at `0x180183d5b`
- `ntdll!RtlReleaseRelativeName` at `0x180183d5b`
- `ntdll!NtOpenFile` at `0x180183d4f`
- `ntdll!NtOpenFile` at `0x180183d4f`
- `ntdll!RtlNtStatusToDosError` at `0x180183e19`
- `ntdll!RtlNtStatusToDosError` at `0x180183e19`
- `ntdll!NtClose` at `0x180183dd3`
- `ntdll!NtClose` at `0x180183dee`
- `ntdll!NtClose` at `0x180183dd3`
- `ntdll!NtClose` at `0x180183dee`
- `ntdll!RtlFreeHeap` at `0x180183d73`
- `ntdll!RtlFreeHeap` at `0x180183d73`
- `ntdll!NtRestoreKey` at `0x180183dc7`
- `ntdll!NtRestoreKey` at `0x180183de2`
- `ntdll!NtRestoreKey` at `0x180183dc7`
- `ntdll!NtRestoreKey` at `0x180183de2`
- `ext-ms-win-kernel32-registry-l1-1-0!TermsrvRestoreKey` at `0x180183e11`
- `ext-ms-win-kernel32-registry-l1-1-0!TermsrvRestoreKey` at `0x180183e11`

## pseudocode

```c

```
