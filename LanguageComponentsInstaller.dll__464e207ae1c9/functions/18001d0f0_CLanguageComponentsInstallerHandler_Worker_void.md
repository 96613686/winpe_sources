# CLanguageComponentsInstallerHandler::Worker(void)

- ea: `0x18001d0f0`
- end: `0x18001d294`
- name: `?Worker@CLanguageComponentsInstallerHandler@@EEAAJXZ`
- size: `420`
- prototype: `__int64 __fastcall(CLanguageComponentsInstallerHandler *__hidden this)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180003520`
- `0x180004118`
- `0x18000c26c`
- `0x18000c28c`
- `0x18001844c`
- `0x1800188a4`
- `0x180018ac4`
- `0x180019168`
- `0x18001b5b4`
- `0x18001b728`
- `0x18001d0f0`
- `0x18002085c`
- `0x18002354c`
- `0x180027b54`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18001d268`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18001d268`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18001d124`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18001d124`
- `ServicingUAPI!GetServicingStatus` at `0x18001d177`
- `ServicingUAPI!GetServicingStatus` at `0x18001d177`

## string_xrefs

- `0x18001d188`: `onecore\shell\cpls\internationalsettings\languagecomponentsinstaller\dll\languagecomponentsinstaller.cpp`
- `0x18001d252`: `onecore\shell\cpls\internationalsettings\languagecomponentsinstaller\dll\languagecomponentsinstaller.cpp`

## pseudocode

```c
__int64 __fastcall CLanguageComponentsInstallerHandler::Worker(CLanguageComponentsInstallerHandler *this)
{
  int v2; // ebx
  int v3; // esi
  int ServicingStatus; // eax
  __int64 v5; // rdx
  wil::details::in1diag3 *v6; // rcx
  int v8[2]; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD v9[3]; // [rsp+28h] [rbp-D8h] BYREF
  const wchar_t *v10; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v11[200]; // [rsp+48h] [rbp-B8h] BYREF
  int v12; // [rsp+110h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]

  v2 = RoInitialize(1);
  v8[0] = v2;
  v3 = v2;
  if ( v2 >= 0 && _InterlockedCompareExchange((volatile signed __int32 *)this + 9, 1, 1) != 1 )
  {
    memset_0(v11, 0, 0xC0u);
    v10 = L"LanguageFeaturesOnDemand";
    v12 = 0;
    ServicingStatus = GetServicingStatus(&v10, &v12);
    if ( ServicingStatus < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1BF,
        (unsigned int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\languagecomponentsinstaller.cpp",
        (const char *)(unsigned int)ServicingStatus,
        v8[0]);
    if ( (v12 & 8) == 0 )
    {
      CLanguageComponentsInstallerHandler::ParseArguments(this, *((const unsigned __int16 **)this + 1));
      if ( *((_DWORD *)this + 15) == 1 )
      {
        v3 = 0;
        if ( (IsRunningAsLocalSystem() || (unsigned int)LUAIsAdminAndIsOSSilentElevationOn())
          && CLanguageComponentsInstallerHandler::HasMinimumTimeElapsedSinceLastFailure(this)
          && !CLanguageComponentsInstallerHandler::IsInstallationBlockedByCTAPolicy(this) )
        {
          v9[0] = this;
          v9[1] = CLanguageComponentsInstallerHandler::RequestFeaturesInstall;
          v3 = wil::ResultFromException<_lambda_28df3cfd6063d893b9f038089fbbae27_>(v9);
          if ( v3 < 0 )
          {
            CLanguageComponentsInstallerHandler::SetLastFailedAttemptTime(this);
            if ( ((v3 + 2146498224) & 0xFFFFFFFB) == 0 )
              CLanguageComponentsInstallerHandler::SetTaskEnabledStateForCurrentUserAccordingToFutureAction(this, v5, 0);
          }
        }
      }
      else if ( *((_DWORD *)this + 15) == 2 )
      {
        *(_QWORD *)v8 = this;
        v3 = wil::ResultFromException__lambda_866fdbbd41730231c616b55332c38b61___(v8);
      }
      else
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
        v3 = -2147024809;
      }
    }
  }
  v6 = retaddr;
  if ( v3 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x3A,
      (unsigned int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\languagecomponentsinstaller.cpp",
      (const char *)(unsigned int)v3,
      v8[0]);
  if ( v2 >= 0 )
    RoUninitialize(v6);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18001d0f0  mov     [rsp-8+arg_8], rbx
0x18001d0f5  mov     [rsp-8+arg_10], rsi
0x18001d0fa  push    rbp
0x18001d0fb  push    rdi
0x18001d0fc  push    r14
0x18001d0fe  lea     rbp, [rsp-20h]
0x18001d103  sub     rsp, 120h
0x18001d10a  mov     rax, cs:__security_cookie
0x18001d111  xor     rax, rsp
0x18001d114  mov     [rbp+30h+var_18], rax
0x18001d118  mov     rdi, rcx
0x18001d11b  mov     r14d, 1
0x18001d121  mov     ecx, r14d
0x18001d124  call    cs:__imp_RoInitialize
0x18001d12a  mov     ebx, eax
0x18001d12c  mov     [rsp+130h+var_110], eax; int
0x18001d130  mov     esi, eax
0x18001d132  test    eax, eax
0x18001d134  js      loc_18001D247
0x18001d13a  mov     eax, r14d
0x18001d13d  lock cmpxchg [rdi+24h], r14d
0x18001d143  jz      loc_18001D247
0x18001d149  xor     edx, edx; Val
0x18001d14b  mov     r8d, 0C0h; Size
0x18001d151  lea     rcx, [rsp+130h+var_E8]; void *
0x18001d156  call    memset_0
0x18001d15b  lea     rax, aLanguagefeatur; "LanguageFeaturesOnDemand"
0x18001d162  mov     [rsp+130h+var_F0], rax
0x18001d167  mov     [rbp+30h+var_20], 0
0x18001d16e  lea     rdx, [rbp+30h+var_20]
0x18001d172  lea     rcx, [rsp+130h+var_F0]
0x18001d177  call    cs:__imp_GetServicingStatus
0x18001d17d  mov     rcx, [rbp+38h]; this
0x18001d181  test    eax, eax
0x18001d183  jns     short loc_18001D199
0x18001d185  mov     r9d, eax; char *
0x18001d188  lea     r8, aOnecoreShellCp_1; "onecore\\shell\\cpls\\internationalsett"...
0x18001d18f  mov     edx, 1BFh; void *
0x18001d194  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001d199  test    byte ptr [rbp+30h+var_20], 8
0x18001d19d  jnz     loc_18001D247
0x18001d1a3  mov     rdx, [rdi+8]; unsigned __int16 *
0x18001d1a7  mov     rcx, rdi; this
0x18001d1aa  call    ?ParseArguments@CLanguageComponentsInstallerHandler@@AEAAXPEBG@Z; CLanguageComponentsInstallerHandler::ParseArguments(ushort const *)
0x18001d1af  cmp     [rdi+3Ch], r14d
0x18001d1b3  jnz     short loc_18001D224
0x18001d1b5  xor     esi, esi
0x18001d1b7  call    ?IsRunningAsLocalSystem@@YA_NXZ; IsRunningAsLocalSystem(void)
0x18001d1bc  test    al, al
0x18001d1be  jnz     short loc_18001D1C9
0x18001d1c0  call    LUAIsAdminAndIsOSSilentElevationOn
0x18001d1c5  test    eax, eax
0x18001d1c7  jz      short loc_18001D247
0x18001d1c9  mov     rcx, rdi; this
0x18001d1cc  call    ?HasMinimumTimeElapsedSinceLastFailure@CLanguageComponentsInstallerHandler@@AEBA_NXZ; CLanguageComponentsInstallerHandler::HasMinimumTimeElapsedSinceLastFailure(void)
0x18001d1d1  test    al, al
0x18001d1d3  jz      short loc_18001D247
0x18001d1d5  mov     rcx, rdi; this
0x18001d1d8  call    ?IsInstallationBlockedByCTAPolicy@CLanguageComponentsInstallerHandler@@AEBA_NXZ; CLanguageComponentsInstallerHandler::IsInstallationBlockedByCTAPolicy(void)
0x18001d1dd  test    al, al
0x18001d1df  jnz     short loc_18001D247
0x18001d1e1  mov     [rsp+130h+var_108], rdi
0x18001d1e6  lea     rax, ?RequestFeaturesInstall@CLanguageComponentsInstallerHandler@@CAXAEBV?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@@Z; CLanguageComponentsInstallerHandler::RequestFeaturesInstall(std::vector<CbsLanguageFeature> const &)
0x18001d1ed  mov     [rsp+130h+var_100], rax
0x18001d1f2  lea     rcx, [rsp+130h+var_108]
0x18001d1f7  call    ??$ResultFromException@V_lambda_28df3cfd6063d893b9f038089fbbae27_@@@wil@@YAJ$$QEAV_lambda_28df3cfd6063d893b9f038089fbbae27_@@@Z; wil::ResultFromException<_lambda_28df3cfd6063d893b9f038089fbbae27_>(_lambda_28df3cfd6063d893b9f038089fbbae27_ &&)
0x18001d1fc  mov     esi, eax
0x18001d1fe  test    eax, eax
0x18001d200  jns     short loc_18001D247
0x18001d202  mov     rcx, rdi; this
0x18001d205  call    ?SetLastFailedAttemptTime@CLanguageComponentsInstallerHandler@@AEBAXXZ; CLanguageComponentsInstallerHandler::SetLastFailedAttemptTime(void)
0x18001d20a  lea     eax, [rsi+7FF0F6B0h]
0x18001d210  test    eax, 0FFFFFFFBh
0x18001d215  jnz     short loc_18001D247
0x18001d217  xor     r8d, r8d
0x18001d21a  mov     rcx, rdi
0x18001d21d  call    ?SetTaskEnabledStateForCurrentUserAccordingToFutureAction@CLanguageComponentsInstallerHandler@@AEBAXPEBGW4FutureAction@@@Z; CLanguageComponentsInstallerHandler::SetTaskEnabledStateForCurrentUserAccordingToFutureAction(ushort const *,FutureAction)
0x18001d222  jmp     short loc_18001D247
0x18001d224  cmp     dword ptr [rdi+3Ch], 2
0x18001d228  jnz     short loc_18001D23D
0x18001d22a  mov     qword ptr [rsp+130h+var_110], rdi
0x18001d22f  lea     rcx, [rsp+130h+var_110]
0x18001d234  call    wil__ResultFromException__lambda_866fdbbd41730231c616b55332c38b61___
0x18001d239  mov     esi, eax
0x18001d23b  jmp     short loc_18001D247
0x18001d23d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001d242  mov     esi, 80070057h
0x18001d247  mov     rcx, [rbp+38h]; this
0x18001d24b  test    esi, esi
0x18001d24d  jns     short loc_18001D264
0x18001d24f  mov     r9d, esi; char *
0x18001d252  lea     r8, aOnecoreShellCp_1; "onecore\\shell\\cpls\\internationalsett"...
0x18001d259  mov     edx, 3Ah ; ':'; void *
0x18001d25e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001d263  nop
0x18001d264  test    ebx, ebx
0x18001d266  js      short loc_18001D26E
0x18001d268  call    cs:__imp_RoUninitialize
0x18001d26e  mov     eax, esi
0x18001d270  mov     rcx, [rbp+30h+var_18]
0x18001d274  xor     rcx, rsp; StackCookie
0x18001d277  call    __security_check_cookie
0x18001d27c  lea     r11, [rsp+130h+var_10]
0x18001d284  mov     rbx, [r11+28h]
0x18001d288  mov     rsi, [r11+30h]
0x18001d28c  mov     rsp, r11
0x18001d28f  pop     r14
0x18001d291  pop     rdi
0x18001d292  pop     rbp
0x18001d293  retn
```
