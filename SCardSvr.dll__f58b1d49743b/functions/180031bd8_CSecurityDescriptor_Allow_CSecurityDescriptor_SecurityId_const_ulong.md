# CSecurityDescriptor::Allow(CSecurityDescriptor::SecurityId const *,ulong)

- ea: `0x180031bd8`
- end: `0x180031c38`
- name: `?Allow@CSecurityDescriptor@@QEAAJPEBUSecurityId@1@K@Z`
- size: `96`
- prototype: `__int64 __fastcall(struct _ACL **this, struct _SID_IDENTIFIER_AUTHORITY *, DWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800297a0`

## callees

- `0x180031a40`
- `0x180031bd8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031c11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031c11`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180031c07`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180031c07`

## pseudocode

```c
__int64 __fastcall CSecurityDescriptor::Allow(struct _ACL **this, struct _SID_IDENTIFIER_AUTHORITY *a2, DWORD a3)
{
  int v4; // ebx
  signed int LastError; // eax

  v4 = CSecurityDescriptor::AddAccessAllowedACEToACL(this + 3, a2, a3);
  if ( v4 >= 0 && !SetSecurityDescriptorDacl(*this, 1, this[3], 0) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180031bd8  mov     [rsp+arg_0], rbx
0x180031bdd  mov     [rsp+arg_8], rsi
0x180031be2  push    rdi
0x180031be3  sub     rsp, 20h
0x180031be7  mov     rdi, rcx
0x180031bea  add     rcx, 18h; struct _ACL **
0x180031bee  call    ?AddAccessAllowedACEToACL@CSecurityDescriptor@@SAJPEAPEAU_ACL@@PEBUSecurityId@1@K@Z; CSecurityDescriptor::AddAccessAllowedACEToACL(_ACL * *,CSecurityDescriptor::SecurityId const *,ulong)
0x180031bf3  mov     ebx, eax
0x180031bf5  test    eax, eax
0x180031bf7  js      short loc_180031C26
0x180031bf9  mov     r8, [rdi+18h]; pDacl
0x180031bfd  xor     r9d, r9d; bDaclDefaulted
0x180031c00  mov     rcx, [rdi]; pSecurityDescriptor
0x180031c03  lea     edx, [r9+1]; bDaclPresent
0x180031c07  call    cs:__imp_SetSecurityDescriptorDacl
0x180031c0d  test    eax, eax
0x180031c0f  jnz     short loc_180031C26
0x180031c11  call    cs:__imp_GetLastError
0x180031c17  mov     ebx, eax
0x180031c19  test    eax, eax
0x180031c1b  jle     short loc_180031C26
0x180031c1d  movzx   ebx, ax
0x180031c20  or      ebx, 80070000h
0x180031c26  mov     rsi, [rsp+28h+arg_8]
0x180031c2b  mov     eax, ebx
0x180031c2d  mov     rbx, [rsp+28h+arg_0]
0x180031c32  add     rsp, 20h
0x180031c36  pop     rdi
0x180031c37  retn
```
