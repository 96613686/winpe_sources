# ConvertStringSecurityDescriptorToSecurityDescriptorW

- ea: `0x100106cb`
- end: `0x100106d1`
- name: `ConvertStringSecurityDescriptorToSecurityDescriptorW`
- size: `6`
- prototype: `BOOL __stdcall(LPCWSTR StringSecurityDescriptor, DWORD StringSDRevision, PSECURITY_DESCRIPTOR *SecurityDescriptor, PULONG SecurityDescriptorSize)`
- caller_count: `2`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x10004adb`
- `0x10006e5d`

## import_xrefs

- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x100106cb`

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
0x100106cb  jmp     ds:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
```
