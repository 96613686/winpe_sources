# CreatePerUserSecurityDescriptor(void)

- ea: `0x140014348`
- end: `0x1400146a4`
- name: `?CreatePerUserSecurityDescriptor@@YAJXZ`
- size: `860`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14003a8e8`

## callees

- `0x140005924`
- `0x14000ea90`
- `0x14000eab4`
- `0x14000f208`
- `0x140014348`
- `0x140037ca8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400143d3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14001443f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14001447b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400144bb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400143d3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14001443f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14001447b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400144bb`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x14001455a`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x14001455a`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1400145d5`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x14001461a`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1400145d5`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x14001461a`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x14001458a`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x14001458a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1400144ea`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1400144ea`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x140014572`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x140014572`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x140014532`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x140014532`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1400145a1`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1400145a1`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x140014546`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x140014546`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001438b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400143d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014449`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014481`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400144c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400145ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400145e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014624`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001438b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400143d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014449`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014481`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400144c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400145ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400145e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014624`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14001436f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14001436f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x140014381`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x140014381`

## pseudocode

```c
// Hidden C++ exception states: #wind=57
__int64 CreatePerUserSecurityDescriptor(void)
{
  HANDLE CurrentProcess; // rax
  signed int v1; // eax
  signed int v2; // r14d
  PSID *v3; // rdi
  PSID *v4; // rsi
  signed int LastError; // eax
  signed int v6; // eax
  signed int v7; // eax
  signed int v8; // eax
  struct _ACL *v9; // rbx
  unsigned __int64 v10; // r12
  signed int v11; // eax
  void *v12; // rax
  signed int v13; // eax
  PSID *v15; // [rsp+30h] [rbp-38h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+38h] [rbp-30h] BYREF
  __int64 v17; // [rsp+58h] [rbp-10h]
  DWORD TokenInformationLength; // [rsp+B0h] [rbp+48h] BYREF
  void *TokenHandle; // [rsp+B8h] [rbp+50h] BYREF
  struct _ACL *v20; // [rsp+C0h] [rbp+58h] BYREF
  PSID *v21; // [rsp+C8h] [rbp+60h] BYREF

  TokenHandle = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &TokenHandle,
    0);
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    v3 = 0;
    v4 = 0;
    v15 = 0;
    v21 = 0;
    TokenInformationLength = 0;
    GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError == 122 )
    {
      v2 = 0;
      v15 = (PSID *)operator new[](TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
      v3 = v15;
      if ( !v15 )
        goto LABEL_42;
    }
    else
    {
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
      if ( v2 < 0 )
        goto LABEL_22;
    }
    if ( GetTokenInformation(TokenHandle, TokenUser, v3, TokenInformationLength, &TokenInformationLength) )
      goto LABEL_14;
    v6 = GetLastError();
    v2 = v6;
    if ( v6 > 0 )
      v2 = (unsigned __int16)v6 | 0x80070000;
    if ( v2 >= 0 )
    {
LABEL_14:
      GetTokenInformation(TokenHandle, TokenPrimaryGroup, 0, 0, &TokenInformationLength);
      v7 = GetLastError();
      if ( v7 != 122 )
      {
        if ( v7 > 0 )
          v2 = (unsigned __int16)v7 | 0x80070000;
        else
          v2 = v7;
        if ( v2 < 0 )
          goto LABEL_22;
        goto LABEL_19;
      }
      v21 = (PSID *)operator new[](TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
      v4 = v21;
      if ( v21 )
      {
LABEL_19:
        if ( !GetTokenInformation(TokenHandle, TokenPrimaryGroup, v4, TokenInformationLength, &TokenInformationLength) )
        {
          v8 = GetLastError();
          v2 = v8;
          if ( v8 > 0 )
            v2 = (unsigned __int16)v8 | 0x80070000;
        }
        goto LABEL_22;
      }
LABEL_42:
      v2 = -2147024882;
    }
LABEL_22:
    v9 = 0;
    LODWORD(v10) = 0;
    v20 = 0;
    if ( v2 >= 0 )
    {
      v10 = GetLengthSid(*v3) + 16;
      v20 = (struct _ACL *)operator new[](v10, (const struct std::nothrow_t *)&std::nothrow);
      v9 = v20;
      if ( !v20 )
        v2 = -2147024882;
    }
    v17 = 0;
    memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
    if ( v2 < 0 )
      goto LABEL_45;
    if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u)
      || !SetSecurityDescriptorOwner(pSecurityDescriptor, *v3, 0)
      || !SetSecurityDescriptorGroup(pSecurityDescriptor, *v4, 0)
      || !InitializeAcl(v9, v10, 2u)
      || !AddAccessAllowedAce(v9, 2u, 0x1F0081u, *v3)
      || !SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v9, 0) )
    {
      v11 = GetLastError();
      v2 = v11;
      if ( v11 > 0 )
        v2 = (unsigned __int16)v11 | 0x80070000;
      if ( v2 < 0 )
        goto LABEL_45;
    }
    if ( MakeSelfRelativeSD(pSecurityDescriptor, 0, &g_perUserSDLength) )
    {
      v2 = -2147467259;
    }
    else
    {
      if ( GetLastError() != 122 )
        goto LABEL_39;
      v12 = operator new[](g_perUserSDLength, (const struct std::nothrow_t *)&std::nothrow);
      g_perUserSD = v12;
      if ( v12 )
      {
        if ( !MakeSelfRelativeSD(pSecurityDescriptor, v12, &g_perUserSDLength) )
        {
LABEL_39:
          v13 = GetLastError();
          v2 = v13;
          if ( v13 > 0 )
            v2 = (unsigned __int16)v13 | 0x80070000;
        }
      }
      else
      {
        v2 = -2147024882;
      }
    }
LABEL_45:
    TPointer<_ACL>::~TPointer<_ACL>(&v20);
    TPointer<_ACL>::~TPointer<_ACL>(&v21);
    TPointer<_TOKEN_USER>::~TPointer<_TOKEN_USER>(&v15);
    goto LABEL_46;
  }
  v1 = GetLastError();
  v2 = v1;
  if ( v1 > 0 )
    v2 = (unsigned __int16)v1 | 0x80070000;
LABEL_46:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140014348  push    rbp
0x14001434a  push    rbx
0x14001434b  push    rsi
0x14001434c  push    rdi
0x14001434d  push    r12
0x14001434f  push    r13
0x140014351  push    r14
0x140014353  push    r15
0x140014355  mov     rbp, rsp
0x140014358  sub     rsp, 68h
0x14001435c  xor     edx, edx
0x14001435e  mov     [rbp+TokenHandle], 0
0x140014366  lea     rcx, [rbp+TokenHandle]
0x14001436a  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x14001436f  call    cs:__imp_GetCurrentProcess
0x140014375  lea     r8, [rbp+TokenHandle]; TokenHandle
0x140014379  mov     edx, 8; DesiredAccess
0x14001437e  mov     rcx, rax; ProcessHandle
0x140014381  call    cs:__imp_OpenProcessToken
0x140014387  test    eax, eax
0x140014389  jnz     short loc_1400143AC
0x14001438b  call    cs:__imp_GetLastError
0x140014391  mov     r14d, eax
0x140014394  test    eax, eax
0x140014396  jle     loc_140014687
0x14001439c  movzx   r14d, ax
0x1400143a0  or      r14d, 80070000h
0x1400143a7  jmp     loc_140014687
0x1400143ac  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1400143b0  lea     rax, [rbp+TokenInformationLength]
0x1400143b4  xor     edi, edi
0x1400143b6  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x1400143bb  xor     esi, esi
0x1400143bd  mov     [rbp+var_38], rdi
0x1400143c1  xor     r9d, r9d; TokenInformationLength
0x1400143c4  mov     [rbp+arg_18], rsi
0x1400143c8  xor     r8d, r8d; TokenInformation
0x1400143cb  mov     [rbp+TokenInformationLength], esi
0x1400143ce  lea     ebx, [rdi+1]
0x1400143d1  mov     edx, ebx; TokenInformationClass
0x1400143d3  call    cs:__imp_GetTokenInformation
0x1400143d9  call    cs:__imp_GetLastError
0x1400143df  mov     r13d, 8007000Eh
0x1400143e5  mov     r14d, eax
0x1400143e8  lea     r15d, [r13-0Eh]
0x1400143ec  cmp     eax, 7Ah ; 'z'
0x1400143ef  jz      short loc_140014407
0x1400143f1  test    eax, eax
0x1400143f3  jle     short loc_1400143FC
0x1400143f5  movzx   r14d, ax
0x1400143f9  or      r14d, r15d
0x1400143fc  test    r14d, r14d
0x1400143ff  js      loc_1400144D9
0x140014405  jmp     short loc_140014429
0x140014407  mov     ecx, [rbp+TokenInformationLength]; unsigned __int64
0x14001440a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140014411  xor     r14d, r14d
0x140014414  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140014419  mov     [rbp+var_38], rax
0x14001441d  mov     rdi, rax
0x140014420  test    rax, rax
0x140014423  jz      loc_140014659
0x140014429  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x14001442d  lea     rax, [rbp+TokenInformationLength]
0x140014431  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x140014435  mov     r8, rdi; TokenInformation
0x140014438  mov     edx, ebx; TokenInformationClass
0x14001443a  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x14001443f  call    cs:__imp_GetTokenInformation
0x140014445  test    eax, eax
0x140014447  jnz     short loc_140014462
0x140014449  call    cs:__imp_GetLastError
0x14001444f  mov     r14d, eax
0x140014452  test    eax, eax
0x140014454  jle     short loc_14001445D
0x140014456  movzx   r14d, ax
0x14001445a  or      r14d, r15d
0x14001445d  test    r14d, r14d
0x140014460  js      short loc_1400144D9
0x140014462  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x140014466  lea     rax, [rbp+TokenInformationLength]
0x14001446a  xor     r9d, r9d; TokenInformationLength
0x14001446d  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x140014472  xor     r8d, r8d; TokenInformation
0x140014475  lea     ebx, [r9+5]
0x140014479  mov     edx, ebx; TokenInformationClass
0x14001447b  call    cs:__imp_GetTokenInformation
0x140014481  call    cs:__imp_GetLastError
0x140014487  cmp     eax, 7Ah ; 'z'
0x14001448a  jz      loc_14001463A
0x140014490  test    eax, eax
0x140014492  jg      short loc_140014499
0x140014494  mov     r14d, eax
0x140014497  jmp     short loc_1400144A0
0x140014499  movzx   r14d, ax
0x14001449d  or      r14d, r15d
0x1400144a0  test    r14d, r14d
0x1400144a3  js      short loc_1400144D9
0x1400144a5  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1400144a9  lea     rax, [rbp+TokenInformationLength]
0x1400144ad  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1400144b1  mov     r8, rsi; TokenInformation
0x1400144b4  mov     edx, ebx; TokenInformationClass
0x1400144b6  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x1400144bb  call    cs:__imp_GetTokenInformation
0x1400144c1  test    eax, eax
0x1400144c3  jnz     short loc_1400144D9
0x1400144c5  call    cs:__imp_GetLastError
0x1400144cb  mov     r14d, eax
0x1400144ce  test    eax, eax
0x1400144d0  jle     short loc_1400144D9
0x1400144d2  movzx   r14d, ax
0x1400144d6  or      r14d, r15d
0x1400144d9  xor     ebx, ebx
0x1400144db  xor     r12d, r12d
0x1400144de  mov     [rbp+arg_10], rbx
0x1400144e2  test    r14d, r14d
0x1400144e5  js      short loc_140014511
0x1400144e7  mov     rcx, [rdi]; pSid
0x1400144ea  call    cs:__imp_GetLengthSid
0x1400144f0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400144f7  lea     r12d, [rax+10h]
0x1400144fb  mov     ecx, r12d; unsigned __int64
0x1400144fe  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140014503  test    rax, rax
0x140014506  mov     [rbp+arg_10], rax
0x14001450a  mov     rbx, rax
0x14001450d  cmovz   r14d, r13d
0x140014511  xor     eax, eax
0x140014513  xorps   xmm0, xmm0
0x140014516  mov     [rbp+var_10], rax
0x14001451a  movups  [rbp+pSecurityDescriptor], xmm0
0x14001451e  movups  [rbp+var_20], xmm0
0x140014522  test    r14d, r14d
0x140014525  js      loc_14001466C
0x14001452b  lea     edx, [rax+1]; dwRevision
0x14001452e  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x140014532  call    cs:__imp_InitializeSecurityDescriptor
0x140014538  test    eax, eax
0x14001453a  jz      short loc_1400145AB
0x14001453c  mov     rdx, [rdi]; pOwner
0x14001453f  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x140014543  xor     r8d, r8d; bOwnerDefaulted
0x140014546  call    cs:__imp_SetSecurityDescriptorOwner
0x14001454c  test    eax, eax
0x14001454e  jz      short loc_1400145AB
0x140014550  mov     rdx, [rsi]; pGroup
0x140014553  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x140014557  xor     r8d, r8d; bGroupDefaulted
0x14001455a  call    cs:__imp_SetSecurityDescriptorGroup
0x140014560  test    eax, eax
0x140014562  jz      short loc_1400145AB
0x140014564  mov     esi, 2
0x140014569  mov     edx, r12d; nAclLength
0x14001456c  mov     r8d, esi; dwAclRevision
0x14001456f  mov     rcx, rbx; pAcl
0x140014572  call    cs:__imp_InitializeAcl
0x140014578  test    eax, eax
0x14001457a  jz      short loc_1400145AB
0x14001457c  mov     r9, [rdi]; pSid
0x14001457f  mov     r8d, 1F0081h; AccessMask
0x140014585  mov     edx, esi; dwAceRevision
0x140014587  mov     rcx, rbx; pAcl
0x14001458a  call    cs:__imp_AddAccessAllowedAce
0x140014590  test    eax, eax
0x140014592  jz      short loc_1400145AB
0x140014594  xor     r9d, r9d; bDaclDefaulted
0x140014597  lea     edx, [rsi-1]; bDaclPresent
0x14001459a  mov     r8, rbx; pDacl
0x14001459d  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x1400145a1  call    cs:__imp_SetSecurityDescriptorDacl
0x1400145a7  test    eax, eax
0x1400145a9  jnz     short loc_1400145C8
0x1400145ab  call    cs:__imp_GetLastError
0x1400145b1  mov     r14d, eax
0x1400145b4  test    eax, eax
0x1400145b6  jle     short loc_1400145BF
0x1400145b8  movzx   r14d, ax
0x1400145bc  or      r14d, r15d
0x1400145bf  test    r14d, r14d
0x1400145c2  js      loc_14001466C
0x1400145c8  lea     r8, ?g_perUserSDLength@@3KA; lpdwBufferLength
0x1400145cf  xor     edx, edx; pSelfRelativeSecurityDescriptor
0x1400145d1  lea     rcx, [rbp+pSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x1400145d5  call    cs:__imp_MakeSelfRelativeSD
0x1400145db  test    eax, eax
0x1400145dd  jnz     loc_140014666
0x1400145e3  call    cs:__imp_GetLastError
0x1400145e9  cmp     eax, 7Ah ; 'z'
0x1400145ec  jnz     short loc_140014624
0x1400145ee  mov     ecx, cs:?g_perUserSDLength@@3KA; unsigned __int64
0x1400145f4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400145fb  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140014600  mov     cs:?g_perUserSD@@3PEAU_SECURITY_DESCRIPTOR@@EA, rax; _SECURITY_DESCRIPTOR * g_perUserSD
0x140014607  test    rax, rax
0x14001460a  jz      short loc_140014661
0x14001460c  lea     r8, ?g_perUserSDLength@@3KA; lpdwBufferLength
0x140014613  mov     rdx, rax; pSelfRelativeSecurityDescriptor
0x140014616  lea     rcx, [rbp+pSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x14001461a  call    cs:__imp_MakeSelfRelativeSD
0x140014620  test    eax, eax
0x140014622  jnz     short loc_14001466C
0x140014624  call    cs:__imp_GetLastError
0x14001462a  mov     r14d, eax
0x14001462d  test    eax, eax
0x14001462f  jle     short loc_14001466C
0x140014631  movzx   r14d, ax
0x140014635  or      r14d, r15d
0x140014638  jmp     short loc_14001466C
0x14001463a  mov     ecx, [rbp+TokenInformationLength]; unsigned __int64
0x14001463d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140014644  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140014649  mov     [rbp+arg_18], rax
0x14001464d  mov     rsi, rax
0x140014650  test    rax, rax
0x140014653  jnz     loc_1400144A5
0x140014659  mov     r14d, r13d
0x14001465c  jmp     loc_1400144D9
0x140014661  mov     r14d, r13d
0x140014664  jmp     short loc_14001466C
0x140014666  mov     r14d, 80004005h
0x14001466c  lea     rcx, [rbp+arg_10]
0x140014670  call    ??1?$TPointer@U_ACL@@@@QEAA@XZ; TPointer<_ACL>::~TPointer<_ACL>(void)
0x140014675  lea     rcx, [rbp+arg_18]
0x140014679  call    ??1?$TPointer@U_ACL@@@@QEAA@XZ; TPointer<_ACL>::~TPointer<_ACL>(void)
0x14001467e  lea     rcx, [rbp+var_38]
0x140014682  call    ??1?$TPointer@U_TOKEN_USER@@@@QEAA@XZ; TPointer<_TOKEN_USER>::~TPointer<_TOKEN_USER>(void)
0x140014687  lea     rcx, [rbp+TokenHandle]
0x14001468b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x140014690  mov     eax, r14d
0x140014693  add     rsp, 68h
0x140014697  pop     r15
0x140014699  pop     r14
0x14001469b  pop     r13
0x14001469d  pop     r12
0x14001469f  pop     rdi
0x1400146a0  pop     rsi
0x1400146a1  pop     rbx
0x1400146a2  pop     rbp
0x1400146a3  retn
```
