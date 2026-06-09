# ConvertSecurityDescriptorToStringSecurityDescriptorA

- ea: `0x180031d40`
- end: `0x180031f08`
- name: `ConvertSecurityDescriptorToStringSecurityDescriptorA`
- size: `456`
- prototype: `BOOL __stdcall(PSECURITY_DESCRIPTOR SecurityDescriptor, DWORD RequestedStringSDRevision, SECURITY_INFORMATION SecurityInformation, LPSTR *StringSecurityDescriptor, PULONG StringSecurityDescriptorLen)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18001e218`
- `0x180031d40`

## import_xrefs

- `KERNELBASE!LocalAlloc` at `0x180031e3e`
- `KERNELBASE!LocalAlloc` at `0x180031e81`
- `KERNELBASE!LocalAlloc` at `0x180031e3e`
- `KERNELBASE!LocalAlloc` at `0x180031e81`
- `KERNEL32!LocalFree` at `0x180031e03`
- `KERNEL32!LocalFree` at `0x180031ed4`
- `KERNEL32!LocalFree` at `0x180031e03`
- `KERNEL32!LocalFree` at `0x180031ed4`
- `KERNEL32!WideCharToMultiByte` at `0x180031df2`
- `KERNEL32!WideCharToMultiByte` at `0x180031ec5`
- `KERNEL32!WideCharToMultiByte` at `0x180031df2`
- `KERNEL32!WideCharToMultiByte` at `0x180031ec5`
- `KERNEL32!SetLastError` at `0x180031dbb`
- `KERNEL32!SetLastError` at `0x180031e2f`
- `KERNEL32!SetLastError` at `0x180031e4f`
- `KERNEL32!SetLastError` at `0x180031e59`
- `KERNEL32!SetLastError` at `0x180031efd`
- `KERNEL32!SetLastError` at `0x180031dbb`
- `KERNEL32!SetLastError` at `0x180031e2f`
- `KERNEL32!SetLastError` at `0x180031e4f`
- `KERNEL32!SetLastError` at `0x180031e59`
- `KERNEL32!SetLastError` at `0x180031efd`

## pseudocode

```c

```
