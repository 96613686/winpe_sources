# CtapPluginAddAuthenticatorCredentials

- ea: `0x18011144c`
- end: `0x18011235d`
- name: `CtapPluginAddAuthenticatorCredentials`
- size: `3857`
- prototype: ``
- caller_count: `1`
- callee_count: `41`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800db20c`

## callees

- `0x18001cd78`
- `0x18001df88`
- `0x180021878`
- `0x18003164c`
- `0x1800328b8`
- `0x1800350b4`
- `0x180036da4`
- `0x180037f6c`
- `0x18003988c`
- `0x1800398d8`
- `0x18003a3c0`
- `0x18003a9e8`
- `0x180041350`
- `0x18004349c`
- `0x180043f2c`
- `0x1800467e0`
- `0x180048b70`
- `0x18004ae04`
- `0x18004f5b4`
- `0x18004f5d0`
- `0x180062fcc`
- `0x18006f30c`
- `0x180072974`
- `0x180081454`
- `0x180093428`
- `0x1800b265c`
- `0x1800b28fc`
- `0x1800b2dfc`
- `0x1800b2f9c`
- `0x1800d2d14`
- `0x18010b338`
- `0x18010bdbc`
- `0x18010bf78`
- `0x18010c8d0`
- `0x18010d430`
- `0x18010dd30`
- `0x18010e874`
- `0x18011144c`
- `0x18011c42c`
- `0x180121b94`
- `0x18013c090`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180111628`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180111628`

## string_xrefs

- `0x1801115b3`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x18011168c`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180111756`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x18011181e`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x1801118de`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180111a57`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180111bc8`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180111d30`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180111e4c`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180111f37`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180111ffe`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x18011216b`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x1801122be`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180112312`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180111e0d`: `WebAuthNPluginAuthenticatorAddCredentialsTest::reason::encoding_failed`
- `0x180111ef8`: `WebAuthNPluginAuthenticatorAddCredentialsTest::reason::encoding_failed`
- `0x1801114f8`: `WebAuthNPluginAuthenticatorAddCredentialsTest::reason::invalid_parameters`
- `0x180111573`: `WebAuthNPluginAuthenticatorAddCredentialsTest::reason::plugin_authenticators_reg_key_not_found`
- `0x180111638`: `WebAuthNPluginAuthenticatorAddCredentialsTest::reason::clsid_not_found`
- `0x18011189e`: `WebAuthNPluginAuthenticatorAddCredentialsTest::reason::name_not_found`
- `0x180112208`: `WebAuthNPluginAuthenticatorAddCredentialsTest::reason::credential_list_empty`
- `0x180111716`: `WebAuthNPluginAuthenticatorAddCredentialsTest::reason::package_verification_failed`
- `0x1801117e3`: `WebAuthNPluginAuthenticatorAddCredentialsTest::reason::decoding_failed`
- `0x180111b89`: `WebAuthNPluginAuthenticatorAddCredentialsTest::reason::decoding_failed`
- `0x180111cfb`: `WebAuthNPluginAuthenticatorAddCredentialsTest::reason::credential_id_exists`
- `0x180112085`: `WebAuthNPluginAuthenticatorAddCredentialsTest::reason::credentials_added`
- `0x18011222c`: `WebAuthNPluginAuthenticatorAddCredentialsTest::reason::credentials_added`
- `0x180111a17`: `WebAuthNPluginAuthenticatorAddCredentialsTest::reason::get_credential_list_failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=14 #try_helpers=1
__int64 __fastcall CtapPluginAddAuthenticatorCredentials(
        HANDLE token,
        __int128 *a2,
        const WCHAR *a3,
        __int64 a4,
        unsigned int a5)
{
  const char *v8; // rdx
  __int64 v9; // rbx
  __int64 v10; // rax
  const char *v11; // rax
  char v12; // r8
  const char *v13; // rdx
  int UserPluginAuthenticatorsRegKey; // ebx
  const char *v15; // rax
  HKEY *v17; // rax
  const char *v18; // rdx
  int ShouldAllowPluginOperation; // ebx
  HKEY v20; // r8
  const char *v21; // rax
  bool v22; // sf
  const char *v23; // rdx
  const char *v24; // rax
  const char *v25; // rdx
  unsigned int v26; // ebx
  const char *v27; // rax
  unsigned int v28; // eax
  unsigned int v29; // ebx
  __int64 v30; // rdi
  const char *v31; // rdx
  int PluginAuthenticatorName; // ebx
  const char *v33; // rax
  int ExistingCredentials; // eax
  const char *v35; // rdx
  unsigned int v36; // ebx
  const char *v37; // rax
  const char *v38; // rdx
  unsigned int v39; // ebx
  const char *v40; // rax
  unsigned int v41; // eax
  unsigned int v42; // ebx
  __int64 v43; // rbx
  unsigned int i; // esi
  __int64 v45; // rdx
  unsigned int j; // ebx
  __int64 v47; // rdx
  const char *v48; // rdx
  const char *v49; // rax
  const char *v50; // rdx
  unsigned int v51; // ebx
  const char *v52; // rax
  unsigned int v53; // eax
  unsigned int v54; // ebx
  const char *v55; // rdx
  unsigned int v56; // ebx
  const char *v57; // rax
  unsigned int v58; // eax
  unsigned int v59; // ebx
  __int64 v60; // rax
  int v61; // eax
  const char *v62; // rdx
  unsigned int v63; // ebx
  const char *v64; // rax
  __int64 v65; // rax
  const char *v66; // rdx
  const char *v67; // rax
  const char *v68; // rdx
  const char *v69; // rax
  int phkResult; // [rsp+20h] [rbp-208h]
  int phkResulta; // [rsp+20h] [rbp-208h]
  unsigned int phkResultb; // [rsp+20h] [rbp-208h]
  unsigned int phkResultc; // [rsp+20h] [rbp-208h]
  unsigned int phkResultd; // [rsp+20h] [rbp-208h]
  unsigned int phkResulte; // [rsp+20h] [rbp-208h]
  void *v76; // [rsp+30h] [rbp-1F8h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-1F0h] BYREF
  __int64 v78; // [rsp+40h] [rbp-1E8h] BYREF
  __int64 v79; // [rsp+48h] [rbp-1E0h] BYREF
  unsigned int v80; // [rsp+50h] [rbp-1D8h] BYREF
  __int64 v81; // [rsp+58h] [rbp-1D0h] BYREF
  __int128 v82; // [rsp+60h] [rbp-1C8h] BYREF
  __int64 v83; // [rsp+70h] [rbp-1B8h]
  _BYTE v84[56]; // [rsp+80h] [rbp-1A8h] BYREF
  __int64 v85; // [rsp+B8h] [rbp-170h] BYREF
  __int128 v86; // [rsp+C0h] [rbp-168h] BYREF
  _QWORD v87[8]; // [rsp+D0h] [rbp-158h] BYREF
  _BYTE v88[64]; // [rsp+110h] [rbp-118h] BYREF
  char v89; // [rsp+150h] [rbp-D8h]
  _BYTE v90[32]; // [rsp+158h] [rbp-D0h] BYREF
  unsigned __int8 v91[40]; // [rsp+178h] [rbp-B0h] BYREF
  _BYTE v92[32]; // [rsp+1A0h] [rbp-88h] BYREF
  _BYTE v93[32]; // [rsp+1C0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+0h]

  v79 = 0;
  v86 = *a2;
  tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::open_and_watch_errors(
    &v79,
    v84,
    &v86);
  wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>,wil::err_returncode_policy>(&v79);
  tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(
    &v79,
    &v85);
  v9 = -1;
  if ( a3 )
  {
    v10 = -1;
    do
      ++v10;
    while ( a3[v10] );
  }
  v11 = tip2::details::reason_string(
          (tip2::details *)"WebAuthNPluginAuthenticatorAddCredentialsTest::reason::invalid_parameters",
          v8);
  if ( v12 )
    tip2::details::shared_data<1,0,0>::get_or_add_flag_under_lock(v79 + 8, 2, v11);
  tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(&v79);
  if ( !a3 )
    goto LABEL_69;
  do
    ++v9;
  while ( a3[v9] );
  if ( !v9 || !a4 || !a5 )
  {
LABEL_69:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x849,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
      (const char *)0x80070057LL,
      phkResult);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(v84);
    return 2147942487LL;
  }
  hKey = 0;
  UserPluginAuthenticatorsRegKey = GetUserPluginAuthenticatorsRegKey((__int64)token, (__int64)&hKey);
  if ( UserPluginAuthenticatorsRegKey < 0 )
  {
    v15 = tip2::details::reason_string(
            (tip2::details *)"WebAuthNPluginAuthenticatorAddCredentialsTest::reason::plugin_authenticators_reg_key_not_found",
            v13);
    tip2::details::shared_data<1,0,0>::set_flag_without_lock(v85 + 8, 13, v15);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x852,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
        (const char *)(unsigned int)UserPluginAuthenticatorsRegKey,
        phkResult);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(v84);
    return (unsigned int)UserPluginAuthenticatorsRegKey;
  }
  v76 = 0;
  v17 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v76);
  ShouldAllowPluginOperation = RegOpenKeyExW(hKey, a3, 0, 0xF003Fu, v17);
  if ( ShouldAllowPluginOperation )
  {
    v21 = tip2::details::reason_string(
            (tip2::details *)"WebAuthNPluginAuthenticatorAddCredentialsTest::reason::clsid_not_found",
            v18);
    if ( ShouldAllowPluginOperation == 2 )
      tip2::details::shared_data<1,0,0>::set_flag_without_lock(v85 + 8, 6, v21);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
    {
      v22 = ShouldAllowPluginOperation < 0;
      if ( ShouldAllowPluginOperation > 0 )
      {
        ShouldAllowPluginOperation = (unsigned __int16)ShouldAllowPluginOperation | 0x80070000;
        v22 = ShouldAllowPluginOperation < 0;
      }
      if ( v22 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x860,
          (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
          (const char *)(unsigned int)ShouldAllowPluginOperation,
          phkResulta);
    }
    else if ( ShouldAllowPluginOperation > 0 )
    {
      ShouldAllowPluginOperation = (unsigned __int16)ShouldAllowPluginOperation | 0x80070000;
    }
LABEL_30:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v76);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(v84);
    return (unsigned int)ShouldAllowPluginOperation;
  }
  ShouldAllowPluginOperation = CtapPluginInternal::ShouldAllowPluginOperation(token, v76, v20);
  if ( ShouldAllowPluginOperation < 0 )
  {
    v24 = tip2::details::reason_string(
            (tip2::details *)"WebAuthNPluginAuthenticatorAddCredentialsTest::reason::package_verification_failed",
            v23);
    tip2::details::shared_data<1,0,0>::set_flag_without_lock(v85 + 8, 5, v24);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x86D,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
        (const char *)(unsigned int)ShouldAllowPluginOperation,
        phkResulta);
    goto LABEL_30;
  }
  v78 = 0;
  v26 = CtapCborDecodeCredentialDetailsArray(a5, a4, (unsigned int)&v78, 0, 0);
  if ( v26
    && (v27 = tip2::details::reason_string(
                (tip2::details *)"WebAuthNPluginAuthenticatorAddCredentialsTest::reason::decoding_failed",
                v25),
        tip2::details::shared_data<1,0,0>::set_flag_without_lock(v85 + 8, 4, v27),
        (v28 = CtapCborErrorToWin32Error(v26)) != 0) )
  {
    v29 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x87D,
            (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
            (const char *)v28,
            phkResultb);
    wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>(&v78);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v76);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(v84);
    return v29;
  }
  else
  {
    v30 = v78;
    if ( v78 )
    {
      std::wstring::wstring(v90);
      PluginAuthenticatorName = CtapPluginInternal::GetPluginAuthenticatorName(v76, v90);
      if ( PluginAuthenticatorName >= 0 )
      {
        std::wstring::wstring(v92, v90);
        std::wstring::wstring(v93, a3);
        tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(
          &v79,
          &v85);
        std::wstring::operator=(v79 + 304, v90);
        tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(&v79);
        v82 = 0;
        v83 = 0;
        ExistingCredentials = CtapPluginGetExistingCredentials(token, a3, &v82);
        v36 = ExistingCredentials;
        if ( ExistingCredentials == -2147024894 || (_QWORD)v82 == *((_QWORD *)&v82 + 1) )
        {
          v65 = std::vector<unsigned char>::vector<unsigned char>(v91, a4, a4 + a5);
          SetCredentials(token, v76, v65);
          v67 = tip2::details::reason_string(
                  (tip2::details *)"WebAuthNPluginAuthenticatorAddCredentialsTest::reason::credential_list_empty",
                  v66);
          tip2::details::shared_data<1,0,0>::set_flag_without_lock(v85 + 8, 8, v67);
          v69 = tip2::details::reason_string(
                  (tip2::details *)"WebAuthNPluginAuthenticatorAddCredentialsTest::reason::credentials_added",
                  v68);
          tip2::details::shared_data<1,0,0>::set_flag_without_lock(v85 + 8, 12, v69);
          std::vector<unsigned char>::_Tidy(&v82);
          FidoCredProvHelper::CreatedPasskeyInfo::~CreatedPasskeyInfo((FidoCredProvHelper::CreatedPasskeyInfo *)v92);
          std::wstring::_Tidy_deallocate(v90);
          wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>(&v78);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v76);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(v84);
          return 0;
        }
        else if ( ExistingCredentials >= 0 )
        {
          FidoCredProvHelper::Locations::PluginAuthenticator::PluginAuthenticator(
            (FidoCredProvHelper::Locations::PluginAuthenticator *)v88,
            (const struct FidoCredProvHelper::Locations::PluginAuthenticator *)v92);
          v89 = 5;
          CredentialAuthenticatorCache::ClearAuthenticator(token, v88);
          std::_Variant_base<FidoCredProvHelper::Locations::Empty,FidoCredProvHelper::Locations::ThisPc,FidoCredProvHelper::Locations::QrCode,FidoCredProvHelper::Locations::SecurityKey,FidoCredProvHelper::Locations::LinkedDevice,FidoCredProvHelper::Locations::PluginAuthenticator,FidoCredProvHelper::Locations::SyncedAccount>::_Destroy(v88);
          v81 = 0;
          v39 = CtapCborDecodeCredentialDetailsArray(DWORD2(v82) - (int)v82, v82, (unsigned int)&v81, 0, 0);
          if ( v39
            && (v40 = tip2::details::reason_string(
                        (tip2::details *)"WebAuthNPluginAuthenticatorAddCredentialsTest::reason::decoding_failed",
                        v38),
                tip2::details::shared_data<1,0,0>::set_flag_without_lock(v85 + 8, 4, v40),
                (v41 = CtapCborErrorToWin32Error(v39)) != 0) )
          {
            v42 = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x8B5,
                    (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                    (const char *)v41,
                    phkResultc);
            wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>(&v81);
            std::vector<unsigned char>::_Tidy(&v82);
            FidoCredProvHelper::CreatedPasskeyInfo::~CreatedPasskeyInfo((FidoCredProvHelper::CreatedPasskeyInfo *)v92);
            std::wstring::_Tidy_deallocate(v90);
            wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>(&v78);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v76);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
            tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(v84);
            return v42;
          }
          else
          {
            v43 = v81;
            if ( v81 )
            {
              std::unordered_set<std::string>::unordered_set<std::string>(v87);
              for ( i = 0; i < *(_DWORD *)v43; ++i )
              {
                v45 = *(_QWORD *)(*(_QWORD *)(v43 + 8) + 8LL * i);
                std::string::string(v91, *(_QWORD *)(v45 + 8), *(unsigned int *)(v45 + 4));
                std::_Hash<std::_Uset_traits<std::string,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::string>,0>>::emplace<std::string const &>(
                  v87,
                  (__int64)&v86,
                  v91);
                std::string::_Tidy_deallocate(v91);
              }
              for ( j = 0; j < *(_DWORD *)v30; ++j )
              {
                v47 = *(_QWORD *)(*(_QWORD *)(v30 + 8) + 8LL * j);
                std::string::string(v91, *(_QWORD *)(v47 + 8), *(unsigned int *)(v47 + 4));
                if ( (unsigned __int8)std::_Hash<std::_Uset_traits<std::string,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::string>,0>>::contains(
                                        v87,
                                        v91) )
                {
                  v49 = tip2::details::reason_string(
                          (tip2::details *)"WebAuthNPluginAuthenticatorAddCredentialsTest::reason::credential_id_exists",
                          v48);
                  tip2::details::shared_data<1,0,0>::set_flag_without_lock(v85 + 8, 7, v49);
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x8C9,
                    (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                    (const char *)0x8009000FLL,
                    phkResultc);
                  std::string::_Tidy_deallocate(v91);
                  std::_Hash<std::_Uset_traits<std::string,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::string>,0>>::~_Hash<std::_Uset_traits<std::string,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::string>,0>>(v87);
                  wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>(&v81);
                  std::vector<unsigned char>::_Tidy(&v82);
                  FidoCredProvHelper::CreatedPasskeyInfo::~CreatedPasskeyInfo((FidoCredProvHelper::CreatedPasskeyInfo *)v92);
                  std::wstring::_Tidy_deallocate(v90);
                  wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>(&v78);
                  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v76);
                  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
                  tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(v84);
                  return 2148073487LL;
                }
                std::string::_Tidy_deallocate(v91);
              }
              v80 = 0;
              v79 = 0;
              v51 = CtapCborEncodeAppendToArray((unsigned int)&v80, (unsigned int)&v79, DWORD2(v82) - (int)v82, v82, 0);
              if ( v51
                && (v52 = tip2::details::reason_string(
                            (tip2::details *)"WebAuthNPluginAuthenticatorAddCredentialsTest::reason::encoding_failed",
                            v50),
                    tip2::details::shared_data<1,0,0>::set_flag_without_lock(v85 + 8, 3, v52),
                    (v53 = CtapCborErrorToWin32Error(v51)) != 0) )
              {
                v54 = wil::details::in1diag3::Return_Win32(
                        retaddr,
                        (void *)0x8D8,
                        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                        (const char *)v53,
                        phkResultd);
                std::_Hash<std::_Uset_traits<std::string,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::string>,0>>::~_Hash<std::_Uset_traits<std::string,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::string>,0>>(v87);
                wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>(&v81);
                std::vector<unsigned char>::_Tidy(&v82);
                FidoCredProvHelper::CreatedPasskeyInfo::~CreatedPasskeyInfo((FidoCredProvHelper::CreatedPasskeyInfo *)v92);
                std::wstring::_Tidy_deallocate(v90);
                wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>(&v78);
                wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v76);
                wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
                tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(v84);
                return v54;
              }
              else
              {
                v56 = CtapCborEncodeAppendToArray((unsigned int)&v80, (unsigned int)&v79, a5, a4, 0);
                if ( v56
                  && (v57 = tip2::details::reason_string(
                              (tip2::details *)"WebAuthNPluginAuthenticatorAddCredentialsTest::reason::encoding_failed",
                              v55),
                      tip2::details::shared_data<1,0,0>::set_flag_without_lock(v85 + 8, 3, v57),
                      (v58 = CtapCborErrorToWin32Error(v56)) != 0) )
                {
                  v59 = wil::details::in1diag3::Return_Win32(
                          retaddr,
                          (void *)0x8E3,
                          (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                          (const char *)v58,
                          phkResulte);
                  std::_Hash<std::_Uset_traits<std::string,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::string>,0>>::~_Hash<std::_Uset_traits<std::string,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::string>,0>>(v87);
                  wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>(&v81);
                  std::vector<unsigned char>::_Tidy(&v82);
                  FidoCredProvHelper::CreatedPasskeyInfo::~CreatedPasskeyInfo((FidoCredProvHelper::CreatedPasskeyInfo *)v92);
                  std::wstring::_Tidy_deallocate(v90);
                  wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>(&v78);
                  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v76);
                  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
                  tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(v84);
                  return v59;
                }
                else
                {
                  v60 = std::vector<unsigned char>::vector<unsigned char>(v91, v79, v79 + v80);
                  v61 = SetCredentials(token, v76, v60);
                  v63 = v61;
                  if ( v61 >= 0 )
                  {
                    v64 = tip2::details::reason_string(
                            (tip2::details *)"WebAuthNPluginAuthenticatorAddCredentialsTest::reason::credentials_added",
                            v62);
                    tip2::details::shared_data<1,0,0>::set_flag_without_lock(v85 + 8, 12, v64);
                    FidoCredProvHelper::Locations::PluginAuthenticator::PluginAuthenticator(
                      (FidoCredProvHelper::Locations::PluginAuthenticator *)v88,
                      (const struct FidoCredProvHelper::Locations::PluginAuthenticator *)v92);
                    v89 = 5;
                    CredentialAuthenticatorCache::ClearAuthenticator(token, v88);
                    std::_Variant_base<FidoCredProvHelper::Locations::Empty,FidoCredProvHelper::Locations::ThisPc,FidoCredProvHelper::Locations::QrCode,FidoCredProvHelper::Locations::SecurityKey,FidoCredProvHelper::Locations::LinkedDevice,FidoCredProvHelper::Locations::PluginAuthenticator,FidoCredProvHelper::Locations::SyncedAccount>::_Destroy(v88);
                    std::_Hash<std::_Uset_traits<std::string,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::string>,0>>::~_Hash<std::_Uset_traits<std::string,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::string>,0>>(v87);
                    wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>(&v81);
                    std::vector<unsigned char>::_Tidy(&v82);
                    FidoCredProvHelper::CreatedPasskeyInfo::~CreatedPasskeyInfo((FidoCredProvHelper::CreatedPasskeyInfo *)v92);
                    std::wstring::_Tidy_deallocate(v90);
                    wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>(&v78);
                    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v76);
                    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
                    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(v84);
                    return 0;
                  }
                  else
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x8E7,
                      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                      (const char *)(unsigned int)v61,
                      phkResulte);
                    std::_Hash<std::_Uset_traits<std::string,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::string>,0>>::~_Hash<std::_Uset_traits<std::string,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::string>,0>>(v87);
                    wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>(&v81);
                    std::vector<unsigned char>::_Tidy(&v82);
                    FidoCredProvHelper::CreatedPasskeyInfo::~CreatedPasskeyInfo((FidoCredProvHelper::CreatedPasskeyInfo *)v92);
                    std::wstring::_Tidy_deallocate(v90);
                    wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>(&v78);
                    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v76);
                    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
                    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(v84);
                    return v63;
                  }
                }
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x8B7,
                (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                (const char *)0x80004003LL,
                phkResultc);
              wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>(&v81);
              std::vector<unsigned char>::_Tidy(&v82);
              FidoCredProvHelper::CreatedPasskeyInfo::~CreatedPasskeyInfo((FidoCredProvHelper::CreatedPasskeyInfo *)v92);
              std::wstring::_Tidy_deallocate(v90);
              wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>(&v78);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v76);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
              tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(v84);
              return 2147500035LL;
            }
          }
        }
        else
        {
          v37 = tip2::details::reason_string(
                  (tip2::details *)"WebAuthNPluginAuthenticatorAddCredentialsTest::reason::get_credential_list_failed",
                  v35);
          tip2::details::shared_data<1,0,0>::set_flag_without_lock(v85 + 8, 14, v37);
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x8A2,
              (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
              (const char *)v36,
              phkResultb);
          std::vector<unsigned char>::_Tidy(&v82);
          FidoCredProvHelper::CreatedPasskeyInfo::~CreatedPasskeyInfo((FidoCredProvHelper::CreatedPasskeyInfo *)v92);
          std::wstring::_Tidy_deallocate(v90);
          wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>(&v78);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v76);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(v84);
          return v36;
        }
      }
      else
      {
        v33 = tip2::details::reason_string(
                (tip2::details *)"WebAuthNPluginAuthenticatorAddCredentialsTest::reason::name_not_found",
                v31);
        tip2::details::shared_data<1,0,0>::set_flag_without_lock(v85 + 8, 10, v33);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x888,
            (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
            (const char *)(unsigned int)PluginAuthenticatorName,
            phkResultb);
        std::wstring::_Tidy_deallocate(v90);
        wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>(&v78);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v76);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(v84);
        return (unsigned int)PluginAuthenticatorName;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x87F,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
        (const char *)0x80004003LL,
        phkResultb);
      wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>(&v78);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v76);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(v84);
      return 2147500035LL;
    }
  }
}

```

## disassembly

```asm
0x18011144c  push    rbx
0x18011144e  push    rsi
0x18011144f  push    rdi
0x180111450  push    r12
0x180111452  push    r13
0x180111454  push    r14
0x180111456  push    r15
0x180111458  sub     rsp, 1F0h
0x18011145f  mov     rax, cs:__security_cookie
0x180111466  xor     rax, rsp
0x180111469  mov     [rsp+228h+var_48], rax
0x180111471  mov     r15, r9
0x180111474  mov     rsi, r8
0x180111477  mov     r14, rcx
0x18011147a  mov     r12d, [rsp+228h+arg_20]
0x180111482  xor     r13d, r13d
0x180111485  mov     [rsp+228h+var_1E0], r13
0x18011148a  movups  xmm0, xmmword ptr [rdx]
0x18011148d  movdqu  [rsp+228h+var_168], xmm0
0x180111496  lea     r8, [rsp+228h+var_168]
0x18011149e  lea     rdx, [rsp+228h+var_1A8]
0x1801114a6  lea     rcx, [rsp+228h+var_1E0]
0x1801114ab  call    ?open_and_watch_errors@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@@2@U_GUID@@@Z; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::open_and_watch_errors(_GUID)
0x1801114b0  lea     rcx, [rsp+228h+var_1E0]
0x1801114b5  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>,wil::err_returncode_policy>(void)
0x1801114ba  nop
0x1801114bb  lea     rdx, [rsp+228h+var_170]
0x1801114c3  lea     rcx, [rsp+228h+var_1E0]
0x1801114c8  call    ??0?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@@tip2@@IEAA@AEBV?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@@Z; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>,wil::err_returncode_policy> const &)
0x1801114cd  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1801114d1  test    rsi, rsi
0x1801114d4  jz      short loc_1801114F5
0x1801114d6  mov     rax, rbx
0x1801114d9  inc     rax
0x1801114dc  cmp     [rsi+rax*2], r13w
0x1801114e1  jnz     short loc_1801114D9
0x1801114e3  test    rax, rax
0x1801114e6  jz      short loc_1801114F5
0x1801114e8  test    r15, r15
0x1801114eb  jz      short loc_1801114F5
0x1801114ed  test    r12d, r12d
0x1801114f0  mov     r8b, r13b
0x1801114f3  jnz     short loc_1801114F8
0x1801114f5  mov     r8b, 1
0x1801114f8  lea     rcx, aWebauthnplugin_49; "WebAuthNPluginAuthenticatorAddCredentia"...
0x1801114ff  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x180111504  test    r8b, r8b
0x180111507  jz      short loc_18011151F
0x180111509  mov     edx, 2
0x18011150e  mov     rcx, [rsp+228h+var_1E0]
0x180111513  add     rcx, 8
0x180111517  mov     r8, rax
0x18011151a  call    ?get_or_add_flag_under_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAPEAUtest_flag@3@GPEBD@Z; tip2::details::shared_data<1,0,0>::get_or_add_flag_under_lock(ushort,char const *)
0x18011151f  lea     rcx, [rsp+228h+var_1E0]
0x180111524  call    ??1?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(void)
0x180111529  test    rsi, rsi
0x18011152c  jz      loc_180112302
0x180111532  inc     rbx
0x180111535  cmp     [rsi+rbx*2], r13w
0x18011153a  jnz     short loc_180111532
0x18011153c  test    rbx, rbx
0x18011153f  jz      loc_180112302
0x180111545  test    r15, r15
0x180111548  jz      loc_180112302
0x18011154e  test    r12d, r12d
0x180111551  jz      loc_180112302
0x180111557  mov     [rsp+228h+hKey], r13
0x18011155c  lea     rdx, [rsp+228h+hKey]
0x180111561  mov     rcx, r14
0x180111564  call    GetUserPluginAuthenticatorsRegKey
0x180111569  mov     ebx, eax
0x18011156b  test    eax, eax
0x18011156d  jns     loc_180111603
0x180111573  lea     rcx, aWebauthnplugin_71; "WebAuthNPluginAuthenticatorAddCredentia"...
0x18011157a  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18011157f  mov     r8, rax
0x180111582  mov     edx, 0Dh
0x180111587  mov     rcx, [rsp+228h+var_170]
0x18011158f  add     rcx, 8
0x180111593  call    ?set_flag_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXGPEBD@Z; tip2::details::shared_data<1,0,0>::set_flag_without_lock(ushort,char const *)
0x180111598  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl(void)'::`2'::impl
0x18011159f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x1801115a4  test    al, al
0x1801115a6  jz      short loc_1801115E4
0x1801115a8  mov     rcx, [rsp+228h]; this
0x1801115b0  mov     r9d, ebx; char *
0x1801115b3  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x1801115ba  mov     edx, 852h; void *
0x1801115bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801115c4  nop
0x1801115c5  lea     rcx, [rsp+228h+hKey]
0x1801115ca  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801115cf  nop
0x1801115d0  lea     rcx, [rsp+228h+var_1A8]
0x1801115d8  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(void)
0x1801115dd  mov     eax, ebx
0x1801115df  jmp     loc_180112339
0x1801115e4  lea     rcx, [rsp+228h+hKey]
0x1801115e9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801115ee  nop
0x1801115ef  lea     rcx, [rsp+228h+var_1A8]
0x1801115f7  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(void)
0x1801115fc  mov     eax, ebx
0x1801115fe  jmp     loc_180112339
0x180111603  mov     [rsp+228h+var_1F8], r13
0x180111608  lea     rcx, [rsp+228h+var_1F8]
0x18011160d  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180111612  mov     qword ptr [rsp+228h+phkResult], rax; int
0x180111617  mov     r9d, 0F003Fh; samDesired
0x18011161d  xor     r8d, r8d; ulOptions
0x180111620  mov     rdx, rsi; lpSubKey
0x180111623  mov     rcx, [rsp+228h+hKey]; hKey
0x180111628  call    cs:__imp_RegOpenKeyExW
0x18011162e  mov     ebx, eax
0x180111630  test    eax, eax
0x180111632  jz      loc_1801116FF
0x180111638  lea     rcx, aWebauthnplugin_54; "WebAuthNPluginAuthenticatorAddCredentia"...
0x18011163f  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x180111644  cmp     ebx, 2
0x180111647  jnz     short loc_180111660
0x180111649  lea     edx, [rbx+4]
0x18011164c  mov     rcx, [rsp+228h+var_170]
0x180111654  add     rcx, 8
0x180111658  mov     r8, rax
0x18011165b  call    ?set_flag_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXGPEBD@Z; tip2::details::shared_data<1,0,0>::set_flag_without_lock(ushort,char const *)
0x180111660  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl(void)'::`2'::impl
0x180111667  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x18011166c  test    al, al
0x18011166e  jz      short loc_1801116C8
0x180111670  test    ebx, ebx
0x180111672  jle     short loc_18011167F
0x180111674  movzx   ebx, bx
0x180111677  or      ebx, 80070000h
0x18011167d  test    ebx, ebx
0x18011167f  jns     short loc_18011169E
0x180111681  mov     rcx, [rsp+228h]; this
0x180111689  mov     r9d, ebx; char *
0x18011168c  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180111693  mov     edx, 860h; void *
0x180111698  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011169d  nop
0x18011169e  lea     rcx, [rsp+228h+var_1F8]
0x1801116a3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801116a8  nop
0x1801116a9  lea     rcx, [rsp+228h+hKey]
0x1801116ae  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801116b3  nop
0x1801116b4  lea     rcx, [rsp+228h+var_1A8]
0x1801116bc  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(void)
0x1801116c1  mov     eax, ebx
0x1801116c3  jmp     loc_180112339
0x1801116c8  test    ebx, ebx
0x1801116ca  jle     short loc_1801116D5
0x1801116cc  movzx   ebx, bx
0x1801116cf  or      ebx, 80070000h
0x1801116d5  lea     rcx, [rsp+228h+var_1F8]
0x1801116da  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801116df  nop
0x1801116e0  lea     rcx, [rsp+228h+hKey]
0x1801116e5  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801116ea  nop
0x1801116eb  lea     rcx, [rsp+228h+var_1A8]
0x1801116f3  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(void)
0x1801116f8  mov     eax, ebx
0x1801116fa  jmp     loc_180112339
0x1801116ff  mov     rdx, [rsp+228h+var_1F8]; void *
0x180111704  mov     rcx, r14; token
0x180111707  call    ?ShouldAllowPluginOperation@CtapPluginInternal@@YAJQEAXQEAUHKEY__@@@Z; CtapPluginInternal::ShouldAllowPluginOperation(void * const,HKEY__ * const)
0x18011170c  mov     ebx, eax
0x18011170e  test    eax, eax
0x180111710  jns     loc_1801117BC
0x180111716  lea     rcx, aWebauthnplugin_107; "WebAuthNPluginAuthenticatorAddCredentia"...
0x18011171d  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x180111722  mov     r8, rax
0x180111725  mov     edx, 5
0x18011172a  mov     rcx, [rsp+228h+var_170]
0x180111732  add     rcx, 8
0x180111736  call    ?set_flag_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXGPEBD@Z; tip2::details::shared_data<1,0,0>::set_flag_without_lock(ushort,char const *)
0x18011173b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl(void)'::`2'::impl
0x180111742  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x180111747  test    al, al
0x180111749  jz      short loc_180111792
0x18011174b  mov     rcx, [rsp+228h]; this
0x180111753  mov     r9d, ebx; char *
0x180111756  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18011175d  mov     edx, 86Dh; void *
0x180111762  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180111767  nop
0x180111768  lea     rcx, [rsp+228h+var_1F8]
0x18011176d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180111772  nop
0x180111773  lea     rcx, [rsp+228h+hKey]
0x180111778  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18011177d  nop
0x18011177e  lea     rcx, [rsp+228h+var_1A8]
0x180111786  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(void)
0x18011178b  mov     eax, ebx
0x18011178d  jmp     loc_180112339
0x180111792  lea     rcx, [rsp+228h+var_1F8]
0x180111797  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18011179c  nop
0x18011179d  lea     rcx, [rsp+228h+hKey]
0x1801117a2  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801117a7  nop
0x1801117a8  lea     rcx, [rsp+228h+var_1A8]
0x1801117b0  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(void)
0x1801117b5  mov     eax, ebx
0x1801117b7  jmp     loc_180112339
0x1801117bc  mov     [rsp+228h+var_1E8], r13
0x1801117c1  mov     qword ptr [rsp+228h+phkResult], r13; int
0x1801117c6  xor     r9d, r9d
0x1801117c9  lea     r8, [rsp+228h+var_1E8]
0x1801117ce  mov     rdx, r15
0x1801117d1  mov     ecx, r12d
0x1801117d4  call    CtapCborDecodeCredentialDetailsArray
0x1801117d9  mov     ebx, eax
0x1801117db  test    eax, eax
0x1801117dd  jz      loc_180111866
0x1801117e3  lea     rcx, aWebauthnplugin_44; "WebAuthNPluginAuthenticatorAddCredentia"...
0x1801117ea  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1801117ef  mov     r8, rax
0x1801117f2  mov     edx, 4
0x1801117f7  mov     rcx, [rsp+228h+var_170]
0x1801117ff  add     rcx, 8
0x180111803  call    ?set_flag_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXGPEBD@Z; tip2::details::shared_data<1,0,0>::set_flag_without_lock(ushort,char const *)
0x180111808  mov     ecx, ebx
0x18011180a  call    CtapCborErrorToWin32Error
0x18011180f  test    eax, eax
0x180111811  jz      short loc_180111866
0x180111813  mov     rcx, [rsp+228h]; this
0x18011181b  mov     r9d, eax; char *
0x18011181e  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180111825  mov     edx, 87Dh; void *
0x18011182a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18011182f  mov     ebx, eax
0x180111831  lea     rcx, [rsp+228h+var_1E8]
0x180111836  call    ??1?$unique_storage@U?$resource_policy@PEAEP6AXPEAX@Z$1?FidoFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAEPEAE$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<uchar *,void (*)(void *),&FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<uchar *,void (*)(void *),&FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>(void)
0x18011183b  nop
0x18011183c  lea     rcx, [rsp+228h+var_1F8]
0x180111841  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180111846  nop
0x180111847  lea     rcx, [rsp+228h+hKey]
0x18011184c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180111851  nop
0x180111852  lea     rcx, [rsp+228h+var_1A8]
0x18011185a  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(void)
0x18011185f  mov     eax, ebx
0x180111861  jmp     loc_180112339
0x180111866  mov     rdi, [rsp+228h+var_1E8]
0x18011186b  test    rdi, rdi
0x18011186e  jz      loc_1801122AE
0x180111874  lea     rcx, [rsp+228h+var_D0]
0x18011187c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180111881  nop
0x180111882  lea     rdx, [rsp+228h+var_D0]
0x18011188a  mov     rcx, [rsp+228h+var_1F8]
0x18011188f  call    ?GetPluginAuthenticatorName@CtapPluginInternal@@YAJPEAUHKEY__@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CtapPluginInternal::GetPluginAuthenticatorName(HKEY__ *,std::wstring &)
0x180111894  mov     ebx, eax
0x180111896  test    eax, eax
0x180111898  jns     loc_180111976
0x18011189e  lea     rcx, aWebauthnplugin_128; "WebAuthNPluginAuthenticatorAddCredentia"...
0x1801118a5  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1801118aa  mov     r8, rax
0x1801118ad  mov     edx, 0Ah
0x1801118b2  mov     rcx, [rsp+228h+var_170]
0x1801118ba  add     rcx, 8
0x1801118be  call    ?set_flag_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXGPEBD@Z; tip2::details::shared_data<1,0,0>::set_flag_without_lock(ushort,char const *)
0x1801118c3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl(void)'::`2'::impl
0x1801118ca  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x1801118cf  test    al, al
0x1801118d1  jz      short loc_180111933
0x1801118d3  mov     rcx, [rsp+228h]; this
0x1801118db  mov     r9d, ebx; char *
0x1801118de  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x1801118e5  mov     edx, 888h; void *
0x1801118ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801118ef  nop
0x1801118f0  lea     rcx, [rsp+228h+var_D0]
0x1801118f8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801118fd  nop
0x1801118fe  lea     rcx, [rsp+228h+var_1E8]
0x180111903  call    ??1?$unique_storage@U?$resource_policy@PEAEP6AXPEAX@Z$1?FidoFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAEPEAE$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<uchar *,void (*)(void *),&FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<uchar *,void (*)(void *),&FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>(void)
0x180111908  nop
0x180111909  lea     rcx, [rsp+228h+var_1F8]
0x18011190e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180111913  nop
0x180111914  lea     rcx, [rsp+228h+hKey]
0x180111919  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18011191e  nop
0x18011191f  lea     rcx, [rsp+228h+var_1A8]
0x180111927  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(void)
0x18011192c  mov     eax, ebx
0x18011192e  jmp     loc_180112339
0x180111933  lea     rcx, [rsp+228h+var_D0]
0x18011193b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180111940  nop
0x180111941  lea     rcx, [rsp+228h+var_1E8]
0x180111946  call    ??1?$unique_storage@U?$resource_policy@PEAEP6AXPEAX@Z$1?FidoFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAEPEAE$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<uchar *,void (*)(void *),&FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<uchar *,void (*)(void *),&FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>(void)
0x18011194b  nop
0x18011194c  lea     rcx, [rsp+228h+var_1F8]
  ... truncated ...
```
