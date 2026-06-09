# StringSd::GetSecurityDescriptor(void * *)

- ea: `0x180013080`
- end: `0x1800130c6`
- name: `?GetSecurityDescriptor@StringSd@@QEAAJPEAPEAX@Z`
- size: `70`
- prototype: `int __fastcall(LPCWSTR *this, void **)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180025bbc`
- `0x1800282a0`

## callees

- `0x180013080`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800130b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800130b2`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180013097`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180013097`

## pseudocode

```c
int __fastcall StringSd::GetSecurityDescriptor(LPCWSTR *this, void **a2)
{
  int result; // eax

  if ( !a2 )
    return -2147024809;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(*this, 1u, a2, 0) )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180013080  sub     rsp, 28h
0x180013084  test    rdx, rdx
0x180013087  jz      short loc_1800130A8
0x180013089  mov     rcx, [rcx]; StringSecurityDescriptor
0x18001308c  mov     r8, rdx; SecurityDescriptor
0x18001308f  mov     edx, 1; StringSDRevision
0x180013094  xor     r9d, r9d; SecurityDescriptorSize
0x180013097  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18001309d  test    eax, eax
0x18001309f  jz      short loc_1800130B2
0x1800130a1  xor     eax, eax
0x1800130a3  add     rsp, 28h
0x1800130a7  retn
0x1800130a8  mov     eax, 80070057h
0x1800130ad  add     rsp, 28h
0x1800130b1  retn
0x1800130b2  call    cs:__imp_GetLastError
0x1800130b8  test    eax, eax
0x1800130ba  jle     short loc_1800130AD
0x1800130bc  movzx   eax, ax
0x1800130bf  or      eax, 80070000h
0x1800130c4  jmp     short loc_1800130AD
```
