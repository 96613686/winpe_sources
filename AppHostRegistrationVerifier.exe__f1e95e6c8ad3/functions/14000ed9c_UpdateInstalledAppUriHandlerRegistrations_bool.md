# UpdateInstalledAppUriHandlerRegistrations(bool)

- ea: `0x14000ed9c`
- end: `0x14000f29e`
- name: `?UpdateInstalledAppUriHandlerRegistrations@@YAX_N@Z`
- size: `1282`
- prototype: `void __fastcall(char)`
- caller_count: `1`
- callee_count: `27`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140008150`

## callees

- `0x140002210`
- `0x140003cd8`
- `0x140008450`
- `0x140009294`
- `0x140009738`
- `0x1400099c4`
- `0x14000a04c`
- `0x14000a13c`
- `0x14000a3f0`
- `0x14000a448`
- `0x14000a500`
- `0x14000a544`
- `0x14000ad34`
- `0x14000b114`
- `0x14000be20`
- `0x14000bef8`
- `0x14000ced4`
- `0x14000d49c`
- `0x14000dfdc`
- `0x14000e1e0`
- `0x14000e348`
- `0x14000ed9c`
- `0x14000f2a4`
- `0x14000f3b8`
- `0x14000fbb0`
- `0x14000fc20`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000eeab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000eeba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000f055`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000eeab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000eeba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000f055`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000ef29`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000ef29`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x14000ef54`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x14000ef54`

## string_xrefs

- `0x14000edcc`: `VerifyAllInstalled`

## pseudocode

```c
void __fastcall UpdateInstalledAppUriHandlerRegistrations(char a1)
{
  char v1; // r13
  HSTRING *v2; // r15
  AppUriHandlerRegistrationInfo *v3; // r12
  __int64 RegKeyForPackageAndHost; // rax
  const unsigned __int16 *StringRawBuffer; // rsi
  const unsigned __int16 *v6; // rbx
  unsigned int v7; // eax
  unsigned int v8; // r8d
  int v9; // eax
  __int64 v10; // rsi
  __int64 (__fastcall *v11)(__int64, HSTRING, _QWORD); // rbx
  int v12; // eax
  __int64 (__fastcall ***v13)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v14)(_QWORD, GUID *, _QWORD); // rsi
  int v15; // eax
  PCWSTR v16; // rax
  __int64 AppUriHandlerJsonFromWebHost; // rax
  __int64 (__fastcall ***v18)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v19)(_QWORD, GUID *, _QWORD); // rsi
  int v20; // eax
  int v21; // eax
  struct Windows::Data::Json::IJsonObject **AppUriHandlerRegistrationEntryFromJson; // rax
  struct Windows::Data::Json::IJsonObject *v23; // rbx
  unsigned int v24; // r8d
  const char *v25; // r9
  unsigned int lpData; // [rsp+20h] [rbp-368h]
  char v27; // [rsp+30h] [rbp-358h] BYREF
  _BYTE v28[7]; // [rsp+31h] [rbp-357h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-350h] BYREF
  __int64 (__fastcall ***v30)(_QWORD, GUID *, _QWORD); // [rsp+40h] [rbp-348h] BYREF
  __int64 (__fastcall ***v31)(_QWORD, GUID *, _QWORD); // [rsp+48h] [rbp-340h] BYREF
  BYTE Data[8]; // [rsp+50h] [rbp-338h] BYREF
  __int64 v33; // [rsp+58h] [rbp-330h] BYREF
  __int64 v34; // [rsp+60h] [rbp-328h] BYREF
  struct Windows::Data::Json::IJsonObject *v35; // [rsp+68h] [rbp-320h] BYREF
  HSTRING *v36; // [rsp+70h] [rbp-318h]
  _BYTE v37[8]; // [rsp+78h] [rbp-310h] BYREF
  AppUriHandlerRegistrationInfo *v38[2]; // [rsp+80h] [rbp-308h] BYREF
  __int64 v39; // [rsp+90h] [rbp-2F8h]
  HKEY phkResult; // [rsp+98h] [rbp-2F0h] BYREF
  _BYTE v41[8]; // [rsp+A0h] [rbp-2E8h] BYREF
  _BYTE v42[8]; // [rsp+A8h] [rbp-2E0h] BYREF
  AppUriHandlerRegistrationInfo *v43; // [rsp+B0h] [rbp-2D8h]
  _QWORD v44[42]; // [rsp+C0h] [rbp-2C8h] BYREF
  _QWORD v45[42]; // [rsp+210h] [rbp-178h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+388h] [rbp+0h]

  v1 = a1;
  wil::ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v45,
    "VerifyAllInstalled");
  v45[0] = &HostNameVerifierProvider::VerifyAllInstalled::`vftable';
  HostNameVerifierProvider::VerifyAllInstalled::StartActivity((HostNameVerifierProvider::VerifyAllInstalled *)v45);
  wil::ActivateInstance<Windows::Data::Json::IJsonObject>(v37);
  wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::copy<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>(
    v37,
    &v33);
  GetAllAppUriHandlerRegistrationsAsHostnameAndPackageFamilyName(v38);
  v2 = (HSTRING *)v38[0];
  v3 = v38[1];
  v43 = v38[1];
  while ( 1 )
  {
    v36 = v2;
    if ( v2 == (HSTRING *)v3 )
      break;
    try
    {
      hKey = 0;
      RegKeyForPackageAndHost = GetRegKeyForPackageAndHost(&phkResult);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::operator=(
        &hKey,
        RegKeyForPackageAndHost);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
      if ( hKey && (v1 || DoesAppRequireValidation(hKey)) )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(*v2, 0);
        v6 = WindowsGetStringRawBuffer(v2[1], 0);
        wil::ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
          v44,
          "VerifyFromWeb");
        v44[0] = &HostNameVerifierProvider::VerifyFromWeb::`vftable';
        HostNameVerifierProvider::VerifyFromWeb::StartActivity(
          (HostNameVerifierProvider::VerifyFromWeb *)v44,
          v6,
          StringRawBuffer);
        *(_DWORD *)Data = 0;
        v7 = RegSetValueExW(hKey, L"IsDelegatedValidation", 0, 4u, Data, 4u);
        if ( v7 )
          wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x179, v8, (const char *)v7, lpData);
        RegDeleteValueW(hKey, L"IsEnabledByCapability");
        v27 = 0;
        v9 = (*(__int64 (__fastcall **)(__int64, HSTRING, char *))(*(_QWORD *)v33 + 64LL))(v33, *v2, &v27);
        if ( v9 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x180,
            (unsigned int)"onecoreuap\\base\\appmodel\\apphostnameregistrationverifier\\lib\\hostnameverifier.cpp",
            (const char *)(unsigned int)v9,
            lpData);
        v31 = 0;
        v30 = 0;
        if ( v27 )
        {
          v10 = v33;
          v11 = *(__int64 (__fastcall **)(__int64, HSTRING, _QWORD))(*(_QWORD *)v33 + 48LL);
          Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&v30);
          v12 = v11(v10, *v2, &v30);
          if ( v12 < 0 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0x185,
              (unsigned int)"onecoreuap\\base\\appmodel\\apphostnameregistrationverifier\\lib\\hostnameverifier.cpp",
              (const char *)(unsigned int)v12,
              lpData);
          v13 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v30;
          v14 = **v30;
          Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&v31);
          v15 = v14(v13, &GUID_08c1ddb6_0cbd_4a9a_b5d3_2f852dc37e81, &v31);
          if ( v15 < 0 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0x186,
              (unsigned int)"onecoreuap\\base\\appmodel\\apphostnameregistrationverifier\\lib\\hostnameverifier.cpp",
              (const char *)(unsigned int)v15,
              lpData);
        }
        else
        {
          v16 = WindowsGetStringRawBuffer(*v2, 0);
          AppUriHandlerJsonFromWebHost = GetAppUriHandlerJsonFromWebHost(v41, v16);
          Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::operator=(&v31, AppUriHandlerJsonFromWebHost);
          Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(v41);
          v18 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v31;
          v19 = **v31;
          Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&v30);
          v20 = v19(v18, &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e, &v30);
          if ( v20 < 0 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0x18B,
              (unsigned int)"onecoreuap\\base\\appmodel\\apphostnameregistrationverifier\\lib\\hostnameverifier.cpp",
              (const char *)(unsigned int)v20,
              lpData);
          v28[0] = 0;
          v21 = (*(__int64 (__fastcall **)(__int64, HSTRING, __int64 (__fastcall ***)(_QWORD, GUID *, _QWORD), _BYTE *))(*(_QWORD *)v33 + 80LL))(
                  v33,
                  *v2,
                  v30,
                  v28);
          if ( v21 < 0 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0x18E,
              (unsigned int)"onecoreuap\\base\\appmodel\\apphostnameregistrationverifier\\lib\\hostnameverifier.cpp",
              (const char *)(unsigned int)v21,
              lpData);
        }
        v35 = 0;
        AppUriHandlerRegistrationEntryFromJson = (struct Windows::Data::Json::IJsonObject **)GetAppUriHandlerRegistrationEntryFromJson(
                                                                                               v42,
                                                                                               v31,
                                                                                               v2[1]);
        v23 = 0;
        if ( &v34 != (__int64 *)AppUriHandlerRegistrationEntryFromJson )
        {
          v23 = *AppUriHandlerRegistrationEntryFromJson;
          *AppUriHandlerRegistrationEntryFromJson = 0;
        }
        v34 = 0;
        v35 = v23;
        Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&v34);
        Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(v42);
        if ( v23 )
          UpdateRegistryForAppUriHandlerPackage(v23, hKey);
        else
          UpdatePackageForFailedValidation(hKey);
        wil::ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v44);
        Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&v35);
        Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&v30);
        Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&v31);
        HostNameVerifierProvider::VerifyFromWeb::~VerifyFromWeb((HostNameVerifierProvider::VerifyFromWeb *)v44);
      }
    }
    catch ( ... )
    {
      try
      {
        UpdatePackageForFailedValidation(hKey);
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(retaddr, (void *)0x1AB, v24, v25);
      }
      v1 = a1;
      v2 = v36;
      v3 = v43;
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    v2 += 2;
  }
  wil::ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v45);
  if ( v38[0] )
  {
    std::_Destroy_range<std::allocator<AppUriHandlerRegistrationInfo>>(v38[0]);
    std::_Deallocate<16>(v38[0], (v39 - (unsigned __int64)v38[0]) & 0xFFFFFFFFFFFFFFF0uLL);
    *(_OWORD *)v38 = 0;
    v39 = 0;
  }
  wil::com_ptr_t<Windows::Internal::StateRepository::IDynamicAppUriHandlerStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::StateRepository::IDynamicAppUriHandlerStatics,wil::err_exception_policy>(&v33);
  wil::com_ptr_t<Windows::Internal::StateRepository::IDynamicAppUriHandlerStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::StateRepository::IDynamicAppUriHandlerStatics,wil::err_exception_policy>(v37);
  HostNameVerifierProvider::VerifyAllInstalled::~VerifyAllInstalled((HostNameVerifierProvider::VerifyAllInstalled *)v45);
}

```

## disassembly

```asm
0x14000ed9c  mov     [rsp+arg_8], rbx
0x14000eda1  mov     [rsp+arg_10], rsi
0x14000eda6  mov     [rsp+arg_0], cl
0x14000edaa  push    r12
0x14000edac  push    r13
0x14000edae  push    r15
0x14000edb0  sub     rsp, 370h
0x14000edb7  mov     rax, cs:__security_cookie
0x14000edbe  xor     rax, rsp
0x14000edc1  mov     [rsp+388h+var_28], rax
0x14000edc9  mov     r13b, cl
0x14000edcc  lea     rdx, aVerifyallinsta; "VerifyAllInstalled"
0x14000edd3  lea     rcx, [rsp+388h+var_178]
0x14000eddb  call    ??0?$ActivityBase@VHostNameVerifierProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x14000ede0  lea     rax, ??_7VerifyAllInstalled@HostNameVerifierProvider@@6B@; const HostNameVerifierProvider::VerifyAllInstalled::`vftable'
0x14000ede7  mov     [rsp+388h+var_178], rax
0x14000edef  lea     rcx, [rsp+388h+var_178]; this
0x14000edf7  call    ?StartActivity@VerifyAllInstalled@HostNameVerifierProvider@@QEAAXXZ; HostNameVerifierProvider::VerifyAllInstalled::StartActivity(void)
0x14000edfc  nop
0x14000edfd  lea     rcx, [rsp+388h+var_310]
0x14000ee02  call    ??$ActivateInstance@UIJsonObject@Json@Data@Windows@@@wil@@YA?AV?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::ActivateInstance<Windows::Data::Json::IJsonObject>(ushort const *)
0x14000ee07  nop
0x14000ee08  lea     rdx, [rsp+388h+var_330]
0x14000ee0d  lea     rcx, [rsp+388h+var_310]
0x14000ee12  call    ??$copy@U?$IMap@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@U?$IMap@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::copy<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>(void)
0x14000ee17  nop
0x14000ee18  lea     rcx, [rsp+388h+var_308]
0x14000ee20  call    ?GetAllAppUriHandlerRegistrationsAsHostnameAndPackageFamilyName@@YA?AV?$vector@UAppUriHandlerRegistrationInfo@@V?$allocator@UAppUriHandlerRegistrationInfo@@@std@@@std@@XZ; GetAllAppUriHandlerRegistrationsAsHostnameAndPackageFamilyName(void)
0x14000ee25  nop
0x14000ee26  mov     r15, [rsp+388h+var_308]
0x14000ee2e  mov     r12, [rsp+388h+var_308+8]
0x14000ee36  mov     [rsp+388h+var_2D8], r12
0x14000ee3e  mov     [rsp+388h+var_318], r15
0x14000ee43  cmp     r15, r12
0x14000ee46  jz      loc_14000F1F5
0x14000ee4c  mov     [rsp+388h+hKey], 0
0x14000ee55  mov     r8, [r15]
0x14000ee58  mov     rdx, [r15+8]
0x14000ee5c  lea     rcx, [rsp+388h+phkResult]; phkResult
0x14000ee64  call    ?GetRegKeyForPackageAndHost@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUHSTRING__@@0@Z; GetRegKeyForPackageAndHost(HSTRING__ *,HSTRING__ *)
0x14000ee69  mov     rdx, rax
0x14000ee6c  lea     rcx, [rsp+388h+hKey]
0x14000ee71  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&)
0x14000ee76  lea     rcx, [rsp+388h+phkResult]
0x14000ee7e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14000ee83  cmp     [rsp+388h+hKey], 0
0x14000ee89  jz      loc_14000F1CB
0x14000ee8f  test    r13b, r13b
0x14000ee92  jnz     short loc_14000EEA6
0x14000ee94  mov     rcx, [rsp+388h+hKey]; hKey
0x14000ee99  call    ?DoesAppRequireValidation@@YA_NPEAUHKEY__@@@Z; DoesAppRequireValidation(HKEY__ *)
0x14000ee9e  test    al, al
0x14000eea0  jz      loc_14000F1CB
0x14000eea6  xor     edx, edx; length
0x14000eea8  mov     rcx, [r15]; string
0x14000eeab  call    cs:__imp_WindowsGetStringRawBuffer
0x14000eeb1  mov     rsi, rax
0x14000eeb4  xor     edx, edx; length
0x14000eeb6  mov     rcx, [r15+8]; string
0x14000eeba  call    cs:__imp_WindowsGetStringRawBuffer
0x14000eec0  mov     rbx, rax
0x14000eec3  lea     rdx, aVerifyfromweb; "VerifyFromWeb"
0x14000eeca  lea     rcx, [rsp+388h+var_2C8]
0x14000eed2  call    ??0?$ActivityBase@VHostNameVerifierProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x14000eed7  lea     rax, ??_7VerifyFromWeb@HostNameVerifierProvider@@6B@; const HostNameVerifierProvider::VerifyFromWeb::`vftable'
0x14000eede  mov     [rsp+388h+var_2C8], rax
0x14000eee6  mov     r8, rsi; unsigned __int16 *
0x14000eee9  mov     rdx, rbx; unsigned __int16 *
0x14000eeec  lea     rcx, [rsp+388h+var_2C8]; this
0x14000eef4  call    ?StartActivity@VerifyFromWeb@HostNameVerifierProvider@@QEAAXPEBG0@Z; HostNameVerifierProvider::VerifyFromWeb::StartActivity(ushort const *,ushort const *)
0x14000eef9  nop
0x14000eefa  mov     dword ptr [rsp+388h+Data], 0
0x14000ef02  mov     [rsp+388h+cbData], 4; cbData
0x14000ef0a  lea     rax, [rsp+388h+Data]
0x14000ef0f  mov     [rsp+388h+lpData], rax; int
0x14000ef14  mov     r9d, 4; dwType
0x14000ef1a  xor     r8d, r8d; Reserved
0x14000ef1d  lea     rdx, aIsdelegatedval; "IsDelegatedValidation"
0x14000ef24  mov     rcx, [rsp+388h+hKey]; hKey
0x14000ef29  call    cs:__imp_RegSetValueExW
0x14000ef2f  mov     rcx, [rsp+388h]; this
0x14000ef37  test    eax, eax
0x14000ef39  jz      short loc_14000EF48
0x14000ef3b  mov     r9d, eax; char *
0x14000ef3e  mov     edx, 179h; void *
0x14000ef43  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x14000ef48  lea     rdx, aIsenabledbycap; "IsEnabledByCapability"
0x14000ef4f  mov     rcx, [rsp+388h+hKey]; hKey
0x14000ef54  call    cs:__imp_RegDeleteValueW
0x14000ef5a  mov     [rsp+388h+var_358], 0
0x14000ef5f  mov     rcx, [rsp+388h+var_330]
0x14000ef64  mov     rax, [rcx]
0x14000ef67  lea     r8, [rsp+388h+var_358]
0x14000ef6c  mov     rdx, [r15]
0x14000ef6f  mov     rax, [rax+40h]
0x14000ef73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ef78  mov     rcx, [rsp+388h]; this
0x14000ef80  test    eax, eax
0x14000ef82  jns     short loc_14000EF98
0x14000ef84  mov     r9d, eax; char *
0x14000ef87  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\apphostname"...
0x14000ef8e  mov     edx, 180h; void *
0x14000ef93  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000ef98  mov     [rsp+388h+var_340], 0
0x14000efa1  mov     [rsp+388h+var_348], 0
0x14000efaa  cmp     [rsp+388h+var_358], 0
0x14000efaf  jz      loc_14000F050
0x14000efb5  mov     rsi, [rsp+388h+var_330]
0x14000efba  mov     rax, [rsi]
0x14000efbd  mov     rbx, [rax+30h]
0x14000efc1  lea     rcx, [rsp+388h+var_348]
0x14000efc6  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000efcb  lea     r8, [rsp+388h+var_348]
0x14000efd0  mov     rdx, [r15]
0x14000efd3  mov     rcx, rsi
0x14000efd6  mov     rax, rbx
0x14000efd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000efde  mov     rcx, [rsp+388h]; this
0x14000efe6  test    eax, eax
0x14000efe8  jns     short loc_14000EFFF
0x14000efea  mov     r9d, eax; char *
0x14000efed  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\apphostname"...
0x14000eff4  mov     edx, 185h; void *
0x14000eff9  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000efff  mov     rbx, [rsp+388h+var_348]
0x14000f004  mov     rax, [rbx]
0x14000f007  mov     rsi, [rax]
0x14000f00a  lea     rcx, [rsp+388h+var_340]
0x14000f00f  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000f014  lea     r8, [rsp+388h+var_340]
0x14000f019  lea     rdx, _GUID_08c1ddb6_0cbd_4a9a_b5d3_2f852dc37e81
0x14000f020  mov     rcx, rbx
0x14000f023  mov     rax, rsi
0x14000f026  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f02b  nop
0x14000f02c  mov     rcx, [rsp+388h]; this
0x14000f034  test    eax, eax
0x14000f036  jns     loc_14000F116
0x14000f03c  mov     r9d, eax; char *
0x14000f03f  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\apphostname"...
0x14000f046  mov     edx, 186h; void *
0x14000f04b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000f050  xor     edx, edx; length
0x14000f052  mov     rcx, [r15]; string
0x14000f055  call    cs:__imp_WindowsGetStringRawBuffer
0x14000f05b  mov     rdx, rax
0x14000f05e  lea     rcx, [rsp+388h+var_2E8]
0x14000f066  call    ?GetAppUriHandlerJsonFromWebHost@@YA?AV?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@PEBG@Z; GetAppUriHandlerJsonFromWebHost(ushort const *)
0x14000f06b  mov     rdx, rax
0x14000f06e  lea     rcx, [rsp+388h+var_340]
0x14000f073  call    ??4?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::operator=(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray> &&)
0x14000f078  lea     rcx, [rsp+388h+var_2E8]
0x14000f080  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000f085  nop
0x14000f086  mov     rbx, [rsp+388h+var_340]
0x14000f08b  mov     rax, [rbx]
0x14000f08e  mov     rsi, [rax]
0x14000f091  lea     rcx, [rsp+388h+var_348]
0x14000f096  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000f09b  lea     r8, [rsp+388h+var_348]
0x14000f0a0  lea     rdx, _GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e
0x14000f0a7  mov     rcx, rbx
0x14000f0aa  mov     rax, rsi
0x14000f0ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f0b2  nop
0x14000f0b3  mov     rcx, [rsp+388h]; this
0x14000f0bb  test    eax, eax
0x14000f0bd  jns     short loc_14000F0D3
0x14000f0bf  mov     r9d, eax; char *
0x14000f0c2  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\apphostname"...
0x14000f0c9  mov     edx, 18Bh; void *
0x14000f0ce  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000f0d3  mov     [rsp+388h+var_357], 0
0x14000f0d8  mov     rcx, [rsp+388h+var_330]
0x14000f0dd  mov     rax, [rcx]
0x14000f0e0  lea     r9, [rsp+388h+var_357]
0x14000f0e5  mov     r8, [rsp+388h+var_348]
0x14000f0ea  mov     rdx, [r15]
0x14000f0ed  mov     rax, [rax+50h]
0x14000f0f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f0f6  mov     rcx, [rsp+388h]; this
0x14000f0fe  test    eax, eax
0x14000f100  jns     short loc_14000F116
0x14000f102  mov     r9d, eax; char *
0x14000f105  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\apphostname"...
0x14000f10c  mov     edx, 18Eh; void *
0x14000f111  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000f116  mov     [rsp+388h+var_320], 0
0x14000f11f  mov     r8, [r15+8]
0x14000f123  mov     rdx, [rsp+388h+var_340]
0x14000f128  lea     rcx, [rsp+388h+var_2E0]
0x14000f130  call    ?GetAppUriHandlerRegistrationEntryFromJson@@YA?AV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEAUIJsonArray@Json@Data@Windows@@PEAUHSTRING__@@@Z; GetAppUriHandlerRegistrationEntryFromJson(Windows::Data::Json::IJsonArray *,HSTRING__ *)
0x14000f135  xor     ebx, ebx
0x14000f137  lea     rcx, [rsp+388h+var_328]
0x14000f13c  cmp     rcx, rax
0x14000f13f  jz      short loc_14000F14B
0x14000f141  mov     rbx, [rax]
0x14000f144  mov     qword ptr [rax], 0
0x14000f14b  mov     [rsp+388h+var_328], 0
0x14000f154  mov     [rsp+388h+var_320], rbx
0x14000f159  lea     rcx, [rsp+388h+var_328]
0x14000f15e  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000f163  lea     rcx, [rsp+388h+var_2E0]
0x14000f16b  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000f170  test    rbx, rbx
0x14000f173  jz      short loc_14000F184
0x14000f175  mov     rdx, [rsp+388h+hKey]; HKEY
0x14000f17a  mov     rcx, rbx; struct Windows::Data::Json::IJsonObject *
0x14000f17d  call    ?UpdateRegistryForAppUriHandlerPackage@@YAXPEAUIJsonObject@Json@Data@Windows@@PEAUHKEY__@@@Z; UpdateRegistryForAppUriHandlerPackage(Windows::Data::Json::IJsonObject *,HKEY__ *)
0x14000f182  jmp     short loc_14000F18E
0x14000f184  mov     rcx, [rsp+388h+hKey]; hKey
0x14000f189  call    ?UpdatePackageForFailedValidation@@YAXPEAUHKEY__@@@Z; UpdatePackageForFailedValidation(HKEY__ *)
0x14000f18e  lea     rcx, [rsp+388h+var_2C8]
0x14000f196  call    ?Stop@?$ActivityBase@VHostNameVerifierProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x14000f19b  nop
0x14000f19c  lea     rcx, [rsp+388h+var_320]
0x14000f1a1  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000f1a6  nop
0x14000f1a7  lea     rcx, [rsp+388h+var_348]
0x14000f1ac  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000f1b1  nop
0x14000f1b2  lea     rcx, [rsp+388h+var_340]
0x14000f1b7  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000f1bc  nop
0x14000f1bd  lea     rcx, [rsp+388h+var_2C8]; this
0x14000f1c5  call    ??1VerifyFromWeb@HostNameVerifierProvider@@QEAA@XZ; HostNameVerifierProvider::VerifyFromWeb::~VerifyFromWeb(void)
0x14000f1ca  nop
0x14000f1cb  jmp     short loc_14000F1E2
0x14000f1cd  mov     r13b, [rsp+388h+arg_0]
0x14000f1d5  mov     r15, [rsp+388h+var_318]
0x14000f1da  mov     r12, [rsp+388h+var_2D8]
0x14000f1e2  lea     rcx, [rsp+388h+hKey]
0x14000f1e7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14000f1ec  add     r15, 10h
0x14000f1f0  jmp     loc_14000EE3E
0x14000f1f5  lea     rcx, [rsp+388h+var_178]
0x14000f1fd  call    ?Stop@?$ActivityBase@VHostNameVerifierProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x14000f202  nop
0x14000f203  mov     rcx, [rsp+388h+var_308]; this
0x14000f20b  test    rcx, rcx
0x14000f20e  jz      short loc_14000F251
0x14000f210  mov     rdx, [rsp+388h+var_308+8]
0x14000f218  call    ??$_Destroy_range@V?$allocator@UAppUriHandlerRegistrationInfo@@@std@@@std@@YAXPEAUAppUriHandlerRegistrationInfo@@QEAU1@AEAV?$allocator@UAppUriHandlerRegistrationInfo@@@0@@Z; std::_Destroy_range<std::allocator<AppUriHandlerRegistrationInfo>>(AppUriHandlerRegistrationInfo *,AppUriHandlerRegistrationInfo * const,std::allocator<AppUriHandlerRegistrationInfo> &)
0x14000f21d  mov     rcx, [rsp+388h+var_308]
0x14000f225  mov     rdx, [rsp+388h+var_2F8]
0x14000f22d  sub     rdx, rcx
0x14000f230  and     rdx, 0FFFFFFFFFFFFFFF0h
0x14000f234  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x14000f239  xorps   xmm0, xmm0
0x14000f23c  movdqu  xmmword ptr [rsp+388h+var_308], xmm0
0x14000f245  mov     [rsp+388h+var_2F8], 0
0x14000f251  lea     rcx, [rsp+388h+var_330]
0x14000f256  call    ??1?$com_ptr_t@UIDynamicAppUriHandlerStatics@StateRepository@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::StateRepository::IDynamicAppUriHandlerStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::StateRepository::IDynamicAppUriHandlerStatics,wil::err_exception_policy>(void)
0x14000f25b  nop
0x14000f25c  lea     rcx, [rsp+388h+var_310]
0x14000f261  call    ??1?$com_ptr_t@UIDynamicAppUriHandlerStatics@StateRepository@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::StateRepository::IDynamicAppUriHandlerStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::StateRepository::IDynamicAppUriHandlerStatics,wil::err_exception_policy>(void)
0x14000f266  nop
0x14000f267  lea     rcx, [rsp+388h+var_178]; this
0x14000f26f  call    ??1VerifyAllInstalled@HostNameVerifierProvider@@QEAA@XZ; HostNameVerifierProvider::VerifyAllInstalled::~VerifyAllInstalled(void)
0x14000f274  mov     rcx, [rsp+388h+var_28]
0x14000f27c  xor     rcx, rsp; StackCookie
0x14000f27f  call    __security_check_cookie
0x14000f284  lea     r11, [rsp+388h+var_18]
0x14000f28c  mov     rbx, [r11+28h]
0x14000f290  mov     rsi, [r11+30h]
0x14000f294  mov     rsp, r11
0x14000f297  pop     r15
0x14000f299  pop     r13
0x14000f29b  pop     r12
0x14000f29d  retn
```
