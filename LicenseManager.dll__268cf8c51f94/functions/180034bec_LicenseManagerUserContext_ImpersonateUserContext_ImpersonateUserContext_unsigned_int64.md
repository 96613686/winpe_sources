# LicenseManagerUserContext::ImpersonateUserContext::ImpersonateUserContext(unsigned __int64)

- ea: `0x180034bec`
- end: `0x180034e5a`
- name: `??0ImpersonateUserContext@LicenseManagerUserContext@@QEAA@_K@Z`
- size: `622`
- prototype: `__int64 __fastcall(LicenseManagerUserContext::ImpersonateUserContext *__hidden this, unsigned __int64)`
- caller_count: `7`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180034930`
- `0x1800349c8`
- `0x1800349f0`
- `0x180034ad0`
- `0x180034b30`
- `0x1800496e0`
- `0x18006bf60`

## callees

- `0x18000b7a4`
- `0x1800104c8`
- `0x180013b50`
- `0x180034bec`
- `0x18003b09c`
- `0x18008a400`
- `0x18009336c`
- `0x1800933a8`
- `0x18009f05c`
- `0x1800ab4a0`
- `0x1800ab54c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180034cbc`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180034e28`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180034cbc`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180034e28`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180034c1f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180034c1f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180034c37`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180034c37`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrGetImpersonationTokenForContext` at `0x180034c63`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrGetImpersonationTokenForContext` at `0x180034c63`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x180034d9c`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x180034d9c`
- `ext-ms-win-session-usermgr-l1-2-1!UMgrGetStandardAccessImpersonationTokenForContext` at `0x180034dba`
- `ext-ms-win-session-usermgr-l1-2-1!UMgrGetStandardAccessImpersonationTokenForContext` at `0x180034dba`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180034c98`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180034df1`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180034c98`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180034df1`

## string_xrefs

- `0x180034ce8`: `LicenseManagerUserContext::ImpersonateUserContext::ImpersonateUserContext`
- `0x180034cdc`: `Got a user context but couldn't get the user token, things may not work well (0x%08x)`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
LicenseManagerUserContext::ImpersonateUserContext *__fastcall LicenseManagerUserContext::ImpersonateUserContext::ImpersonateUserContext(
        void **this,
        __int64 a2)
{
  HANDLE CurrentThread; // rax
  int ImpersonationTokenForContext; // eax
  const char *v6; // r9
  void **v8; // [rsp+30h] [rbp-30h] BYREF
  HANDLE TokenHandle; // [rsp+38h] [rbp-28h]
  void **v10; // [rsp+40h] [rbp-20h] BYREF
  HANDLE Token; // [rsp+48h] [rbp-18h] BYREF
  void **v12; // [rsp+50h] [rbp-10h] BYREF
  HANDLE hExistingToken; // [rsp+58h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  LicenseManagerUserContext::ImpersonateUserContext *v15; // [rsp+90h] [rbp+30h] BYREF
  int v16; // [rsp+98h] [rbp+38h]
  int v17; // [rsp+A0h] [rbp+40h]

  v15 = (LicenseManagerUserContext::ImpersonateUserContext *)this;
  *(_BYTE *)this = 0;
  this[1] = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  this[2] = 0;
  CurrentThread = GetCurrentThread();
  OpenThreadToken(CurrentThread, 0x2000Eu, 1, this + 2);
  GetEffectiveToken(&v8);
  if ( a2 )
  {
    v12 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
    hExistingToken = 0;
    ImpersonationTokenForContext = UMgrGetImpersonationTokenForContext(TokenHandle, a2, &hExistingToken);
    if ( ImpersonationTokenForContext >= 0 && hExistingToken )
    {
      v10 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
      Token = 0;
      if ( !DuplicateTokenEx(hExistingToken, 0x2000Eu, 0, SecurityImpersonation, TokenImpersonation, &Token) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x29,
          (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\usercontexthelper.h",
          v6);
      *(_BYTE *)this = SetThreadToken(0, Token);
      v10 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
      Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(&v10);
    }
    else
    {
      LogMessage(
        2u,
        "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\usercontexthelper.h",
        0x2Eu,
        "LicenseManagerUserContext::ImpersonateUserContext::ImpersonateUserContext",
        (wchar_t *)L"Got a user context but couldn't get the user token, things may not work well (0x%08x)",
        ImpersonationTokenForContext);
    }
    v12 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
    Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(&v12);
  }
  else
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl) )
    {
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_LicenseManagerShadowAdminOnesettingsCheck>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_LicenseManagerShadowAdminOnesettingsCheck>::GetImpl'::`2'::impl)
        || (UpdateLicenseManagerOneSettings(), !byte_1800F297C) )
      {
        v17 = 0;
        v16 = 0;
        if ( (unsigned int)LUAIsShadowAdminEnabled() )
        {
          if ( (int)LUAIsElevatedToken(TokenHandle) >= 0 )
          {
            if ( v16 )
            {
              if ( v17 )
              {
                v15 = 0;
                if ( (int)UMgrQueryUserContext(TokenHandle, &v15) >= 0 )
                {
                  v10 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
                  Token = 0;
                  if ( (int)UMgrGetStandardAccessImpersonationTokenForContext(TokenHandle, v15, &Token) >= 0 && Token )
                  {
                    v12 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
                    hExistingToken = 0;
                    if ( DuplicateTokenEx(
                           Token,
                           0x2000Eu,
                           0,
                           SecurityImpersonation,
                           TokenImpersonation,
                           &hExistingToken) )
                    {
                      Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::operator=(
                        &v8,
                        &v12);
                    }
                    v12 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
                    Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(&v12);
                  }
                  v10 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
                  Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(&v10);
                }
              }
            }
          }
        }
      }
    }
    *(_BYTE *)this = SetThreadToken(0, TokenHandle);
  }
  v8 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(&v8);
  return (LicenseManagerUserContext::ImpersonateUserContext *)this;
}

```

## disassembly

```asm
0x180034bec  mov     [rsp-28h+arg_18], rbx
0x180034bf1  mov     [rsp-28h+arg_0], rcx
0x180034bf6  push    rbp
0x180034bf7  push    rsi
0x180034bf8  push    rdi
0x180034bf9  push    r14
0x180034bfb  push    r15
0x180034bfd  mov     rbp, rsp
0x180034c00  sub     rsp, 60h
0x180034c04  mov     rsi, rdx
0x180034c07  mov     rdi, rcx
0x180034c0a  xor     r14d, r14d
0x180034c0d  mov     [rcx], r14b
0x180034c10  lea     r15, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x180034c17  mov     [rcx+8], r15
0x180034c1b  mov     [rcx+10h], r14
0x180034c1f  call    cs:__imp_GetCurrentThread
0x180034c25  lea     r9, [rdi+10h]; TokenHandle
0x180034c29  mov     ebx, 2000Eh
0x180034c2e  lea     r8d, [r14+1]; OpenAsSelf
0x180034c32  mov     edx, ebx; DesiredAccess
0x180034c34  mov     rcx, rax; ThreadHandle
0x180034c37  call    cs:__imp_OpenThreadToken
0x180034c3d  lea     rcx, [rbp+var_30]
0x180034c41  call    ?GetEffectiveToken@@YA?AV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@XZ; GetEffectiveToken(void)
0x180034c46  nop
0x180034c47  test    rsi, rsi
0x180034c4a  jz      loc_180034D18
0x180034c50  mov     [rbp+var_10], r15
0x180034c54  mov     [rbp+hExistingToken], r14
0x180034c58  lea     r8, [rbp+hExistingToken]
0x180034c5c  mov     rdx, rsi
0x180034c5f  mov     rcx, [rbp+TokenHandle]
0x180034c63  call    cs:__imp_UMgrGetImpersonationTokenForContext
0x180034c69  test    eax, eax
0x180034c6b  js      short loc_180034CD8
0x180034c6d  mov     rcx, [rbp+hExistingToken]; hExistingToken
0x180034c71  test    rcx, rcx
0x180034c74  jz      short loc_180034CD8
0x180034c76  mov     [rbp+var_20], r15
0x180034c7a  mov     [rbp+Token], r14
0x180034c7e  lea     rax, [rbp+Token]
0x180034c82  mov     [rsp+60h+phNewToken], rax; phNewToken
0x180034c87  mov     [rsp+60h+TokenType], 2; TokenType
0x180034c8f  lea     r9d, [r14+2]; ImpersonationLevel
0x180034c93  xor     r8d, r8d; lpTokenAttributes
0x180034c96  mov     edx, ebx; dwDesiredAccess
0x180034c98  call    cs:__imp_DuplicateTokenEx
0x180034c9e  mov     rcx, [rbp+28h]; this
0x180034ca2  test    eax, eax
0x180034ca4  jnz     short loc_180034CB6
0x180034ca6  lea     r8, aOnecoreuapEndu_13; "onecoreuap\\enduser\\winstore\\licensem"...
0x180034cad  lea     edx, [rax+29h]; void *
0x180034cb0  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180034cb6  mov     rdx, [rbp+Token]; Token
0x180034cba  xor     ecx, ecx; Thread
0x180034cbc  call    cs:__imp_SetThreadToken
0x180034cc2  test    eax, eax
0x180034cc4  setnz   al
0x180034cc7  mov     [rdi], al
0x180034cc9  mov     [rbp+var_20], r15
0x180034ccd  lea     rcx, [rbp+var_20]
0x180034cd1  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x180034cd6  jmp     short loc_180034D06
0x180034cd8  mov     dword ptr [rsp+60h+phNewToken], eax
0x180034cdc  lea     rax, aGotAUserContex; "Got a user context but couldn't get the"...
0x180034ce3  mov     qword ptr [rsp+60h+TokenType], rax; Format
0x180034ce8  lea     r9, aLicensemanager_22; "LicenseManagerUserContext::ImpersonateU"...
0x180034cef  mov     r8d, 2Eh ; '.'; unsigned int
0x180034cf5  lea     rdx, aOnecoreuapEndu_13; "onecoreuap\\enduser\\winstore\\licensem"...
0x180034cfc  lea     ecx, [r8-2Ch]; unsigned int
0x180034d00  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x180034d05  nop
0x180034d06  mov     [rbp+var_10], r15
0x180034d0a  lea     rcx, [rbp+var_10]
0x180034d0e  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x180034d13  jmp     loc_180034E35
0x180034d18  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShadowAdmin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin> `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl(void)'::`2'::impl
0x180034d1f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(void)
0x180034d24  test    al, al
0x180034d26  jz      loc_180034E22
0x180034d2c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_LicenseManagerShadowAdminOnesettingsCheck@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_LicenseManagerShadowAdminOnesettingsCheck@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LicenseManagerShadowAdminOnesettingsCheck> `wil::Feature<__WilFeatureTraits_Feature_LicenseManagerShadowAdminOnesettingsCheck>::GetImpl(void)'::`2'::impl
0x180034d33  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_LicenseManagerShadowAdminOnesettingsCheck@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LicenseManagerShadowAdminOnesettingsCheck>::__private_IsEnabled(void)
0x180034d38  test    al, al
0x180034d3a  jz      short loc_180034D4E
0x180034d3c  call    ?UpdateLicenseManagerOneSettings@@YAXXZ; UpdateLicenseManagerOneSettings(void)
0x180034d41  cmp     cs:byte_1800F297C, r14b
0x180034d48  jnz     loc_180034E22
0x180034d4e  mov     [rbp+arg_10], r14d
0x180034d52  mov     [rbp+arg_8], r14d
0x180034d56  call    LUAIsShadowAdminEnabled
0x180034d5b  test    eax, eax
0x180034d5d  jz      loc_180034E22
0x180034d63  lea     r8, [rbp+arg_10]
0x180034d67  lea     rdx, [rbp+arg_8]
0x180034d6b  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180034d6f  call    LUAIsElevatedToken
0x180034d74  test    eax, eax
0x180034d76  js      loc_180034E22
0x180034d7c  cmp     [rbp+arg_8], r14d
0x180034d80  jz      loc_180034E22
0x180034d86  cmp     [rbp+arg_10], r14d
0x180034d8a  jz      loc_180034E22
0x180034d90  mov     [rbp+arg_0], r14
0x180034d94  lea     rdx, [rbp+arg_0]
0x180034d98  mov     rcx, [rbp+TokenHandle]
0x180034d9c  call    cs:__imp_UMgrQueryUserContext
0x180034da2  test    eax, eax
0x180034da4  js      short loc_180034E22
0x180034da6  mov     [rbp+var_20], r15
0x180034daa  mov     [rbp+Token], r14
0x180034dae  lea     r8, [rbp+Token]
0x180034db2  mov     rdx, [rbp+arg_0]
0x180034db6  mov     rcx, [rbp+TokenHandle]
0x180034dba  call    cs:__imp_UMgrGetStandardAccessImpersonationTokenForContext
0x180034dc0  test    eax, eax
0x180034dc2  js      short loc_180034E15
0x180034dc4  mov     rcx, [rbp+Token]; hExistingToken
0x180034dc8  test    rcx, rcx
0x180034dcb  jz      short loc_180034E15
0x180034dcd  mov     [rbp+var_10], r15
0x180034dd1  mov     [rbp+hExistingToken], r14
0x180034dd5  lea     rax, [rbp+hExistingToken]
0x180034dd9  mov     [rsp+60h+phNewToken], rax; phNewToken
0x180034dde  mov     [rsp+60h+TokenType], 2; TokenType
0x180034de6  mov     r9d, 2; ImpersonationLevel
0x180034dec  xor     r8d, r8d; lpTokenAttributes
0x180034def  mov     edx, ebx; dwDesiredAccess
0x180034df1  call    cs:__imp_DuplicateTokenEx
0x180034df7  test    eax, eax
0x180034df9  jz      short loc_180034E08
0x180034dfb  lea     rdx, [rbp+var_10]
0x180034dff  lea     rcx, [rbp+var_30]
0x180034e03  call    ??4?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAAEAV0123@$$QEAV0123@@Z; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::operator=(Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> &&)
0x180034e08  mov     [rbp+var_10], r15
0x180034e0c  lea     rcx, [rbp+var_10]
0x180034e10  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x180034e15  mov     [rbp+var_20], r15
0x180034e19  lea     rcx, [rbp+var_20]
0x180034e1d  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x180034e22  mov     rdx, [rbp+TokenHandle]; Token
0x180034e26  xor     ecx, ecx; Thread
0x180034e28  call    cs:__imp_SetThreadToken
0x180034e2e  test    eax, eax
0x180034e30  setnz   al
0x180034e33  mov     [rdi], al
0x180034e35  mov     [rbp+var_30], r15
0x180034e39  lea     rcx, [rbp+var_30]
0x180034e3d  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x180034e42  nop
0x180034e43  mov     rax, rdi
0x180034e46  mov     rbx, [rsp+60h+arg_18]
0x180034e4e  add     rsp, 60h
0x180034e52  pop     r15
0x180034e54  pop     r14
0x180034e56  pop     rdi
0x180034e57  pop     rsi
0x180034e58  pop     rbp
0x180034e59  retn
```
