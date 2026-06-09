# ConvertSecurityDescriptorToStringSecurityDescriptorW

- ea: `0x100106d1`
- end: `0x100106d7`
- name: `ConvertSecurityDescriptorToStringSecurityDescriptorW`
- size: `6`
- prototype: `BOOL __stdcall(PSECURITY_DESCRIPTOR SecurityDescriptor, DWORD RequestedStringSDRevision, SECURITY_INFORMATION SecurityInformation, LPWSTR *StringSecurityDescriptor, PULONG StringSecurityDescriptorLen)`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x100042be`

## import_xrefs

- `ADVAPI32!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x100106d1`

## pseudocode

```c
// attributes: thunk
BOOL __stdcall ConvertSecurityDescriptorToStringSecurityDescriptorW(
        PSECURITY_DESCRIPTOR SecurityDescriptor,
        DWORD RequestedStringSDRevision,
        SECURITY_INFORMATION SecurityInformation,
        LPWSTR *StringSecurityDescriptor,
        PULONG StringSecurityDescriptorLen)
{
  return __imp_ConvertSecurityDescriptorToStringSecurityDescriptorW(
           SecurityDescriptor,
           RequestedStringSDRevision,
           SecurityInformation,
           StringSecurityDescriptor,
           StringSecurityDescriptorLen);
}

```

## disassembly

```asm
0x100106d1  jmp     ds:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
```
