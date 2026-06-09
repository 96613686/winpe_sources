# CSecurityDescriptor::CopyACL(_ACL *,_ACL *)

- ea: `0x180031c40`
- end: `0x180031d08`
- name: `?CopyACL@CSecurityDescriptor@@SAJPEAU_ACL@@0@Z`
- size: `200`
- prototype: `signed int __fastcall(PACL pAcl, PACL)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180031a40`

## callees

- `0x180031c40`
- `0x1800326d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031c91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031c91`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180031cb7`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180031cb7`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180031c87`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180031c87`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180031cdb`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180031cdb`

## pseudocode

```c
signed int __fastcall CSecurityDescriptor::CopyACL(PACL pAcl, PACL a2)
{
  signed int result; // eax
  DWORD i; // ebx
  LPVOID pAce; // [rsp+30h] [rbp-28h] BYREF
  __int64 v7; // [rsp+38h] [rbp-20h] BYREF
  int v8; // [rsp+40h] [rbp-18h]

  v7 = 0;
  v8 = 0;
  pAce = 0;
  if ( !a2 )
    return 0;
  if ( GetAclInformation(a2, &v7, 0xCu, AclSizeInformation) )
  {
    for ( i = 0; i < (unsigned int)v7; ++i )
    {
      if ( !GetAce(a2, i, &pAce) || !AddAce(pAcl, 2u, 0xFFFFFFFF, pAce, *((unsigned __int16 *)pAce + 1)) )
        goto LABEL_3;
    }
    return 0;
  }
LABEL_3:
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180031c40  mov     r11, rsp
0x180031c43  mov     [r11+18h], rbx
0x180031c47  mov     [r11+20h], rsi
0x180031c4b  push    rdi
0x180031c4c  sub     rsp, 50h
0x180031c50  mov     rax, cs:__security_cookie
0x180031c57  xor     rax, rsp
0x180031c5a  mov     [rsp+58h+var_10], rax
0x180031c5f  xor     eax, eax
0x180031c61  mov     rdi, rdx
0x180031c64  mov     [r11-20h], rax
0x180031c68  mov     rsi, rcx
0x180031c6b  mov     [rsp+58h+var_18], eax
0x180031c6f  mov     [r11-28h], rax
0x180031c73  test    rdx, rdx
0x180031c76  jz      short loc_180031CE9
0x180031c78  lea     r9d, [rax+2]; dwAclInformationClass
0x180031c7c  mov     rcx, rdi; pAcl
0x180031c7f  lea     r8d, [rax+0Ch]; nAclInformationLength
0x180031c83  lea     rdx, [r11-20h]; pAclInformation
0x180031c87  call    cs:__imp_GetAclInformation
0x180031c8d  test    eax, eax
0x180031c8f  jnz     short loc_180031CA5
0x180031c91  call    cs:__imp_GetLastError
0x180031c97  test    eax, eax
0x180031c99  jle     short loc_180031CEB
0x180031c9b  movzx   eax, ax
0x180031c9e  or      eax, 80070000h
0x180031ca3  jmp     short loc_180031CEB
0x180031ca5  xor     ebx, ebx
0x180031ca7  cmp     ebx, dword ptr [rsp+58h+var_20]
0x180031cab  jnb     short loc_180031CE9
0x180031cad  lea     r8, [rsp+58h+pAce]; pAce
0x180031cb2  mov     edx, ebx; dwAceIndex
0x180031cb4  mov     rcx, rdi; pAcl
0x180031cb7  call    cs:__imp_GetAce
0x180031cbd  test    eax, eax
0x180031cbf  jz      short loc_180031C91
0x180031cc1  mov     r9, [rsp+58h+pAce]; pAceList
0x180031cc6  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x180031cca  mov     edx, 2; dwAceRevision
0x180031ccf  mov     rcx, rsi; pAcl
0x180031cd2  movzx   eax, word ptr [r9+2]
0x180031cd7  mov     [rsp+58h+nAceListLength], eax; nAceListLength
0x180031cdb  call    cs:__imp_AddAce
0x180031ce1  test    eax, eax
0x180031ce3  jz      short loc_180031C91
0x180031ce5  inc     ebx
0x180031ce7  jmp     short loc_180031CA7
0x180031ce9  xor     eax, eax
0x180031ceb  mov     rcx, [rsp+58h+var_10]
0x180031cf0  xor     rcx, rsp; StackCookie
0x180031cf3  call    __security_check_cookie
0x180031cf8  mov     rbx, [rsp+58h+arg_10]
0x180031cfd  mov     rsi, [rsp+58h+arg_18]
0x180031d02  add     rsp, 50h
0x180031d06  pop     rdi
0x180031d07  retn
```
