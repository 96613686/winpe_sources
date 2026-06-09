# ConvertSecurityDescriptorToStringSecurityDescriptorA

- ea: `0x180035390`
- end: `0x18003559b`
- name: `ConvertSecurityDescriptorToStringSecurityDescriptorA`
- size: `523`
- prototype: `BOOL __stdcall(PSECURITY_DESCRIPTOR SecurityDescriptor, DWORD RequestedStringSDRevision, SECURITY_INFORMATION SecurityInformation, LPSTR *StringSecurityDescriptor, PULONG StringSecurityDescriptorLen)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18001cfb8`
- `0x180035390`

## import_xrefs

- `KERNELBASE!LocalAlloc` at `0x1800354a7`
- `KERNELBASE!LocalAlloc` at `0x1800354fc`
- `KERNELBASE!LocalAlloc` at `0x1800354a7`
- `KERNELBASE!LocalAlloc` at `0x1800354fc`
- `KERNEL32!LocalFree` at `0x18003545f`
- `KERNEL32!LocalFree` at `0x18003555b`
- `KERNEL32!LocalFree` at `0x18003545f`
- `KERNEL32!LocalFree` at `0x18003555b`
- `KERNEL32!WideCharToMultiByte` at `0x180035448`
- `KERNEL32!WideCharToMultiByte` at `0x180035546`
- `KERNEL32!WideCharToMultiByte` at `0x180035448`
- `KERNEL32!WideCharToMultiByte` at `0x180035546`
- `KERNEL32!SetLastError` at `0x18003540b`
- `KERNEL32!SetLastError` at `0x180035492`
- `KERNEL32!SetLastError` at `0x1800354be`
- `KERNEL32!SetLastError` at `0x1800354ce`
- `KERNEL32!SetLastError` at `0x18003558a`
- `KERNEL32!SetLastError` at `0x18003540b`
- `KERNEL32!SetLastError` at `0x180035492`
- `KERNEL32!SetLastError` at `0x1800354be`
- `KERNEL32!SetLastError` at `0x1800354ce`
- `KERNEL32!SetLastError` at `0x18003558a`

## pseudocode

```c

```
