# SetEfsCacheRegkeyAccess(HKEY__ *)

- ea: `0x1802097e0`
- end: `0x180209a75`
- name: `?SetEfsCacheRegkeyAccess@@YAJPEAUHKEY__@@@Z`
- size: `661`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180209ab4`

## callees

- `0x180022710`
- `0x1800eb1b0`
- `0x1801244c0`
- `0x18012540e`
- `0x1802097e0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180209a4e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180209a4e`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x180209a22`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x180209a22`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1802099cf`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1802099cf`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1802099e9`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1802099e9`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180209834`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18020985e`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180209888`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1802098b2`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180209834`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18020985e`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180209888`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1802098b2`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorControl` at `0x180209a00`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorControl` at `0x180209a00`
- `api-ms-win-security-trustee-l1-1-1!BuildExplicitAccessWithNameW` at `0x180209902`
- `api-ms-win-security-trustee-l1-1-1!BuildExplicitAccessWithNameW` at `0x180209939`
- `api-ms-win-security-trustee-l1-1-1!BuildExplicitAccessWithNameW` at `0x180209902`
- `api-ms-win-security-trustee-l1-1-1!BuildExplicitAccessWithNameW` at `0x180209939`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18020998a`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18020998a`

## pseudocode

```c
__int64 __fastcall SetEfsCacheRegkeyAccess(HKEY hKey)
{
  signed int Error; // ebx
  __int64 v3; // rdi
  __int64 i; // rsi
  WCHAR *v5; // rcx
  signed int v6; // edi
  LSTATUS v7; // eax
  PACL v8; // rcx
  DWORD cbSid; // [rsp+30h] [rbp-D0h] BYREF
  PACL pDacl; // [rsp+38h] [rbp-C8h] BYREF
  PACL *p_pDacl; // [rsp+40h] [rbp-C0h] BYREF
  PACL NewAcl; // [rsp+48h] [rbp-B8h] BYREF
  char v14; // [rsp+50h] [rbp-B0h]
  _OWORD pSecurityDescriptor[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v16; // [rsp+78h] [rbp-88h]
  struct _EXPLICIT_ACCESS_W pExplicitAccess[4]; // [rsp+80h] [rbp-80h] BYREF
  _DWORD pSid[17]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v19[68]; // [rsp+184h] [rbp+84h] BYREF
  _BYTE v20[68]; // [rsp+1C8h] [rbp+C8h] BYREF
  _BYTE v21[68]; // [rsp+20Ch] [rbp+10Ch] BYREF

  Error = 0;
  memset_0(pSid, 0, 0x110u);
  cbSid = 68;
  if ( !CreateWellKnownSid(WinLocalSystemSid, 0, pSid, &cbSid) )
    Error = ResultFromLastError();
  cbSid = 68;
  if ( Error >= 0 && !CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, v19, &cbSid) )
    Error = ResultFromLastError();
  cbSid = 68;
  if ( Error >= 0 && !CreateWellKnownSid(WinBuiltinPowerUsersSid, 0, v20, &cbSid) )
    Error = ResultFromLastError();
  cbSid = 68;
  if ( Error >= 0 && !CreateWellKnownSid(WinBuiltinUsersSid, 0, v21, &cbSid) )
    Error = ResultFromLastError();
  pDacl = 0;
  if ( Error >= 0 )
  {
    memset_0(pExplicitAccess, 0, sizeof(pExplicitAccess));
    BuildExplicitAccessWithNameW(pExplicitAccess, 0, 0xF003Fu, GRANT_ACCESS, 3u);
    pExplicitAccess[0].Trustee.TrusteeForm = TRUSTEE_IS_SID;
    pExplicitAccess[0].Trustee.ptstrName = (LPWCH)pSid;
    v3 = 1;
    for ( i = 1; i != 4; ++i )
    {
      BuildExplicitAccessWithNameW(&pExplicitAccess[v3], 0, 0x20019u, GRANT_ACCESS, 3u);
      pExplicitAccess[v3].Trustee.TrusteeForm = TRUSTEE_IS_SID;
      v5 = (WCHAR *)&pSid[17 * i];
      pExplicitAccess[v3++].Trustee.ptstrName = v5;
    }
    NewAcl = 0;
    p_pDacl = &pDacl;
    v14 = 1;
    v6 = SetEntriesInAclW(4u, pExplicitAccess, 0, &NewAcl);
    wil::details::out_param_t<wistd::unique_ptr<wchar_t,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<wchar_t,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_pDacl);
    if ( v6 )
    {
      if ( v6 > 0 )
        Error = (unsigned __int16)v6 | 0x80070000;
      else
        Error = v6;
    }
  }
  v16 = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  if ( Error >= 0 )
  {
    if ( InitializeSecurityDescriptor(pSecurityDescriptor, 1u)
      && SetSecurityDescriptorDacl(pSecurityDescriptor, 1, pDacl, 0)
      && SetSecurityDescriptorControl(pSecurityDescriptor, 0x1000u, 0x1000u)
      || (Error = ResultFromLastError(), Error >= 0) )
    {
      v7 = RegSetKeySecurity(hKey, 4u, pSecurityDescriptor);
      if ( v7 )
      {
        if ( v7 > 0 )
          Error = (unsigned __int16)v7 | 0x80070000;
        else
          Error = v7;
      }
    }
  }
  v8 = pDacl;
  pDacl = 0;
  if ( v8 )
    LocalFree(v8);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1802097e0  push    rbp
0x1802097e2  push    rbx
0x1802097e3  push    rsi
0x1802097e4  push    rdi
0x1802097e5  push    r12
0x1802097e7  push    r14
0x1802097e9  lea     rbp, [rsp-168h]
0x1802097f1  sub     rsp, 268h
0x1802097f8  mov     rax, cs:__security_cookie
0x1802097ff  xor     rax, rsp
0x180209802  mov     [rbp+190h+var_40], rax
0x180209809  mov     r14, rcx
0x18020980c  xor     edx, edx; Val
0x18020980e  lea     rcx, [rbp+190h+pSid]; void *
0x180209812  mov     r8d, 110h; Size
0x180209818  xor     ebx, ebx
0x18020981a  call    memset_0
0x18020981f  lea     edi, [rbx+44h]
0x180209822  xor     edx, edx; DomainSid
0x180209824  lea     r9, [rsp+290h+cbSid]; cbSid
0x180209829  mov     [rsp+290h+cbSid], edi
0x18020982d  lea     r8, [rbp+190h+pSid]; pSid
0x180209831  lea     ecx, [rbx+16h]; WellKnownSidType
0x180209834  call    cs:__imp_CreateWellKnownSid
0x18020983a  test    eax, eax
0x18020983c  jnz     short loc_180209845
0x18020983e  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180209843  mov     ebx, eax
0x180209845  mov     [rsp+290h+cbSid], edi
0x180209849  test    ebx, ebx
0x18020984b  js      short loc_18020986F
0x18020984d  xor     edx, edx; DomainSid
0x18020984f  lea     r9, [rsp+290h+cbSid]; cbSid
0x180209854  lea     r8, [rbp+190h+var_10C]; pSid
0x18020985b  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x18020985e  call    cs:__imp_CreateWellKnownSid
0x180209864  test    eax, eax
0x180209866  jnz     short loc_18020986F
0x180209868  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18020986d  mov     ebx, eax
0x18020986f  mov     [rsp+290h+cbSid], edi
0x180209873  test    ebx, ebx
0x180209875  js      short loc_180209899
0x180209877  xor     edx, edx; DomainSid
0x180209879  lea     r9, [rsp+290h+cbSid]; cbSid
0x18020987e  lea     r8, [rbp+190h+var_C8]; pSid
0x180209885  lea     ecx, [rdx+1Dh]; WellKnownSidType
0x180209888  call    cs:__imp_CreateWellKnownSid
0x18020988e  test    eax, eax
0x180209890  jnz     short loc_180209899
0x180209892  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180209897  mov     ebx, eax
0x180209899  mov     [rsp+290h+cbSid], edi
0x18020989d  test    ebx, ebx
0x18020989f  js      short loc_1802098C3
0x1802098a1  xor     edx, edx; DomainSid
0x1802098a3  lea     r9, [rsp+290h+cbSid]; cbSid
0x1802098a8  lea     r8, [rbp+190h+var_84]; pSid
0x1802098af  lea     ecx, [rdx+1Bh]; WellKnownSidType
0x1802098b2  call    cs:__imp_CreateWellKnownSid
0x1802098b8  test    eax, eax
0x1802098ba  jnz     short loc_1802098C3
0x1802098bc  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1802098c1  mov     ebx, eax
0x1802098c3  mov     [rsp+290h+pDacl], 0
0x1802098cc  mov     r12d, 1
0x1802098d2  test    ebx, ebx
0x1802098d4  js      loc_1802099AF
0x1802098da  xor     edx, edx; Val
0x1802098dc  lea     rcx, [rbp+190h+pExplicitAccess]; void *
0x1802098e0  mov     r8d, 0C0h; Size
0x1802098e6  call    memset_0
0x1802098eb  mov     r9d, r12d; AccessMode
0x1802098ee  mov     [rsp+290h+Inheritance], 3; Inheritance
0x1802098f6  xor     edx, edx; pTrusteeName
0x1802098f8  lea     rcx, [rbp+190h+pExplicitAccess]; pExplicitAccess
0x1802098fc  mov     r8d, 0F003Fh; AccessPermissions
0x180209902  call    cs:__imp_BuildExplicitAccessWithNameW
0x180209908  lea     rax, [rbp+190h+pSid]
0x18020990c  mov     [rbp+190h+pExplicitAccess.Trustee.TrusteeForm], 0
0x180209913  mov     [rbp+190h+pExplicitAccess.Trustee.ptstrName], rax
0x180209917  lea     edi, [r12+2Fh]
0x18020991c  mov     esi, r12d
0x18020991f  lea     rcx, [rbp+190h+pExplicitAccess]
0x180209923  mov     [rsp+290h+Inheritance], 3; Inheritance
0x18020992b  add     rcx, rdi; pExplicitAccess
0x18020992e  mov     r9d, r12d; AccessMode
0x180209931  xor     edx, edx; pTrusteeName
0x180209933  mov     r8d, 20019h; AccessPermissions
0x180209939  call    cs:__imp_BuildExplicitAccessWithNameW
0x18020993f  imul    rax, rsi, 44h ; 'D'
0x180209943  lea     rcx, [rbp+190h+pSid]
0x180209947  mov     [rbp+rdi+190h+pExplicitAccess.Trustee.TrusteeForm], 0
0x18020994f  add     rcx, rax
0x180209952  add     rsi, r12
0x180209955  mov     [rbp+rdi+190h+pExplicitAccess.Trustee.ptstrName], rcx
0x18020995a  add     rdi, 30h ; '0'
0x18020995e  cmp     rsi, 4
0x180209962  jnz     short loc_18020991F
0x180209964  lea     rax, [rsp+290h+pDacl]
0x180209969  mov     [rsp+290h+NewAcl], 0
0x180209972  lea     r9, [rsp+290h+NewAcl]; NewAcl
0x180209977  mov     [rsp+290h+var_250], rax
0x18020997c  xor     r8d, r8d; OldAcl
0x18020997f  mov     [rsp+290h+var_240], r12b
0x180209984  lea     rdx, [rbp+190h+pExplicitAccess]; pListOfExplicitEntries
0x180209988  mov     ecx, esi; cCountOfExplicitEntries
0x18020998a  call    cs:__imp_SetEntriesInAclW
0x180209990  lea     rcx, [rsp+290h+var_250]
0x180209995  mov     edi, eax
0x180209997  call    ??1?$out_param_t@V?$unique_ptr@_WU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<wchar_t,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<wchar_t,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18020999c  test    edi, edi
0x18020999e  jz      short loc_1802099AF
0x1802099a0  jg      short loc_1802099A6
0x1802099a2  mov     ebx, edi
0x1802099a4  jmp     short loc_1802099AF
0x1802099a6  movzx   ebx, di
0x1802099a9  or      ebx, 80070000h
0x1802099af  xor     eax, eax
0x1802099b1  xorps   xmm0, xmm0
0x1802099b4  mov     [rsp+290h+var_218], rax
0x1802099b9  movups  [rsp+290h+pSecurityDescriptor], xmm0
0x1802099be  movups  [rsp+290h+var_228], xmm0
0x1802099c3  test    ebx, ebx
0x1802099c5  js      short loc_180209A3B
0x1802099c7  mov     edx, r12d; dwRevision
0x1802099ca  lea     rcx, [rsp+290h+pSecurityDescriptor]; pSecurityDescriptor
0x1802099cf  call    cs:__imp_InitializeSecurityDescriptor
0x1802099d5  test    eax, eax
0x1802099d7  jz      short loc_180209A0A
0x1802099d9  mov     r8, [rsp+290h+pDacl]; pDacl
0x1802099de  lea     rcx, [rsp+290h+pSecurityDescriptor]; pSecurityDescriptor
0x1802099e3  xor     r9d, r9d; bDaclDefaulted
0x1802099e6  mov     edx, r12d; bDaclPresent
0x1802099e9  call    cs:__imp_SetSecurityDescriptorDacl
0x1802099ef  test    eax, eax
0x1802099f1  jz      short loc_180209A0A
0x1802099f3  mov     edx, 1000h; ControlBitsOfInterest
0x1802099f8  lea     rcx, [rsp+290h+pSecurityDescriptor]; pSecurityDescriptor
0x1802099fd  mov     r8d, edx; ControlBitsToSet
0x180209a00  call    cs:__imp_SetSecurityDescriptorControl
0x180209a06  test    eax, eax
0x180209a08  jnz     short loc_180209A15
0x180209a0a  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180209a0f  mov     ebx, eax
0x180209a11  test    eax, eax
0x180209a13  js      short loc_180209A3B
0x180209a15  lea     r8, [rsp+290h+pSecurityDescriptor]; pSecurityDescriptor
0x180209a1a  mov     edx, 4; SecurityInformation
0x180209a1f  mov     rcx, r14; hKey
0x180209a22  call    cs:__imp_RegSetKeySecurity
0x180209a28  test    eax, eax
0x180209a2a  jz      short loc_180209A3B
0x180209a2c  jg      short loc_180209A32
0x180209a2e  mov     ebx, eax
0x180209a30  jmp     short loc_180209A3B
0x180209a32  movzx   ebx, ax
0x180209a35  or      ebx, 80070000h
0x180209a3b  mov     rcx, [rsp+290h+pDacl]; hMem
0x180209a40  mov     [rsp+290h+pDacl], 0
0x180209a49  test    rcx, rcx
0x180209a4c  jz      short loc_180209A54
0x180209a4e  call    cs:__imp_LocalFree
0x180209a54  mov     eax, ebx
0x180209a56  mov     rcx, [rbp+190h+var_40]
0x180209a5d  xor     rcx, rsp; StackCookie
0x180209a60  call    __security_check_cookie
0x180209a65  add     rsp, 268h
0x180209a6c  pop     r14
0x180209a6e  pop     r12
0x180209a70  pop     rdi
0x180209a71  pop     rsi
0x180209a72  pop     rbx
0x180209a73  pop     rbp
0x180209a74  retn
```
