# WebAuthNPluginAuthenticatorAddCredentials

- ea: `0x1800bb670`
- end: `0x1800bbdc7`
- name: `WebAuthNPluginAuthenticatorAddCredentials`
- size: `1879`
- prototype: `__int64 __fastcall(GUID *rguid, unsigned int, struct _WEBAUTHN_PLUGIN_CREDENTIAL_DETAILS *)`
- caller_count: `0`
- callee_count: `35`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800010a8`
- `0x18001cd78`
- `0x180036da4`
- `0x1800467e0`
- `0x180046820`
- `0x18004685c`
- `0x18004f5b4`
- `0x1800537a4`
- `0x180055188`
- `0x18006cfd4`
- `0x18006d0e4`
- `0x18006f174`
- `0x18006f7b0`
- `0x180079444`
- `0x18007e064`
- `0x180087804`
- `0x180095468`
- `0x1800ae6d8`
- `0x1800af5dc`
- `0x1800b1424`
- `0x1800b265c`
- `0x1800b28fc`
- `0x1800b2dfc`
- `0x1800b2f9c`
- `0x1800b366c`
- `0x1800b4170`
- `0x1800b5034`
- `0x1800b54f0`
- `0x1800b7994`
- `0x1800b7aa4`
- `0x1800baa08`
- `0x1800bb670`
- `0x1800c3618`
- `0x1800d3914`
- `0x18013c090`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800bb8d6`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800bb8d6`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x1800bb798`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x1800bb798`

## string_xrefs

- `0x1800bb6bd`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800bb754`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800bb7d7`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800bb870`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800bb90e`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800bb9e9`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800bba88`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800bbbf6`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800bbd70`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800bb844`: `WebAuthNPluginAuthenticatorAddCredentialsTest::reason::invalid_parameters`
- `0x1800bb8e0`: `WebAuthNPluginAuthenticatorAddCredentialsTest::reason::invalid_parameters`
- `0x1800bb9c0`: `WebAuthNPluginAuthenticatorAddCredentialsTest::reason::invalid_parameters`
- `0x1800bba45`: `WebAuthNPluginAuthenticatorAddCredentialsTest::reason::invalid_parameters`
- `0x1800bbd42`: `WebAuthNPluginAuthenticatorAddCredentialsTest::reason::invalid_parameters`
- `0x1800bb726`: `WebAuthNPluginAuthenticatorAddCredentialsTest::reason::remote_session`
- `0x1800bb7a9`: `WebAuthNPluginAuthenticatorAddCredentialsTest::reason::remote_session`
- `0x1800bbce1`: `WebAuthNPluginAuthenticatorAddCredentialsTest::reason::generic_failure`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall WebAuthNPluginAuthenticatorAddCredentials(
        GUID *rguid,
        unsigned int a2,
        struct _WEBAUTHN_PLUGIN_CREDENTIAL_DETAILS *a3)
{
  const char *v7; // rdx
  const char *v8; // rax
  const char *v9; // rdx
  const char *v10; // rax
  const char *v11; // rdx
  const char *v12; // rax
  const char *v13; // rdx
  const char *v14; // rax
  __int64 v15; // rax
  __int64 v16; // rbx
  __int64 v17; // r8
  const char *v18; // rdx
  int v19; // ebx
  const char *v20; // rax
  const char *v21; // rdx
  unsigned int v22; // ebx
  const char *v23; // rax
  int v24; // eax
  int v25; // ebx
  __int64 v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rcx
  int v29; // r8d
  int v30; // r9d
  int *v31; // rcx
  void *v32; // rdx
  const char *v33; // rdx
  unsigned int v34; // eax
  char v35; // r9
  const char *v36; // rax
  int v37; // [rsp+20h] [rbp-378h]
  __int64 v38; // [rsp+30h] [rbp-368h] BYREF
  char v39; // [rsp+38h] [rbp-360h] BYREF
  char v40; // [rsp+39h] [rbp-35Fh] BYREF
  _QWORD v41[2]; // [rsp+40h] [rbp-358h] BYREF
  struct _GUID v42; // [rsp+50h] [rbp-348h] BYREF
  struct _WEBAUTHN_CREDENTIAL_DETAILS_LIST *v43; // [rsp+60h] [rbp-338h] BYREF
  _BYTE v44[24]; // [rsp+68h] [rbp-330h] BYREF
  __int128 v45; // [rsp+80h] [rbp-318h] BYREF
  __int64 v46; // [rsp+90h] [rbp-308h]
  _BYTE v47[64]; // [rsp+A0h] [rbp-2F8h] BYREF
  _BYTE v48[232]; // [rsp+E0h] [rbp-2B8h] BYREF
  unsigned int v49; // [rsp+1C8h] [rbp-1D0h] BYREF
  _QWORD v50[42]; // [rsp+1D0h] [rbp-1C8h] BYREF
  OLECHAR sz[40]; // [rsp+320h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+398h] [rbp+0h]

  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::GetImpl'::`2'::impl) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA2C,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
      (const char *)0x80004001LL,
      v37);
    return 2147500033LL;
  }
  v38 = 0;
  tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::start_and_watch_errors(
    &v38,
    v47);
  v39 = 0;
  memset_0(v48, 0, 0x238u);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
  {
    if ( ShouldSendRequestToRemoteSession(0) )
    {
      v8 = tip2::details::reason_string(
             (tip2::details *)"WebAuthNPluginAuthenticatorAddCredentialsTest::reason::remote_session",
             v7);
      tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(
        &v38,
        9,
        v8);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA38,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
        (const char *)0x80090029LL,
        v37);
      tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(v47);
      wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>,wil::err_returncode_policy>(&v38);
      return 2148073513LL;
    }
  }
  else if ( (unsigned __int8)IsWinStationIsSessionRemoteablePresent()
         && (unsigned __int8)WinStationIsSessionRemoteable(0, 0xFFFFFFFFLL, &v39)
         && v39 )
  {
    v10 = tip2::details::reason_string(
            (tip2::details *)"WebAuthNPluginAuthenticatorAddCredentialsTest::reason::remote_session",
            v9);
    tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(
      &v38,
      9,
      v10);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA41,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
      (const char *)0x80090029LL,
      v37);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(v47);
    wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>,wil::err_returncode_policy>(&v38);
    return 2148073513LL;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
  {
    if ( !a2 )
    {
      tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(v47);
      wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>,wil::err_returncode_policy>(&v38);
      return 0;
    }
    if ( !a3 )
    {
      v12 = tip2::details::reason_string(
              (tip2::details *)"WebAuthNPluginAuthenticatorAddCredentialsTest::reason::invalid_parameters",
              v11);
      tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(
        &v38,
        2,
        v12);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA4F,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
        (const char *)0x80090027LL,
        v37);
      tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(v47);
      wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>,wil::err_returncode_policy>(&v38);
      return 2148073511LL;
    }
  }
  else if ( !a2 || !a3 )
  {
    v36 = tip2::details::reason_string(
            (tip2::details *)"WebAuthNPluginAuthenticatorAddCredentialsTest::reason::invalid_parameters",
            v11);
    tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(
      &v38,
      2,
      v36);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA57,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
      (const char *)0x80090027LL,
      v37);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(v47);
    wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>,wil::err_returncode_policy>(&v38);
    return 2148073511LL;
  }
  memset_0(sz, 0, sizeof(sz));
  if ( !StringFromGUID2(rguid, sz, 40) )
  {
    v14 = tip2::details::reason_string(
            (tip2::details *)"WebAuthNPluginAuthenticatorAddCredentialsTest::reason::invalid_parameters",
            v13);
    tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(
      &v38,
      2,
      v14);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA60,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
      (const char *)0x80090027LL,
      v37);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(v47);
    wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>,wil::err_returncode_policy>(&v38);
    return 2148073511LL;
  }
  v50[2] = sz;
  v15 = tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::ensure_data(&v38);
  tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(
    v41,
    v15);
  v16 = v41[0];
  v17 = -1;
  do
    ++v17;
  while ( sz[v17] );
  std::wstring::_Assign<unsigned short>(v41[0] + 272LL, sz);
  *(_DWORD *)(v16 + 400) = a2;
  tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::close(v41);
  v43 = 0;
  v19 = ConvertExperimental2CredentialDetailsArrayToWebAuthNCredentialsList(a2, a3, &v43);
  if ( v19 < 0 )
  {
    v20 = tip2::details::reason_string(
            (tip2::details *)"WebAuthNPluginAuthenticatorAddCredentialsTest::reason::invalid_parameters",
            v18);
    tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::set_flag(
      &v38,
      2,
      v20);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA70,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
      (const char *)(unsigned int)v19,
      v37);
    tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(v41);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(v47);
    wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>,wil::err_returncode_policy>(&v38);
    return (unsigned int)v19;
  }
  v22 = CtapCborEncodeCredentialDetailsList(v43, &v49, v50);
  if ( v22 )
  {
    v23 = tip2::details::reason_string(
            (tip2::details *)"WebAuthNPluginAuthenticatorAddCredentialsTest::reason::invalid_parameters",
            v21);
    tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::set_flag(
      &v38,
      2,
      v23);
    v24 = CtapCborErrorToWin32Error(v22);
    v25 = v24;
    if ( v24 > 0 )
      v25 = (unsigned __int16)v24 | 0x80070000;
    if ( v25 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA7F,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
        (const char *)(unsigned int)v25,
        v37);
LABEL_28:
    tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(v41);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(v47);
    wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>,wil::err_returncode_policy>(&v38);
    return (unsigned int)v25;
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsPostGAFixes>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsPostGAFixes>::GetImpl'::`2'::impl) )
  {
LABEL_43:
    v42 = *(struct _GUID *)tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::test_id(
                             &v38,
                             &v43);
    v25 = I_EncodeAndSendRpcRequest(0x69u, &v42, (struct _CTAPCBOR_RPC_REQUEST *)v48, 0, 0);
    if ( v38 )
    {
      if ( (unsigned __int8)tip2::details::shared_data<1,0,0>::is_running(v38 + 8) )
      {
        v34 = (unsigned int)tip2::details::reason_string(
                              (tip2::details *)"WebAuthNPluginAuthenticatorAddCredentialsTest::reason::generic_failure",
                              v33);
        tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::set_flag_value_if<long>(
          (unsigned int)&v38,
          1,
          v34,
          v25,
          v35);
        if ( v38 )
          tip2::details::shared_data<1,0,0>::complete_without_lock(v38 + 8);
      }
    }
    goto LABEL_28;
  }
  v45 = 0;
  v46 = 0;
  v40 = 0;
  *(_QWORD *)&v42.Data1 = v50[0];
  *(_QWORD *)v42.Data4 = v49;
  v26 = CtapCbor::WebAuthNCredentialDetailsList::FromCborFallback(&v43, &v42);
  *(_QWORD *)&v42.Data1 = &v40;
  *(_QWORD *)v42.Data4 = &v45;
  std::tuple<CtapCbor::WebAuthNCredentialDetailsList &,bool &>::operator=<CtapCbor::WebAuthNCredentialDetailsList,bool,0>(
    &v42,
    v26);
  std::vector<CtapCbor::WebAuthNCredentialDetails>::_Tidy(v44);
  if ( !v40 )
  {
    std::vector<CtapCbor::WebAuthNCredentialDetails>::_Tidy(&v45);
    goto LABEL_43;
  }
  if ( (byte_1801AEA05 & 2) != 0 )
    McTemplateU0z_EventWriteTransfer(v28, v27, sz);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl) )
  {
    v31 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
    if ( (unsigned int)*v31 > 3 )
    {
      v32 = &unk_18018A3D8;
LABEL_38:
      *(_QWORD *)&v42.Data1 = sz;
      LODWORD(v43) = -2089418750;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v31,
        (_DWORD)v32,
        v29,
        v30,
        (__int64)&v43,
        (__int64)&v42);
    }
  }
  else if ( (unsigned int)dword_1801AB110 > 3 )
  {
    v32 = &unk_18018A2DA;
    v31 = &dword_1801AB110;
    goto LABEL_38;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA9A,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
      (const char *)0x83760002LL,
      v37);
  std::vector<CtapCbor::WebAuthNCredentialDetails>::_Tidy(&v45);
  tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(v41);
  tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(v47);
  wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>,wil::err_returncode_policy>(&v38);
  return 2205548546LL;
}

```

## disassembly

```asm
0x1800bb670  mov     [rsp+arg_18], rbx
0x1800bb675  push    rsi
0x1800bb676  push    rdi
0x1800bb677  push    r14
0x1800bb679  sub     rsp, 380h
0x1800bb680  mov     rax, cs:__security_cookie
0x1800bb687  xor     rax, rsp
0x1800bb68a  mov     [rsp+398h+var_28], rax
0x1800bb692  mov     rsi, r8
0x1800bb695  mov     edi, edx
0x1800bb697  mov     rbx, rcx
0x1800bb69a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PasskeyPluginAuthenticators@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PasskeyPluginAuthenticators@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators> `wil::Feature<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::GetImpl(void)'::`2'::impl
0x1800bb6a1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PasskeyPluginAuthenticators@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::__private_IsEnabled(void)
0x1800bb6a6  xor     r14d, r14d
0x1800bb6a9  test    al, al
0x1800bb6ab  jnz     short loc_1800BB6D5
0x1800bb6ad  mov     rcx, [rsp+398h]; this
0x1800bb6b5  mov     ebx, 80004001h
0x1800bb6ba  mov     r9d, ebx; char *
0x1800bb6bd  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800bb6c4  mov     edx, 0A2Ch; void *
0x1800bb6c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bb6ce  mov     eax, ebx
0x1800bb6d0  jmp     loc_1800BBDA2
0x1800bb6d5  mov     [rsp+398h+var_368], r14
0x1800bb6da  lea     rdx, [rsp+398h+var_2F8]
0x1800bb6e2  lea     rcx, [rsp+398h+var_368]
0x1800bb6e7  call    ?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::start_and_watch_errors(void)
0x1800bb6ec  nop
0x1800bb6ed  mov     [rsp+398h+var_360], r14b
0x1800bb6f2  xor     edx, edx; Val
0x1800bb6f4  mov     r8d, 238h; Size
0x1800bb6fa  lea     rcx, [rsp+398h+var_2B8]; void *
0x1800bb702  call    memset_0
0x1800bb707  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl(void)'::`2'::impl
0x1800bb70e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x1800bb713  test    al, al
0x1800bb715  jz      short loc_1800BB785
0x1800bb717  xor     ecx, ecx; unsigned __int8 *
0x1800bb719  call    ?ShouldSendRequestToRemoteSession@@YA_NPEAE@Z; ShouldSendRequestToRemoteSession(uchar *)
0x1800bb71e  test    al, al
0x1800bb720  jz      loc_1800BB808
0x1800bb726  lea     rcx, aWebauthnplugin_84; "WebAuthNPluginAuthenticatorAddCredentia"...
0x1800bb72d  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800bb732  mov     r8, rax
0x1800bb735  mov     edx, 9
0x1800bb73a  lea     rcx, [rsp+398h+var_368]
0x1800bb73f  call    ?complete_and_ignore@?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(ushort,char const *)
0x1800bb744  mov     rcx, [rsp+398h]; this
0x1800bb74c  mov     ebx, 80090029h
0x1800bb751  mov     r9d, ebx; char *
0x1800bb754  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800bb75b  mov     edx, 0A38h; void *
0x1800bb760  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bb765  nop
0x1800bb766  lea     rcx, [rsp+398h+var_2F8]
0x1800bb76e  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(void)
0x1800bb773  nop
0x1800bb774  lea     rcx, [rsp+398h+var_368]
0x1800bb779  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>,wil::err_returncode_policy>(void)
0x1800bb77e  mov     eax, ebx
0x1800bb780  jmp     loc_1800BBDA2
0x1800bb785  call    IsWinStationIsSessionRemoteablePresent
0x1800bb78a  test    al, al
0x1800bb78c  jz      short loc_1800BB808
0x1800bb78e  lea     r8, [rsp+398h+var_360]
0x1800bb793  or      edx, 0FFFFFFFFh
0x1800bb796  xor     ecx, ecx
0x1800bb798  call    cs:__imp_WinStationIsSessionRemoteable
0x1800bb79e  test    al, al
0x1800bb7a0  jz      short loc_1800BB808
0x1800bb7a2  cmp     [rsp+398h+var_360], r14b
0x1800bb7a7  jz      short loc_1800BB808
0x1800bb7a9  lea     rcx, aWebauthnplugin_84; "WebAuthNPluginAuthenticatorAddCredentia"...
0x1800bb7b0  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800bb7b5  mov     r8, rax
0x1800bb7b8  mov     edx, 9
0x1800bb7bd  lea     rcx, [rsp+398h+var_368]
0x1800bb7c2  call    ?complete_and_ignore@?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(ushort,char const *)
0x1800bb7c7  mov     rcx, [rsp+398h]; this
0x1800bb7cf  mov     ebx, 80090029h
0x1800bb7d4  mov     r9d, ebx; char *
0x1800bb7d7  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800bb7de  mov     edx, 0A41h; void *
0x1800bb7e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bb7e8  nop
0x1800bb7e9  lea     rcx, [rsp+398h+var_2F8]
0x1800bb7f1  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(void)
0x1800bb7f6  nop
0x1800bb7f7  lea     rcx, [rsp+398h+var_368]
0x1800bb7fc  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>,wil::err_returncode_policy>(void)
0x1800bb801  mov     eax, ebx
0x1800bb803  jmp     loc_1800BBDA2
0x1800bb808  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl(void)'::`2'::impl
0x1800bb80f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x1800bb814  test    al, al
0x1800bb816  jz      loc_1800BB8A1
0x1800bb81c  test    edi, edi
0x1800bb81e  jnz     short loc_1800BB83F
0x1800bb820  lea     rcx, [rsp+398h+var_2F8]
0x1800bb828  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(void)
0x1800bb82d  nop
0x1800bb82e  lea     rcx, [rsp+398h+var_368]
0x1800bb833  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>,wil::err_returncode_policy>(void)
0x1800bb838  xor     eax, eax
0x1800bb83a  jmp     loc_1800BBDA2
0x1800bb83f  test    rsi, rsi
0x1800bb842  jnz     short loc_1800BB8B2
0x1800bb844  lea     rcx, aWebauthnplugin_49; "WebAuthNPluginAuthenticatorAddCredentia"...
0x1800bb84b  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800bb850  mov     r8, rax
0x1800bb853  lea     edx, [rsi+2]
0x1800bb856  lea     rcx, [rsp+398h+var_368]
0x1800bb85b  call    ?complete_and_ignore@?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(ushort,char const *)
0x1800bb860  mov     rcx, [rsp+398h]; this
0x1800bb868  mov     ebx, 80090027h
0x1800bb86d  mov     r9d, ebx; char *
0x1800bb870  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800bb877  mov     edx, 0A4Fh; void *
0x1800bb87c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bb881  nop
0x1800bb882  lea     rcx, [rsp+398h+var_2F8]
0x1800bb88a  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(void)
0x1800bb88f  nop
0x1800bb890  lea     rcx, [rsp+398h+var_368]
0x1800bb895  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>,wil::err_returncode_policy>(void)
0x1800bb89a  mov     eax, ebx
0x1800bb89c  jmp     loc_1800BBDA2
0x1800bb8a1  test    edi, edi
0x1800bb8a3  jz      loc_1800BBD42
0x1800bb8a9  test    rsi, rsi
0x1800bb8ac  jz      loc_1800BBD42
0x1800bb8b2  xor     edx, edx; Val
0x1800bb8b4  lea     r8d, [rdx+50h]; Size
0x1800bb8b8  lea     rcx, [rsp+398h+sz]; void *
0x1800bb8c0  call    memset_0
0x1800bb8c5  mov     r8d, 28h ; '('; cchMax
0x1800bb8cb  lea     rdx, [rsp+398h+sz]; lpsz
0x1800bb8d3  mov     rcx, rbx; rguid
0x1800bb8d6  call    cs:__imp_StringFromGUID2
0x1800bb8dc  test    eax, eax
0x1800bb8de  jnz     short loc_1800BB93F
0x1800bb8e0  lea     rcx, aWebauthnplugin_49; "WebAuthNPluginAuthenticatorAddCredentia"...
0x1800bb8e7  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800bb8ec  mov     r8, rax
0x1800bb8ef  mov     edx, 2
0x1800bb8f4  lea     rcx, [rsp+398h+var_368]
0x1800bb8f9  call    ?complete_and_ignore@?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(ushort,char const *)
0x1800bb8fe  mov     rcx, [rsp+398h]; this
0x1800bb906  mov     ebx, 80090027h
0x1800bb90b  mov     r9d, ebx; char *
0x1800bb90e  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800bb915  mov     edx, 0A60h; void *
0x1800bb91a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bb91f  nop
0x1800bb920  lea     rcx, [rsp+398h+var_2F8]
0x1800bb928  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(void)
0x1800bb92d  nop
0x1800bb92e  lea     rcx, [rsp+398h+var_368]
0x1800bb933  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>,wil::err_returncode_policy>(void)
0x1800bb938  mov     eax, ebx
0x1800bb93a  jmp     loc_1800BBDA2
0x1800bb93f  lea     rax, [rsp+398h+sz]
0x1800bb947  mov     [rsp+398h+var_1B8], rax
0x1800bb94f  lea     rcx, [rsp+398h+var_368]
0x1800bb954  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::ensure_data(void)
0x1800bb959  mov     rdx, rax
0x1800bb95c  lea     rcx, [rsp+398h+var_358]
0x1800bb961  call    ??0?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@@tip2@@IEAA@AEBV?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@@Z; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>,wil::err_returncode_policy> const &)
0x1800bb966  nop
0x1800bb967  mov     rbx, [rsp+398h+var_358]
0x1800bb96c  lea     rcx, [rbx+110h]
0x1800bb973  lea     rax, [rsp+398h+sz]
0x1800bb97b  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800bb97f  inc     r8
0x1800bb982  cmp     [rax+r8*2], r14w
0x1800bb987  jnz     short loc_1800BB97F
0x1800bb989  lea     rdx, [rsp+398h+sz]
0x1800bb991  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800bb996  mov     [rbx+190h], edi
0x1800bb99c  lea     rcx, [rsp+398h+var_358]
0x1800bb9a1  call    ?close@?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::close(void)
0x1800bb9a6  mov     [rsp+398h+var_338], r14
0x1800bb9ab  lea     r8, [rsp+398h+var_338]; struct _WEBAUTHN_CREDENTIAL_DETAILS_LIST **
0x1800bb9b0  mov     rdx, rsi; struct _WEBAUTHN_PLUGIN_CREDENTIAL_DETAILS *
0x1800bb9b3  mov     ecx, edi; unsigned int
0x1800bb9b5  call    ?ConvertExperimental2CredentialDetailsArrayToWebAuthNCredentialsList@@YAJKPEBU_WEBAUTHN_PLUGIN_CREDENTIAL_DETAILS@@PEAPEAU_WEBAUTHN_CREDENTIAL_DETAILS_LIST@@@Z; ConvertExperimental2CredentialDetailsArrayToWebAuthNCredentialsList(ulong,_WEBAUTHN_PLUGIN_CREDENTIAL_DETAILS const *,_WEBAUTHN_CREDENTIAL_DETAILS_LIST * *)
0x1800bb9ba  mov     ebx, eax
0x1800bb9bc  test    eax, eax
0x1800bb9be  jns     short loc_1800BBA25
0x1800bb9c0  lea     rcx, aWebauthnplugin_49; "WebAuthNPluginAuthenticatorAddCredentia"...
0x1800bb9c7  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800bb9cc  mov     r8, rax
0x1800bb9cf  mov     edx, 2
0x1800bb9d4  lea     rcx, [rsp+398h+var_368]
0x1800bb9d9  call    ?set_flag@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::set_flag(ushort,char const *)
0x1800bb9de  mov     rcx, [rsp+398h]; this
0x1800bb9e6  mov     r9d, ebx; char *
0x1800bb9e9  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800bb9f0  mov     edx, 0A70h; void *
0x1800bb9f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bb9fa  nop
0x1800bb9fb  lea     rcx, [rsp+398h+var_358]
0x1800bba00  call    ??1?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(void)
0x1800bba05  nop
0x1800bba06  lea     rcx, [rsp+398h+var_2F8]
0x1800bba0e  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(void)
0x1800bba13  nop
0x1800bba14  lea     rcx, [rsp+398h+var_368]
0x1800bba19  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>,wil::err_returncode_policy>(void)
0x1800bba1e  mov     eax, ebx
0x1800bba20  jmp     loc_1800BBDA2
0x1800bba25  lea     r8, [rsp+398h+var_1C8]
0x1800bba2d  lea     rdx, [rsp+398h+var_1D0]
0x1800bba35  mov     rcx, [rsp+398h+var_338]
0x1800bba3a  call    CtapCborEncodeCredentialDetailsList
0x1800bba3f  mov     ebx, eax
0x1800bba41  test    eax, eax
0x1800bba43  jz      short loc_1800BBAC4
0x1800bba45  lea     rcx, aWebauthnplugin_49; "WebAuthNPluginAuthenticatorAddCredentia"...
0x1800bba4c  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800bba51  mov     r8, rax
0x1800bba54  mov     edx, 2
0x1800bba59  lea     rcx, [rsp+398h+var_368]
0x1800bba5e  call    ?set_flag@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::set_flag(ushort,char const *)
0x1800bba63  mov     ecx, ebx
0x1800bba65  call    CtapCborErrorToWin32Error
0x1800bba6a  mov     ebx, eax
0x1800bba6c  test    eax, eax
0x1800bba6e  jle     short loc_1800BBA79
0x1800bba70  movzx   ebx, ax
0x1800bba73  or      ebx, 80070000h
0x1800bba79  test    ebx, ebx
0x1800bba7b  jns     short loc_1800BBA9A
0x1800bba7d  mov     rcx, [rsp+398h]; this
0x1800bba85  mov     r9d, ebx; char *
0x1800bba88  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800bba8f  mov     edx, 0A7Fh; void *
0x1800bba94  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bba99  nop
0x1800bba9a  lea     rcx, [rsp+398h+var_358]
0x1800bba9f  call    ??1?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(void)
0x1800bbaa4  nop
0x1800bbaa5  lea     rcx, [rsp+398h+var_2F8]
0x1800bbaad  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(void)
0x1800bbab2  nop
0x1800bbab3  lea     rcx, [rsp+398h+var_368]
0x1800bbab8  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>,wil::err_returncode_policy>(void)
0x1800bbabd  mov     eax, ebx
0x1800bbabf  jmp     loc_1800BBDA2
0x1800bbac4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsPostGAFixes@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsPostGAFixes@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsPostGAFixes> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsPostGAFixes>::GetImpl(void)'::`2'::impl
0x1800bbacb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsPostGAFixes@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsPostGAFixes>::__private_IsEnabled(void)
0x1800bbad0  test    al, al
0x1800bbad2  jz      loc_1800BBC8B
0x1800bbad8  mov     ecx, [rsp+398h+var_1D0]
0x1800bbadf  mov     rax, [rsp+398h+var_1C8]
0x1800bbae7  xorps   xmm0, xmm0
0x1800bbaea  movdqu  [rsp+398h+var_318], xmm0
0x1800bbaf3  mov     [rsp+398h+var_308], r14
0x1800bbafb  mov     [rsp+398h+var_35F], r14b
0x1800bbb00  mov     qword ptr [rsp+398h+var_348.Data1], rax
0x1800bbb05  mov     qword ptr [rsp+398h+var_348.Data4], rcx
0x1800bbb0a  lea     rdx, [rsp+398h+var_348]
0x1800bbb0f  lea     rcx, [rsp+398h+var_338]
0x1800bbb14  call    ?FromCborFallback@WebAuthNCredentialDetailsList@CtapCbor@@SA?AV?$tuple@UWebAuthNCredentialDetailsList@CtapCbor@@_N@std@@V?$span@$$CBE$0?0@4@@Z; CtapCbor::WebAuthNCredentialDetailsList::FromCborFallback(std::span<uchar const,-1>)
0x1800bbb19  lea     rcx, [rsp+398h+var_35F]
0x1800bbb1e  mov     qword ptr [rsp+398h+var_348.Data1], rcx
0x1800bbb23  lea     rcx, [rsp+398h+var_318]
0x1800bbb2b  mov     qword ptr [rsp+398h+var_348.Data4], rcx
0x1800bbb30  mov     rdx, rax
0x1800bbb33  lea     rcx, [rsp+398h+var_348]
0x1800bbb38  call    ??$?4UWebAuthNCredentialDetailsList@CtapCbor@@_N$0A@@?$tuple@AEAUWebAuthNCredentialDetailsList@CtapCbor@@AEA_N@std@@QEAAAEAV01@$$QEAV?$tuple@UWebAuthNCredentialDetailsList@CtapCbor@@_N@1@@Z; std::tuple<CtapCbor::WebAuthNCredentialDetailsList &,bool &>::operator=<CtapCbor::WebAuthNCredentialDetailsList,bool,0>(std::tuple<CtapCbor::WebAuthNCredentialDetailsList,bool> &&)
0x1800bbb3d  lea     rcx, [rsp+398h+var_330]
0x1800bbb42  call    ?_Tidy@?$vector@UWebAuthNCredentialDetails@CtapCbor@@V?$allocator@UWebAuthNCredentialDetails@CtapCbor@@@std@@@std@@AEAAXXZ; std::vector<CtapCbor::WebAuthNCredentialDetails>::_Tidy(void)
0x1800bbb47  cmp     [rsp+398h+var_35F], r14b
0x1800bbb4c  jz      loc_1800BBC7E
0x1800bbb52  test    cs:byte_1801AEA05, 2
0x1800bbb59  jz      short loc_1800BBB68
0x1800bbb5b  lea     r8, [rsp+398h+sz]
0x1800bbb63  call    McTemplateU0z_EventWriteTransfer
0x1800bbb68  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2> `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl(void)'::`2'::impl
0x1800bbb6f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(void)
0x1800bbb74  test    al, al
0x1800bbb76  jz      short loc_1800BBB91
0x1800bbb78  call    ?get@?$static_lazy@VFidoPluginProvider@@@details@wil@@QEAAPEAVFidoPluginProvider@@P6AXXZ@Z; wil::details::static_lazy<FidoPluginProvider>::get(void (*)(void))
0x1800bbb7d  mov     rcx, [rax+10h]
0x1800bbb81  mov     eax, [rcx]
0x1800bbb83  cmp     eax, 3
0x1800bbb86  jbe     short loc_1800BBBD8
0x1800bbb88  lea     rdx, unk_18018A3D8
0x1800bbb8f  jmp     short loc_1800BBBAA
0x1800bbb91  mov     eax, cs:dword_1801AB110
0x1800bbb97  cmp     eax, 3
0x1800bbb9a  jbe     short loc_1800BBBD8
0x1800bbb9c  lea     rdx, unk_18018A2DA
0x1800bbba3  lea     rcx, dword_1801AB110
0x1800bbbaa  lea     rax, [rsp+398h+sz]
0x1800bbbb2  mov     qword ptr [rsp+398h+var_348.Data1], rax
0x1800bbbb7  lea     rax, [rsp+398h+var_348]
0x1800bbbbc  mov     [rsp+398h+var_370], rax
  ... truncated ...
```
