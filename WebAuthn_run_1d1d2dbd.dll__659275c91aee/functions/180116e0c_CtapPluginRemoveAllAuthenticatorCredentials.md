# CtapPluginRemoveAllAuthenticatorCredentials

- ea: `0x180116e0c`
- end: `0x1801174e1`
- name: `CtapPluginRemoveAllAuthenticatorCredentials`
- size: `1749`
- prototype: ``
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800db548`

## callees

- `0x18001df88`
- `0x180021878`
- `0x180036da4`
- `0x180037f6c`
- `0x18003988c`
- `0x1800398d8`
- `0x18003a3c0`
- `0x18003a9e8`
- `0x18004349c`
- `0x180043f2c`
- `0x1800467e0`
- `0x180048b70`
- `0x18004f5b4`
- `0x18006f30c`
- `0x180072974`
- `0x180093428`
- `0x1800b265c`
- `0x1800b2934`
- `0x1800b2e44`
- `0x1800b2fec`
- `0x18010d430`
- `0x18010e9bc`
- `0x180116e0c`
- `0x18011c42c`
- `0x180121b94`
- `0x18013c090`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180116fcd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180116fcd`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1801172a5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1801172a5`

## string_xrefs

- `0x180116ee0`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180116f5e`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180117031`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x1801170f5`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x1801171bf`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180117372`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180116e9a`: `WebAuthNPluginAuthenticatorRemoveAllCredentialsTest::reason::invalid_parameters`
- `0x180116f1f`: `WebAuthNPluginAuthenticatorRemoveAllCredentialsTest::reason::plugin_authenticators_reg_key_not_found`
- `0x180116fdd`: `WebAuthNPluginAuthenticatorRemoveAllCredentialsTest::reason::clsid_not_found`
- `0x1801172ad`: `WebAuthNPluginAuthenticatorRemoveAllCredentialsTest::reason::credential_list_empty`
- `0x180117321`: `WebAuthNPluginAuthenticatorRemoveAllCredentialsTest::reason::delete_autofill_credentials_failed`
- `0x1801170b5`: `WebAuthNPluginAuthenticatorRemoveAllCredentialsTest::reason::package_verification_failed`
- `0x18011717f`: `WebAuthNPluginAuthenticatorRemoveAllCredentialsTest::reason::name_not_found`
- `0x180117452`: `WebAuthNPluginAuthenticatorRemoveAllCredentialsTest::reason::credentials_removed`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall CtapPluginRemoveAllAuthenticatorCredentials(HANDLE token, __int128 *a2, const WCHAR *a3)
{
  const char *v5; // rdx
  __int64 v6; // rax
  const char *v7; // rax
  char v8; // r8
  const char *v10; // rdx
  int UserPluginAuthenticatorsRegKey; // ebx
  const char *v12; // rax
  HKEY *v13; // rax
  const char *v14; // rdx
  int ShouldAllowPluginOperation; // ebx
  HKEY v16; // r8
  const char *v17; // rax
  bool v18; // sf
  const char *v19; // rdx
  const char *v20; // rax
  const char *v21; // rdx
  int PluginAuthenticatorName; // ebx
  const char *v23; // rax
  int v24; // ebx
  const char *v25; // rdx
  const char *v26; // rax
  const char *v27; // rdx
  const char *v28; // rax
  bool v29; // sf
  const char *v30; // rdx
  const char *v31; // rax
  int phkResult; // [rsp+20h] [rbp-158h]
  int phkResulta; // [rsp+20h] [rbp-158h]
  HKEY v34; // [rsp+30h] [rbp-148h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-140h] BYREF
  _QWORD v36[2]; // [rsp+40h] [rbp-138h] BYREF
  _BYTE v37[56]; // [rsp+50h] [rbp-128h] BYREF
  __int64 v38; // [rsp+88h] [rbp-F0h] BYREF
  __int128 v39; // [rsp+90h] [rbp-E8h] BYREF
  _BYTE v40[72]; // [rsp+A0h] [rbp-D8h] BYREF
  _BYTE v41[40]; // [rsp+E8h] [rbp-90h] BYREF
  _BYTE v42[32]; // [rsp+110h] [rbp-68h] BYREF
  _BYTE v43[32]; // [rsp+130h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+0h]

  v36[0] = 0;
  v39 = *a2;
  tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>::open_and_watch_errors(
    v36,
    v37,
    &v39);
  wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>,wil::err_returncode_policy>(v36);
  tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(
    v36,
    &v38);
  if ( a3 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a3[v6] );
  }
  v7 = tip2::details::reason_string(
         (tip2::details *)"WebAuthNPluginAuthenticatorRemoveAllCredentialsTest::reason::invalid_parameters",
         v5);
  if ( v8 )
    tip2::details::shared_data<1,0,0>::get_or_add_flag_under_lock(v36[0] + 8LL, 2, v7);
  tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>(v36);
  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9C0,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
      (const char *)0x80004003LL,
      phkResult);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>(v37);
    return 2147500035LL;
  }
  hKey = 0;
  UserPluginAuthenticatorsRegKey = GetUserPluginAuthenticatorsRegKey(token, &hKey);
  if ( UserPluginAuthenticatorsRegKey < 0 )
  {
    v12 = tip2::details::reason_string(
            (tip2::details *)"WebAuthNPluginAuthenticatorRemoveAllCredentialsTest::reason::plugin_authenticators_reg_key_not_found",
            v10);
    tip2::details::shared_data<1,0,0>::set_flag_without_lock(v38 + 8, 8, v12);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9C9,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
        (const char *)(unsigned int)UserPluginAuthenticatorsRegKey,
        phkResult);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>(v37);
    return (unsigned int)UserPluginAuthenticatorsRegKey;
  }
  v34 = 0;
  v13 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v34);
  ShouldAllowPluginOperation = RegOpenKeyExW(hKey, a3, 0, 0xF003Fu, v13);
  if ( ShouldAllowPluginOperation )
  {
    v17 = tip2::details::reason_string(
            (tip2::details *)"WebAuthNPluginAuthenticatorRemoveAllCredentialsTest::reason::clsid_not_found",
            v14);
    if ( ShouldAllowPluginOperation == 2 )
      tip2::details::shared_data<1,0,0>::set_flag_without_lock(v38 + 8, 4, v17);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
    {
      v18 = ShouldAllowPluginOperation < 0;
      if ( ShouldAllowPluginOperation > 0 )
      {
        ShouldAllowPluginOperation = (unsigned __int16)ShouldAllowPluginOperation | 0x80070000;
        v18 = ShouldAllowPluginOperation < 0;
      }
      if ( v18 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x9D7,
          (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
          (const char *)(unsigned int)ShouldAllowPluginOperation,
          phkResulta);
    }
    else if ( ShouldAllowPluginOperation > 0 )
    {
      ShouldAllowPluginOperation = (unsigned __int16)ShouldAllowPluginOperation | 0x80070000;
    }
LABEL_27:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v34);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>(v37);
    return (unsigned int)ShouldAllowPluginOperation;
  }
  ShouldAllowPluginOperation = CtapPluginInternal::ShouldAllowPluginOperation(token, v34, v16);
  if ( ShouldAllowPluginOperation < 0 )
  {
    v20 = tip2::details::reason_string(
            (tip2::details *)"WebAuthNPluginAuthenticatorRemoveAllCredentialsTest::reason::package_verification_failed",
            v19);
    tip2::details::shared_data<1,0,0>::set_flag_without_lock(v38 + 8, 3, v20);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9E4,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
        (const char *)(unsigned int)ShouldAllowPluginOperation,
        phkResulta);
    goto LABEL_27;
  }
  std::wstring::wstring(v41);
  PluginAuthenticatorName = CtapPluginInternal::GetPluginAuthenticatorName(v34, v41);
  if ( PluginAuthenticatorName >= 0 )
  {
    std::wstring::wstring(v42, v41);
    std::wstring::wstring(v43, a3);
    tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(
      v36,
      &v38);
    std::wstring::operator=(v36[0] + 304LL, v41);
    tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>(v36);
    v24 = RegDeleteValueW(v34, L"AutofillCredentials");
    v26 = tip2::details::reason_string(
            (tip2::details *)"WebAuthNPluginAuthenticatorRemoveAllCredentialsTest::reason::credential_list_empty",
            v25);
    if ( v24 == 2 )
    {
      tip2::details::shared_data<1,0,0>::set_flag_without_lock(v38 + 8, 5, v26);
      FidoCredProvHelper::CreatedPasskeyInfo::~CreatedPasskeyInfo((FidoCredProvHelper::CreatedPasskeyInfo *)v42);
      std::wstring::_Tidy_deallocate(v41);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v34);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>(v37);
      return 0;
    }
    else if ( v24 )
    {
      v28 = tip2::details::reason_string(
              (tip2::details *)"WebAuthNPluginAuthenticatorRemoveAllCredentialsTest::reason::delete_autofill_credentials_failed",
              v27);
      tip2::details::shared_data<1,0,0>::set_flag_without_lock(v38 + 8, 9, v28);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
      {
        v29 = v24 < 0;
        if ( v24 > 0 )
        {
          v24 = (unsigned __int16)v24 | 0x80070000;
          v29 = v24 < 0;
        }
        if ( v29 )
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xA05,
            (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
            (const char *)(unsigned int)v24,
            phkResulta);
      }
      else if ( v24 > 0 )
      {
        v24 = (unsigned __int16)v24 | 0x80070000;
      }
      FidoCredProvHelper::CreatedPasskeyInfo::~CreatedPasskeyInfo((FidoCredProvHelper::CreatedPasskeyInfo *)v42);
      std::wstring::_Tidy_deallocate(v41);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v34);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>(v37);
      return (unsigned int)v24;
    }
    else
    {
      FidoCredProvHelper::Locations::PluginAuthenticator::PluginAuthenticator(
        (FidoCredProvHelper::Locations::PluginAuthenticator *)v40,
        (const struct FidoCredProvHelper::Locations::PluginAuthenticator *)v42);
      v40[64] = 5;
      CredentialAuthenticatorCache::ClearAuthenticator(token, v40);
      std::_Variant_base<FidoCredProvHelper::Locations::Empty,FidoCredProvHelper::Locations::ThisPc,FidoCredProvHelper::Locations::QrCode,FidoCredProvHelper::Locations::SecurityKey,FidoCredProvHelper::Locations::LinkedDevice,FidoCredProvHelper::Locations::PluginAuthenticator,FidoCredProvHelper::Locations::SyncedAccount>::_Destroy(v40);
      v31 = tip2::details::reason_string(
              (tip2::details *)"WebAuthNPluginAuthenticatorRemoveAllCredentialsTest::reason::credentials_removed",
              v30);
      tip2::details::shared_data<1,0,0>::set_flag_without_lock(v38 + 8, 10, v31);
      FidoCredProvHelper::CreatedPasskeyInfo::~CreatedPasskeyInfo((FidoCredProvHelper::CreatedPasskeyInfo *)v42);
      std::wstring::_Tidy_deallocate(v41);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v34);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>(v37);
      return 0;
    }
  }
  else
  {
    v23 = tip2::details::reason_string(
            (tip2::details *)"WebAuthNPluginAuthenticatorRemoveAllCredentialsTest::reason::name_not_found",
            v21);
    tip2::details::shared_data<1,0,0>::set_flag_without_lock(v38 + 8, 7, v23);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9F3,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
        (const char *)(unsigned int)PluginAuthenticatorName,
        phkResulta);
    std::wstring::_Tidy_deallocate(v41);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v34);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>(v37);
    return (unsigned int)PluginAuthenticatorName;
  }
}

```

## disassembly

```asm
0x180116e0c  mov     [rsp+arg_18], rbx
0x180116e11  push    rsi
0x180116e12  push    rdi
0x180116e13  push    r14
0x180116e15  sub     rsp, 160h
0x180116e1c  mov     rax, cs:__security_cookie
0x180116e23  xor     rax, rsp
0x180116e26  mov     [rsp+178h+var_28], rax
0x180116e2e  mov     rdi, r8
0x180116e31  mov     rsi, rcx
0x180116e34  xor     r14d, r14d
0x180116e37  mov     [rsp+178h+var_138], r14
0x180116e3c  movups  xmm0, xmmword ptr [rdx]
0x180116e3f  movdqu  [rsp+178h+var_E8], xmm0
0x180116e48  lea     r8, [rsp+178h+var_E8]
0x180116e50  lea     rdx, [rsp+178h+var_128]
0x180116e55  lea     rcx, [rsp+178h+var_138]
0x180116e5a  call    ?open_and_watch_errors@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest@@U1@@details@tip2@@@2@U_GUID@@@Z; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>::open_and_watch_errors(_GUID)
0x180116e5f  lea     rcx, [rsp+178h+var_138]
0x180116e64  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>,wil::err_returncode_policy>(void)
0x180116e69  nop
0x180116e6a  lea     rdx, [rsp+178h+var_F0]
0x180116e72  lea     rcx, [rsp+178h+var_138]
0x180116e77  call    ??0?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@@tip2@@IEAA@AEBV?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@@Z; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>,wil::err_returncode_policy> const &)
0x180116e7c  test    rdi, rdi
0x180116e7f  jz      short loc_180116E97
0x180116e81  or      rax, 0FFFFFFFFFFFFFFFFh
0x180116e85  inc     rax
0x180116e88  cmp     [rdi+rax*2], r14w
0x180116e8d  jnz     short loc_180116E85
0x180116e8f  test    rax, rax
0x180116e92  mov     r8b, r14b
0x180116e95  jnz     short loc_180116E9A
0x180116e97  mov     r8b, 1
0x180116e9a  lea     rcx, aWebauthnplugin_130; "WebAuthNPluginAuthenticatorRemoveAllCre"...
0x180116ea1  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x180116ea6  test    r8b, r8b
0x180116ea9  jz      short loc_180116EC1
0x180116eab  mov     edx, 2
0x180116eb0  mov     rcx, [rsp+178h+var_138]
0x180116eb5  add     rcx, 8
0x180116eb9  mov     r8, rax
0x180116ebc  call    ?get_or_add_flag_under_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAPEAUtest_flag@3@GPEBD@Z; tip2::details::shared_data<1,0,0>::get_or_add_flag_under_lock(ushort,char const *)
0x180116ec1  lea     rcx, [rsp+178h+var_138]
0x180116ec6  call    ??1?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>(void)
0x180116ecb  test    rdi, rdi
0x180116ece  jnz     short loc_180116F03
0x180116ed0  mov     rcx, [rsp+178h]; this
0x180116ed8  mov     ebx, 80004003h
0x180116edd  mov     r9d, ebx; char *
0x180116ee0  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180116ee7  mov     edx, 9C0h; void *
0x180116eec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180116ef1  nop
0x180116ef2  lea     rcx, [rsp+178h+var_128]
0x180116ef7  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>(void)
0x180116efc  mov     eax, ebx
0x180116efe  jmp     loc_1801174BC
0x180116f03  mov     [rsp+178h+hKey], r14
0x180116f08  lea     rdx, [rsp+178h+hKey]
0x180116f0d  mov     rcx, rsi
0x180116f10  call    GetUserPluginAuthenticatorsRegKey
0x180116f15  mov     ebx, eax
0x180116f17  test    eax, eax
0x180116f19  jns     loc_180116FA8
0x180116f1f  lea     rcx, aWebauthnplugin_111; "WebAuthNPluginAuthenticatorRemoveAllCre"...
0x180116f26  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x180116f2b  mov     r8, rax
0x180116f2e  mov     edx, 8
0x180116f33  mov     rcx, [rsp+178h+var_F0]
0x180116f3b  add     rcx, rdx
0x180116f3e  call    ?set_flag_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXGPEBD@Z; tip2::details::shared_data<1,0,0>::set_flag_without_lock(ushort,char const *)
0x180116f43  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl(void)'::`2'::impl
0x180116f4a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x180116f4f  test    al, al
0x180116f51  jz      short loc_180116F8C
0x180116f53  mov     rcx, [rsp+178h]; this
0x180116f5b  mov     r9d, ebx; char *
0x180116f5e  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180116f65  mov     edx, 9C9h; void *
0x180116f6a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180116f6f  nop
0x180116f70  lea     rcx, [rsp+178h+hKey]
0x180116f75  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180116f7a  nop
0x180116f7b  lea     rcx, [rsp+178h+var_128]
0x180116f80  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>(void)
0x180116f85  mov     eax, ebx
0x180116f87  jmp     loc_1801174BC
0x180116f8c  lea     rcx, [rsp+178h+hKey]
0x180116f91  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180116f96  nop
0x180116f97  lea     rcx, [rsp+178h+var_128]
0x180116f9c  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>(void)
0x180116fa1  mov     eax, ebx
0x180116fa3  jmp     loc_1801174BC
0x180116fa8  mov     [rsp+178h+var_148], r14
0x180116fad  lea     rcx, [rsp+178h+var_148]
0x180116fb2  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180116fb7  mov     qword ptr [rsp+178h+phkResult], rax; int
0x180116fbc  mov     r9d, 0F003Fh; samDesired
0x180116fc2  xor     r8d, r8d; ulOptions
0x180116fc5  mov     rdx, rdi; lpSubKey
0x180116fc8  mov     rcx, [rsp+178h+hKey]; hKey
0x180116fcd  call    cs:__imp_RegOpenKeyExW
0x180116fd3  mov     ebx, eax
0x180116fd5  test    eax, eax
0x180116fd7  jz      loc_18011709E
0x180116fdd  lea     rcx, aWebauthnplugin_143; "WebAuthNPluginAuthenticatorRemoveAllCre"...
0x180116fe4  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x180116fe9  cmp     ebx, 2
0x180116fec  jnz     short loc_180117005
0x180116fee  lea     edx, [rbx+2]
0x180116ff1  mov     rcx, [rsp+178h+var_F0]
0x180116ff9  add     rcx, 8
0x180116ffd  mov     r8, rax
0x180117000  call    ?set_flag_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXGPEBD@Z; tip2::details::shared_data<1,0,0>::set_flag_without_lock(ushort,char const *)
0x180117005  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl(void)'::`2'::impl
0x18011700c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x180117011  test    al, al
0x180117013  jz      short loc_18011706A
0x180117015  test    ebx, ebx
0x180117017  jle     short loc_180117024
0x180117019  movzx   ebx, bx
0x18011701c  or      ebx, 80070000h
0x180117022  test    ebx, ebx
0x180117024  jns     short loc_180117043
0x180117026  mov     rcx, [rsp+178h]; this
0x18011702e  mov     r9d, ebx; char *
0x180117031  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180117038  mov     edx, 9D7h; void *
0x18011703d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180117042  nop
0x180117043  lea     rcx, [rsp+178h+var_148]
0x180117048  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18011704d  nop
0x18011704e  lea     rcx, [rsp+178h+hKey]
0x180117053  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180117058  nop
0x180117059  lea     rcx, [rsp+178h+var_128]
0x18011705e  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>(void)
0x180117063  mov     eax, ebx
0x180117065  jmp     loc_1801174BC
0x18011706a  test    ebx, ebx
0x18011706c  jle     short loc_180117077
0x18011706e  movzx   ebx, bx
0x180117071  or      ebx, 80070000h
0x180117077  lea     rcx, [rsp+178h+var_148]
0x18011707c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180117081  nop
0x180117082  lea     rcx, [rsp+178h+hKey]
0x180117087  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18011708c  nop
0x18011708d  lea     rcx, [rsp+178h+var_128]
0x180117092  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>(void)
0x180117097  mov     eax, ebx
0x180117099  jmp     loc_1801174BC
0x18011709e  mov     rdx, [rsp+178h+var_148]; void *
0x1801170a3  mov     rcx, rsi; token
0x1801170a6  call    ?ShouldAllowPluginOperation@CtapPluginInternal@@YAJQEAXQEAUHKEY__@@@Z; CtapPluginInternal::ShouldAllowPluginOperation(void * const,HKEY__ * const)
0x1801170ab  mov     ebx, eax
0x1801170ad  test    eax, eax
0x1801170af  jns     loc_180117155
0x1801170b5  lea     rcx, aWebauthnplugin_48; "WebAuthNPluginAuthenticatorRemoveAllCre"...
0x1801170bc  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1801170c1  mov     r8, rax
0x1801170c4  mov     edx, 3
0x1801170c9  mov     rcx, [rsp+178h+var_F0]
0x1801170d1  add     rcx, 8
0x1801170d5  call    ?set_flag_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXGPEBD@Z; tip2::details::shared_data<1,0,0>::set_flag_without_lock(ushort,char const *)
0x1801170da  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl(void)'::`2'::impl
0x1801170e1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x1801170e6  test    al, al
0x1801170e8  jz      short loc_18011712E
0x1801170ea  mov     rcx, [rsp+178h]; this
0x1801170f2  mov     r9d, ebx; char *
0x1801170f5  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x1801170fc  mov     edx, 9E4h; void *
0x180117101  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180117106  nop
0x180117107  lea     rcx, [rsp+178h+var_148]
0x18011710c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180117111  nop
0x180117112  lea     rcx, [rsp+178h+hKey]
0x180117117  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18011711c  nop
0x18011711d  lea     rcx, [rsp+178h+var_128]
0x180117122  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>(void)
0x180117127  mov     eax, ebx
0x180117129  jmp     loc_1801174BC
0x18011712e  lea     rcx, [rsp+178h+var_148]
0x180117133  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180117138  nop
0x180117139  lea     rcx, [rsp+178h+hKey]
0x18011713e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180117143  nop
0x180117144  lea     rcx, [rsp+178h+var_128]
0x180117149  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>(void)
0x18011714e  mov     eax, ebx
0x180117150  jmp     loc_1801174BC
0x180117155  lea     rcx, [rsp+178h+var_90]
0x18011715d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180117162  nop
0x180117163  lea     rdx, [rsp+178h+var_90]
0x18011716b  mov     rcx, [rsp+178h+var_148]
0x180117170  call    ?GetPluginAuthenticatorName@CtapPluginInternal@@YAJPEAUHKEY__@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CtapPluginInternal::GetPluginAuthenticatorName(HKEY__ *,std::wstring &)
0x180117175  mov     ebx, eax
0x180117177  test    eax, eax
0x180117179  jns     loc_18011723B
0x18011717f  lea     rcx, aWebauthnplugin_137; "WebAuthNPluginAuthenticatorRemoveAllCre"...
0x180117186  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18011718b  mov     r8, rax
0x18011718e  mov     edx, 7
0x180117193  mov     rcx, [rsp+178h+var_F0]
0x18011719b  add     rcx, 8
0x18011719f  call    ?set_flag_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXGPEBD@Z; tip2::details::shared_data<1,0,0>::set_flag_without_lock(ushort,char const *)
0x1801171a4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl(void)'::`2'::impl
0x1801171ab  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x1801171b0  test    al, al
0x1801171b2  jz      short loc_180117206
0x1801171b4  mov     rcx, [rsp+178h]; this
0x1801171bc  mov     r9d, ebx; char *
0x1801171bf  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x1801171c6  mov     edx, 9F3h; void *
0x1801171cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801171d0  nop
0x1801171d1  lea     rcx, [rsp+178h+var_90]
0x1801171d9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801171de  nop
0x1801171df  lea     rcx, [rsp+178h+var_148]
0x1801171e4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801171e9  nop
0x1801171ea  lea     rcx, [rsp+178h+hKey]
0x1801171ef  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801171f4  nop
0x1801171f5  lea     rcx, [rsp+178h+var_128]
0x1801171fa  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>(void)
0x1801171ff  mov     eax, ebx
0x180117201  jmp     loc_1801174BC
0x180117206  lea     rcx, [rsp+178h+var_90]
0x18011720e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180117213  nop
0x180117214  lea     rcx, [rsp+178h+var_148]
0x180117219  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18011721e  nop
0x18011721f  lea     rcx, [rsp+178h+hKey]
0x180117224  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180117229  nop
0x18011722a  lea     rcx, [rsp+178h+var_128]
0x18011722f  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>(void)
0x180117234  mov     eax, ebx
0x180117236  jmp     loc_1801174BC
0x18011723b  lea     rdx, [rsp+178h+var_90]
0x180117243  lea     rcx, [rsp+178h+var_68]
0x18011724b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180117250  nop
0x180117251  mov     rdx, rdi
0x180117254  lea     rcx, [rsp+178h+var_48]
0x18011725c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180117261  nop
0x180117262  lea     rdx, [rsp+178h+var_F0]
0x18011726a  lea     rcx, [rsp+178h+var_138]
0x18011726f  call    ??0?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@@tip2@@IEAA@AEBV?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@@Z; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>,wil::err_returncode_policy> const &)
0x180117274  nop
0x180117275  mov     rcx, [rsp+178h+var_138]
0x18011727a  add     rcx, 130h
0x180117281  lea     rdx, [rsp+178h+var_90]
0x180117289  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18011728e  nop
0x18011728f  lea     rcx, [rsp+178h+var_138]
0x180117294  call    ??1?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>(void)
0x180117299  lea     rdx, aAutofillcreden; "AutofillCredentials"
0x1801172a0  mov     rcx, [rsp+178h+var_148]; hKey
0x1801172a5  call    cs:__imp_RegDeleteValueW
0x1801172ab  mov     ebx, eax
0x1801172ad  lea     rcx, aWebauthnplugin_110; "WebAuthNPluginAuthenticatorRemoveAllCre"...
0x1801172b4  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1801172b9  cmp     ebx, 2
0x1801172bc  jnz     short loc_180117319
0x1801172be  lea     edx, [rbx+3]
0x1801172c1  mov     rcx, [rsp+178h+var_F0]
0x1801172c9  add     rcx, 8
0x1801172cd  mov     r8, rax
0x1801172d0  call    ?set_flag_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXGPEBD@Z; tip2::details::shared_data<1,0,0>::set_flag_without_lock(ushort,char const *)
0x1801172d5  nop
0x1801172d6  lea     rcx, [rsp+178h+var_68]; this
0x1801172de  call    ??1CreatedPasskeyInfo@FidoCredProvHelper@@QEAA@XZ; FidoCredProvHelper::CreatedPasskeyInfo::~CreatedPasskeyInfo(void)
0x1801172e3  nop
0x1801172e4  lea     rcx, [rsp+178h+var_90]
0x1801172ec  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801172f1  nop
0x1801172f2  lea     rcx, [rsp+178h+var_148]
0x1801172f7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801172fc  nop
0x1801172fd  lea     rcx, [rsp+178h+hKey]
0x180117302  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180117307  nop
0x180117308  lea     rcx, [rsp+178h+var_128]
0x18011730d  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>(void)
0x180117312  xor     eax, eax
  ... truncated ...
```
