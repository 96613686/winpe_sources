# LocationCallerInfoHelper::GetCallerSIDs(ATL::CSid &,ATL::CSid &)

- ea: `0x18001de04`
- end: `0x18001e14f`
- name: `?GetCallerSIDs@LocationCallerInfoHelper@@SAJAEAVCSid@ATL@@0@Z`
- size: `843`
- prototype: `static int(struct ATL::CSid *, struct ATL::CSid *)`
- caller_count: `6`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180022100`
- `0x18008e8b0`
- `0x1800d2810`
- `0x1800f93ec`
- `0x180108630`
- `0x18011a104`

## callees

- `0x18001be08`
- `0x18001de04`
- `0x18001e170`
- `0x18001e858`
- `0x18001eb88`
- `0x18001f09c`
- `0x18005affc`
- `0x18009c310`
- `0x1800a98c0`
- `0x18015e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001debb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dfe4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001debb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dfe4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001dead`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001dead`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001decc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001decc`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001dee5`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001dee5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001de8c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001de8c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001df5c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001df5c`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18001de60`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18001de60`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001dfa3`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001e011`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001e0d8`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001dfa3`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001e011`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001e0d8`
- `api-ms-win-appmodel-identity-l1-2-0!AppContainerDeriveSidFromMoniker` at `0x18001e05e`
- `api-ms-win-appmodel-identity-l1-2-0!AppContainerDeriveSidFromMoniker` at `0x18001e05e`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFamilyNameFromToken` at `0x18001df91`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFamilyNameFromToken` at `0x18001df91`

## string_xrefs

- `0x18001e125`: `sidAppContainer.LoadAccount(static_cast<const SID*>(packageSid))`
- `0x18001e0b7`: `LocationCallerInfoHelper::GetCallerSIDs`
- `0x18001e131`: `LocationCallerInfoHelper::GetCallerSIDs`
- `0x18001e0be`: `onecoreuap\drivers\MobilePC\Location\Product\Common\inc\locationCallerInfoHelper.h`
- `0x18001e10b`: `onecoreuap\drivers\MobilePC\Location\Product\Common\inc\locationCallerInfoHelper.h`
- `0x18001e138`: `onecoreuap\drivers\MobilePC\Location\Product\Common\inc\locationCallerInfoHelper.h`
- `0x18001e0ab`: `sidAppContainer.IsValid()`
- `0x18001e0f8`: `AppContainerDeriveSidFromMoniker(packageFamilyName, psid)`
- `0x18001e104`: `LocationCallerInfoHelper::GetPackageSidFromTokenUsingPFN`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall LocationCallerInfoHelper::GetCallerSIDs(struct ATL::CSid *a1, struct ATL::CSid *a2)
{
  HRESULT v4; // eax
  signed int AppContainerSid; // edi
  char v6; // si
  bool v7; // bl
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  int v12; // eax
  const unsigned __int16 *v13; // r8
  wil::details *v14; // [rsp+28h] [rbp-D8h]
  int v15; // [rsp+30h] [rbp-D0h]
  void *TokenHandle; // [rsp+38h] [rbp-C8h] BYREF
  struct _SID *v17; // [rsp+40h] [rbp-C0h] BYREF
  UINT32 TokenInformation; // [rsp+48h] [rbp-B8h] BYREF
  void **token; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE token_8[2]; // [rsp+58h] [rbp-A8h]
  __int64 v21; // [rsp+68h] [rbp-98h]
  WCHAR packageFamilyName[72]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+138h] [rbp+38h]

  token = &ATL::CAccessToken::`vftable';
  *(_OWORD *)token_8 = 0;
  v21 = 0;
  v4 = CoImpersonateClient();
  AppContainerSid = v4;
  v6 = 1;
  v7 = v4 >= 0;
  LOBYTE(v15) = v4 >= 0;
  if ( (int)(v4 + 0x80000000) >= 0 && v4 != -2147417833 )
  {
LABEL_19:
    if ( v7 )
      CoRevertToSelf();
    goto LABEL_14;
  }
  CurrentThread = GetCurrentThread();
  TokenHandle = 0;
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    ((void (__fastcall *)(void ***))token[1])(&token);
    token_8[0] = TokenHandle;
  }
  else
  {
    if ( GetLastError() != 1008 )
      goto LABEL_31;
    CurrentProcess = GetCurrentProcess();
    TokenHandle = 0;
    if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    {
      ((void (__fastcall *)(void ***))token[1])(&token);
      token_8[0] = TokenHandle;
    }
    else
    {
      v6 = 0;
    }
    if ( !v6 )
      goto LABEL_31;
  }
  if ( (unsigned __int8)ATL::CAccessToken::GetInfoConvert<ATL::CSid,_TOKEN_USER>(&token, a1) )
  {
    TokenInformation = 0;
    LODWORD(TokenHandle) = 0;
    if ( GetTokenInformation(token_8[0], TokenIsAppContainer, &TokenInformation, 4u, (PDWORD)&TokenHandle) )
    {
      if ( !TokenInformation )
      {
        v17 = 0;
        TokenInformation = 65;
        if ( !GetPackageFamilyNameFromToken(token_8[0], &TokenInformation, packageFamilyName) && TokenInformation )
        {
          v12 = AppContainerDeriveSidFromMoniker(packageFamilyName, &v17);
          if ( v12 < 0 )
          {
            LODWORD(v14) = v12;
            wil::details::in1diag5::Return_Hr(
              retaddr,
              (void *)0x35C,
              (unsigned int)"onecoreuap\\drivers\\MobilePC\\Location\\Product\\Common\\inc\\locationCallerInfoHelper.h",
              "LocationCallerInfoHelper::GetPackageSidFromTokenUsingPFN",
              "AppContainerDeriveSidFromMoniker(packageFamilyName, psid)",
              v14,
              v15);
          }
          else if ( v17 )
          {
            if ( !ATL::CSid::LoadAccount(a2, v17, v13) )
            {
              LODWORD(v14) = -2147023559;
              wil::details::in1diag5::_Log_Hr(
                retaddr,
                (void *)0x180,
                (unsigned int)"onecoreuap\\drivers\\MobilePC\\Location\\Product\\Common\\inc\\locationCallerInfoHelper.h",
                "LocationCallerInfoHelper::GetCallerSIDs",
                "sidAppContainer.LoadAccount(static_cast<const SID*>(packageSid))",
                (const char *)v14,
                v15);
            }
            if ( !ATL::CSid::IsValid(a2) )
            {
              LODWORD(v14) = -2147023559;
              wil::details::in1diag5::_Log_Hr(
                retaddr,
                (void *)0x181,
                (unsigned int)"onecoreuap\\drivers\\MobilePC\\Location\\Product\\Common\\inc\\locationCallerInfoHelper.h",
                "LocationCallerInfoHelper::GetCallerSIDs",
                "sidAppContainer.IsValid()",
                (const char *)v14,
                v15);
            }
          }
        }
        if ( v7 )
          CoRevertToSelf();
        AppContainerSid = 0;
        goto LABEL_14;
      }
    }
    else
    {
      LastError = GetLastError();
      AppContainerSid = LastError;
      if ( LastError > 0 )
        AppContainerSid = (unsigned __int16)LastError | 0x80070000;
      if ( AppContainerSid < 0 )
        goto LABEL_19;
    }
    AppContainerSid = LocationCallerInfoHelper::GetAppContainerSid((const struct ATL::CAccessToken *)&token, a2);
    goto LABEL_19;
  }
LABEL_31:
  if ( v7 )
    CoRevertToSelf();
  AppContainerSid = -2147467259;
LABEL_14:
  token = &ATL::CAccessToken::`vftable';
  ATL::CAccessToken::Clear((ATL::CAccessToken *)&token);
  return (unsigned int)AppContainerSid;
}

```

## disassembly

```asm
0x18001de04  mov     [rsp-8+arg_10], rbx
0x18001de09  mov     [rsp-8+arg_18], rsi
0x18001de0e  push    rbp
0x18001de0f  push    rdi
0x18001de10  push    r13
0x18001de12  push    r14
0x18001de14  push    r15
0x18001de16  lea     rbp, [rsp-10h]
0x18001de1b  sub     rsp, 110h
0x18001de22  mov     rax, cs:__security_cookie
0x18001de29  xor     rax, rsp
0x18001de2c  mov     [rbp+30h+var_30], rax
0x18001de30  mov     r14, rdx
0x18001de33  mov     r15, rcx
0x18001de36  xorps   xmm0, xmm0
0x18001de39  movups  xmmword ptr [rsp+130h+token], xmm0
0x18001de3e  movups  [rsp+130h+var_D0], xmm0
0x18001de43  lea     r13, ??_7CAccessToken@ATL@@6B@; const ATL::CAccessToken::`vftable'
0x18001de4a  mov     [rsp+130h+token], r13
0x18001de4f  movdqu  xmmword ptr [rsp+130h+token+8], xmm0
0x18001de55  mov     qword ptr [rsp+130h+var_D0+8], 0
0x18001de5e  xor     bl, bl
0x18001de60  call    cs:__imp_CoImpersonateClient
0x18001de66  mov     edi, eax
0x18001de68  mov     [rsp+130h+var_FC], eax
0x18001de6c  movzx   ebx, bl
0x18001de6f  mov     esi, 1
0x18001de74  test    eax, eax
0x18001de76  cmovns  ebx, esi
0x18001de79  mov     byte ptr [rsp+130h+var_100], bl; int
0x18001de7d  mov     ecx, 80000000h
0x18001de82  add     eax, ecx
0x18001de84  test    ecx, eax
0x18001de86  jz      loc_18001E019
0x18001de8c  call    cs:__imp_GetCurrentThread
0x18001de92  mov     [rsp+130h+TokenHandle], 0
0x18001de9b  lea     r9, [rsp+130h+TokenHandle]; TokenHandle
0x18001dea0  mov     r8d, esi; OpenAsSelf
0x18001dea3  mov     edi, 8
0x18001dea8  mov     edx, edi; DesiredAccess
0x18001deaa  mov     rcx, rax; ThreadHandle
0x18001dead  call    cs:__imp_OpenThreadToken
0x18001deb3  test    eax, eax
0x18001deb5  jnz     loc_18001E027
0x18001debb  call    cs:__imp_GetLastError
0x18001dec1  cmp     eax, 3F0h
0x18001dec6  jnz     loc_18001E0D4
0x18001decc  call    cs:__imp_GetCurrentProcess
0x18001ded2  mov     [rsp+130h+TokenHandle], 0
0x18001dedb  lea     r8, [rsp+130h+TokenHandle]; TokenHandle
0x18001dee0  mov     edx, edi; DesiredAccess
0x18001dee2  mov     rcx, rax; ProcessHandle
0x18001dee5  call    cs:__imp_OpenProcessToken
0x18001deeb  test    eax, eax
0x18001deed  jz      loc_18001E0E8
0x18001def3  mov     rax, [rsp+130h+token]
0x18001def8  lea     rcx, [rsp+130h+token]
0x18001defd  mov     rax, [rax+8]
0x18001df01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df06  mov     rax, [rsp+130h+TokenHandle]
0x18001df0b  mov     [rsp+130h+token+8], rax
0x18001df10  test    sil, sil
0x18001df13  jz      loc_18001E0D4
0x18001df19  mov     rdx, r15
0x18001df1c  lea     rcx, [rsp+130h+token]
0x18001df21  call    ??$GetInfoConvert@VCSid@ATL@@U_TOKEN_USER@@@CAccessToken@ATL@@IEBA_NPEAVCSid@1@W4_TOKEN_INFORMATION_CLASS@@PEAU_TOKEN_USER@@@Z; ATL::CAccessToken::GetInfoConvert<ATL::CSid,_TOKEN_USER>(ATL::CSid *,_TOKEN_INFORMATION_CLASS,_TOKEN_USER *)
0x18001df26  test    al, al
0x18001df28  jz      loc_18001E0D4
0x18001df2e  mov     [rsp+130h+TokenInformation], 0
0x18001df36  mov     dword ptr [rsp+130h+TokenHandle], 0
0x18001df3e  lea     rax, [rsp+130h+TokenHandle]
0x18001df43  mov     [rsp+130h+ReturnLength], rax; ReturnLength
0x18001df48  mov     r9d, 4; TokenInformationLength
0x18001df4e  lea     r8, [rsp+130h+TokenInformation]; TokenInformation
0x18001df53  lea     edx, [r9+19h]; TokenInformationClass
0x18001df57  mov     rcx, [rsp+130h+token+8]; TokenHandle
0x18001df5c  call    cs:__imp_GetTokenInformation
0x18001df62  test    eax, eax
0x18001df64  jz      short loc_18001DFE4
0x18001df66  cmp     [rsp+130h+TokenInformation], 0
0x18001df6b  jnz     loc_18001DFFE
0x18001df71  mov     [rsp+130h+var_F0], 0
0x18001df7a  mov     [rsp+130h+TokenInformation], 41h ; 'A'
0x18001df82  lea     r8, [rsp+130h+packageFamilyName]; packageFamilyName
0x18001df87  lea     rdx, [rsp+130h+TokenInformation]; packageFamilyNameLength
0x18001df8c  mov     rcx, [rsp+130h+token+8]; token
0x18001df91  call    cs:__imp_GetPackageFamilyNameFromToken
0x18001df97  test    eax, eax
0x18001df99  jz      loc_18001E049
0x18001df9f  test    bl, bl
0x18001dfa1  jz      short loc_18001DFA9
0x18001dfa3  call    cs:__imp_CoRevertToSelf
0x18001dfa9  xor     edi, edi
0x18001dfab  mov     [rsp+130h+token], r13
0x18001dfb0  lea     rcx, [rsp+130h+token]; this
0x18001dfb5  call    ?Clear@CAccessToken@ATL@@MEAAXXZ; ATL::CAccessToken::Clear(void)
0x18001dfba  mov     eax, edi
0x18001dfbc  mov     rcx, [rbp+30h+var_30]
0x18001dfc0  xor     rcx, rsp; StackCookie
0x18001dfc3  call    __security_check_cookie
0x18001dfc8  lea     r11, [rsp+130h+var_20]
0x18001dfd0  mov     rbx, [r11+40h]
0x18001dfd4  mov     rsi, [r11+48h]
0x18001dfd8  mov     rsp, r11
0x18001dfdb  pop     r15
0x18001dfdd  pop     r14
0x18001dfdf  pop     r13
0x18001dfe1  pop     rdi
0x18001dfe2  pop     rbp
0x18001dfe3  retn
0x18001dfe4  call    cs:__imp_GetLastError
0x18001dfea  nop
0x18001dfeb  mov     edi, eax
0x18001dfed  test    eax, eax
0x18001dfef  jle     short loc_18001DFFA
0x18001dff1  movzx   edi, ax
0x18001dff4  or      edi, 80070000h
0x18001dffa  test    edi, edi
0x18001dffc  js      short loc_18001E00D
0x18001dffe  mov     rdx, r14; struct ATL::CSid *
0x18001e001  lea     rcx, [rsp+130h+token]; struct ATL::CAccessToken *
0x18001e006  call    ?GetAppContainerSid@LocationCallerInfoHelper@@SAJAEBVCAccessToken@ATL@@AEAVCSid@3@@Z; LocationCallerInfoHelper::GetAppContainerSid(ATL::CAccessToken const &,ATL::CSid &)
0x18001e00b  mov     edi, eax
0x18001e00d  test    bl, bl
0x18001e00f  jz      short loc_18001DFAB
0x18001e011  call    cs:__imp_CoRevertToSelf
0x18001e017  jmp     short loc_18001DFAB
0x18001e019  cmp     edi, 80010117h
0x18001e01f  jz      loc_18001DE8C
0x18001e025  jmp     short loc_18001E00D
0x18001e027  mov     rax, [rsp+130h+token]
0x18001e02c  lea     rcx, [rsp+130h+token]
0x18001e031  mov     rax, [rax+8]
0x18001e035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e03a  mov     rax, [rsp+130h+TokenHandle]
0x18001e03f  mov     [rsp+130h+token+8], rax
0x18001e044  jmp     loc_18001DF19
0x18001e049  cmp     [rsp+130h+TokenInformation], 0
0x18001e04e  jbe     loc_18001DF9F
0x18001e054  lea     rdx, [rsp+130h+var_F0]
0x18001e059  lea     rcx, [rsp+130h+packageFamilyName]
0x18001e05e  call    cs:__imp_AppContainerDeriveSidFromMoniker
0x18001e064  test    eax, eax
0x18001e066  js      loc_18001E0F0
0x18001e06c  mov     rdx, [rsp+130h+var_F0]; struct _SID *
0x18001e071  test    rdx, rdx
0x18001e074  jz      loc_18001DF9F
0x18001e07a  mov     rcx, r14; this
0x18001e07d  call    ?LoadAccount@CSid@ATL@@QEAA_NPEBU_SID@@PEBG@Z; ATL::CSid::LoadAccount(_SID const *,ushort const *)
0x18001e082  mov     rcx, [rbp+38h]; this
0x18001e086  mov     edi, 80070539h
0x18001e08b  test    al, al
0x18001e08d  jz      loc_18001E121
0x18001e093  mov     rcx, r14; this
0x18001e096  call    ?IsValid@CSid@ATL@@QEBA_NXZ; ATL::CSid::IsValid(void)
0x18001e09b  mov     rcx, [rbp+38h]; this
0x18001e09f  test    al, al
0x18001e0a1  jnz     loc_18001DF9F
0x18001e0a7  mov     dword ptr [rsp+130h+var_108], edi; char *
0x18001e0ab  lea     rax, aSidappcontaine_0; "sidAppContainer.IsValid()"
0x18001e0b2  mov     [rsp+130h+ReturnLength], rax; char *
0x18001e0b7  lea     r9, aLocationcaller_0; "LocationCallerInfoHelper::GetCallerSIDs"
0x18001e0be  lea     r8, aOnecoreuapDriv_91; "onecoreuap\\drivers\\MobilePC\\Location"...
0x18001e0c5  mov     edx, 181h; void *
0x18001e0ca  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x18001e0cf  jmp     loc_18001DF9F
0x18001e0d4  test    bl, bl
0x18001e0d6  jz      short loc_18001E0DE
0x18001e0d8  call    cs:__imp_CoRevertToSelf
0x18001e0de  mov     edi, 80004005h
0x18001e0e3  jmp     loc_18001DFAB
0x18001e0e8  xor     sil, sil
0x18001e0eb  jmp     loc_18001DF10
0x18001e0f0  mov     rcx, [rbp+38h]; this
0x18001e0f4  mov     dword ptr [rsp+130h+var_108], eax; wil::details *
0x18001e0f8  lea     rax, aAppcontainerde_1; "AppContainerDeriveSidFromMoniker(packag"...
0x18001e0ff  mov     [rsp+130h+ReturnLength], rax; char *
0x18001e104  lea     r9, aLocationcaller_2; "LocationCallerInfoHelper::GetPackageSid"...
0x18001e10b  lea     r8, aOnecoreuapDriv_91; "onecoreuap\\drivers\\MobilePC\\Location"...
0x18001e112  mov     edx, 35Ch; void *
0x18001e117  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18001e11c  jmp     loc_18001DF9F
0x18001e121  mov     dword ptr [rsp+130h+var_108], edi; char *
0x18001e125  lea     rax, aSidappcontaine; "sidAppContainer.LoadAccount(static_cast"...
0x18001e12c  mov     [rsp+130h+ReturnLength], rax; char *
0x18001e131  lea     r9, aLocationcaller_0; "LocationCallerInfoHelper::GetCallerSIDs"
0x18001e138  lea     r8, aOnecoreuapDriv_91; "onecoreuap\\drivers\\MobilePC\\Location"...
0x18001e13f  mov     edx, 180h; void *
0x18001e144  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x18001e149  jmp     loc_18001E093
```
