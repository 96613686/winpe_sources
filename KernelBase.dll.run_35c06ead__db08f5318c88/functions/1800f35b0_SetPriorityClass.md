# SetPriorityClass

- ea: `0x1800f35b0`
- end: `0x1800f385e`
- name: `SetPriorityClass`
- size: `686`
- prototype: `BOOL __stdcall(HANDLE hProcess, DWORD dwPriorityClass)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800134a0`
- `0x1800f35b0`
- `0x1800f3864`
- `0x180124b90`
- `0x18012d119`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x1800f37cb`
- `ntdll!RtlSetLastWin32Error` at `0x1800f3814`
- `ntdll!RtlSetLastWin32Error` at `0x1800f37cb`
- `ntdll!RtlSetLastWin32Error` at `0x1800f3814`
- `ntdll!RtlReleasePrivilege` at `0x1800f381f`
- `ntdll!RtlReleasePrivilege` at `0x1800f381f`
- `ntdll!NtSetInformationProcess` at `0x1800f365e`
- `ntdll!NtSetInformationProcess` at `0x1800f36cc`
- `ntdll!NtSetInformationProcess` at `0x1800f3724`
- `ntdll!NtSetInformationProcess` at `0x1800f374a`
- `ntdll!NtSetInformationProcess` at `0x1800f376d`
- `ntdll!NtSetInformationProcess` at `0x1800f365e`
- `ntdll!NtSetInformationProcess` at `0x1800f36cc`
- `ntdll!NtSetInformationProcess` at `0x1800f3724`
- `ntdll!NtSetInformationProcess` at `0x1800f374a`
- `ntdll!NtSetInformationProcess` at `0x1800f376d`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800f3601`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800f3601`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800f367f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800f367f`
- `ntdll!NtCompareObjects` at `0x1800f37dc`
- `ntdll!NtCompareObjects` at `0x1800f37dc`

## pseudocode

```c

```
