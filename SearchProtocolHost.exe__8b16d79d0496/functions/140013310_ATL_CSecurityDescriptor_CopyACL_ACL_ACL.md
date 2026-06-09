# ATL::CSecurityDescriptor::CopyACL(_ACL *,_ACL *)

- ea: `0x140013310`
- end: `0x1400133da`
- name: `?CopyACL@CSecurityDescriptor@ATL@@SAJPEAU_ACL@@0@Z`
- size: `202`
- prototype: `__int64 __fastcall(PACL pAcl, PACL)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140011920`

## callees

- `0x140005240`
- `0x1400124cc`
- `0x140013310`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AddAce` at `0x1400133ad`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x1400133ad`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x140013366`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x140013366`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x140013389`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x140013389`

## pseudocode

```c
__int64 __fastcall ATL::CSecurityDescriptor::CopyACL(PACL pAcl, PACL a2)
{
  DWORD i; // ebx
  LPVOID pAce; // [rsp+30h] [rbp-28h] BYREF
  __int64 pAclInformation; // [rsp+38h] [rbp-20h] BYREF
  int v8; // [rsp+40h] [rbp-18h]

  pAclInformation = 0;
  v8 = 0;
  pAce = 0;
  if ( !pAcl )
    return 2147500035LL;
  if ( a2 )
  {
    if ( !GetAclInformation(a2, &pAclInformation, 0xCu, AclSizeInformation) )
      return ResultFromLastError();
    for ( i = 0; i < (unsigned int)pAclInformation; ++i )
    {
      if ( !GetAce(a2, i, &pAce) || !AddAce(pAcl, 2u, 0xFFFFFFFF, pAce, *((unsigned __int16 *)pAce + 1)) )
        return ResultFromLastError();
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140013310  mov     r11, rsp
0x140013313  mov     [r11+18h], rbx
0x140013317  mov     [r11+20h], rsi
0x14001331b  push    rdi
0x14001331c  sub     rsp, 50h
0x140013320  mov     rax, cs:__security_cookie
0x140013327  xor     rax, rsp
0x14001332a  mov     [rsp+58h+var_10], rax
0x14001332f  xor     eax, eax
0x140013331  mov     rdi, rdx
0x140013334  mov     [r11-20h], rax
0x140013338  mov     rsi, rcx
0x14001333b  mov     [rsp+58h+var_18], eax
0x14001333f  mov     [r11-28h], rax
0x140013343  test    rcx, rcx
0x140013346  jnz     short loc_14001334F
0x140013348  mov     eax, 80004003h
0x14001334d  jmp     short loc_1400133BD
0x14001334f  test    rdi, rdi
0x140013352  jz      short loc_1400133BB
0x140013354  mov     r9d, 2; dwAclInformationClass
0x14001335a  lea     rdx, [rsp+58h+pAclInformation]; pAclInformation
0x14001335f  mov     rcx, rdi; pAcl
0x140013362  lea     r8d, [r9+0Ah]; nAclInformationLength
0x140013366  call    cs:__imp_GetAclInformation
0x14001336c  test    eax, eax
0x14001336e  jnz     short loc_140013377
0x140013370  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x140013375  jmp     short loc_1400133BD
0x140013377  xor     ebx, ebx
0x140013379  cmp     ebx, dword ptr [rsp+58h+pAclInformation]
0x14001337d  jnb     short loc_1400133BB
0x14001337f  lea     r8, [rsp+58h+pAce]; pAce
0x140013384  mov     edx, ebx; dwAceIndex
0x140013386  mov     rcx, rdi; pAcl
0x140013389  call    cs:__imp_GetAce
0x14001338f  test    eax, eax
0x140013391  jz      short loc_140013370
0x140013393  mov     r9, [rsp+58h+pAce]; pAceList
0x140013398  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x14001339c  mov     edx, 2; dwAceRevision
0x1400133a1  mov     rcx, rsi; pAcl
0x1400133a4  movzx   eax, word ptr [r9+2]
0x1400133a9  mov     [rsp+58h+nAceListLength], eax; nAceListLength
0x1400133ad  call    cs:__imp_AddAce
0x1400133b3  test    eax, eax
0x1400133b5  jz      short loc_140013370
0x1400133b7  inc     ebx
0x1400133b9  jmp     short loc_140013379
0x1400133bb  xor     eax, eax
0x1400133bd  mov     rcx, [rsp+58h+var_10]
0x1400133c2  xor     rcx, rsp; StackCookie
0x1400133c5  call    __security_check_cookie
0x1400133ca  mov     rbx, [rsp+58h+arg_10]
0x1400133cf  mov     rsi, [rsp+58h+arg_18]
0x1400133d4  add     rsp, 50h
0x1400133d8  pop     rdi
0x1400133d9  retn
```
