# CopyReparsePoint

- ea: `0x1801109b8`
- end: `0x180110b86`
- name: `CopyReparsePoint`
- size: `462`
- prototype: `__int64 __fastcall(HANDLE FileHandle, HANDLE, HANDLE Handle)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting`

## callers

- `0x1800d061c`

## callees

- `0x1800134a0`
- `0x1801109b8`

## import_xrefs

- `ntdll!NtFsControlFile` at `0x180110a57`
- `ntdll!NtFsControlFile` at `0x180110b08`
- `ntdll!NtFsControlFile` at `0x180110a57`
- `ntdll!NtFsControlFile` at `0x180110b08`
- `ntdll!NtWaitForSingleObject` at `0x180110a74`
- `ntdll!NtWaitForSingleObject` at `0x180110b1f`
- `ntdll!NtWaitForSingleObject` at `0x180110a74`
- `ntdll!NtWaitForSingleObject` at `0x180110b1f`
- `ntdll!RtlReleasePrivilege` at `0x180110b43`
- `ntdll!RtlReleasePrivilege` at `0x180110b43`
- `ntdll!RtlAcquirePrivilege` at `0x180110abd`
- `ntdll!RtlAcquirePrivilege` at `0x180110abd`
- `ntdll!RtlFreeHeap` at `0x180110b5b`
- `ntdll!RtlFreeHeap` at `0x180110b5b`
- `ntdll!RtlAllocateHeap` at `0x1801109fc`
- `ntdll!RtlAllocateHeap` at `0x1801109fc`

## pseudocode

```c

```
