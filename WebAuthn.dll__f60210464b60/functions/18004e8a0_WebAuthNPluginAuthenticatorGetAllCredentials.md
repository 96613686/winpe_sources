# WebAuthNPluginAuthenticatorGetAllCredentials

- ea: `0x18004e8a0`
- end: `0x18004f067`
- name: `WebAuthNPluginAuthenticatorGetAllCredentials`
- size: `1991`
- prototype: `__int64 __fastcall(GUID *rguid)`
- caller_count: `0`
- callee_count: `31`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000c9d0`
- `0x18001cd78`
- `0x1800328b8`
- `0x180036da4`
- `0x1800467e0`
- `0x18004685c`
- `0x180049de0`
- `0x18004ae04`
- `0x18004e8a0`
- `0x18004f070`
- `0x18004f548`
- `0x18004f5b4`
- `0x1800537a4`
- `0x180055188`
- `0x18006cfd4`
- `0x18006f7b0`
- `0x180079444`
- `0x18007e064`
- `0x180081454`
- `0x180095468`
- `0x1800b265c`
- `0x1800b2918`
- `0x1800b2e20`
- `0x1800b2fc4`
- `0x1800b3a70`
- `0x1800b4170`
- `0x1800b5064`
- `0x1800b5548`
- `0x1800b79cc`
- `0x1800b7b0c`
- `0x18013c090`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18004eae5`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18004eae5`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x18004ea54`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x18004ea54`

## string_xrefs

- `0x18004e8f3`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x18004e935`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x18004e978`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x18004ea13`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x18004ea93`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x18004eb1d`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x18004ec25`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x18004ed11`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x18004edb2`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x18004eea5`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x18004ee62`: `WebAuthNPluginAuthenticatorGetAllCredentialsTest::reason::credential_list_conversion_failed`
- `0x18004e9e5`: `WebAuthNPluginAuthenticatorGetAllCredentialsTest::reason::remote_session`
- `0x18004ea65`: `WebAuthNPluginAuthenticatorGetAllCredentialsTest::reason::remote_session`
- `0x18004ec4e`: `WebAuthNPluginAuthenticatorGetAllCredentialsTest::reason::generic_failure`
- `0x18004ed46`: `WebAuthNPluginAuthenticatorGetAllCredentialsTest::reason::generic_failure`
- `0x18004ede6`: `WebAuthNPluginAuthenticatorGetAllCredentialsTest::reason::generic_failure`
- `0x18004eed9`: `WebAuthNPluginAuthenticatorGetAllCredentialsTest::reason::generic_failure`
- `0x18004efee`: `WebAuthNPluginAuthenticatorGetAllCredentialsTest::reason::generic_failure`
- `0x18004efa7`: `WebAuthNPluginAuthenticatorGetAllCredentialsTest::reason::credential_list_empty`
- `0x18004eaef`: `WebAuthNPluginAuthenticatorGetAllCredentialsTest::reason::invalid_parameters`
- `0x18004ecd9`: `WebAuthNPluginAuthenticatorGetAllCredentialsTest::reason::decoding_failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall WebAuthNPluginAuthenticatorGetAllCredentials(GUID *rguid, unsigned int *a2, _QWORD *a3)
{
  const char *v7; // rdx
  const char *v8; // rax
  const char *v9; // rdx
  const char *v10; // rax
  const char *v11; // rdx
  const char *v12; // rax
  __int64 v13; // rax
  __int64 v14; // r8
  int v15; // eax
  const char *v16; // rdx
  unsigned int v17; // ebx
  const char *v18; // rdx
  const char *v19; // rdx
  unsigned int v20; // esi
  const char *v21; // rax
  unsigned int v22; // eax
  struct _WEBAUTHN_CREDENTIAL_DETAILS_LIST *v23; // rbx
  const char *v24; // rdx
  const char *v25; // rax
  const char *v26; // rdx
  const char *v27; // rax
  int v28; // eax
  const char *v29; // rax
  __int64 v30; // rax
  unsigned int v31; // ebx
  const char *v32; // rax
  __int64 v33; // rdx
  __int64 v34; // rcx
  char v35; // r8
  const char *v36; // rdx
  const char *v37; // rax
  int v38; // [rsp+20h] [rbp-368h]
  int v39; // [rsp+20h] [rbp-368h]
  unsigned int v40; // [rsp+20h] [rbp-368h]
  __int64 v41; // [rsp+30h] [rbp-358h] BYREF
  _BYTE v42[4]; // [rsp+38h] [rbp-350h] BYREF
  unsigned int v43; // [rsp+3Ch] [rbp-34Ch] BYREF
  __int64 v44; // [rsp+40h] [rbp-348h] BYREF
  LPVOID lpMem; // [rsp+48h] [rbp-340h] BYREF
  struct _WEBAUTHN_CREDENTIAL_DETAILS_LIST *v46[2]; // [rsp+50h] [rbp-338h] BYREF
  struct _GUID v47; // [rsp+60h] [rbp-328h] BYREF
  _BYTE v48[64]; // [rsp+70h] [rbp-318h] BYREF
  __int64 *v49; // [rsp+B0h] [rbp-2D8h]
  char v50; // [rsp+B8h] [rbp-2D0h]
  _BYTE v51[256]; // [rsp+C0h] [rbp-2C8h] BYREF
  OLECHAR *v52; // [rsp+1C0h] [rbp-1C8h]
  OLECHAR sz[40]; // [rsp+300h] [rbp-88h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+388h] [rbp+0h]

  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::__private_IsEnabled(
                           `wil::Feature<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::GetImpl'::`2'::impl,
                           a2,
                           a3) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB9F,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
      (const char *)0x80004001LL,
      v38);
    return 2147500033LL;
  }
  v41 = 0;
  tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::start_and_watch_errors(
    &v41,
    v48);
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBA3,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
      (const char *)0x80090027LL,
      v38);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>(v48);
    wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>,wil::err_returncode_policy>(&v41);
    return 2148073511LL;
  }
  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBA4,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
      (const char *)0x80090027LL,
      v38);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>(v48);
    wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>,wil::err_returncode_policy>(&v41);
    return 2148073511LL;
  }
  v42[0] = 0;
  memset_0(v51, 0, 0x238u);
  *a3 = 0;
  *a2 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
  {
    if ( ShouldSendRequestToRemoteSession(0) )
    {
      v8 = tip2::details::reason_string(
             (tip2::details *)"WebAuthNPluginAuthenticatorGetAllCredentialsTest::reason::remote_session",
             v7);
      tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(
        &v41,
        7,
        v8);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBB0,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
        (const char *)0x80090029LL,
        v38);
      tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>(v48);
      wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>,wil::err_returncode_policy>(&v41);
      return 2148073513LL;
    }
  }
  else if ( (unsigned __int8)IsWinStationIsSessionRemoteablePresent()
         && (unsigned __int8)WinStationIsSessionRemoteable(0, 0xFFFFFFFFLL, v42)
         && v42[0] )
  {
    v10 = tip2::details::reason_string(
            (tip2::details *)"WebAuthNPluginAuthenticatorGetAllCredentialsTest::reason::remote_session",
            v9);
    tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(
      &v41,
      7,
      v10);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBB9,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
      (const char *)0x80090029LL,
      v38);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>(v48);
    wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>,wil::err_returncode_policy>(&v41);
    return 2148073513LL;
  }
  memset_0(sz, 0, sizeof(sz));
  if ( !StringFromGUID2(rguid, sz, 40) )
  {
    v12 = tip2::details::reason_string(
            (tip2::details *)"WebAuthNPluginAuthenticatorGetAllCredentialsTest::reason::invalid_parameters",
            v11);
    tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(
      &v41,
      2,
      v12);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBC2,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
      (const char *)0x80090027LL,
      v38);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>(v48);
    wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>,wil::err_returncode_policy>(&v41);
    return 2148073511LL;
  }
  v52 = sz;
  v13 = tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::ensure_data(&v41);
  tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(
    &v44,
    v13);
  v14 = -1;
  do
    ++v14;
  while ( sz[v14] );
  std::wstring::_Assign<unsigned short>(v44 + 272, sz);
  tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::close(&v44);
  v43 = 0;
  lpMem = 0;
  v49 = &v41;
  v50 = 1;
  tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::test_id(
    &v41,
    &v47);
  v15 = I_EncodeAndSendRpcRequest(0x6Eu, &v47, (struct _CTAPCBOR_RPC_REQUEST *)v51, &v43, (unsigned __int8 **)&lpMem);
  v17 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBD5,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
      (const char *)(unsigned int)v15,
      v39);
    if ( !v41 || !(unsigned __int8)tip2::details::shared_data<1,0,0>::is_running(v41 + 8) )
      goto LABEL_42;
    goto LABEL_41;
  }
  if ( v43 && lpMem )
  {
    v46[0] = 0;
    v20 = CtapCborDecodeCredentialDetailsArray(v43, (_DWORD)lpMem, (unsigned int)v46, 0, 0);
    if ( v20 )
    {
      v21 = tip2::details::reason_string(
              (tip2::details *)"WebAuthNPluginAuthenticatorGetAllCredentialsTest::reason::decoding_failed",
              v19);
      tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::complete_and_fail(
        &v41,
        3,
        v21);
      v22 = CtapCborErrorToWin32Error(v20);
      if ( v22 )
      {
        v17 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0xBE5,
                (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
                (const char *)v22,
                v40);
        wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>(v46);
        if ( !v41 || !(unsigned __int8)tip2::details::shared_data<1,0,0>::is_running(v41 + 8) )
          goto LABEL_42;
        goto LABEL_41;
      }
    }
    v23 = v46[0];
    if ( v46[0] )
    {
      CtapCltFree(lpMem);
      *(_QWORD *)&v47.Data1 = 0;
      v43 = 0;
      if ( (int)ConvertWebAuthNCredentialsListToExperimental2WebAuthNPluginCredentialsList(
                  v23,
                  (struct _WEBAUTHN_PLUGIN_CREDENTIAL_DETAILS **)&v47,
                  &v43) < 0 )
      {
        v27 = tip2::details::reason_string(
                (tip2::details *)"WebAuthNPluginAuthenticatorGetAllCredentialsTest::reason::credential_list_conversion_failed",
                v26);
        tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::complete_and_fail(
          &v41,
          9,
          v27);
        v28 = CtapCborErrorToWin32Error(v20);
        v17 = v28;
        if ( v28 > 0 )
          v17 = (unsigned __int16)v28 | 0x80070000;
        if ( (v17 & 0x80000000) != 0 )
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xBEF,
            (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
            (const char *)v17,
            v40);
        wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>(v46);
        if ( !v41 || !(unsigned __int8)tip2::details::shared_data<1,0,0>::is_running(v41 + 8) )
          goto LABEL_42;
LABEL_41:
        v29 = tip2::details::reason_string(
                (tip2::details *)"WebAuthNPluginAuthenticatorGetAllCredentialsTest::reason::generic_failure",
                v18);
        tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::set_flag(
          &v41,
          1,
          v29);
        tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::complete(&v41);
LABEL_42:
        tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>(&v44);
        tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>(v48);
        wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>,wil::err_returncode_policy>(&v41);
        return v17;
      }
      v30 = tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::ensure_data(&v41);
      tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(
        &lpMem,
        v30);
      v31 = v43;
      *((_DWORD *)lpMem + 100) = v43;
      tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>(&lpMem);
      *a3 = *(_QWORD *)&v47.Data1;
      *a2 = v31;
      tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::complete(&v41);
      wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>(v46);
      tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>(&v44);
      tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>(v48);
      wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>,wil::err_returncode_policy>(&v41);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBE7,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
        (const char *)0x80004003LL,
        v40);
      wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>(v46);
      if ( v41 && (unsigned __int8)tip2::details::shared_data<1,0,0>::is_running(v41 + 8) )
      {
        v25 = tip2::details::reason_string(
                (tip2::details *)"WebAuthNPluginAuthenticatorGetAllCredentialsTest::reason::generic_failure",
                v24);
        tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::set_flag(
          &v41,
          1,
          v25);
        tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::complete(&v41);
      }
      tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>(&v44);
      tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>(v48);
      wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>,wil::err_returncode_policy>(&v41);
      return 2147500035LL;
    }
  }
  else
  {
    v32 = tip2::details::reason_string(
            (tip2::details *)"WebAuthNPluginAuthenticatorGetAllCredentialsTest::reason::credential_list_empty",
            v16);
    v34 = v41;
    if ( v35 && v41 )
    {
      LOBYTE(v33) = 1;
      tip2::details::shared_data<1,0,0>::complete_without_lock(v41 + 8, v33, 6, v32);
      v34 = v41;
    }
    if ( v34 && (unsigned __int8)tip2::details::shared_data<1,0,0>::is_running(v34 + 8) )
    {
      v37 = tip2::details::reason_string(
              (tip2::details *)"WebAuthNPluginAuthenticatorGetAllCredentialsTest::reason::generic_failure",
              v36);
      tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::set_flag(
        &v41,
        1,
        v37);
      tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::complete(&v41);
    }
    tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>(&v44);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>(v48);
    wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>,wil::err_returncode_policy>(&v41);
    return 0;
  }
}

```

## disassembly

```asm
0x18004e8a0  mov     [rsp+arg_18], rbx
0x18004e8a5  push    rsi
0x18004e8a6  push    r12
0x18004e8a8  push    r13
0x18004e8aa  push    r14
0x18004e8ac  push    r15
0x18004e8ae  sub     rsp, 360h
0x18004e8b5  mov     rax, cs:__security_cookie
0x18004e8bc  xor     rax, rsp
0x18004e8bf  mov     [rsp+388h+var_38], rax
0x18004e8c7  mov     r14, r8
0x18004e8ca  mov     r15, rdx
0x18004e8cd  mov     rbx, rcx
0x18004e8d0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PasskeyPluginAuthenticators@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PasskeyPluginAuthenticators@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators> `wil::Feature<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::GetImpl(void)'::`2'::impl
0x18004e8d7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PasskeyPluginAuthenticators@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::__private_IsEnabled(void)
0x18004e8dc  xor     r12d, r12d
0x18004e8df  test    al, al
0x18004e8e1  jnz     short loc_18004E90B
0x18004e8e3  mov     rcx, [rsp+388h]; this
0x18004e8eb  mov     ebx, 80004001h
0x18004e8f0  mov     r9d, ebx; char *
0x18004e8f3  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18004e8fa  mov     edx, 0B9Fh; void *
0x18004e8ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e904  mov     eax, ebx
0x18004e906  jmp     loc_18004F03D
0x18004e90b  mov     [rsp+388h+var_358], r12
0x18004e910  lea     rdx, [rsp+388h+var_318]
0x18004e915  lea     rcx, [rsp+388h+var_358]
0x18004e91a  call    ?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::start_and_watch_errors(void)
0x18004e91f  nop
0x18004e920  test    r15, r15
0x18004e923  jnz     short loc_18004E963
0x18004e925  mov     rcx, [rsp+388h]; this
0x18004e92d  mov     ebx, 80090027h
0x18004e932  mov     r9d, ebx; char *
0x18004e935  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18004e93c  mov     edx, 0BA3h; void *
0x18004e941  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e946  nop
0x18004e947  lea     rcx, [rsp+388h+var_318]
0x18004e94c  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>(void)
0x18004e951  nop
0x18004e952  lea     rcx, [rsp+388h+var_358]
0x18004e957  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>,wil::err_returncode_policy>(void)
0x18004e95c  mov     eax, ebx
0x18004e95e  jmp     loc_18004F03D
0x18004e963  test    r14, r14
0x18004e966  jnz     short loc_18004E9A6
0x18004e968  mov     rcx, [rsp+388h]; this
0x18004e970  mov     ebx, 80090027h
0x18004e975  mov     r9d, ebx; char *
0x18004e978  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18004e97f  mov     edx, 0BA4h; void *
0x18004e984  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e989  nop
0x18004e98a  lea     rcx, [rsp+388h+var_318]
0x18004e98f  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>(void)
0x18004e994  nop
0x18004e995  lea     rcx, [rsp+388h+var_358]
0x18004e99a  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>,wil::err_returncode_policy>(void)
0x18004e99f  mov     eax, ebx
0x18004e9a1  jmp     loc_18004F03D
0x18004e9a6  mov     [rsp+388h+var_350], r12b
0x18004e9ab  xor     edx, edx; Val
0x18004e9ad  mov     r8d, 238h; Size
0x18004e9b3  lea     rcx, [rsp+388h+var_2C8]; void *
0x18004e9bb  call    memset_0
0x18004e9c0  mov     [r14], r12
0x18004e9c3  mov     [r15], r12d
0x18004e9c6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl(void)'::`2'::impl
0x18004e9cd  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x18004e9d2  test    al, al
0x18004e9d4  jz      short loc_18004EA41
0x18004e9d6  xor     ecx, ecx; unsigned __int8 *
0x18004e9d8  call    ?ShouldSendRequestToRemoteSession@@YA_NPEAE@Z; ShouldSendRequestToRemoteSession(uchar *)
0x18004e9dd  test    al, al
0x18004e9df  jz      loc_18004EAC1
0x18004e9e5  lea     rcx, aWebauthnplugin_93; "WebAuthNPluginAuthenticatorGetAllCreden"...
0x18004e9ec  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18004e9f1  mov     r8, rax
0x18004e9f4  mov     edx, 7
0x18004e9f9  lea     rcx, [rsp+388h+var_358]
0x18004e9fe  call    ?complete_and_ignore@?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(ushort,char const *)
0x18004ea03  mov     rcx, [rsp+388h]; this
0x18004ea0b  mov     ebx, 80090029h
0x18004ea10  mov     r9d, ebx; char *
0x18004ea13  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18004ea1a  mov     edx, 0BB0h; void *
0x18004ea1f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ea24  nop
0x18004ea25  lea     rcx, [rsp+388h+var_318]
0x18004ea2a  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>(void)
0x18004ea2f  nop
0x18004ea30  lea     rcx, [rsp+388h+var_358]
0x18004ea35  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>,wil::err_returncode_policy>(void)
0x18004ea3a  mov     eax, ebx
0x18004ea3c  jmp     loc_18004F03D
0x18004ea41  call    IsWinStationIsSessionRemoteablePresent
0x18004ea46  test    al, al
0x18004ea48  jz      short loc_18004EAC1
0x18004ea4a  lea     r8, [rsp+388h+var_350]
0x18004ea4f  or      edx, 0FFFFFFFFh
0x18004ea52  xor     ecx, ecx
0x18004ea54  call    cs:__imp_WinStationIsSessionRemoteable
0x18004ea5a  test    al, al
0x18004ea5c  jz      short loc_18004EAC1
0x18004ea5e  cmp     [rsp+388h+var_350], r12b
0x18004ea63  jz      short loc_18004EAC1
0x18004ea65  lea     rcx, aWebauthnplugin_93; "WebAuthNPluginAuthenticatorGetAllCreden"...
0x18004ea6c  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18004ea71  mov     r8, rax
0x18004ea74  mov     edx, 7
0x18004ea79  lea     rcx, [rsp+388h+var_358]
0x18004ea7e  call    ?complete_and_ignore@?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(ushort,char const *)
0x18004ea83  mov     rcx, [rsp+388h]; this
0x18004ea8b  mov     ebx, 80090029h
0x18004ea90  mov     r9d, ebx; char *
0x18004ea93  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18004ea9a  mov     edx, 0BB9h; void *
0x18004ea9f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004eaa4  nop
0x18004eaa5  lea     rcx, [rsp+388h+var_318]
0x18004eaaa  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>(void)
0x18004eaaf  nop
0x18004eab0  lea     rcx, [rsp+388h+var_358]
0x18004eab5  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>,wil::err_returncode_policy>(void)
0x18004eaba  mov     eax, ebx
0x18004eabc  jmp     loc_18004F03D
0x18004eac1  xor     edx, edx; Val
0x18004eac3  lea     r8d, [rdx+50h]; Size
0x18004eac7  lea     rcx, [rsp+388h+sz]; void *
0x18004eacf  call    memset_0
0x18004ead4  mov     r8d, 28h ; '('; cchMax
0x18004eada  lea     rdx, [rsp+388h+sz]; lpsz
0x18004eae2  mov     rcx, rbx; rguid
0x18004eae5  call    cs:__imp_StringFromGUID2
0x18004eaeb  test    eax, eax
0x18004eaed  jnz     short loc_18004EB4B
0x18004eaef  lea     rcx, aWebauthnplugin_27; "WebAuthNPluginAuthenticatorGetAllCreden"...
0x18004eaf6  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18004eafb  mov     r8, rax
0x18004eafe  mov     edx, 2
0x18004eb03  lea     rcx, [rsp+388h+var_358]
0x18004eb08  call    ?complete_and_ignore@?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(ushort,char const *)
0x18004eb0d  mov     rcx, [rsp+388h]; this
0x18004eb15  mov     ebx, 80090027h
0x18004eb1a  mov     r9d, ebx; char *
0x18004eb1d  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18004eb24  mov     edx, 0BC2h; void *
0x18004eb29  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004eb2e  nop
0x18004eb2f  lea     rcx, [rsp+388h+var_318]
0x18004eb34  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>(void)
0x18004eb39  nop
0x18004eb3a  lea     rcx, [rsp+388h+var_358]
0x18004eb3f  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>,wil::err_returncode_policy>(void)
0x18004eb44  mov     eax, ebx
0x18004eb46  jmp     loc_18004F03D
0x18004eb4b  lea     rax, [rsp+388h+sz]
0x18004eb53  mov     [rsp+388h+var_1C8], rax
0x18004eb5b  lea     rcx, [rsp+388h+var_358]
0x18004eb60  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::ensure_data(void)
0x18004eb65  mov     rdx, rax
0x18004eb68  lea     rcx, [rsp+388h+var_348]
0x18004eb6d  call    ??0?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@@tip2@@IEAA@AEBV?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@@Z; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>,wil::err_returncode_policy> const &)
0x18004eb72  nop
0x18004eb73  mov     rcx, [rsp+388h+var_348]
0x18004eb78  add     rcx, 110h
0x18004eb7f  lea     rax, [rsp+388h+sz]
0x18004eb87  or      r8, 0FFFFFFFFFFFFFFFFh
0x18004eb8b  inc     r8
0x18004eb8e  cmp     [rax+r8*2], r12w
0x18004eb93  jnz     short loc_18004EB8B
0x18004eb95  lea     rdx, [rsp+388h+sz]
0x18004eb9d  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18004eba2  lea     rcx, [rsp+388h+var_348]
0x18004eba7  call    ?close@?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::close(void)
0x18004ebac  mov     [rsp+388h+var_34C], r12d
0x18004ebb1  mov     [rsp+388h+lpMem], r12
0x18004ebb6  lea     rax, [rsp+388h+var_358]
0x18004ebbb  mov     [rsp+388h+var_2D8], rax
0x18004ebc3  mov     r13d, 1
0x18004ebc9  mov     [rsp+388h+var_2D0], r13b
0x18004ebd1  lea     rdx, [rsp+388h+var_328]
0x18004ebd6  lea     rcx, [rsp+388h+var_358]
0x18004ebdb  call    ?test_id@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest@@U1@@details@tip2@@@tip2@@QEBA?AU_GUID@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::test_id(void)
0x18004ebe0  movaps  xmm1, xmmword ptr [rsp+388h+var_328.Data1]
0x18004ebe5  movdqa  xmmword ptr [rsp+388h+var_328.Data1], xmm1
0x18004ebeb  lea     rax, [rsp+388h+lpMem]
0x18004ebf0  mov     qword ptr [rsp+388h+var_368], rax; int
0x18004ebf5  lea     r9, [rsp+388h+var_34C]; unsigned int *
0x18004ebfa  lea     r8, [rsp+388h+var_2C8]; struct _CTAPCBOR_RPC_REQUEST *
0x18004ec02  lea     rdx, [rsp+388h+var_328]; struct _GUID *
0x18004ec07  lea     ecx, [r13+6Dh]; unsigned int
0x18004ec0b  call    ?I_EncodeAndSendRpcRequest@@YAJKU_GUID@@AEAU_CTAPCBOR_RPC_REQUEST@@PEAKPEAPEAE@Z; I_EncodeAndSendRpcRequest(ulong,_GUID,_CTAPCBOR_RPC_REQUEST &,ulong *,uchar * *)
0x18004ec10  mov     ebx, eax
0x18004ec12  test    eax, eax
0x18004ec14  jns     loc_18004EC9C
0x18004ec1a  mov     rcx, [rsp+388h]; this
0x18004ec22  mov     r9d, eax; char *
0x18004ec25  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18004ec2c  mov     edx, 0BD5h; void *
0x18004ec31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ec36  nop
0x18004ec37  mov     rcx, [rsp+388h+var_358]
0x18004ec3c  test    rcx, rcx
0x18004ec3f  jz      short loc_18004EC75
0x18004ec41  add     rcx, 8
0x18004ec45  call    ?is_running@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::is_running(void)
0x18004ec4a  test    al, al
0x18004ec4c  jz      short loc_18004EC75
0x18004ec4e  lea     rcx, aWebauthnplugin_132; "WebAuthNPluginAuthenticatorGetAllCreden"...
0x18004ec55  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18004ec5a  mov     r8, rax
0x18004ec5d  mov     edx, r13d
0x18004ec60  lea     rcx, [rsp+388h+var_358]
0x18004ec65  call    ?set_flag@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::set_flag(ushort,char const *)
0x18004ec6a  lea     rcx, [rsp+388h+var_358]
0x18004ec6f  call    ?complete@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginCallbackTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::complete(void)
0x18004ec74  nop
0x18004ec75  lea     rcx, [rsp+388h+var_348]
0x18004ec7a  call    ??1?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>(void)
0x18004ec7f  nop
0x18004ec80  lea     rcx, [rsp+388h+var_318]
0x18004ec85  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>(void)
0x18004ec8a  nop
0x18004ec8b  lea     rcx, [rsp+388h+var_358]
0x18004ec90  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>,wil::err_returncode_policy>(void)
0x18004ec95  mov     eax, ebx
0x18004ec97  jmp     loc_18004F03D
0x18004ec9c  mov     ecx, [rsp+388h+var_34C]
0x18004eca0  test    ecx, ecx
0x18004eca2  jz      loc_18004EFA4
0x18004eca8  cmp     [rsp+388h+lpMem], r12
0x18004ecad  jz      loc_18004EF9F
0x18004ecb3  mov     [rsp+388h+var_338], r12
0x18004ecb8  mov     qword ptr [rsp+388h+var_368], r12; int
0x18004ecbd  xor     r9d, r9d
0x18004ecc0  lea     r8, [rsp+388h+var_338]
0x18004ecc5  mov     rdx, [rsp+388h+lpMem]
0x18004ecca  call    CtapCborDecodeCredentialDetailsArray
0x18004eccf  mov     esi, eax
0x18004ecd1  test    eax, eax
0x18004ecd3  jz      loc_18004ED94
0x18004ecd9  lea     rcx, aWebauthnplugin_140; "WebAuthNPluginAuthenticatorGetAllCreden"...
0x18004ece0  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18004ece5  mov     r8, rax
0x18004ece8  mov     edx, 3
0x18004eced  lea     rcx, [rsp+388h+var_358]
0x18004ecf2  call    ?complete_and_fail@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::complete_and_fail(ushort,char const *)
0x18004ecf7  mov     ecx, esi
0x18004ecf9  call    CtapCborErrorToWin32Error
0x18004ecfe  test    eax, eax
0x18004ed00  jz      loc_18004ED94
0x18004ed06  mov     rcx, [rsp+388h]; this
0x18004ed0e  mov     r9d, eax; char *
0x18004ed11  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18004ed18  mov     edx, 0BE5h; void *
0x18004ed1d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004ed22  mov     ebx, eax
0x18004ed24  lea     rcx, [rsp+388h+var_338]
0x18004ed29  call    ??1?$unique_storage@U?$resource_policy@PEAEP6AXPEAX@Z$1?FidoFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAEPEAE$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<uchar *,void (*)(void *),&FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<uchar *,void (*)(void *),&FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>(void)
0x18004ed2e  nop
0x18004ed2f  mov     rcx, [rsp+388h+var_358]
0x18004ed34  test    rcx, rcx
0x18004ed37  jz      short loc_18004ED6D
0x18004ed39  add     rcx, 8
0x18004ed3d  call    ?is_running@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::is_running(void)
0x18004ed42  test    al, al
0x18004ed44  jz      short loc_18004ED6D
0x18004ed46  lea     rcx, aWebauthnplugin_132; "WebAuthNPluginAuthenticatorGetAllCreden"...
0x18004ed4d  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18004ed52  mov     r8, rax
0x18004ed55  mov     edx, r13d
0x18004ed58  lea     rcx, [rsp+388h+var_358]
0x18004ed5d  call    ?set_flag@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::set_flag(ushort,char const *)
0x18004ed62  lea     rcx, [rsp+388h+var_358]
0x18004ed67  call    ?complete@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginCallbackTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::complete(void)
0x18004ed6c  nop
0x18004ed6d  lea     rcx, [rsp+388h+var_348]
0x18004ed72  call    ??1?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>(void)
0x18004ed77  nop
0x18004ed78  lea     rcx, [rsp+388h+var_318]
0x18004ed7d  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>(void)
0x18004ed82  nop
0x18004ed83  lea     rcx, [rsp+388h+var_358]
0x18004ed88  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>,wil::err_returncode_policy>(void)
0x18004ed8d  mov     eax, ebx
0x18004ed8f  jmp     loc_18004F03D
0x18004ed94  mov     rbx, [rsp+388h+var_338]
0x18004ed99  test    rbx, rbx
0x18004ed9c  jnz     loc_18004EE34
0x18004eda2  mov     rcx, [rsp+388h]; this
0x18004edaa  mov     ebx, 80004003h
0x18004edaf  mov     r9d, ebx; char *
0x18004edb2  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18004edb9  mov     edx, 0BE7h; void *
0x18004edbe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004edc3  nop
  ... truncated ...
```
