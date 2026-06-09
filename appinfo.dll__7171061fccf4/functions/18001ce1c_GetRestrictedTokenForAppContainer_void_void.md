# GetRestrictedTokenForAppContainer(void *,void * *)

- ea: `0x18001ce1c`
- end: `0x18001cff2`
- name: `?GetRestrictedTokenForAppContainer@@YAJPEAXPEAPEAX@Z`
- size: `470`
- prototype: `signed int __fastcall(HANDLE ExistingTokenHandle, PHANDLE NewTokenHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18002ce70`

## callees

- `0x18001ce1c`
- `0x18001e7bc`
- `0x18001efc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ce58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ceba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cec4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cece`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cf9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cfa8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cfb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ce58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ceba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cec4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cece`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cf9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cfa8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cfb2`
- `api-ms-win-security-base-l1-1-0!CreateRestrictedToken` at `0x18001cf94`
- `api-ms-win-security-base-l1-1-0!CreateRestrictedToken` at `0x18001cf94`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001ce4a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001ceb0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001ce4a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001ceb0`

## pseudocode

```c
signed int __fastcall GetRestrictedTokenForAppContainer(HANDLE ExistingTokenHandle, PHANDLE NewTokenHandle)
{
  unsigned int *v3; // rbx
  signed int result; // eax
  unsigned int v6; // edi
  unsigned __int64 v7; // rax
  struct _LUID_AND_ATTRIBUTES *v8; // rax
  signed int v9; // r9d
  unsigned int v10; // r8d
  struct _LUID_AND_ATTRIBUTES *PrivilegesToDelete; // rdi
  DWORD v12; // edx
  __int64 v13; // rax
  __int64 v14; // rcx
  unsigned int LastError; // esi
  DWORD TokenInformationLength; // [rsp+90h] [rbp+18h] BYREF

  TokenInformationLength = 0;
  v3 = 0;
  if ( GetTokenInformation(ExistingTokenHandle, TokenPrivileges, 0, 0, &TokenInformationLength) )
    goto LABEL_12;
  result = GetLastError();
  if ( result != 122 )
  {
    if ( result > 0 )
      return (unsigned __int16)result | 0xC0070000;
    return result;
  }
  v3 = (unsigned int *)operator new[](TokenInformationLength, (const struct std::nothrow_t *)std::nothrow);
  if ( !v3 )
    return -1073741801;
  if ( GetTokenInformation(ExistingTokenHandle, TokenPrivileges, v3, TokenInformationLength, &TokenInformationLength) )
  {
LABEL_12:
    v7 = 12LL * *v3;
    if ( !is_mul_ok(*v3, 0xCu) )
      v7 = -1;
    v8 = (struct _LUID_AND_ATTRIBUTES *)operator new[](v7, (const struct std::nothrow_t *)std::nothrow);
    v9 = 0;
    v10 = 0;
    for ( PrivilegesToDelete = v8; v10 < *v3; ++v10 )
    {
      if ( v3[3 * v10 + 1] != 23 && v3[3 * v10 + 1] != 33 || v3[3 * v10 + 2] )
      {
        v12 = v3[3 * v10 + 3];
        v13 = v9++;
        v14 = v13;
        PrivilegesToDelete[v14].Luid = *(LUID *)&v3[3 * v10 + 1];
        PrivilegesToDelete[v14].Attributes = v12;
      }
    }
    if ( CreateRestrictedToken(ExistingTokenHandle, 0, 0, 0, v9, PrivilegesToDelete, 0, 0, NewTokenHandle) )
    {
      if ( PrivilegesToDelete )
        operator delete(PrivilegesToDelete);
      LastError = 0;
    }
    else
    {
      if ( (int)GetLastError() > 0 )
        LastError = (unsigned __int16)GetLastError() | 0xC0070000;
      else
        LastError = GetLastError();
      if ( PrivilegesToDelete )
        operator delete(PrivilegesToDelete);
    }
    operator delete(v3);
    return LastError;
  }
  else
  {
    if ( (int)GetLastError() > 0 )
      v6 = (unsigned __int16)GetLastError() | 0xC0070000;
    else
      v6 = GetLastError();
    operator delete(v3);
    return v6;
  }
}

```

## disassembly

```asm
0x18001ce1c  mov     rax, rsp
0x18001ce1f  push    rbx
0x18001ce20  push    rbp
0x18001ce21  push    rsi
0x18001ce22  push    rdi
0x18001ce23  sub     rsp, 58h
0x18001ce27  mov     dword ptr [rax+18h], 0
0x18001ce2e  lea     rax, [rax+18h]
0x18001ce32  mov     rbp, rdx
0x18001ce35  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x18001ce3a  xor     ebx, ebx
0x18001ce3c  xor     r9d, r9d; TokenInformationLength
0x18001ce3f  xor     r8d, r8d; TokenInformation
0x18001ce42  mov     rsi, rcx
0x18001ce45  lea     edi, [rbx+3]
0x18001ce48  mov     edx, edi; TokenInformationClass
0x18001ce4a  call    cs:__imp_GetTokenInformation
0x18001ce50  test    eax, eax
0x18001ce52  jnz     loc_18001CEF6
0x18001ce58  call    cs:__imp_GetLastError
0x18001ce5e  cmp     eax, 7Ah ; 'z'
0x18001ce61  jz      short loc_18001CE78
0x18001ce63  test    eax, eax
0x18001ce65  jle     loc_18001CFE9
0x18001ce6b  movzx   eax, ax
0x18001ce6e  or      eax, 0C0070000h
0x18001ce73  jmp     loc_18001CFE9
0x18001ce78  mov     ecx, [rsp+78h+TokenInformationLength]; unsigned __int64
0x18001ce7f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001ce86  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001ce8b  mov     rbx, rax
0x18001ce8e  test    rax, rax
0x18001ce91  jz      short loc_18001CEEC
0x18001ce93  mov     r9d, [rsp+78h+TokenInformationLength]; TokenInformationLength
0x18001ce9b  lea     rax, [rsp+78h+TokenInformationLength]
0x18001cea3  mov     r8, rbx; TokenInformation
0x18001cea6  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x18001ceab  mov     edx, edi; TokenInformationClass
0x18001cead  mov     rcx, rsi; TokenHandle
0x18001ceb0  call    cs:__imp_GetTokenInformation
0x18001ceb6  test    eax, eax
0x18001ceb8  jnz     short loc_18001CEF6
0x18001ceba  call    cs:__imp_GetLastError
0x18001cec0  test    eax, eax
0x18001cec2  jg      short loc_18001CECE
0x18001cec4  call    cs:__imp_GetLastError
0x18001ceca  mov     edi, eax
0x18001cecc  jmp     short loc_18001CEDD
0x18001cece  call    cs:__imp_GetLastError
0x18001ced4  movzx   edi, ax
0x18001ced7  or      edi, 0C0070000h
0x18001cedd  mov     rcx, rbx; Block
0x18001cee0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001cee5  mov     eax, edi
0x18001cee7  jmp     loc_18001CFE9
0x18001ceec  mov     eax, 0C0000017h
0x18001cef1  jmp     loc_18001CFE9
0x18001cef6  mov     ecx, [rbx]
0x18001cef8  mov     eax, 0Ch
0x18001cefd  mul     rcx
0x18001cf00  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001cf07  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001cf0e  cmovb   rax, rcx
0x18001cf12  mov     rcx, rax; unsigned __int64
0x18001cf15  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001cf1a  xor     r9d, r9d
0x18001cf1d  xor     r8d, r8d
0x18001cf20  mov     rdi, rax
0x18001cf23  cmp     [rbx], r8d
0x18001cf26  jbe     short loc_18001CF69
0x18001cf28  movsxd  rax, r8d
0x18001cf2b  lea     rdx, [rax+rax*2]
0x18001cf2f  cmp     dword ptr [rbx+rdx*4+4], 17h
0x18001cf34  jz      short loc_18001CF3D
0x18001cf36  cmp     dword ptr [rbx+rdx*4+4], 21h ; '!'
0x18001cf3b  jnz     short loc_18001CF44
0x18001cf3d  cmp     dword ptr [rbx+rdx*4+8], 0
0x18001cf42  jz      short loc_18001CF61
0x18001cf44  movsd   xmm0, qword ptr [rbx+rdx*4+4]
0x18001cf4a  mov     edx, [rbx+rdx*4+0Ch]
0x18001cf4e  movsxd  rax, r9d
0x18001cf51  inc     r9d
0x18001cf54  lea     rcx, [rax+rax*2]
0x18001cf58  movsd   qword ptr [rdi+rcx*4], xmm0
0x18001cf5d  mov     [rdi+rcx*4+8], edx
0x18001cf61  inc     r8d
0x18001cf64  cmp     r8d, [rbx]
0x18001cf67  jb      short loc_18001CF28
0x18001cf69  mov     [rsp+78h+NewTokenHandle], rbp; NewTokenHandle
0x18001cf6e  xor     r8d, r8d; DisableSidCount
0x18001cf71  mov     [rsp+78h+SidsToRestrict], 0; SidsToRestrict
0x18001cf7a  xor     edx, edx; Flags
0x18001cf7c  mov     [rsp+78h+RestrictedSidCount], 0; RestrictedSidCount
0x18001cf84  mov     rcx, rsi; ExistingTokenHandle
0x18001cf87  mov     [rsp+78h+PrivilegesToDelete], rdi; PrivilegesToDelete
0x18001cf8c  mov     dword ptr [rsp+78h+ReturnLength], r9d; DeletePrivilegeCount
0x18001cf91  xor     r9d, r9d; SidsToDisable
0x18001cf94  call    cs:__imp_CreateRestrictedToken
0x18001cf9a  test    eax, eax
0x18001cf9c  jnz     short loc_18001CFD0
0x18001cf9e  call    cs:__imp_GetLastError
0x18001cfa4  test    eax, eax
0x18001cfa6  jg      short loc_18001CFB2
0x18001cfa8  call    cs:__imp_GetLastError
0x18001cfae  mov     esi, eax
0x18001cfb0  jmp     short loc_18001CFC1
0x18001cfb2  call    cs:__imp_GetLastError
0x18001cfb8  movzx   esi, ax
0x18001cfbb  or      esi, 0C0070000h
0x18001cfc1  test    rdi, rdi
0x18001cfc4  jz      short loc_18001CFDF
0x18001cfc6  mov     rcx, rdi; Block
0x18001cfc9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001cfce  jmp     short loc_18001CFDF
0x18001cfd0  test    rdi, rdi
0x18001cfd3  jz      short loc_18001CFDD
0x18001cfd5  mov     rcx, rdi; Block
0x18001cfd8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001cfdd  xor     esi, esi
0x18001cfdf  mov     rcx, rbx; Block
0x18001cfe2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001cfe7  mov     eax, esi
0x18001cfe9  add     rsp, 58h
0x18001cfed  pop     rdi
0x18001cfee  pop     rsi
0x18001cfef  pop     rbp
0x18001cff0  pop     rbx
0x18001cff1  retn
```
