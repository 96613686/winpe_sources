# StoredIdentity::StoredIdentity(std::shared_ptr<Nexus>)

- ea: `0x1800336cc`
- end: `0x180033a36`
- name: `??0StoredIdentity@@QEAA@V?$shared_ptr@VNexus@@@std@@@Z`
- size: `874`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180033534`
- `0x18006c63c`
- `0x1800704d8`

## callees

- `0x1800104c8`
- `0x180013b50`
- `0x1800336cc`
- `0x180033a3c`
- `0x180043324`
- `0x180075e60`
- `0x180076300`
- `0x180076e64`
- `0x180082410`
- `0x18008a400`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800337b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800337b4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800337aa`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180033806`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003393c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003396a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800337aa`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180033806`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003393c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003396a`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18003383d`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800338b6`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18003383d`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800338b6`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180033864`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800338dd`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180033864`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800338dd`

## string_xrefs

- `0x1800338f0`: `Capturing identity for LocalService, this probably isn't intended`
- `0x180033877`: `Capturing identity for LocalSystem, this probably isn't intended`
- `0x180033990`: `Capturing identity with too weak an impersonation level, this isn't intended`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall StoredIdentity::StoredIdentity(__int64 a1, _QWORD *a2)
{
  __int64 v4; // rax
  const char *v5; // r9
  PSID *v7; // rsi
  const char *v8; // r9
  const char *v9; // r9
  const char *v10; // r9
  int *v11; // r14
  const struct std::nothrow_t *v12; // rdx
  const char *v13; // r9
  const struct std::nothrow_t *v14; // rdx
  volatile signed __int32 *v15; // rdi
  DWORD TokenInformationLength; // [rsp+30h] [rbp-49h] BYREF
  DWORD cbSid; // [rsp+34h] [rbp-45h] BYREF
  __int64 v19; // [rsp+38h] [rbp-41h]
  _QWORD *v20; // [rsp+40h] [rbp-39h]
  PSID *v21; // [rsp+48h] [rbp-31h]
  int *v22; // [rsp+50h] [rbp-29h]
  _BYTE pSid[80]; // [rsp+60h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v19 = a1;
  v20 = a2;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ILicenseIdentityContext,ILicenseIdentityInternal>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ILicenseIdentityContext,ILicenseIdentityInternal>();
  *(_QWORD *)a1 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ILicenseIdentityContext,ILicenseIdentityInternal>::`vftable'{for `ILicenseIdentityContext'};
  *(_QWORD *)(a1 + 8) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ILicenseIdentityContext,ILicenseIdentityInternal>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ILicenseIdentityInternal>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)a1 = &StoredIdentity::`vftable'{for `ILicenseIdentityContext'};
  *(_QWORD *)(a1 + 8) = &StoredIdentity::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ILicenseIdentityInternal>'};
  *(_QWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  v4 = a2[1];
  if ( v4 )
    _InterlockedAdd((volatile signed __int32 *)(v4 + 8), 1u);
  *(_QWORD *)(a1 + 24) = *a2;
  *(_QWORD *)(a1 + 32) = a2[1];
  GetEffectiveToken(a1 + 40);
  *(_WORD *)(a1 + 56) = 257;
  TokenInformationLength = 0;
  if ( !GetTokenInformation(*(HANDLE *)(a1 + 48), TokenUser, 0, 0, &TokenInformationLength) && GetLastError() != 122 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x20C,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\identity.cpp",
      v5);
  v7 = (PSID *)operator new[](TokenInformationLength);
  v21 = v7;
  if ( !GetTokenInformation(*(HANDLE *)(a1 + 48), TokenUser, v7, TokenInformationLength, &TokenInformationLength) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x20E,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\identity.cpp",
      v8);
  cbSid = 68;
  if ( !CreateWellKnownSid(WinLocalSystemSid, 0, pSid, &cbSid) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x213,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\identity.cpp",
      v9);
  if ( EqualSid(pSid, *v7) )
  {
    if ( !IsMultiuserPlatform() )
      LogMessage(
        2u,
        "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\identity.cpp",
        0x218u,
        "StoredIdentity::StoredIdentity",
        (wchar_t *)L"Capturing identity for LocalSystem, this probably isn't intended");
    *(_BYTE *)(a1 + 56) = 0;
  }
  cbSid = 68;
  if ( !CreateWellKnownSid(WinLocalServiceSid, 0, pSid, &cbSid) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x21D,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\identity.cpp",
      v10);
  if ( EqualSid(pSid, *v7) )
  {
    if ( !(unsigned __int8)IsCompareContentIdPresent() )
      LogMessage(
        2u,
        "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\identity.cpp",
        0x222u,
        "StoredIdentity::StoredIdentity",
        (wchar_t *)L"Capturing identity for LocalService, this probably isn't intended");
    *(_BYTE *)(a1 + 56) = 0;
  }
  TokenInformationLength = 0;
  GetTokenInformation(*(HANDLE *)(a1 + 48), TokenImpersonationLevel, 0, 0, &TokenInformationLength);
  v11 = (int *)operator new[](TokenInformationLength);
  v22 = v11;
  if ( !GetTokenInformation(
          *(HANDLE *)(a1 + 48),
          TokenImpersonationLevel,
          v11,
          TokenInformationLength,
          &TokenInformationLength) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x22A,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\identity.cpp",
      v13);
  if ( *v11 < 2 )
  {
    LogMessage(
      2u,
      "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\identity.cpp",
      0x22Eu,
      "StoredIdentity::StoredIdentity",
      (wchar_t *)L"Capturing identity with too weak an impersonation level, this isn't intended");
    *(_BYTE *)(a1 + 57) = 0;
  }
  operator delete(v11, v12);
  operator delete(v7, v14);
  v15 = (volatile signed __int32 *)a2[1];
  if ( v15 )
  {
    if ( _InterlockedExchangeAdd(v15 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
      if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x1800336cc  mov     [rsp-8+arg_10], rbx
0x1800336d1  mov     [rsp-8+arg_18], rsi
0x1800336d6  push    rbp
0x1800336d7  push    rdi
0x1800336d8  push    r14
0x1800336da  lea     rbp, [rsp-47h]
0x1800336df  sub     rsp, 0C0h
0x1800336e6  mov     rax, cs:__security_cookie
0x1800336ed  xor     rax, rsp
0x1800336f0  mov     [rbp+57h+var_20], rax
0x1800336f4  mov     rdi, rdx
0x1800336f7  mov     rbx, rcx
0x1800336fa  mov     [rbp+57h+var_98], rcx
0x1800336fe  mov     [rbp+57h+var_90], rdx
0x180033702  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UILicenseIdentityContext@@UILicenseIdentityInternal@@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ILicenseIdentityContext,ILicenseIdentityInternal>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ILicenseIdentityContext,ILicenseIdentityInternal>(void)
0x180033707  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UILicenseIdentityContext@@UILicenseIdentityInternal@@@WRL@Microsoft@@6BILicenseIdentityContext@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ILicenseIdentityContext,ILicenseIdentityInternal>::`vftable'{for `ILicenseIdentityContext'}
0x18003370e  mov     [rbx], rcx
0x180033711  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UILicenseIdentityContext@@UILicenseIdentityInternal@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UILicenseIdentityInternal@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ILicenseIdentityContext,ILicenseIdentityInternal>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ILicenseIdentityInternal>'}
0x180033718  mov     [rbx+8], rax
0x18003371c  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180033723  test    rcx, rcx
0x180033726  jz      short loc_180033735
0x180033728  mov     rax, [rcx]
0x18003372b  mov     rax, [rax+8]
0x18003372f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033734  nop
0x180033735  lea     rax, ??_7StoredIdentity@@6BILicenseIdentityContext@@@; const StoredIdentity::`vftable'{for `ILicenseIdentityContext'}
0x18003373c  mov     [rbx], rax
0x18003373f  lea     rax, ??_7StoredIdentity@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UILicenseIdentityInternal@@@Details@WRL@Microsoft@@@; const StoredIdentity::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ILicenseIdentityInternal>'}
0x180033746  mov     [rbx+8], rax
0x18003374a  mov     qword ptr [rbx+18h], 0
0x180033752  mov     qword ptr [rbx+20h], 0
0x18003375a  mov     rax, [rdi+8]
0x18003375e  mov     r14d, 1
0x180033764  test    rax, rax
0x180033767  jz      short loc_18003376E
0x180033769  lock add [rax+8], r14d
0x18003376e  mov     rax, [rdi]
0x180033771  mov     [rbx+18h], rax
0x180033775  mov     rax, [rdi+8]
0x180033779  mov     [rbx+20h], rax
0x18003377d  lea     rcx, [rbx+28h]
0x180033781  call    ?GetEffectiveToken@@YA?AV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@XZ; GetEffectiveToken(void)
0x180033786  nop
0x180033787  mov     word ptr [rbx+38h], 101h
0x18003378d  mov     [rbp+57h+TokenInformationLength], 0
0x180033794  lea     rax, [rbp+57h+TokenInformationLength]
0x180033798  mov     [rsp+0D0h+ReturnLength], rax; ReturnLength
0x18003379d  xor     r9d, r9d; TokenInformationLength
0x1800337a0  xor     r8d, r8d; TokenInformation
0x1800337a3  mov     edx, r14d; TokenInformationClass
0x1800337a6  mov     rcx, [rbx+30h]; TokenHandle
0x1800337aa  call    cs:__imp_GetTokenInformation
0x1800337b0  test    eax, eax
0x1800337b2  jnz     short loc_1800337C4
0x1800337b4  call    cs:__imp_GetLastError
0x1800337ba  cmp     eax, 7Ah ; 'z'
0x1800337bd  jz      short loc_1800337C4
0x1800337bf  mov     al, r14b
0x1800337c2  jmp     short loc_1800337C6
0x1800337c4  xor     al, al
0x1800337c6  mov     rcx, [rbp+5Fh]; this
0x1800337ca  test    al, al
0x1800337cc  jz      short loc_1800337E0
0x1800337ce  lea     r8, aOnecoreuapEndu_34; "onecoreuap\\enduser\\winstore\\licensem"...
0x1800337d5  mov     edx, 20Ch; void *
0x1800337da  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800337e0  mov     ecx, [rbp+57h+TokenInformationLength]; unsigned __int64
0x1800337e3  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800337e8  mov     rsi, rax
0x1800337eb  mov     [rbp+57h+var_88], rax
0x1800337ef  lea     rax, [rbp+57h+TokenInformationLength]
0x1800337f3  mov     [rsp+0D0h+ReturnLength], rax; ReturnLength
0x1800337f8  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x1800337fc  mov     r8, rsi; TokenInformation
0x1800337ff  mov     edx, r14d; TokenInformationClass
0x180033802  mov     rcx, [rbx+30h]; TokenHandle
0x180033806  call    cs:__imp_GetTokenInformation
0x18003380c  mov     rcx, [rbp+5Fh]; this
0x180033810  test    eax, eax
0x180033812  jnz     short loc_180033826
0x180033814  lea     r8, aOnecoreuapEndu_34; "onecoreuap\\enduser\\winstore\\licensem"...
0x18003381b  mov     edx, 20Eh; void *
0x180033820  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180033826  mov     r14d, 44h ; 'D'
0x18003382c  mov     [rbp+57h+cbSid], r14d
0x180033830  lea     r9, [rbp+57h+cbSid]; cbSid
0x180033834  lea     r8, [rbp+57h+pSid]; pSid
0x180033838  xor     edx, edx; DomainSid
0x18003383a  lea     ecx, [rdx+16h]; WellKnownSidType
0x18003383d  call    cs:__imp_CreateWellKnownSid
0x180033843  mov     rcx, [rbp+5Fh]; this
0x180033847  test    eax, eax
0x180033849  jnz     short loc_18003385D
0x18003384b  lea     r8, aOnecoreuapEndu_34; "onecoreuap\\enduser\\winstore\\licensem"...
0x180033852  mov     edx, 213h; void *
0x180033857  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18003385d  mov     rdx, [rsi]; pSid2
0x180033860  lea     rcx, [rbp+57h+pSid]; pSid1
0x180033864  call    cs:__imp_EqualSid
0x18003386a  test    eax, eax
0x18003386c  jz      short loc_1800338A5
0x18003386e  call    ?IsMultiuserPlatform@@YA_NXZ; IsMultiuserPlatform(void)
0x180033873  test    al, al
0x180033875  jnz     short loc_1800338A1
0x180033877  lea     rax, aCapturingIdent; "Capturing identity for LocalSystem, thi"...
0x18003387e  mov     [rsp+0D0h+ReturnLength], rax; Format
0x180033883  lea     r9, aStoredidentity_0; "StoredIdentity::StoredIdentity"
0x18003388a  mov     r8d, 218h; unsigned int
0x180033890  lea     rdx, aOnecoreuapEndu_34; "onecoreuap\\enduser\\winstore\\licensem"...
0x180033897  mov     ecx, 2; unsigned int
0x18003389c  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x1800338a1  mov     byte ptr [rbx+38h], 0
0x1800338a5  mov     [rbp+57h+cbSid], r14d
0x1800338a9  lea     r9, [rbp+57h+cbSid]; cbSid
0x1800338ad  lea     r8, [rbp+57h+pSid]; pSid
0x1800338b1  xor     edx, edx; DomainSid
0x1800338b3  lea     ecx, [rdx+17h]; WellKnownSidType
0x1800338b6  call    cs:__imp_CreateWellKnownSid
0x1800338bc  mov     rcx, [rbp+5Fh]; this
0x1800338c0  test    eax, eax
0x1800338c2  jnz     short loc_1800338D6
0x1800338c4  lea     r8, aOnecoreuapEndu_34; "onecoreuap\\enduser\\winstore\\licensem"...
0x1800338cb  mov     edx, 21Dh; void *
0x1800338d0  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800338d6  mov     rdx, [rsi]; pSid2
0x1800338d9  lea     rcx, [rbp+57h+pSid]; pSid1
0x1800338dd  call    cs:__imp_EqualSid
0x1800338e3  test    eax, eax
0x1800338e5  jz      short loc_18003391E
0x1800338e7  call    IsCompareContentIdPresent
0x1800338ec  test    al, al
0x1800338ee  jnz     short loc_18003391A
0x1800338f0  lea     rax, aCapturingIdent_1; "Capturing identity for LocalService, th"...
0x1800338f7  mov     [rsp+0D0h+ReturnLength], rax; Format
0x1800338fc  lea     r9, aStoredidentity_0; "StoredIdentity::StoredIdentity"
0x180033903  mov     r8d, 222h; unsigned int
0x180033909  lea     rdx, aOnecoreuapEndu_34; "onecoreuap\\enduser\\winstore\\licensem"...
0x180033910  mov     ecx, 2; unsigned int
0x180033915  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x18003391a  mov     byte ptr [rbx+38h], 0
0x18003391e  mov     [rbp+57h+TokenInformationLength], 0
0x180033925  lea     rax, [rbp+57h+TokenInformationLength]
0x180033929  mov     [rsp+0D0h+ReturnLength], rax; ReturnLength
0x18003392e  xor     r9d, r9d; TokenInformationLength
0x180033931  xor     r8d, r8d; TokenInformation
0x180033934  lea     edx, [r9+9]; TokenInformationClass
0x180033938  mov     rcx, [rbx+30h]; TokenHandle
0x18003393c  call    cs:__imp_GetTokenInformation
0x180033942  mov     ecx, [rbp+57h+TokenInformationLength]; unsigned __int64
0x180033945  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18003394a  mov     r14, rax
0x18003394d  mov     [rbp+57h+var_80], rax
0x180033951  lea     rax, [rbp+57h+TokenInformationLength]
0x180033955  mov     [rsp+0D0h+ReturnLength], rax; ReturnLength
0x18003395a  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x18003395e  mov     r8, r14; TokenInformation
0x180033961  mov     edx, 9; TokenInformationClass
0x180033966  mov     rcx, [rbx+30h]; TokenHandle
0x18003396a  call    cs:__imp_GetTokenInformation
0x180033970  mov     rcx, [rbp+5Fh]; this
0x180033974  test    eax, eax
0x180033976  jnz     short loc_18003398A
0x180033978  lea     r8, aOnecoreuapEndu_34; "onecoreuap\\enduser\\winstore\\licensem"...
0x18003397f  mov     edx, 22Ah; void *
0x180033984  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18003398a  cmp     dword ptr [r14], 2
0x18003398e  jge     short loc_1800339BE
0x180033990  lea     rax, aCapturingIdent_0; "Capturing identity with too weak an imp"...
0x180033997  mov     [rsp+0D0h+ReturnLength], rax; Format
0x18003399c  lea     r9, aStoredidentity_0; "StoredIdentity::StoredIdentity"
0x1800339a3  mov     r8d, 22Eh; unsigned int
0x1800339a9  lea     rdx, aOnecoreuapEndu_34; "onecoreuap\\enduser\\winstore\\licensem"...
0x1800339b0  mov     ecx, 2; unsigned int
0x1800339b5  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x1800339ba  mov     byte ptr [rbx+39h], 0
0x1800339be  mov     rcx, r14; void *
0x1800339c1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800339c6  nop
0x1800339c7  mov     rcx, rsi; void *
0x1800339ca  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800339cf  nop
0x1800339d0  mov     rdi, [rdi+8]
0x1800339d4  test    rdi, rdi
0x1800339d7  jz      short loc_180033A0F
0x1800339d9  or      esi, 0FFFFFFFFh
0x1800339dc  mov     eax, esi
0x1800339de  lock xadd [rdi+8], eax
0x1800339e3  add     eax, esi
0x1800339e5  jnz     short loc_180033A0F
0x1800339e7  mov     rax, [rdi]
0x1800339ea  mov     rcx, rdi
0x1800339ed  mov     rax, [rax]
0x1800339f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800339f5  mov     edx, esi
0x1800339f7  lock xadd [rdi+0Ch], edx
0x1800339fc  add     edx, esi
0x1800339fe  jnz     short loc_180033A0F
0x180033a00  mov     rdx, [rdi]
0x180033a03  mov     rcx, rdi
0x180033a06  mov     rax, [rdx+8]
0x180033a0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033a0f  mov     rax, rbx
0x180033a12  mov     rcx, [rbp+57h+var_20]
0x180033a16  xor     rcx, rsp; StackCookie
0x180033a19  call    __security_check_cookie
0x180033a1e  lea     r11, [rsp+0D0h+var_10]
0x180033a26  mov     rbx, [r11+30h]
0x180033a2a  mov     rsi, [r11+38h]
0x180033a2e  mov     rsp, r11
0x180033a31  pop     r14
0x180033a33  pop     rdi
0x180033a34  pop     rbp
0x180033a35  retn
```
