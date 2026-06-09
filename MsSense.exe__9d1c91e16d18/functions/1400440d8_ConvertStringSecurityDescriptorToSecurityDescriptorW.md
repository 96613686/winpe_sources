# ConvertStringSecurityDescriptorToSecurityDescriptorW

- ea: `0x1400440d8`
- end: `0x1400440de`
- name: `ConvertStringSecurityDescriptorToSecurityDescriptorW`
- size: `6`
- prototype: `BOOL __stdcall(LPCWSTR StringSecurityDescriptor, DWORD StringSDRevision, PSECURITY_DESCRIPTOR *SecurityDescriptor, PULONG SecurityDescriptorSize)`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14003b68c`

## import_xrefs

- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1400440d8`

## pseudocode

```c
// attributes: thunk
BOOL __stdcall ConvertStringSecurityDescriptorToSecurityDescriptorW(
        LPCWSTR StringSecurityDescriptor,
        DWORD StringSDRevision,
        PSECURITY_DESCRIPTOR *SecurityDescriptor,
        PULONG SecurityDescriptorSize)
{
  return __imp_ConvertStringSecurityDescriptorToSecurityDescriptorW(
           StringSecurityDescriptor,
           StringSDRevision,
           SecurityDescriptor,
           SecurityDescriptorSize);
}

```

## disassembly

```asm
0x1400440d8  jmp     cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
```
