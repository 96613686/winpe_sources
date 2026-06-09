# ATL::CSecurityDescriptor::CopyACL(_ACL *,_ACL *)

- ea: `0x18000a22c`
- end: `0x18000a2f6`
- name: `?CopyACL@CSecurityDescriptor@ATL@@SAJPEAU_ACL@@0@Z`
- size: `202`
- prototype: `__int64 __fastcall(PACL pAcl, PACL)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009420`

## callees

- `0x180001720`
- `0x180009df4`
- `0x18000a22c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18000a2c9`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18000a2c9`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18000a2a5`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18000a2a5`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18000a282`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18000a282`

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
      return ATL::AtlHresultFromLastError();
    for ( i = 0; i < (unsigned int)pAclInformation; ++i )
    {
      if ( !GetAce(a2, i, &pAce) || !AddAce(pAcl, 2u, 0xFFFFFFFF, pAce, *((unsigned __int16 *)pAce + 1)) )
        return ATL::AtlHresultFromLastError();
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000a22c  mov     r11, rsp
0x18000a22f  mov     [r11+18h], rbx
0x18000a233  mov     [r11+20h], rsi
0x18000a237  push    rdi
0x18000a238  sub     rsp, 50h
0x18000a23c  mov     rax, cs:__security_cookie
0x18000a243  xor     rax, rsp
0x18000a246  mov     [rsp+58h+var_10], rax
0x18000a24b  xor     eax, eax
0x18000a24d  mov     rdi, rdx
0x18000a250  mov     [r11-20h], rax
0x18000a254  mov     rsi, rcx
0x18000a257  mov     [rsp+58h+var_18], eax
0x18000a25b  mov     [r11-28h], rax
0x18000a25f  test    rcx, rcx
0x18000a262  jnz     short loc_18000A26B
0x18000a264  mov     eax, 80004003h
0x18000a269  jmp     short loc_18000A2D9
0x18000a26b  test    rdi, rdi
0x18000a26e  jz      short loc_18000A2D7
0x18000a270  mov     r9d, 2; dwAclInformationClass
0x18000a276  lea     rdx, [rsp+58h+pAclInformation]; pAclInformation
0x18000a27b  mov     rcx, rdi; pAcl
0x18000a27e  lea     r8d, [r9+0Ah]; nAclInformationLength
0x18000a282  call    cs:__imp_GetAclInformation
0x18000a288  test    eax, eax
0x18000a28a  jnz     short loc_18000A293
0x18000a28c  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000a291  jmp     short loc_18000A2D9
0x18000a293  xor     ebx, ebx
0x18000a295  cmp     ebx, dword ptr [rsp+58h+pAclInformation]
0x18000a299  jnb     short loc_18000A2D7
0x18000a29b  lea     r8, [rsp+58h+pAce]; pAce
0x18000a2a0  mov     edx, ebx; dwAceIndex
0x18000a2a2  mov     rcx, rdi; pAcl
0x18000a2a5  call    cs:__imp_GetAce
0x18000a2ab  test    eax, eax
0x18000a2ad  jz      short loc_18000A28C
0x18000a2af  mov     r9, [rsp+58h+pAce]; pAceList
0x18000a2b4  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x18000a2b8  mov     edx, 2; dwAceRevision
0x18000a2bd  mov     rcx, rsi; pAcl
0x18000a2c0  movzx   eax, word ptr [r9+2]
0x18000a2c5  mov     [rsp+58h+nAceListLength], eax; nAceListLength
0x18000a2c9  call    cs:__imp_AddAce
0x18000a2cf  test    eax, eax
0x18000a2d1  jz      short loc_18000A28C
0x18000a2d3  inc     ebx
0x18000a2d5  jmp     short loc_18000A295
0x18000a2d7  xor     eax, eax
0x18000a2d9  mov     rcx, [rsp+58h+var_10]
0x18000a2de  xor     rcx, rsp; StackCookie
0x18000a2e1  call    __security_check_cookie
0x18000a2e6  mov     rbx, [rsp+58h+arg_10]
0x18000a2eb  mov     rsi, [rsp+58h+arg_18]
0x18000a2f0  add     rsp, 50h
0x18000a2f4  pop     rdi
0x18000a2f5  retn
```
