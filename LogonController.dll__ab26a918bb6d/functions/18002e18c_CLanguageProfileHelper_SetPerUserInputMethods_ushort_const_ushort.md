# CLanguageProfileHelper::SetPerUserInputMethods(ushort const *,ushort * *)

- ea: `0x18002e18c`
- end: `0x18002e55e`
- name: `?SetPerUserInputMethods@CLanguageProfileHelper@@SAXPEBGPEAPEAG@Z`
- size: `978`
- prototype: `void __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800268e0`
- `0x18002d7f0`
- `0x18002d920`

## callees

- `0x180004b70`
- `0x180006d90`
- `0x18000a584`
- `0x18001c56c`
- `0x18001c860`
- `0x18001db70`
- `0x18001f3a0`
- `0x1800250a0`
- `0x18002547c`
- `0x18002d9d0`
- `0x18002e18c`
- `0x18002f554`
- `0x180035850`
- `0x18003be14`
- `0x18005b3e4`
- `0x1800616f8`
- `0x180062c0c`
- `0x1800650a0`
- `0x18006c000`
- `0x180085bf8`
- `0x180085c90`
- `0x1800962b0`
- `0x18009b790`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18002e3a7`
- `KERNEL32!LocalFree` at `0x18002e500`
- `KERNEL32!LocalFree` at `0x18002e3a7`
- `KERNEL32!LocalFree` at `0x18002e500`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18002e3e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18002e3e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e278`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e3c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e4f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e50c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e278`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e3c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e4f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e50c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002e3f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002e3f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e384`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e392`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e39b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e4db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e4e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e384`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e392`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e39b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e4db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e4e4`
- `WinLangdb!SetUserLanguagesNoSpeller` at `0x18002e2a2`
- `WinLangdb!SetUserLanguagesNoSpeller` at `0x18002e2a2`
- `Bcp47Langs!GetUserLanguagesForUser` at `0x18002e28d`
- `Bcp47Langs!GetUserLanguagesForUser` at `0x18002e28d`
- `Bcp47Langs!GetInputMethodOverrideForUser` at `0x18002e3d4`
- `Bcp47Langs!GetInputMethodOverrideForUser` at `0x18002e3d4`
- `Bcp47Langs!RemoveInputsForAllLanguagesInternal` at `0x18002e2b0`
- `Bcp47Langs!RemoveInputsForAllLanguagesInternal` at `0x18002e2b0`
- `MSCTF!TF_PostAllThreadMsg` at `0x18002e478`
- `MSCTF!TF_PostAllThreadMsg` at `0x18002e478`

## pseudocode

```c
void __fastcall CLanguageProfileHelper::SetPerUserInputMethods(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  void *UserSid; // r12
  __int64 v5; // r14
  void *v6; // rax
  void *v7; // rsi
  int UserInputMethodString; // eax
  unsigned __int16 *v9; // rdi
  __int64 v10; // rax
  void *v11; // r15
  __int64 v12; // rcx
  __int64 v13; // rbx
  unsigned __int64 v14; // rdx
  void *v15; // rbx
  const unsigned __int16 *StringRawBuffer; // rsi
  unsigned __int16 *v17; // rbx
  __int64 v18; // rdx
  __int64 v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // r15
  HKEY v23; // rdx
  __int64 v24; // rdx
  __int64 v25; // rcx
  struct _GUID Buf1; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING string; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING v29[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v30[192]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v31[42]; // [rsp+120h] [rbp+20h] BYREF

  wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v31,
    "CLanguageProfileHelper_SetPerUserInputMethods_Activity");
  v31[0] = &LogonControllerTelemetry::CLanguageProfileHelper_SetPerUserInputMethods_Activity::`vftable';
  Buf1 = *GetFirstRunTelemetryCorrelationId(&Buf1);
  if ( memcmp_0(&Buf1, &GUID_00000000_0000_0000_0000_000000000000, 0x10u) )
    wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(
      v31,
      &Buf1);
  LogonControllerTelemetry::CLanguageProfileHelper_SetPerUserInputMethods_Activity::StartActivity((LogonControllerTelemetry::CLanguageProfileHelper_SetPerUserInputMethods_Activity *)v31);
  *a2 = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DecoupledLanguageAndKeyboardSettings>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DecoupledLanguageAndKeyboardSettings>::GetImpl'::`2'::impl)
    && (!(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_59291947_58995668>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Bugfix_59291947_58995668>::GetImpl'::`2'::impl)
     || !(unsigned __int8)RollbackUpkl(a1)) )
  {
    UserSid = CLanguageProfileHelper::CreateUserSid(a1);
    if ( UserSid )
    {
      v29[0] = 0;
      WindowsDeleteString(0);
      v29[0] = 0;
      if ( (int)GetUserLanguagesForUser(UserSid, 0, v29) >= 0 && (int)SetUserLanguagesNoSpeller(0, v29[0]) >= 0 )
      {
        RemoveInputsForAllLanguagesInternal();
        pv = 0;
        if ( (int)CLanguageProfileHelper::GetUserInputMethodString(UserSid, 1, (unsigned __int16 **)&pv) >= 0 )
        {
          v5 = -1;
          if ( *a1 && (v6 = CLanguageProfileHelper::CreateUserSid(&sourceString), (v7 = v6) != 0) )
          {
            *(_QWORD *)&Buf1.Data1 = 0;
            UserInputMethodString = CLanguageProfileHelper::GetUserInputMethodString(v6, 0, (unsigned __int16 **)&Buf1);
            v9 = (unsigned __int16 *)pv;
            if ( UserInputMethodString >= 0 )
            {
              v10 = -1;
              do
                ++v10;
              while ( *((_WORD *)pv + v10) );
              v11 = *(void **)&Buf1.Data1;
              v12 = -1;
              do
                ++v12;
              while ( *(_WORD *)(*(_QWORD *)&Buf1.Data1 + 2 * v12) );
              v13 = v12 + v10;
              *(_QWORD *)&Buf1.Data1 = 0;
              if ( (int)_AllocStringWorker<CTCoAllocPolicy>(v12, 0, 0, v12 + v10 + 2) >= 0 )
              {
                v14 = v13 + 2;
                v15 = *(void **)&Buf1.Data1;
                if ( (int)StringCchPrintfW(*(unsigned __int16 **)&Buf1.Data1, v14, L"%s;%s", v9, v11) < 0 )
                {
                  CoTaskMemFree(v15);
                }
                else
                {
                  CoTaskMemFree(v9);
                  v9 = (unsigned __int16 *)v15;
                }
              }
              CoTaskMemFree(v11);
            }
            LocalFree(v7);
          }
          else
          {
            v9 = (unsigned __int16 *)pv;
          }
          StringRawBuffer = v9;
          v17 = v9;
          string = 0;
          WindowsDeleteString(0);
          string = 0;
          if ( (int)GetInputMethodOverrideForUser(UserSid, &string) >= 0 )
          {
            if ( WindowsGetStringLen(string) )
            {
              StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
              v19 = -1;
              do
                ++v19;
              while ( StringRawBuffer[v19] );
              v20 = v19 + 1;
              if ( (unsigned __int64)(v19 + 1) > 1 )
              {
                *(_QWORD *)&Buf1.Data1 = 0;
                v21 = -1;
                do
                  ++v21;
                while ( v9[v21] );
                v22 = v20 + v21;
                if ( (int)_AllocStringWorker<CTCoAllocPolicy>(v20, v18, 0, v20 + v21 + 1) >= 0 )
                {
                  v17 = *(unsigned __int16 **)&Buf1.Data1;
                  StringCchPrintfW(*(unsigned __int16 **)&Buf1.Data1, v22 + 1, L"%s;%s", StringRawBuffer, v9);
                }
              }
            }
          }
          InstallLayoutOrTipPrivate(v17);
          TF_PostAllThreadMsg(3);
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_InputSupportForBcp47>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_InputSupportForBcp47>::GetImpl'::`2'::impl) )
          {
            InputProfileSettings::InputProfileSettings((InputProfileSettings *)v30, v23);
            InputProfileSettings::ActivateProfile((InputProfileSettings *)v30, StringRawBuffer);
            InputProfileSettings::~InputProfileSettings((InputProfileSettings *)v30);
          }
          else
          {
            ActivateInputProfileWorker(StringRawBuffer);
          }
          do
            ++v5;
          while ( StringRawBuffer[v5] );
          _AllocStringWorker<CTCoAllocPolicy>(v25, v24, StringRawBuffer, v5);
          if ( v17 != v9 )
            CoTaskMemFree(v17);
          CoTaskMemFree(v9);
          WindowsDeleteString(string);
        }
      }
      LocalFree(UserSid);
      WindowsDeleteString(v29[0]);
    }
  }
  wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v31, 0);
  v31[0] = &LogonControllerTelemetry::CLanguageProfileHelper_SetPerUserInputMethods_Activity::`vftable';
  wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v31);
  wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v31);
}

```

## disassembly

```asm
0x18002e18c  mov     [rsp-8+arg_10], rbx
0x18002e191  push    rbp
0x18002e192  push    rsi
0x18002e193  push    rdi
0x18002e194  push    r12
0x18002e196  push    r13
0x18002e198  push    r14
0x18002e19a  push    r15
0x18002e19c  lea     rbp, [rsp-180h]
0x18002e1a4  sub     rsp, 280h
0x18002e1ab  mov     rax, cs:__security_cookie
0x18002e1b2  xor     rax, rsp
0x18002e1b5  mov     [rbp+1B0h+var_40], rax
0x18002e1bc  mov     r13, rdx
0x18002e1bf  mov     rbx, rcx
0x18002e1c2  lea     rdx, aClanguageprofi; "CLanguageProfileHelper_SetPerUserInputM"...
0x18002e1c9  lea     rcx, [rbp+1B0h+var_190]
0x18002e1cd  call    ??0?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18002e1d2  lea     rdi, ??_7CLanguageProfileHelper_SetPerUserInputMethods_Activity@LogonControllerTelemetry@@6B@; const LogonControllerTelemetry::CLanguageProfileHelper_SetPerUserInputMethods_Activity::`vftable'
0x18002e1d9  mov     [rbp+1B0h+var_190], rdi
0x18002e1dd  lea     rcx, [rsp+2B0h+Buf1]; retstr
0x18002e1e2  call    ?GetFirstRunTelemetryCorrelationId@@YA?AU_GUID@@XZ; GetFirstRunTelemetryCorrelationId(void)
0x18002e1e7  movups  xmm0, xmmword ptr [rax]
0x18002e1ea  movdqu  [rsp+2B0h+Buf1], xmm0
0x18002e1f0  mov     r8d, 10h; Size
0x18002e1f6  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; Buf2
0x18002e1fd  lea     rcx, [rsp+2B0h+Buf1]; Buf1
0x18002e202  call    memcmp_0
0x18002e207  xor     r15d, r15d
0x18002e20a  test    eax, eax
0x18002e20c  jz      short loc_18002E21C
0x18002e20e  lea     rdx, [rsp+2B0h+Buf1]
0x18002e213  lea     rcx, [rbp+1B0h+var_190]
0x18002e217  call    ?SetRelatedActivityId@?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXAEBU_GUID@@@Z; wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(_GUID const &)
0x18002e21c  lea     rcx, [rbp+1B0h+var_190]; this
0x18002e220  call    ?StartActivity@CLanguageProfileHelper_SetPerUserInputMethods_Activity@LogonControllerTelemetry@@QEAAXXZ; LogonControllerTelemetry::CLanguageProfileHelper_SetPerUserInputMethods_Activity::StartActivity(void)
0x18002e225  mov     [r13+0], r15
0x18002e229  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DecoupledLanguageAndKeyboardSettings@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DecoupledLanguageAndKeyboardSettings@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DecoupledLanguageAndKeyboardSettings> `wil::Feature<__WilFeatureTraits_Feature_DecoupledLanguageAndKeyboardSettings>::GetImpl(void)'::`2'::impl
0x18002e230  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DecoupledLanguageAndKeyboardSettings@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DecoupledLanguageAndKeyboardSettings>::__private_IsEnabled(void)
0x18002e235  test    al, al
0x18002e237  jnz     loc_18002E512
0x18002e23d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Bugfix_59291947_58995668@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Bugfix_59291947_58995668@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_59291947_58995668> `wil::Feature<__WilFeatureTraits_Feature_Bugfix_59291947_58995668>::GetImpl(void)'::`2'::impl
0x18002e244  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Bugfix_59291947_58995668@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_59291947_58995668>::__private_IsEnabled(void)
0x18002e249  test    al, al
0x18002e24b  jz      short loc_18002E25D
0x18002e24d  mov     rcx, rbx
0x18002e250  call    RollbackUpkl
0x18002e255  test    al, al
0x18002e257  jnz     loc_18002E512
0x18002e25d  mov     rcx, rbx; unsigned __int16 *
0x18002e260  call    ?CreateUserSid@CLanguageProfileHelper@@CAPEAXPEBG@Z; CLanguageProfileHelper::CreateUserSid(ushort const *)
0x18002e265  mov     r12, rax
0x18002e268  test    rax, rax
0x18002e26b  jz      loc_18002E512
0x18002e271  mov     [rsp+2B0h+var_260], r15
0x18002e276  xor     ecx, ecx; string
0x18002e278  call    cs:__imp_WindowsDeleteString
0x18002e27e  mov     [rsp+2B0h+var_260], r15
0x18002e283  xor     edx, edx
0x18002e285  lea     r8, [rsp+2B0h+var_260]
0x18002e28a  mov     rcx, r12
0x18002e28d  call    cs:__imp_GetUserLanguagesForUser
0x18002e293  test    eax, eax
0x18002e295  js      loc_18002E4FD
0x18002e29b  xor     ecx, ecx
0x18002e29d  mov     rdx, [rsp+2B0h+var_260]
0x18002e2a2  call    cs:__imp_SetUserLanguagesNoSpeller
0x18002e2a8  test    eax, eax
0x18002e2aa  js      loc_18002E4FD
0x18002e2b0  call    cs:__imp_RemoveInputsForAllLanguagesInternal
0x18002e2b6  mov     [rsp+2B0h+pv], r15
0x18002e2bb  lea     r8, [rsp+2B0h+pv]; unsigned __int16 **
0x18002e2c0  mov     dl, 1; bool
0x18002e2c2  mov     rcx, r12; void *
0x18002e2c5  call    ?GetUserInputMethodString@CLanguageProfileHelper@@CAJPEAX_NPEAPEAG@Z; CLanguageProfileHelper::GetUserInputMethodString(void *,bool,ushort * *)
0x18002e2ca  test    eax, eax
0x18002e2cc  js      loc_18002E4FD
0x18002e2d2  or      r14, 0FFFFFFFFFFFFFFFFh
0x18002e2d6  cmp     [rbx], r15w
0x18002e2da  jz      loc_18002E3AF
0x18002e2e0  lea     rcx, sourceString; unsigned __int16 *
0x18002e2e7  call    ?CreateUserSid@CLanguageProfileHelper@@CAPEAXPEBG@Z; CLanguageProfileHelper::CreateUserSid(ushort const *)
0x18002e2ec  mov     rsi, rax
0x18002e2ef  test    rax, rax
0x18002e2f2  jz      loc_18002E3AF
0x18002e2f8  mov     qword ptr [rsp+2B0h+Buf1], r15
0x18002e2fd  lea     r8, [rsp+2B0h+Buf1]; unsigned __int16 **
0x18002e302  xor     edx, edx; bool
0x18002e304  mov     rcx, rax; void *
0x18002e307  call    ?GetUserInputMethodString@CLanguageProfileHelper@@CAJPEAX_NPEAPEAG@Z; CLanguageProfileHelper::GetUserInputMethodString(void *,bool,ushort * *)
0x18002e30c  mov     rdi, [rsp+2B0h+pv]
0x18002e311  test    eax, eax
0x18002e313  js      loc_18002E3A4
0x18002e319  mov     rax, r14
0x18002e31c  inc     rax
0x18002e31f  cmp     [rdi+rax*2], r15w
0x18002e324  jnz     short loc_18002E31C
0x18002e326  mov     r15, qword ptr [rsp+2B0h+Buf1]
0x18002e32b  mov     rcx, r14
0x18002e32e  xor     edx, edx
0x18002e330  inc     rcx
0x18002e333  cmp     [r15+rcx*2], dx
0x18002e338  jnz     short loc_18002E330
0x18002e33a  lea     rbx, [rcx+rax]
0x18002e33e  mov     qword ptr [rsp+2B0h+Buf1], rdx
0x18002e343  lea     rax, [rsp+2B0h+Buf1]
0x18002e348  mov     [rsp+2B0h+var_288], rax
0x18002e34d  lea     r9, [rbx+2]
0x18002e351  xor     r8d, r8d
0x18002e354  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x18002e359  test    eax, eax
0x18002e35b  js      short loc_18002E398
0x18002e35d  mov     [rsp+2B0h+var_290], r15
0x18002e362  mov     r9, rdi
0x18002e365  lea     r8, aSS; "%s;%s"
0x18002e36c  lea     rdx, [rbx+2]; unsigned __int64
0x18002e370  mov     rbx, qword ptr [rsp+2B0h+Buf1]
0x18002e375  mov     rcx, rbx; unsigned __int16 *
0x18002e378  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002e37d  test    eax, eax
0x18002e37f  js      short loc_18002E38F
0x18002e381  mov     rcx, rdi; pv
0x18002e384  call    cs:__imp_CoTaskMemFree
0x18002e38a  mov     rdi, rbx
0x18002e38d  jmp     short loc_18002E398
0x18002e38f  mov     rcx, rbx; pv
0x18002e392  call    cs:__imp_CoTaskMemFree
0x18002e398  mov     rcx, r15; pv
0x18002e39b  call    cs:__imp_CoTaskMemFree
0x18002e3a1  xor     r15d, r15d
0x18002e3a4  mov     rcx, rsi; hMem
0x18002e3a7  call    cs:__imp_LocalFree
0x18002e3ad  jmp     short loc_18002E3B4
0x18002e3af  mov     rdi, [rsp+2B0h+pv]
0x18002e3b4  mov     rsi, rdi
0x18002e3b7  mov     rbx, rdi
0x18002e3ba  mov     [rsp+2B0h+string], r15
0x18002e3bf  xor     ecx, ecx; string
0x18002e3c1  call    cs:__imp_WindowsDeleteString
0x18002e3c7  mov     [rsp+2B0h+string], r15
0x18002e3cc  lea     rdx, [rsp+2B0h+string]
0x18002e3d1  mov     rcx, r12
0x18002e3d4  call    cs:__imp_GetInputMethodOverrideForUser
0x18002e3da  test    eax, eax
0x18002e3dc  js      loc_18002E46B
0x18002e3e2  mov     rcx, [rsp+2B0h+string]; string
0x18002e3e7  call    cs:__imp_WindowsGetStringLen
0x18002e3ed  test    eax, eax
0x18002e3ef  jz      short loc_18002E46B
0x18002e3f1  xor     edx, edx; length
0x18002e3f3  mov     rcx, [rsp+2B0h+string]; string
0x18002e3f8  call    cs:__imp_WindowsGetStringRawBuffer
0x18002e3fe  mov     rsi, rax
0x18002e401  mov     rax, r14
0x18002e404  inc     rax
0x18002e407  cmp     [rsi+rax*2], r15w
0x18002e40c  jnz     short loc_18002E404
0x18002e40e  lea     rcx, [rax+1]
0x18002e412  cmp     rcx, 1
0x18002e416  jbe     short loc_18002E46B
0x18002e418  mov     qword ptr [rsp+2B0h+Buf1], r15
0x18002e41d  mov     rax, r14
0x18002e420  inc     rax
0x18002e423  cmp     [rdi+rax*2], r15w
0x18002e428  jnz     short loc_18002E420
0x18002e42a  lea     r15, [rcx+rax]
0x18002e42e  lea     rax, [rsp+2B0h+Buf1]
0x18002e433  mov     [rsp+2B0h+var_288], rax
0x18002e438  lea     r9, [r15+1]
0x18002e43c  xor     r8d, r8d
0x18002e43f  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x18002e444  test    eax, eax
0x18002e446  js      short loc_18002E468
0x18002e448  mov     rbx, qword ptr [rsp+2B0h+Buf1]
0x18002e44d  mov     [rsp+2B0h+var_290], rdi
0x18002e452  mov     r9, rsi
0x18002e455  lea     r8, aSS; "%s;%s"
0x18002e45c  lea     rdx, [r15+1]; unsigned __int64
0x18002e460  mov     rcx, rbx; unsigned __int16 *
0x18002e463  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002e468  xor     r15d, r15d
0x18002e46b  mov     rcx, rbx; unsigned __int16 *
0x18002e46e  call    InstallLayoutOrTipPrivate
0x18002e473  xor     edx, edx
0x18002e475  lea     ecx, [rdx+3]
0x18002e478  call    cs:__imp_TF_PostAllThreadMsg
0x18002e47e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_InputSupportForBcp47@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_InputSupportForBcp47@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InputSupportForBcp47> `wil::Feature<__WilFeatureTraits_Feature_InputSupportForBcp47>::GetImpl(void)'::`2'::impl
0x18002e485  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_InputSupportForBcp47@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InputSupportForBcp47>::__private_IsEnabled(void)
0x18002e48a  test    al, al
0x18002e48c  jnz     short loc_18002E498
0x18002e48e  mov     rcx, rsi; unsigned __int16 *
0x18002e491  call    ?ActivateInputProfileWorker@@YAHPEBG@Z; ActivateInputProfileWorker(ushort const *)
0x18002e496  jmp     short loc_18002E4B9
0x18002e498  lea     rcx, [rsp+2B0h+var_250]; this
0x18002e49d  call    ??0InputProfileSettings@@QEAA@PEAUHKEY__@@@Z; InputProfileSettings::InputProfileSettings(HKEY__ *)
0x18002e4a2  mov     rdx, rsi; unsigned __int16 *
0x18002e4a5  lea     rcx, [rsp+2B0h+var_250]; this
0x18002e4aa  call    ?ActivateProfile@InputProfileSettings@@QEAAJPEBG@Z; InputProfileSettings::ActivateProfile(ushort const *)
0x18002e4af  lea     rcx, [rsp+2B0h+var_250]; this
0x18002e4b4  call    ??1InputProfileSettings@@QEAA@XZ; InputProfileSettings::~InputProfileSettings(void)
0x18002e4b9  inc     r14
0x18002e4bc  cmp     [rsi+r14*2], r15w
0x18002e4c1  jnz     short loc_18002E4B9
0x18002e4c3  mov     [rsp+2B0h+var_288], r13
0x18002e4c8  mov     r9, r14
0x18002e4cb  mov     r8, rsi
0x18002e4ce  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x18002e4d3  cmp     rbx, rdi
0x18002e4d6  jz      short loc_18002E4E1
0x18002e4d8  mov     rcx, rbx; pv
0x18002e4db  call    cs:__imp_CoTaskMemFree
0x18002e4e1  mov     rcx, rdi; pv
0x18002e4e4  call    cs:__imp_CoTaskMemFree
0x18002e4ea  nop
0x18002e4eb  mov     rcx, [rsp+2B0h+string]; string
0x18002e4f0  call    cs:__imp_WindowsDeleteString
0x18002e4f6  lea     rdi, ??_7CLanguageProfileHelper_SetPerUserInputMethods_Activity@LogonControllerTelemetry@@6B@; const LogonControllerTelemetry::CLanguageProfileHelper_SetPerUserInputMethods_Activity::`vftable'
0x18002e4fd  mov     rcx, r12; hMem
0x18002e500  call    cs:__imp_LocalFree
0x18002e506  nop
0x18002e507  mov     rcx, [rsp+2B0h+var_260]; string
0x18002e50c  call    cs:__imp_WindowsDeleteString
0x18002e512  xor     edx, edx
0x18002e514  lea     rcx, [rbp+1B0h+var_190]
0x18002e518  call    ?Stop@?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18002e51d  nop
0x18002e51e  mov     [rbp+1B0h+var_190], rdi
0x18002e522  lea     rcx, [rbp+1B0h+var_190]
0x18002e526  call    ?Destroy@?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18002e52b  lea     rcx, [rbp+1B0h+var_190]
0x18002e52f  call    ??1?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18002e534  mov     rcx, [rbp+1B0h+var_40]
0x18002e53b  xor     rcx, rsp; StackCookie
0x18002e53e  call    __security_check_cookie
0x18002e543  mov     rbx, [rsp+2B0h+arg_10]
0x18002e54b  add     rsp, 280h
0x18002e552  pop     r15
0x18002e554  pop     r14
0x18002e556  pop     r13
0x18002e558  pop     r12
0x18002e55a  pop     rdi
0x18002e55b  pop     rsi
0x18002e55c  pop     rbp
0x18002e55d  retn
```
