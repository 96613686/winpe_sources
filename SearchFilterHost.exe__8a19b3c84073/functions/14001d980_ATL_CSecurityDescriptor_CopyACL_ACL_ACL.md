# ATL::CSecurityDescriptor::CopyACL(_ACL *,_ACL *)

- ea: `0x14001d980`
- end: `0x14001da4a`
- name: `?CopyACL@CSecurityDescriptor@ATL@@SAJPEAU_ACL@@0@Z`
- size: `202`
- prototype: `__int64 __fastcall(PACL pAcl, PACL)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001ca4c`

## callees

- `0x1400030a0`
- `0x14001d4e8`
- `0x14001d980`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AddAce` at `0x14001da1d`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x14001da1d`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x14001d9d6`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x14001d9d6`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x14001d9f9`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x14001d9f9`

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
0x14001d980  mov     r11, rsp
0x14001d983  mov     [r11+18h], rbx
0x14001d987  mov     [r11+20h], rsi
0x14001d98b  push    rdi
0x14001d98c  sub     rsp, 50h
0x14001d990  mov     rax, cs:__security_cookie
0x14001d997  xor     rax, rsp
0x14001d99a  mov     [rsp+58h+var_10], rax
0x14001d99f  xor     eax, eax
0x14001d9a1  mov     rdi, rdx
0x14001d9a4  mov     [r11-20h], rax
0x14001d9a8  mov     rsi, rcx
0x14001d9ab  mov     [rsp+58h+var_18], eax
0x14001d9af  mov     [r11-28h], rax
0x14001d9b3  test    rcx, rcx
0x14001d9b6  jnz     short loc_14001D9BF
0x14001d9b8  mov     eax, 80004003h
0x14001d9bd  jmp     short loc_14001DA2D
0x14001d9bf  test    rdi, rdi
0x14001d9c2  jz      short loc_14001DA2B
0x14001d9c4  mov     r9d, 2; dwAclInformationClass
0x14001d9ca  lea     rdx, [rsp+58h+pAclInformation]; pAclInformation
0x14001d9cf  mov     rcx, rdi; pAcl
0x14001d9d2  lea     r8d, [r9+0Ah]; nAclInformationLength
0x14001d9d6  call    cs:__imp_GetAclInformation
0x14001d9dc  test    eax, eax
0x14001d9de  jnz     short loc_14001D9E7
0x14001d9e0  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x14001d9e5  jmp     short loc_14001DA2D
0x14001d9e7  xor     ebx, ebx
0x14001d9e9  cmp     ebx, dword ptr [rsp+58h+pAclInformation]
0x14001d9ed  jnb     short loc_14001DA2B
0x14001d9ef  lea     r8, [rsp+58h+pAce]; pAce
0x14001d9f4  mov     edx, ebx; dwAceIndex
0x14001d9f6  mov     rcx, rdi; pAcl
0x14001d9f9  call    cs:__imp_GetAce
0x14001d9ff  test    eax, eax
0x14001da01  jz      short loc_14001D9E0
0x14001da03  mov     r9, [rsp+58h+pAce]; pAceList
0x14001da08  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x14001da0c  mov     edx, 2; dwAceRevision
0x14001da11  mov     rcx, rsi; pAcl
0x14001da14  movzx   eax, word ptr [r9+2]
0x14001da19  mov     [rsp+58h+nAceListLength], eax; nAceListLength
0x14001da1d  call    cs:__imp_AddAce
0x14001da23  test    eax, eax
0x14001da25  jz      short loc_14001D9E0
0x14001da27  inc     ebx
0x14001da29  jmp     short loc_14001D9E9
0x14001da2b  xor     eax, eax
0x14001da2d  mov     rcx, [rsp+58h+var_10]
0x14001da32  xor     rcx, rsp; StackCookie
0x14001da35  call    __security_check_cookie
0x14001da3a  mov     rbx, [rsp+58h+arg_10]
0x14001da3f  mov     rsi, [rsp+58h+arg_18]
0x14001da44  add     rsp, 50h
0x14001da48  pop     rdi
0x14001da49  retn
```
