# SbEFIGetVariable

- ea: `0x180045b6c`
- end: `0x180045c71`
- name: `SbEFIGetVariable`
- size: `261`
- prototype: `__int64 __usercall@<rax>(PCWSTR SourceString@<rcx>, LPGUID VendorGuid@<rdx>, ULONG ReturnLength)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180045e64`

## callees

- `0x180045b6c`
- `0x180045c78`
- `0x18004634c`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180045bbd`
- `ntdll!RtlInitUnicodeString` at `0x180045bbd`
- `ntdll!NtQuerySystemEnvironmentValueEx` at `0x180045bdf`
- `ntdll!NtQuerySystemEnvironmentValueEx` at `0x180045c39`
- `ntdll!NtQuerySystemEnvironmentValueEx` at `0x180045bdf`
- `ntdll!NtQuerySystemEnvironmentValueEx` at `0x180045c39`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180045c07`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180045c07`

## string_xrefs

- `0x180045b8e`: `SeSystemEnvironmentPrivilege`

## pseudocode

```c

```
