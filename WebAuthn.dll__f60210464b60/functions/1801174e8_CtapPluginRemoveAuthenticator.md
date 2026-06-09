# CtapPluginRemoveAuthenticator

- ea: `0x1801174e8`
- end: `0x180117bb3`
- name: `CtapPluginRemoveAuthenticator`
- size: `1739`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800db5ac`

## callees

- `0x18001ee7c`
- `0x180021878`
- `0x1800218b4`
- `0x180023bc8`
- `0x180036da4`
- `0x180037f6c`
- `0x18003a9e8`
- `0x180042df8`
- `0x18004349c`
- `0x180043ad4`
- `0x1800467e0`
- `0x18004f5b4`
- `0x1800537a4`
- `0x180066b34`
- `0x18006f750`
- `0x180072974`
- `0x180092a90`
- `0x1800b2624`
- `0x1800b29dc`
- `0x1800b2f30`
- `0x1800b30dc`
- `0x18010b200`
- `0x18010ec4c`
- `0x1801174e8`
- `0x18011c42c`
- `0x180121b94`
- `0x18013c090`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180117847`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801178e4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180117847`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801178e4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18011761d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18011761d`

## string_xrefs

- `0x1801175af`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180117687`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x1801177a6`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x1801178fb`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180117a6c`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180117b6c`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180117b37`: `WebAuthNPluginRemoveAuthenticatorTest::reason::invalid_parameters`
- `0x180117580`: `WebAuthNPluginRemoveAuthenticatorTest::reason::registry_access_failed`
- `0x1801176a4`: `WebAuthNPluginRemoveAuthenticatorTest::reason::registry_access_failed`
- `0x180117923`: `WebAuthNPluginRemoveAuthenticatorTest::reason::registry_access_failed`
- `0x180117a21`: `WebAuthNPluginRemoveAuthenticatorTest::reason::plugin_cleanup_failed`
- `0x180117639`: `WebAuthNPluginRemoveAuthenticatorTest::reason::clsid_not_found`
- `0x18011775e`: `WebAuthNPluginRemoveAuthenticatorTest::reason::package_verification_failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall CtapPluginRemoveAuthenticator(HANDLE token, __int128 *a2, const WCHAR *a3)
{
  const char *v5; // rdx
  __int64 v6; // rax
  const char *v7; // rdx
  int UserPluginAuthenticatorsRegKey; // ebx
  const char *v9; // rax
  HKEY *v11; // rax
  int ShouldAllowPluginOperation; // ebx
  HKEY v13; // r8
  const char *v14; // rdx
  const char *v15; // rax
  bool v16; // sf
  const char *v17; // rdx
  const char *v18; // rax
  const char *v19; // rax
  const char *v20; // rdx
  const char *v21; // rax
  unsigned __int64 v22; // rbx
  char *v23; // r14
  unsigned __int64 v24; // rcx
  char *v25; // rax
  size_t v26; // rbx
  LSTATUS ValueW; // eax
  unsigned int v28; // ebx
  const char *v29; // rdx
  const char *v30; // rax
  _OWORD *v31; // rdx
  __int64 v32; // rbx
  const char *v33; // rdx
  unsigned int v34; // ebx
  const char *v35; // rax
  const char *v36; // rax
  int phkResult; // [rsp+20h] [rbp-108h]
  int phkResulta; // [rsp+20h] [rbp-108h]
  int phkResultb; // [rsp+20h] [rbp-108h]
  HKEY hkey; // [rsp+40h] [rbp-E8h] BYREF
  DWORD pcbData; // [rsp+48h] [rbp-E0h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-D8h] BYREF
  __int64 v43; // [rsp+58h] [rbp-D0h] BYREF
  PVOID pvData[2]; // [rsp+60h] [rbp-C8h] BYREF
  __int64 v45; // [rsp+70h] [rbp-B8h]
  __int128 v46; // [rsp+80h] [rbp-A8h] BYREF
  _BYTE v47[56]; // [rsp+90h] [rbp-98h] BYREF
  __int64 v48; // [rsp+C8h] [rbp-60h] BYREF
  _OWORD v49[2]; // [rsp+D0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  v43 = 0;
  v46 = *a2;
  tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>::open_and_watch_errors(
    &v43,
    v47,
    &v46);
  wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>,wil::err_returncode_policy>(&v43);
  if ( !a3 )
    goto LABEL_44;
  v6 = -1;
  do
    ++v6;
  while ( a3[v6] );
  if ( !v6 )
  {
LABEL_44:
    v36 = tip2::details::reason_string(
            (tip2::details *)"WebAuthNPluginRemoveAuthenticatorTest::reason::invalid_parameters",
            v5);
    tip2::details::shared_data<1,0,0>::set_flag_without_lock(v48 + 8, 2, v36);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2EA,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
      (const char *)0x80070057LL,
      phkResult);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>(v47);
    return 2147942487LL;
  }
  hKey = 0;
  UserPluginAuthenticatorsRegKey = GetUserPluginAuthenticatorsRegKey((__int64)token, (__int64)&hKey);
  if ( UserPluginAuthenticatorsRegKey < 0 )
  {
    v9 = tip2::details::reason_string(
           (tip2::details *)"WebAuthNPluginRemoveAuthenticatorTest::reason::registry_access_failed",
           v7);
    tip2::details::shared_data<1,0,0>::set_flag_without_lock(v48 + 8, 8, v9);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F2,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
      (const char *)(unsigned int)UserPluginAuthenticatorsRegKey,
      phkResult);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>(v47);
    return (unsigned int)UserPluginAuthenticatorsRegKey;
  }
  *(_QWORD *)&v46 = v47;
  BYTE8(v46) = 1;
  hkey = 0;
  v11 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hkey);
  ShouldAllowPluginOperation = RegOpenKeyExW(hKey, a3, 0, 0xF003Fu, v11);
  if ( ShouldAllowPluginOperation )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
    {
      v15 = tip2::details::reason_string(
              (tip2::details *)"WebAuthNPluginRemoveAuthenticatorTest::reason::clsid_not_found",
              v14);
      if ( ShouldAllowPluginOperation == 2 )
      {
        tip2::details::shared_data<1,0,0>::set_flag_without_lock(v48 + 8, 6, v15);
      }
      else
      {
        v16 = ShouldAllowPluginOperation < 0;
        if ( ShouldAllowPluginOperation <= 0 )
        {
LABEL_13:
          if ( v16 )
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x303,
              (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
              (const char *)(unsigned int)ShouldAllowPluginOperation,
              phkResulta);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
          v18 = tip2::details::reason_string(
                  (tip2::details *)"WebAuthNPluginRemoveAuthenticatorTest::reason::registry_access_failed",
                  v17);
          tip2::details::shared_data<1,0,0>::set_flag_without_lock(v48 + 8, 8, v18);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>(v47);
          return (unsigned int)ShouldAllowPluginOperation;
        }
      }
      ShouldAllowPluginOperation = (unsigned __int16)ShouldAllowPluginOperation | 0x80070000;
      v16 = ShouldAllowPluginOperation < 0;
      goto LABEL_13;
    }
    v19 = tip2::details::reason_string(
            (tip2::details *)"WebAuthNPluginRemoveAuthenticatorTest::reason::clsid_not_found",
            v14);
    if ( ShouldAllowPluginOperation == -2147024894 )
    {
      tip2::details::shared_data<1,0,0>::set_flag_without_lock(v48 + 8, 6, v19);
    }
    else if ( ShouldAllowPluginOperation > 0 )
    {
      ShouldAllowPluginOperation = (unsigned __int16)ShouldAllowPluginOperation | 0x80070000;
    }
LABEL_24:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>(v47);
    return (unsigned int)ShouldAllowPluginOperation;
  }
  ShouldAllowPluginOperation = CtapPluginInternal::ShouldAllowPluginOperation(token, hkey, v13);
  if ( ShouldAllowPluginOperation < 0 )
  {
    v21 = tip2::details::reason_string(
            (tip2::details *)"WebAuthNPluginRemoveAuthenticatorTest::reason::package_verification_failed",
            v20);
    tip2::details::shared_data<1,0,0>::set_flag_without_lock(v48 + 8, 4, v21);
    BYTE8(v46) = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x314,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
        (const char *)(unsigned int)ShouldAllowPluginOperation,
        phkResulta);
    goto LABEL_24;
  }
  pcbData = 0;
  *(_OWORD *)pvData = 0;
  v45 = 0;
  if ( RegGetValueW(hkey, 0, L"AaGuid", 2u, 0, 0, &pcbData) >= 0 )
  {
    v22 = (unsigned __int64)pcbData >> 1;
    v23 = (char *)pvData[1];
    v24 = ((char *)pvData[1] - (char *)pvData[0]) >> 1;
    if ( v22 < v24 )
    {
      v25 = (char *)pvData[0] + 2 * v22;
LABEL_32:
      pvData[1] = v25;
      goto LABEL_33;
    }
    if ( v22 > v24 )
    {
      if ( v22 <= (signed __int64)(v45 - (unsigned __int64)pvData[0]) >> 1 )
      {
        v26 = 2 * (v22 - v24);
        memset_0(pvData[1], 0, v26);
        v25 = &v23[v26];
        goto LABEL_32;
      }
      std::vector<unsigned short>::_Resize_reallocate<std::_Value_init_tag>(pvData, (unsigned __int64)pcbData >> 1);
    }
LABEL_33:
    ValueW = RegGetValueW(hkey, 0, L"AaGuid", 2u, 0, pvData[0], &pcbData);
    v28 = ValueW;
    if ( ValueW < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x322,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
        (const char *)(unsigned int)ValueW,
        phkResultb);
      std::vector<unsigned short>::_Tidy(pvData);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
      v30 = tip2::details::reason_string(
              (tip2::details *)"WebAuthNPluginRemoveAuthenticatorTest::reason::registry_access_failed",
              v29);
      tip2::details::shared_data<1,0,0>::set_flag_without_lock(v48 + 8, 8, v30);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>(v47);
      return v28;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
    {
      v32 = std::wstring::wstring(v49, pvData[0]);
      tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>(
        &v43,
        &v48);
      v31 = (_OWORD *)v32;
    }
    else
    {
      memset(v49, 0, sizeof(v49));
      std::wstring::_Construct<1,unsigned short const *>(v49, pvData[0], ((char *)pvData[1] - (char *)pvData[0]) >> 1);
      tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>(
        &v43,
        &v48);
      v31 = v49;
    }
    std::wstring::operator=(v43 + 336, v31);
    tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>(&v43);
    std::wstring::_Tidy_deallocate(v49);
  }
  v34 = CleanupPluginData(token, a3);
  if ( (v34 & 0x80000000) == 0 )
  {
    wil::impersonate_token(&v43, token);
    WebAuthNSyncCheckEnableSaveLocalDevice();
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v43);
    std::vector<unsigned short>::_Tidy(pvData);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>(v47);
    return 0;
  }
  else
  {
    v35 = tip2::details::reason_string(
            (tip2::details *)"WebAuthNPluginRemoveAuthenticatorTest::reason::plugin_cleanup_failed",
            v33);
    tip2::details::shared_data<1,0,0>::set_flag_value_without_lock<long>(v48 + 8, 10, v35, v34);
    BYTE8(v46) = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x336,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
        (const char *)v34,
        phkResultb);
    std::vector<unsigned short>::_Tidy(pvData);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>(v47);
    return v34;
  }
}

```

## disassembly

```asm
0x1801174e8  push    rbx
0x1801174ea  push    rsi
0x1801174eb  push    rdi
0x1801174ec  push    r14
0x1801174ee  push    r15
0x1801174f0  sub     rsp, 100h
0x1801174f7  mov     rax, cs:__security_cookie
0x1801174fe  xor     rax, rsp
0x180117501  mov     [rsp+128h+var_38], rax
0x180117509  mov     rsi, r8
0x18011750c  mov     rdi, rcx
0x18011750f  xor     r15d, r15d
0x180117512  mov     [rsp+128h+var_D0], r15
0x180117517  movups  xmm0, xmmword ptr [rdx]
0x18011751a  movdqu  [rsp+128h+var_A8], xmm0
0x180117523  lea     r8, [rsp+128h+var_A8]
0x18011752b  lea     rdx, [rsp+128h+var_98]
0x180117533  lea     rcx, [rsp+128h+var_D0]
0x180117538  call    ?open_and_watch_errors@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginRemoveAuthenticatorTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginRemoveAuthenticatorTest@@U1@@details@tip2@@@2@U_GUID@@@Z; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>::open_and_watch_errors(_GUID)
0x18011753d  lea     rcx, [rsp+128h+var_D0]
0x180117542  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginRemoveAuthenticatorTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>,wil::err_returncode_policy>(void)
0x180117547  nop
0x180117548  test    rsi, rsi
0x18011754b  jz      loc_180117B37
0x180117551  or      rax, 0FFFFFFFFFFFFFFFFh
0x180117555  inc     rax
0x180117558  cmp     [rsi+rax*2], r15w
0x18011755d  jnz     short loc_180117555
0x18011755f  test    rax, rax
0x180117562  jz      loc_180117B37
0x180117568  mov     [rsp+128h+hKey], r15
0x18011756d  lea     rdx, [rsp+128h+hKey]
0x180117572  mov     rcx, rdi
0x180117575  call    GetUserPluginAuthenticatorsRegKey
0x18011757a  mov     ebx, eax
0x18011757c  test    eax, eax
0x18011757e  jns     short loc_1801175E0
0x180117580  lea     rcx, aWebauthnplugin_23; "WebAuthNPluginRemoveAuthenticatorTest::"...
0x180117587  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18011758c  mov     r8, rax
0x18011758f  mov     edx, 8
0x180117594  mov     rcx, [rsp+128h+var_60]
0x18011759c  add     rcx, rdx
0x18011759f  call    ?set_flag_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXGPEBD@Z; tip2::details::shared_data<1,0,0>::set_flag_without_lock(ushort,char const *)
0x1801175a4  mov     rcx, [rsp+128h]; this
0x1801175ac  mov     r9d, ebx; char *
0x1801175af  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x1801175b6  mov     edx, 2F2h; void *
0x1801175bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801175c0  nop
0x1801175c1  lea     rcx, [rsp+128h+hKey]
0x1801175c6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801175cb  nop
0x1801175cc  lea     rcx, [rsp+128h+var_98]
0x1801175d4  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginRemoveAuthenticatorTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>(void)
0x1801175d9  mov     eax, ebx
0x1801175db  jmp     loc_180117B93
0x1801175e0  lea     rax, [rsp+128h+var_98]
0x1801175e8  mov     qword ptr [rsp+128h+var_A8], rax
0x1801175f0  mov     byte ptr [rsp+128h+var_A8+8], 1
0x1801175f8  mov     [rsp+128h+hkey], r15
0x1801175fd  lea     rcx, [rsp+128h+hkey]
0x180117602  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180117607  mov     [rsp+128h+phkResult], rax; int
0x18011760c  mov     r9d, 0F003Fh; samDesired
0x180117612  xor     r8d, r8d; ulOptions
0x180117615  mov     rdx, rsi; lpSubKey
0x180117618  mov     rcx, [rsp+128h+hKey]; hKey
0x18011761d  call    cs:__imp_RegOpenKeyExW
0x180117623  mov     ebx, eax
0x180117625  test    eax, eax
0x180117627  jz      loc_180117747
0x18011762d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl(void)'::`2'::impl
0x180117634  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x180117639  lea     rcx, aWebauthnplugin_47; "WebAuthNPluginRemoveAuthenticatorTest::"...
0x180117640  test    al, al
0x180117642  jz      loc_1801176E8
0x180117648  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18011764d  cmp     ebx, 2
0x180117650  jnz     short loc_18011766B
0x180117652  lea     edx, [rbx+4]
0x180117655  mov     rcx, [rsp+128h+var_60]
0x18011765d  add     rcx, 8
0x180117661  mov     r8, rax
0x180117664  call    ?set_flag_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXGPEBD@Z; tip2::details::shared_data<1,0,0>::set_flag_without_lock(ushort,char const *)
0x180117669  jmp     short loc_18011766F
0x18011766b  test    ebx, ebx
0x18011766d  jle     short loc_18011767A
0x18011766f  movzx   ebx, bx
0x180117672  or      ebx, 80070000h
0x180117678  test    ebx, ebx
0x18011767a  jns     short loc_180117699
0x18011767c  mov     rcx, [rsp+128h]; this
0x180117684  mov     r9d, ebx; char *
0x180117687  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18011768e  mov     edx, 303h; void *
0x180117693  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180117698  nop
0x180117699  lea     rcx, [rsp+128h+hkey]
0x18011769e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801176a3  nop
0x1801176a4  lea     rcx, aWebauthnplugin_23; "WebAuthNPluginRemoveAuthenticatorTest::"...
0x1801176ab  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1801176b0  mov     r8, rax
0x1801176b3  mov     edx, 8
0x1801176b8  mov     rcx, [rsp+128h+var_60]
0x1801176c0  add     rcx, rdx
0x1801176c3  call    ?set_flag_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXGPEBD@Z; tip2::details::shared_data<1,0,0>::set_flag_without_lock(ushort,char const *)
0x1801176c8  nop
0x1801176c9  lea     rcx, [rsp+128h+hKey]
0x1801176ce  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801176d3  nop
0x1801176d4  lea     rcx, [rsp+128h+var_98]
0x1801176dc  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginRemoveAuthenticatorTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>(void)
0x1801176e1  mov     eax, ebx
0x1801176e3  jmp     loc_180117B93
0x1801176e8  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1801176ed  cmp     ebx, 80070002h
0x1801176f3  jnz     short loc_180117710
0x1801176f5  mov     edx, 6
0x1801176fa  mov     rcx, [rsp+128h+var_60]
0x180117702  add     rcx, 8
0x180117706  mov     r8, rax
0x180117709  call    ?set_flag_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXGPEBD@Z; tip2::details::shared_data<1,0,0>::set_flag_without_lock(ushort,char const *)
0x18011770e  jmp     short loc_18011771D
0x180117710  test    ebx, ebx
0x180117712  jle     short loc_18011771D
0x180117714  movzx   ebx, bx
0x180117717  or      ebx, 80070000h
0x18011771d  lea     rcx, [rsp+128h+hkey]
0x180117722  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180117727  nop
0x180117728  lea     rcx, [rsp+128h+hKey]
0x18011772d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180117732  nop
0x180117733  lea     rcx, [rsp+128h+var_98]
0x18011773b  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginRemoveAuthenticatorTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>(void)
0x180117740  mov     eax, ebx
0x180117742  jmp     loc_180117B93
0x180117747  mov     rdx, [rsp+128h+hkey]; void *
0x18011774c  mov     rcx, rdi; token
0x18011774f  call    ?ShouldAllowPluginOperation@CtapPluginInternal@@YAJQEAXQEAUHKEY__@@@Z; CtapPluginInternal::ShouldAllowPluginOperation(void * const,HKEY__ * const)
0x180117754  mov     ebx, eax
0x180117756  test    eax, eax
0x180117758  jns     loc_18011780C
0x18011775e  lea     rcx, aWebauthnplugin_89; "WebAuthNPluginRemoveAuthenticatorTest::"...
0x180117765  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18011776a  mov     r8, rax
0x18011776d  mov     edx, 4
0x180117772  mov     rcx, [rsp+128h+var_60]
0x18011777a  add     rcx, 8
0x18011777e  call    ?set_flag_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXGPEBD@Z; tip2::details::shared_data<1,0,0>::set_flag_without_lock(ushort,char const *)
0x180117783  mov     byte ptr [rsp+128h+var_A8+8], r15b
0x18011778b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl(void)'::`2'::impl
0x180117792  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x180117797  test    al, al
0x180117799  jz      short loc_1801177E2
0x18011779b  mov     rcx, [rsp+128h]; this
0x1801177a3  mov     r9d, ebx; char *
0x1801177a6  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x1801177ad  mov     edx, 314h; void *
0x1801177b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801177b7  nop
0x1801177b8  lea     rcx, [rsp+128h+hkey]
0x1801177bd  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801177c2  nop
0x1801177c3  lea     rcx, [rsp+128h+hKey]
0x1801177c8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801177cd  nop
0x1801177ce  lea     rcx, [rsp+128h+var_98]
0x1801177d6  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginRemoveAuthenticatorTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>(void)
0x1801177db  mov     eax, ebx
0x1801177dd  jmp     loc_180117B93
0x1801177e2  lea     rcx, [rsp+128h+hkey]
0x1801177e7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801177ec  nop
0x1801177ed  lea     rcx, [rsp+128h+hKey]
0x1801177f2  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801177f7  nop
0x1801177f8  lea     rcx, [rsp+128h+var_98]
0x180117800  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginRemoveAuthenticatorTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>(void)
0x180117805  mov     eax, ebx
0x180117807  jmp     loc_180117B93
0x18011780c  mov     [rsp+128h+var_E0], r15d
0x180117811  xorps   xmm0, xmm0
0x180117814  movdqu  xmmword ptr [rsp+128h+var_C8], xmm0
0x18011781a  mov     [rsp+128h+var_B8], r15
0x18011781f  lea     rax, [rsp+128h+var_E0]
0x180117824  mov     [rsp+128h+pcbData], rax; pcbData
0x180117829  mov     [rsp+128h+pvData], r15; pvData
0x18011782e  mov     [rsp+128h+phkResult], r15; pdwType
0x180117833  mov     r9d, 2; dwFlags
0x180117839  lea     r8, aAaguid; "AaGuid"
0x180117840  xor     edx, edx; lpSubKey
0x180117842  mov     rcx, [rsp+128h+hkey]; hkey
0x180117847  call    cs:__imp_RegGetValueW
0x18011784d  test    eax, eax
0x18011784f  js      loc_180117A0C
0x180117855  mov     ebx, [rsp+128h+var_E0]
0x180117859  shr     rbx, 1
0x18011785c  mov     rdx, [rsp+128h+var_C8]
0x180117861  mov     r14, [rsp+128h+var_C8+8]
0x180117866  mov     rcx, r14
0x180117869  sub     rcx, rdx
0x18011786c  sar     rcx, 1
0x18011786f  cmp     rbx, rcx
0x180117872  jnb     short loc_18011787A
0x180117874  lea     rax, [rdx+rbx*2]
0x180117878  jmp     short loc_1801178B2
0x18011787a  jbe     short loc_1801178B7
0x18011787c  mov     rax, [rsp+128h+var_B8]
0x180117881  sub     rax, rdx
0x180117884  sar     rax, 1
0x180117887  cmp     rbx, rax
0x18011788a  jbe     short loc_18011789B
0x18011788c  mov     rdx, rbx
0x18011788f  lea     rcx, [rsp+128h+var_C8]
0x180117894  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@GV?$allocator@G@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ushort>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180117899  jmp     short loc_1801178B7
0x18011789b  sub     rbx, rcx
0x18011789e  add     rbx, rbx
0x1801178a1  mov     r8, rbx; Size
0x1801178a4  xor     edx, edx; Val
0x1801178a6  mov     rcx, r14; void *
0x1801178a9  call    memset_0
0x1801178ae  lea     rax, [rbx+r14]
0x1801178b2  mov     [rsp+128h+var_C8+8], rax
0x1801178b7  mov     rax, [rsp+128h+var_C8]
0x1801178bc  lea     rcx, [rsp+128h+var_E0]
0x1801178c1  mov     [rsp+128h+pcbData], rcx; pcbData
0x1801178c6  mov     [rsp+128h+pvData], rax; pvData
0x1801178cb  mov     [rsp+128h+phkResult], r15; int
0x1801178d0  mov     r9d, 2; dwFlags
0x1801178d6  lea     r8, aAaguid; "AaGuid"
0x1801178dd  xor     edx, edx; lpSubKey
0x1801178df  mov     rcx, [rsp+128h+hkey]; hkey
0x1801178e4  call    cs:__imp_RegGetValueW
0x1801178ea  mov     ebx, eax
0x1801178ec  test    eax, eax
0x1801178ee  jns     short loc_180117967
0x1801178f0  mov     rcx, [rsp+128h]; this
0x1801178f8  mov     r9d, eax; char *
0x1801178fb  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180117902  mov     edx, 322h; void *
0x180117907  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011790c  nop
0x18011790d  lea     rcx, [rsp+128h+var_C8]
0x180117912  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180117917  nop
0x180117918  lea     rcx, [rsp+128h+hkey]
0x18011791d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180117922  nop
0x180117923  lea     rcx, aWebauthnplugin_23; "WebAuthNPluginRemoveAuthenticatorTest::"...
0x18011792a  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18011792f  mov     r8, rax
0x180117932  mov     edx, 8
0x180117937  mov     rcx, [rsp+128h+var_60]
0x18011793f  add     rcx, rdx
0x180117942  call    ?set_flag_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXGPEBD@Z; tip2::details::shared_data<1,0,0>::set_flag_without_lock(ushort,char const *)
0x180117947  nop
0x180117948  lea     rcx, [rsp+128h+hKey]
0x18011794d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180117952  nop
0x180117953  lea     rcx, [rsp+128h+var_98]
0x18011795b  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginRemoveAuthenticatorTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>(void)
0x180117960  mov     eax, ebx
0x180117962  jmp     loc_180117B93
0x180117967  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl(void)'::`2'::impl
0x18011796e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x180117973  mov     rdx, [rsp+128h+var_C8]
0x180117978  lea     rcx, [rsp+128h+var_58]
0x180117980  test    al, al
0x180117982  jnz     short loc_1801179C7
0x180117984  xorps   xmm0, xmm0
0x180117987  movups  [rsp+128h+var_58], xmm0
0x18011798f  xorps   xmm1, xmm1
0x180117992  movdqu  [rsp+128h+var_48], xmm1
0x18011799b  mov     r8, [rsp+128h+var_C8+8]
0x1801179a0  sub     r8, rdx
0x1801179a3  sar     r8, 1
0x1801179a6  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1801179ab  lea     rdx, [rsp+128h+var_60]
0x1801179b3  lea     rcx, [rsp+128h+var_D0]
0x1801179b8  call    ??0?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginRemoveAuthenticatorTest@@U1@@details@tip2@@@tip2@@IEAA@AEBV?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginRemoveAuthenticatorTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@@Z; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>(wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>,wil::err_returncode_policy> const &)
0x1801179bd  lea     rdx, [rsp+128h+var_58]
0x1801179c5  jmp     short loc_1801179E4
0x1801179c7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1801179cc  mov     rbx, rax
0x1801179cf  lea     rdx, [rsp+128h+var_60]
0x1801179d7  lea     rcx, [rsp+128h+var_D0]
0x1801179dc  call    ??0?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginRemoveAuthenticatorTest@@U1@@details@tip2@@@tip2@@IEAA@AEBV?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginRemoveAuthenticatorTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@@Z; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>(wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>,wil::err_returncode_policy> const &)
0x1801179e1  mov     rdx, rbx
0x1801179e4  mov     rcx, [rsp+128h+var_D0]
0x1801179e9  add     rcx, 150h
0x1801179f0  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1801179f5  lea     rcx, [rsp+128h+var_D0]
0x1801179fa  call    ??1?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginRemoveAuthenticatorTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>(void)
0x1801179ff  lea     rcx, [rsp+128h+var_58]
0x180117a07  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180117a0c  mov     rdx, rsi
  ... truncated ...
```
