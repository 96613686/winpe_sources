# _lambda_28df3cfd6063d893b9f038089fbbae27_::operator()(void)

- ea: `0x1800140e0`
- end: `0x180014501`
- name: `??R_lambda_28df3cfd6063d893b9f038089fbbae27_@@QEBAXXZ`
- size: `1057`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000c26c`

## callees

- `0x180003520`
- `0x180004118`
- `0x180005954`
- `0x180006380`
- `0x18000a7fc`
- `0x18000afac`
- `0x18000bc70`
- `0x18000c32c`
- `0x18001142c`
- `0x180012160`
- `0x180013388`
- `0x1800140e0`
- `0x180015bb8`
- `0x180017e84`
- `0x18001b728`
- `0x18001bb94`
- `0x18001c058`
- `0x1800214f4`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014113`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800141a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014113`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800141a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180014148`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180014148`
- `Bcp47Langs!GetUserLanguages` at `0x18001412a`
- `Bcp47Langs!GetUserLanguages` at `0x18001412a`

## string_xrefs

- `0x1800141d2`: `InstallationTaskRun`
- `0x1800144ef`: `onecore\shell\cpls\internationalsettings\languagecomponentsinstaller\dll\languagecomponentsinstaller.cpp`

## pseudocode

```c
__int64 __fastcall _lambda_28df3cfd6063d893b9f038089fbbae27_::operator()(_QWORD *a1)
{
  int UserLanguages; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v4; // r8
  HSTRING v5; // rcx
  __int64 v6; // rax
  __int64 v7; // r10
  __int64 v8; // r8
  __int64 v9; // rcx
  __int64 v10; // r9
  __int128 v11; // rax
  _QWORD *v12; // rdx
  _QWORD *v13; // rdx
  _QWORD *v14; // rdx
  unsigned int v15; // eax
  __int64 v16; // rdx
  int v18; // [rsp+20h] [rbp-E0h]
  __int128 v19; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v20; // [rsp+50h] [rbp-B0h]
  _QWORD *v21; // [rsp+60h] [rbp-A0h]
  _QWORD v22[3]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v23[3]; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v24[4]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v25[7]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD *v26; // [rsp+F8h] [rbp-8h]
  _QWORD v27[7]; // [rsp+100h] [rbp+0h] BYREF
  _QWORD *v28; // [rsp+138h] [rbp+38h]
  _QWORD v29[7]; // [rsp+140h] [rbp+40h] BYREF
  _QWORD *v30; // [rsp+178h] [rbp+78h]
  const wchar_t *v31; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v32[200]; // [rsp+188h] [rbp+88h] BYREF
  HSTRING string; // [rsp+250h] [rbp+150h] BYREF
  __int128 v34; // [rsp+258h] [rbp+158h] BYREF
  __int64 v35; // [rsp+268h] [rbp+168h]
  __int64 v36; // [rsp+270h] [rbp+170h] BYREF
  __int64 v37; // [rsp+278h] [rbp+178h]
  __int64 v38; // [rsp+280h] [rbp+180h]
  void **v39; // [rsp+290h] [rbp+190h] BYREF
  int v40; // [rsp+298h] [rbp+198h] BYREF
  char v41; // [rsp+29Ch] [rbp+19Ch]
  int v42; // [rsp+2C0h] [rbp+1C0h] BYREF
  const char *v43; // [rsp+2C8h] [rbp+1C8h]
  __int64 v44; // [rsp+2D0h] [rbp+1D0h]
  char v45; // [rsp+2D8h] [rbp+1D8h]
  int v46; // [rsp+2E0h] [rbp+1E0h]
  _BYTE v47[152]; // [rsp+2E8h] [rbp+1E8h] BYREF
  __int128 v48; // [rsp+380h] [rbp+280h]
  int v49; // [rsp+390h] [rbp+290h]
  __int64 v50; // [rsp+398h] [rbp+298h]
  int *v51; // [rsp+3A0h] [rbp+2A0h]
  __int64 v52; // [rsp+3A8h] [rbp+2A8h]
  __int64 v53; // [rsp+3B0h] [rbp+2B0h]
  void ***v54; // [rsp+3B8h] [rbp+2B8h]
  __int64 v55; // [rsp+3C0h] [rbp+2C0h]
  int v56; // [rsp+3C8h] [rbp+2C8h]
  int *v57; // [rsp+3D0h] [rbp+2D0h]
  char v58; // [rsp+3D8h] [rbp+2D8h]
  _BYTE v59[352]; // [rsp+3E0h] [rbp+2E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+578h] [rbp+478h]

  string = 0;
  WindowsDeleteString(0);
  string = 0;
  UserLanguages = GetUserLanguages(59, &string);
  if ( UserLanguages < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x102,
      (unsigned int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\languagecomponentsinstaller.cpp",
      (const char *)(unsigned int)UserLanguages,
      v18);
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v19 = 0;
  v20 = 0;
  v4 = -1;
  do
    ++v4;
  while ( StringRawBuffer[v4] );
  std::wstring::_Construct<1,unsigned short const *>(&v19);
  WstringContainerFromDelimitedString<std::vector<std::wstring>>(&v34, &v19);
  std::wstring::~wstring(&v19);
  v5 = string;
  if ( string )
    WindowsDeleteString(string);
  CLanguageComponentsInstallerHandler::GetInputLanguages(v5, &v36);
  v40 = 0;
  v41 = 0;
  v45 = 0;
  v42 = 0;
  v43 = "InstallationTaskRun";
  v44 = 0;
  v46 = 0;
  v48 = 0;
  memset_0(v47, 0, sizeof(v47));
  v49 = 1;
  v50 = 0;
  v51 = &v40;
  v52 = 0;
  v53 = 0;
  v54 = &v39;
  v55 = 0;
  v56 = 0;
  v57 = &v42;
  v58 = 0;
  v39 = &LanguageComponentsInstallerTelemetry::InstallationTaskRun::`vftable';
  v6 = std::vector<std::wstring>::vector<std::wstring>(&v19, &v34);
  LanguageComponentsInstallerTelemetry::InstallationTaskRun::StartActivity(&v39, v6);
  v29[0] = &std::_Func_impl_no_alloc<bool (*)(void),bool,>::`vftable';
  v29[1] = RequiredLanguageFeaturesInstaller::DefaultWasSpeechUsedRecently;
  v30 = v29;
  v27[0] = &std::_Func_impl_no_alloc<bool (*)(void),bool,>::`vftable';
  v27[1] = RequiredLanguageFeaturesInstaller::DefaultIsMixedRealityConfigured;
  v28 = v27;
  v25[0] = &std::_Func_impl_no_alloc<enum DigitizerSupport (*)(void),enum DigitizerSupport,>::`vftable';
  v25[1] = &RequiredLanguageFeaturesInstaller::DefaultGetDigitizerSupport;
  v26 = v25;
  v7 = v38;
  v38 = 0;
  v8 = v37;
  v37 = 0;
  v9 = v36;
  v36 = 0;
  string = (HSTRING)v23;
  v10 = v35;
  v35 = 0;
  v11 = v34;
  v34 = 0u;
  v21 = v22;
  memset(v23, 0, sizeof(v23));
  v24[0] = v9;
  v24[1] = v8;
  v24[2] = v7;
  memset(v22, 0, sizeof(v22));
  v19 = v11;
  *(_QWORD *)&v20 = v10;
  memset_0(v32, 0, 0xC0u);
  v31 = L"LanguageFeaturesOnDemand";
  RequiredLanguageFeaturesInstaller::RequiredLanguageFeaturesInstaller(
    (unsigned int)v59,
    (unsigned int)&v31,
    (unsigned int)&v19,
    (unsigned int)v24,
    (__int64)v25,
    (__int64)v27,
    (__int64)v29);
  std::vector<std::wstring>::_Tidy(v22);
  std::vector<std::wstring>::_Tidy(v23);
  if ( v26 )
  {
    v12 = v25;
    LOBYTE(v12) = v26 != v25;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v26 + 32LL))(v26, v12);
    v26 = 0;
  }
  if ( v28 )
  {
    v13 = v27;
    LOBYTE(v13) = v28 != v27;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v28 + 32LL))(v28, v13);
    v28 = 0;
  }
  if ( v30 )
  {
    v14 = v29;
    LOBYTE(v14) = v30 != v29;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v30 + 32LL))(v30, v14);
    v30 = 0;
  }
  v15 = RequiredLanguageFeaturesInstaller::InstallFeatures<void (std::vector<CbsLanguageFeature> const &)>(v59, a1[1]);
  CLanguageComponentsInstallerHandler::SetTaskEnabledStateForCurrentUserAccordingToFutureAction(*a1, v16, v15);
  wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::Stop(&v39);
  RequiredLanguageFeaturesInstaller::~RequiredLanguageFeaturesInstaller((RequiredLanguageFeaturesInstaller *)v59);
  v39 = &LanguageComponentsInstallerTelemetry::InstallationTaskRun::`vftable';
  wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v39);
  wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LanguageComponentsInstallerTelemetryProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(&v39);
  std::vector<std::wstring>::_Tidy(&v36);
  return std::vector<std::wstring>::_Tidy(&v34);
}

```

## disassembly

```asm
0x1800140e0  push    rbp
0x1800140e2  push    rbx
0x1800140e3  push    rsi
0x1800140e4  push    rdi
0x1800140e5  lea     rbp, [rsp-458h]
0x1800140ed  sub     rsp, 558h
0x1800140f4  mov     rax, cs:__security_cookie
0x1800140fb  xor     rax, rsp
0x1800140fe  mov     [rbp+470h+var_30], rax
0x180014105  mov     rbx, rcx
0x180014108  xor     edi, edi
0x18001410a  mov     [rbp+470h+string], rdi
0x180014111  xor     ecx, ecx; string
0x180014113  call    cs:__imp_WindowsDeleteString
0x180014119  mov     [rbp+470h+string], rdi
0x180014120  lea     ecx, [rdi+3Bh]
0x180014123  lea     rdx, [rbp+470h+string]
0x18001412a  call    cs:__imp_GetUserLanguages
0x180014130  mov     rcx, [rbp+478h]; this
0x180014137  test    eax, eax
0x180014139  js      loc_1800144EC
0x18001413f  xor     edx, edx; length
0x180014141  mov     rcx, [rbp+470h+string]; string
0x180014148  call    cs:__imp_WindowsGetStringRawBuffer
0x18001414e  xorps   xmm0, xmm0
0x180014151  movups  [rsp+570h+var_530], xmm0
0x180014156  xorps   xmm1, xmm1
0x180014159  movdqu  [rsp+570h+var_520], xmm1
0x18001415f  or      r8, 0FFFFFFFFFFFFFFFFh
0x180014163  inc     r8
0x180014166  cmp     [rax+r8*2], di
0x18001416b  jnz     short loc_180014163
0x18001416d  mov     rdx, rax
0x180014170  lea     rcx, [rsp+570h+var_530]
0x180014175  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001417a  nop
0x18001417b  lea     rdx, [rsp+570h+var_530]
0x180014180  lea     rcx, [rbp+470h+var_318]
0x180014187  call    ??$WstringContainerFromDelimitedString@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@G@Z; WstringContainerFromDelimitedString<std::vector<std::wstring>>(std::wstring const &,ushort)
0x18001418c  nop
0x18001418d  lea     rcx, [rsp+570h+var_530]; void *
0x180014192  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180014197  nop
0x180014198  mov     rcx, [rbp+470h+string]; string
0x18001419f  test    rcx, rcx
0x1800141a2  jz      short loc_1800141AB
0x1800141a4  call    cs:__imp_WindowsDeleteString
0x1800141aa  nop
0x1800141ab  lea     rdx, [rbp+470h+var_300]
0x1800141b2  call    ?GetInputLanguages@CLanguageComponentsInstallerHandler@@AEBA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ; CLanguageComponentsInstallerHandler::GetInputLanguages(void)
0x1800141b7  nop
0x1800141b8  mov     [rbp+470h+var_2D8], edi
0x1800141be  mov     [rbp+470h+var_2D4], dil
0x1800141c5  mov     [rbp+470h+var_298], dil
0x1800141cc  mov     [rbp+470h+var_2B0], edi
0x1800141d2  lea     rax, aInstallationta; "InstallationTaskRun"
0x1800141d9  mov     [rbp+470h+var_2A8], rax
0x1800141e0  mov     [rbp+470h+var_2A0], rdi
0x1800141e7  mov     [rbp+470h+var_290], edi
0x1800141ed  xorps   xmm0, xmm0
0x1800141f0  movdqa  [rbp+470h+var_1F0], xmm0
0x1800141f8  xor     edx, edx; Val
0x1800141fa  mov     r8d, 98h; Size
0x180014200  lea     rcx, [rbp+470h+var_288]; void *
0x180014207  call    memset_0
0x18001420c  mov     [rbp+470h+var_1E0], 1
0x180014216  xor     eax, eax
0x180014218  mov     [rbp+470h+var_1D8], rax
0x18001421f  lea     rax, [rbp+470h+var_2D8]
0x180014226  mov     [rbp+470h+var_1D0], rax
0x18001422d  mov     [rbp+470h+var_1C8], rdi
0x180014234  mov     [rbp+470h+var_1C0], rdi
0x18001423b  lea     rax, [rbp+470h+var_2E0]
0x180014242  mov     [rbp+470h+var_1B8], rax
0x180014249  mov     [rbp+470h+var_1B0], rdi
0x180014250  mov     [rbp+470h+var_1A8], edi
0x180014256  lea     rax, [rbp+470h+var_2B0]
0x18001425d  mov     [rbp+470h+var_1A0], rax
0x180014264  mov     [rbp+470h+var_198], dil
0x18001426b  lea     rsi, ??_7InstallationTaskRun@LanguageComponentsInstallerTelemetry@@6B@; const LanguageComponentsInstallerTelemetry::InstallationTaskRun::`vftable'
0x180014272  mov     [rbp+470h+var_2E0], rsi
0x180014279  lea     rdx, [rbp+470h+var_318]
0x180014280  lea     rcx, [rsp+570h+var_530]
0x180014285  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::wstring>::vector<std::wstring>(std::vector<std::wstring> const &)
0x18001428a  mov     rdx, rax
0x18001428d  lea     rcx, [rbp+470h+var_2E0]
0x180014294  call    ?StartActivity@InstallationTaskRun@LanguageComponentsInstallerTelemetry@@QEAAXV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; LanguageComponentsInstallerTelemetry::InstallationTaskRun::StartActivity(std::vector<std::wstring>)
0x180014299  nop
0x18001429a  lea     rcx, ??_7?$_Func_impl_no_alloc@P6A_NXZ_N$$V@std@@6B@; const std::_Func_impl_no_alloc<bool (*)(void),bool,>::`vftable'
0x1800142a1  mov     [rbp+470h+var_430], rcx
0x1800142a5  lea     rax, ?DefaultWasSpeechUsedRecently@RequiredLanguageFeaturesInstaller@@CA_NXZ; RequiredLanguageFeaturesInstaller::DefaultWasSpeechUsedRecently(void)
0x1800142ac  mov     [rbp+470h+var_428], rax
0x1800142b0  lea     rax, [rbp+470h+var_430]
0x1800142b4  mov     [rbp+470h+var_3F8], rax
0x1800142b8  mov     [rbp+470h+var_470], rcx
0x1800142bc  lea     rax, ?DefaultIsMixedRealityConfigured@RequiredLanguageFeaturesInstaller@@CA_NXZ; RequiredLanguageFeaturesInstaller::DefaultIsMixedRealityConfigured(void)
0x1800142c3  mov     [rbp+470h+var_468], rax
0x1800142c7  lea     rax, [rbp+470h+var_470]
0x1800142cb  mov     [rbp+470h+var_438], rax
0x1800142cf  lea     rax, ??_7?$_Func_impl_no_alloc@P6A?AW4DigitizerSupport@@XZW41@$$V@std@@6B@; const std::_Func_impl_no_alloc<DigitizerSupport (*)(void),DigitizerSupport,>::`vftable'
0x1800142d6  mov     [rbp+470h+var_4B0], rax
0x1800142da  lea     rax, ?DefaultGetDigitizerSupport@RequiredLanguageFeaturesInstaller@@CA?AW4DigitizerSupport@@XZ; RequiredLanguageFeaturesInstaller::DefaultGetDigitizerSupport(void)
0x1800142e1  mov     [rbp+470h+var_4A8], rax
0x1800142e5  lea     rax, [rbp+470h+var_4B0]
0x1800142e9  mov     [rbp+470h+var_478], rax
0x1800142ed  mov     r10, [rbp+470h+var_2F0]
0x1800142f4  mov     [rbp+470h+var_2F0], rdi
0x1800142fb  mov     r8, [rbp+470h+var_2F8]
0x180014302  mov     [rbp+470h+var_2F8], rdi
0x180014309  mov     rcx, [rbp+470h+var_300]
0x180014310  mov     [rbp+470h+var_300], rdi
0x180014317  lea     rax, [rbp+470h+var_4E8]
0x18001431b  mov     [rbp+470h+string], rax
0x180014322  mov     r9, [rbp+470h+var_308]
0x180014329  mov     [rbp+470h+var_308], rdi
0x180014330  mov     rdx, [rbp+470h+var_310]
0x180014337  mov     [rbp+470h+var_310], rdi
0x18001433e  mov     rax, [rbp+470h+var_318]
0x180014345  mov     [rbp+470h+var_318], rdi
0x18001434c  lea     r11, [rsp+570h+var_500]
0x180014351  mov     [rsp+570h+var_510], r11
0x180014356  mov     [rbp+470h+var_4D8], rdi
0x18001435a  mov     [rbp+470h+var_4E0], rdi
0x18001435e  mov     [rbp+470h+var_4E8], rdi
0x180014362  mov     [rbp+470h+var_4D0], rcx
0x180014366  mov     [rbp+470h+var_4C8], r8
0x18001436a  mov     [rbp+470h+var_4C0], r10
0x18001436e  mov     [rbp+470h+var_4F0], rdi
0x180014372  mov     [rsp+570h+var_4F8], rdi
0x180014377  mov     [rsp+570h+var_500], rdi
0x18001437c  mov     qword ptr [rsp+570h+var_530], rax
0x180014381  mov     qword ptr [rsp+570h+var_530+8], rdx
0x180014386  mov     qword ptr [rsp+570h+var_520], r9
0x18001438b  xor     edx, edx; Val
0x18001438d  mov     r8d, 0C0h; Size
0x180014393  lea     rcx, [rbp+470h+var_3E8]; void *
0x18001439a  call    memset_0
0x18001439f  lea     rax, aLanguagefeatur; "LanguageFeaturesOnDemand"
0x1800143a6  mov     [rbp+470h+var_3F0], rax
0x1800143ad  lea     rax, [rbp+470h+var_430]
0x1800143b1  mov     [rsp+570h+var_540], rax
0x1800143b6  lea     rax, [rbp+470h+var_470]
0x1800143ba  mov     [rsp+570h+var_548], rax
0x1800143bf  lea     rax, [rbp+470h+var_4B0]
0x1800143c3  mov     [rsp+570h+var_550], rax
0x1800143c8  lea     r9, [rbp+470h+var_4D0]
0x1800143cc  lea     r8, [rsp+570h+var_530]
0x1800143d1  lea     rdx, [rbp+470h+var_3F0]
0x1800143d8  lea     rcx, [rbp+470h+var_190]
0x1800143df  call    ??$?0VCbsLanguageSession@@@RequiredLanguageFeaturesInstaller@@QEAA@AEBVCbsLanguageSession@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@1AEBV?$function@$$A6A?AW4DigitizerSupport@@XZ@3@AEBV?$function@$$A6A_NXZ@3@3@Z; RequiredLanguageFeaturesInstaller::RequiredLanguageFeaturesInstaller(CbsLanguageSession const &,std::vector<std::wstring>,std::vector<std::wstring>,std::function<DigitizerSupport (void)> const &,std::function<bool (void)> const &,std::function<bool (void)> const &)
0x1800143e4  nop
0x1800143e5  lea     rcx, [rsp+570h+var_500]
0x1800143ea  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800143ef  nop
0x1800143f0  lea     rcx, [rbp+470h+var_4E8]
0x1800143f4  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800143f9  nop
0x1800143fa  mov     rcx, [rbp+470h+var_478]
0x1800143fe  test    rcx, rcx
0x180014401  jz      short loc_18001441D
0x180014403  mov     rax, [rcx]
0x180014406  lea     rdx, [rbp+470h+var_4B0]
0x18001440a  cmp     rcx, rdx
0x18001440d  setnz   dl
0x180014410  mov     rax, [rax+20h]
0x180014414  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014419  mov     [rbp+470h+var_478], rdi
0x18001441d  mov     rcx, [rbp+470h+var_438]
0x180014421  test    rcx, rcx
0x180014424  jz      short loc_180014440
0x180014426  mov     rax, [rcx]
0x180014429  lea     rdx, [rbp+470h+var_470]
0x18001442d  cmp     rcx, rdx
0x180014430  setnz   dl
0x180014433  mov     rax, [rax+20h]
0x180014437  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001443c  mov     [rbp+470h+var_438], rdi
0x180014440  mov     rcx, [rbp+470h+var_3F8]
0x180014444  test    rcx, rcx
0x180014447  jz      short loc_180014463
0x180014449  mov     rax, [rcx]
0x18001444c  lea     rdx, [rbp+470h+var_430]
0x180014450  cmp     rcx, rdx
0x180014453  setnz   dl
0x180014456  mov     rax, [rax+20h]
0x18001445a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001445f  mov     [rbp+470h+var_3F8], rdi
0x180014463  mov     rdx, [rbx+8]
0x180014467  lea     rcx, [rbp+470h+var_190]
0x18001446e  call    ??$InstallFeatures@$$A6AXAEBV?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@@Z@RequiredLanguageFeaturesInstaller@@QEBA?AW4FutureAction@@A6AXAEBV?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@@Z@Z; RequiredLanguageFeaturesInstaller::InstallFeatures<void (std::vector<CbsLanguageFeature> const &)>(void (&)(std::vector<CbsLanguageFeature> const &))
0x180014473  mov     r8d, eax
0x180014476  mov     rcx, [rbx]
0x180014479  call    ?SetTaskEnabledStateForCurrentUserAccordingToFutureAction@CLanguageComponentsInstallerHandler@@AEBAXPEBGW4FutureAction@@@Z; CLanguageComponentsInstallerHandler::SetTaskEnabledStateForCurrentUserAccordingToFutureAction(ushort const *,FutureAction)
0x18001447e  lea     rcx, [rbp+470h+var_2E0]
0x180014485  call    ?Stop@?$ActivityBase@VLanguageComponentsInstallerTelemetryProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18001448a  nop
0x18001448b  lea     rcx, [rbp+470h+var_190]; this
0x180014492  call    ??1RequiredLanguageFeaturesInstaller@@QEAA@XZ; RequiredLanguageFeaturesInstaller::~RequiredLanguageFeaturesInstaller(void)
0x180014497  nop
0x180014498  mov     [rbp+470h+var_2E0], rsi
0x18001449f  lea     rcx, [rbp+470h+var_2E0]
0x1800144a6  call    ?Destroy@?$ActivityBase@VLanguageComponentsInstallerTelemetryProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800144ab  lea     rcx, [rbp+470h+var_2E0]
0x1800144b2  call    ??1?$ActivityBase@VLanguageComponentsInstallerTelemetryProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LanguageComponentsInstallerTelemetryProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800144b7  nop
0x1800144b8  lea     rcx, [rbp+470h+var_300]
0x1800144bf  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800144c4  nop
0x1800144c5  lea     rcx, [rbp+470h+var_318]
0x1800144cc  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800144d1  mov     rcx, [rbp+470h+var_30]
0x1800144d8  xor     rcx, rsp; StackCookie
0x1800144db  call    __security_check_cookie
0x1800144e0  add     rsp, 558h
0x1800144e7  pop     rdi
0x1800144e8  pop     rsi
0x1800144e9  pop     rbx
0x1800144ea  pop     rbp
0x1800144eb  retn
0x1800144ec  mov     r9d, eax; char *
0x1800144ef  lea     r8, aOnecoreShellCp_1; "onecore\\shell\\cpls\\internationalsett"...
0x1800144f6  mov     edx, 102h; void *
0x1800144fb  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
