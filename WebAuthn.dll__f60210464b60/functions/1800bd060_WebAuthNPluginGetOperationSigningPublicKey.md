# WebAuthNPluginGetOperationSigningPublicKey

- ea: `0x1800bd060`
- end: `0x1800bd623`
- name: `WebAuthNPluginGetOperationSigningPublicKey`
- size: `1475`
- prototype: `__int64 __fastcall(GUID *rguid)`
- caller_count: `0`
- callee_count: `26`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800021d8`
- `0x180003d08`
- `0x180036da4`
- `0x1800467e0`
- `0x180046820`
- `0x18004685c`
- `0x180049de0`
- `0x18004f5b4`
- `0x1800537a4`
- `0x180055188`
- `0x18006cfd4`
- `0x18006f174`
- `0x18006f7b0`
- `0x180079444`
- `0x18007e064`
- `0x180095468`
- `0x1800b1304`
- `0x1800b29a4`
- `0x1800b2ed4`
- `0x1800b308c`
- `0x1800b4170`
- `0x1800b5154`
- `0x1800b523c`
- `0x1800b7cd0`
- `0x1800bd060`
- `0x18013c090`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800bd36b`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800bd36b`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x1800bd27c`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x1800bd27c`

## string_xrefs

- `0x1800bd0ad`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800bd0d8`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800bd106`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800bd22f`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800bd316`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800bd3fa`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800bd58c`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800bd1ae`: `WebAuthNPluginGetOperationSigningPublicKeyTest::reason::remote_session`
- `0x1800bd295`: `WebAuthNPluginGetOperationSigningPublicKeyTest::reason::remote_session`
- `0x1800bd505`: `WebAuthNPluginGetOperationSigningPublicKeyTest::reason::generic_failure`
- `0x1800bd379`: `WebAuthNPluginGetOperationSigningPublicKeyTest::reason::invalid_parameters`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall WebAuthNPluginGetOperationSigningPublicKey(GUID *rguid, unsigned int *a2, unsigned __int8 **a3)
{
  __int64 v6; // rdx
  __int64 v7; // r8
  _DWORD *v9; // rcx
  const char *v10; // rdx
  const char *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // r8
  int v14; // r8d
  int v15; // r9d
  int *v16; // rcx
  int *v17; // rdx
  const char *v18; // rdx
  const char *v19; // rax
  __int64 v20; // rdx
  __int64 v21; // r8
  int v22; // r8d
  int v23; // r9d
  int *v24; // rcx
  __int16 *v25; // rdx
  const char *v26; // rdx
  const char *v27; // rax
  __int64 v28; // rdx
  __int64 v29; // r8
  int v30; // r8d
  int v31; // r9d
  int *v32; // rcx
  int *v33; // rdx
  __int64 v34; // r8
  const char *v35; // rdx
  unsigned int v36; // ebx
  __int64 v37; // r8
  const char *v38; // rax
  int v39; // r8d
  int v40; // r9d
  int *v41; // rcx
  char *v42; // rdx
  int v43; // [rsp+20h] [rbp-358h]
  int v44; // [rsp+20h] [rbp-358h]
  unsigned int v45; // [rsp+30h] [rbp-348h] BYREF
  _BYTE v46[4]; // [rsp+34h] [rbp-344h] BYREF
  __int64 v47; // [rsp+38h] [rbp-340h] BYREF
  __int64 v48; // [rsp+40h] [rbp-338h] BYREF
  unsigned __int8 *v49; // [rsp+48h] [rbp-330h] BYREF
  struct _GUID v50; // [rsp+50h] [rbp-328h] BYREF
  _BYTE v51[64]; // [rsp+60h] [rbp-318h] BYREF
  _BYTE v52[16]; // [rsp+A0h] [rbp-2D8h] BYREF
  _BYTE v53[256]; // [rsp+B0h] [rbp-2C8h] BYREF
  OLECHAR *v54; // [rsp+1B0h] [rbp-1C8h]
  OLECHAR sz[40]; // [rsp+2F0h] [rbp-88h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+378h] [rbp+0h]

  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::__private_IsEnabled(
                           `wil::Feature<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::GetImpl'::`2'::impl,
                           a2,
                           a3) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE6A,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
      (const char *)0x80004001LL,
      v43);
    return 2147500033LL;
  }
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE6B,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
      (const char *)0x80090027LL,
      v43);
    return 2148073511LL;
  }
  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE6C,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
      (const char *)0x80090027LL,
      v43);
    return 2148073511LL;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl,
                          v6,
                          v7) )
  {
    v9 = *(_DWORD **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
    if ( *v9 > 4u )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        v9,
        byte_18018964D,
        0);
  }
  else if ( (unsigned int)dword_1801AB110 > 4 )
  {
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_1801AB110,
      byte_18018968B,
      0);
  }
  v47 = 0;
  tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>>::start_and_watch_errors(
    &v47,
    v51);
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
  {
    v46[0] = 0;
    if ( !(unsigned __int8)IsWinStationIsSessionRemoteablePresent()
      || !(unsigned __int8)WinStationIsSessionRemoteable(0, 0xFFFFFFFFLL, v46)
      || !v46[0] )
    {
      goto LABEL_31;
    }
    v19 = tip2::details::reason_string(
            (tip2::details *)"WebAuthNPluginGetOperationSigningPublicKeyTest::reason::remote_session",
            v18);
    tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(
      &v47,
      4,
      v19);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(
                            `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl,
                            v20,
                            v21) )
    {
      v24 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
      if ( (unsigned int)*v24 > 3 )
      {
        v25 = (__int16 *)byte_1801894D9;
LABEL_29:
        v45 = -2146893783;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (_DWORD)v24,
          (_DWORD)v25,
          v22,
          v23,
          (__int64)&v45);
      }
    }
    else if ( (unsigned int)dword_1801AB110 > 3 )
    {
      v25 = word_180189532;
      v24 = &dword_1801AB110;
      goto LABEL_29;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEA6,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
      (const char *)0x80090029LL,
      v43);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>>(v51);
    wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>,wil::err_returncode_policy>(&v47);
    return 2148073513LL;
  }
  if ( ShouldSendRequestToRemoteSession(0) )
  {
    v11 = tip2::details::reason_string(
            (tip2::details *)"WebAuthNPluginGetOperationSigningPublicKeyTest::reason::remote_session",
            v10);
    tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(
      &v47,
      4,
      v11);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(
                            `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl,
                            v12,
                            v13) )
    {
      v16 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
      if ( (unsigned int)*v16 > 3 )
      {
        v17 = (int *)byte_180189593;
LABEL_19:
        v45 = -2146893783;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (_DWORD)v16,
          (_DWORD)v17,
          v14,
          v15,
          (__int64)&v45);
      }
    }
    else if ( (unsigned int)dword_1801AB110 > 3 )
    {
      v17 = &dword_1801895EC;
      v16 = &dword_1801AB110;
      goto LABEL_19;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE90,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
      (const char *)0x80090029LL,
      v43);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>>(v51);
    wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>,wil::err_returncode_policy>(&v47);
    return 2148073513LL;
  }
LABEL_31:
  memset_0(sz, 0, sizeof(sz));
  if ( !StringFromGUID2(rguid, sz, 40) )
  {
    v27 = tip2::details::reason_string(
            (tip2::details *)"WebAuthNPluginGetOperationSigningPublicKeyTest::reason::invalid_parameters",
            v26);
    tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(
      &v47,
      2,
      v27);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(
                            `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl,
                            v28,
                            v29) )
    {
      v32 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
      if ( (unsigned int)*v32 > 3 )
      {
        v33 = (int *)&byte_180189417;
LABEL_37:
        v45 = -2146893785;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (_DWORD)v32,
          (_DWORD)v33,
          v30,
          v31,
          (__int64)&v45);
      }
    }
    else if ( (unsigned int)dword_1801AB110 > 3 )
    {
      v33 = &dword_180189474;
      v32 = &dword_1801AB110;
      goto LABEL_37;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEBC,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
      (const char *)0x80090027LL,
      v43);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>>(v51);
    wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>,wil::err_returncode_policy>(&v47);
    return 2148073511LL;
  }
  memset_0(v53, 0, 0x238u);
  v54 = sz;
  tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>>::data(
    &v47,
    &v48);
  v34 = -1;
  do
    ++v34;
  while ( sz[v34] );
  std::wstring::_Assign<unsigned short>(v48 + 272, sz);
  tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>>::close(&v48);
  v45 = 0;
  v49 = 0;
  v50 = *(struct _GUID *)tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::test_id(
                           &v47,
                           v52);
  v36 = I_EncodeAndSendRpcRequest(0x70u, &v50, (struct _CTAPCBOR_RPC_REQUEST *)v53, &v45, &v49);
  if ( (v36 & 0x80000000) != 0 )
  {
    if ( v47 )
    {
      if ( (unsigned __int8)tip2::details::shared_data<1,0,0>::is_running(v47 + 8) )
      {
        v38 = tip2::details::reason_string(
                (tip2::details *)"WebAuthNPluginGetOperationSigningPublicKeyTest::reason::generic_failure",
                v35);
        tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>>::set_flag_value<long>(
          &v47,
          1,
          v38,
          v36);
        tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::complete(&v47);
      }
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(
                            `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl,
                            v35,
                            v37) )
    {
      v41 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
      if ( (unsigned int)*v41 > 3 )
      {
        v42 = &byte_180189347;
LABEL_50:
        v45 = v36;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (_DWORD)v41,
          (_DWORD)v42,
          v39,
          v40,
          (__int64)&v45);
      }
    }
    else if ( (unsigned int)dword_1801AB110 > 3 )
    {
      v42 = byte_1801893AB;
      v41 = &dword_1801AB110;
      goto LABEL_50;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEE2,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
      (const char *)v36,
      v44);
    tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>>(&v48);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>>(v51);
    wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>,wil::err_returncode_policy>(&v47);
    return v36;
  }
  *a2 = v45;
  *a3 = v49;
  tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::complete(&v47);
  tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>>(&v48);
  tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>>(v51);
  wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>,wil::err_returncode_policy>(&v47);
  return 0;
}

```

## disassembly

```asm
0x1800bd060  push    rbx
0x1800bd062  push    rsi
0x1800bd063  push    rdi
0x1800bd064  push    r14
0x1800bd066  push    r15
0x1800bd068  sub     rsp, 350h
0x1800bd06f  mov     rax, cs:__security_cookie
0x1800bd076  xor     rax, rsp
0x1800bd079  mov     [rsp+378h+var_38], rax
0x1800bd081  mov     rsi, r8
0x1800bd084  mov     rdi, rdx
0x1800bd087  mov     rbx, rcx
0x1800bd08a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PasskeyPluginAuthenticators@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PasskeyPluginAuthenticators@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators> `wil::Feature<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::GetImpl(void)'::`2'::impl
0x1800bd091  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PasskeyPluginAuthenticators@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::__private_IsEnabled(void)
0x1800bd096  xor     r14d, r14d
0x1800bd099  test    al, al
0x1800bd09b  jnz     short loc_1800BD0C5
0x1800bd09d  mov     rcx, [rsp+378h]; this
0x1800bd0a5  mov     ebx, 80004001h
0x1800bd0aa  mov     r9d, ebx; char *
0x1800bd0ad  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800bd0b4  mov     edx, 0E6Ah; void *
0x1800bd0b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bd0be  mov     eax, ebx
0x1800bd0c0  jmp     loc_1800BD603
0x1800bd0c5  test    rdi, rdi
0x1800bd0c8  jnz     short loc_1800BD0F3
0x1800bd0ca  mov     rcx, [rsp+378h]; this
0x1800bd0d2  mov     r9d, 80090027h; char *
0x1800bd0d8  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800bd0df  mov     edx, 0E6Bh; void *
0x1800bd0e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bd0e9  mov     eax, 80090027h
0x1800bd0ee  jmp     loc_1800BD603
0x1800bd0f3  test    rsi, rsi
0x1800bd0f6  jnz     short loc_1800BD121
0x1800bd0f8  mov     rcx, [rsp+378h]; this
0x1800bd100  mov     r9d, 80090027h; char *
0x1800bd106  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800bd10d  mov     edx, 0E6Ch; void *
0x1800bd112  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bd117  mov     eax, 80090027h
0x1800bd11c  jmp     loc_1800BD603
0x1800bd121  lea     r15, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2> `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl(void)'::`2'::impl
0x1800bd128  mov     rcx, r15
0x1800bd12b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(void)
0x1800bd130  test    al, al
0x1800bd132  jz      short loc_1800BD155
0x1800bd134  call    ?get@?$static_lazy@VFidoPluginProvider@@@details@wil@@QEAAPEAVFidoPluginProvider@@P6AXXZ@Z; wil::details::static_lazy<FidoPluginProvider>::get(void (*)(void))
0x1800bd139  mov     rcx, [rax+10h]
0x1800bd13d  mov     eax, [rcx]
0x1800bd13f  cmp     eax, 4
0x1800bd142  jbe     short loc_1800BD176
0x1800bd144  xor     r8d, r8d
0x1800bd147  lea     rdx, byte_18018964D
0x1800bd14e  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800bd153  jmp     short loc_1800BD176
0x1800bd155  mov     eax, cs:dword_1801AB110
0x1800bd15b  cmp     eax, 4
0x1800bd15e  jbe     short loc_1800BD176
0x1800bd160  xor     r8d, r8d
0x1800bd163  lea     rdx, byte_18018968B
0x1800bd16a  lea     rcx, dword_1801AB110
0x1800bd171  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800bd176  mov     [rsp+378h+var_340], r14
0x1800bd17b  lea     rdx, [rsp+378h+var_318]
0x1800bd180  lea     rcx, [rsp+378h+var_340]
0x1800bd185  call    ?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginGetOperationSigningPublicKeyTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginGetOperationSigningPublicKeyTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>>::start_and_watch_errors(void)
0x1800bd18a  nop
0x1800bd18b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl(void)'::`2'::impl
0x1800bd192  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x1800bd197  test    al, al
0x1800bd199  jz      loc_1800BD260
0x1800bd19f  xor     ecx, ecx; unsigned __int8 *
0x1800bd1a1  call    ?ShouldSendRequestToRemoteSession@@YA_NPEAE@Z; ShouldSendRequestToRemoteSession(uchar *)
0x1800bd1a6  test    al, al
0x1800bd1a8  jz      loc_1800BD347
0x1800bd1ae  lea     rcx, aWebauthnplugin_87; "WebAuthNPluginGetOperationSigningPublic"...
0x1800bd1b5  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800bd1ba  mov     r8, rax
0x1800bd1bd  mov     edx, 4
0x1800bd1c2  lea     rcx, [rsp+378h+var_340]
0x1800bd1c7  call    ?complete_and_ignore@?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(ushort,char const *)
0x1800bd1cc  mov     rcx, r15
0x1800bd1cf  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(void)
0x1800bd1d4  test    al, al
0x1800bd1d6  jz      short loc_1800BD1F1
0x1800bd1d8  call    ?get@?$static_lazy@VFidoPluginProvider@@@details@wil@@QEAAPEAVFidoPluginProvider@@P6AXXZ@Z; wil::details::static_lazy<FidoPluginProvider>::get(void (*)(void))
0x1800bd1dd  mov     rcx, [rax+10h]
0x1800bd1e1  mov     eax, [rcx]
0x1800bd1e3  cmp     eax, 3
0x1800bd1e6  jbe     short loc_1800BD221
0x1800bd1e8  lea     rdx, byte_180189593
0x1800bd1ef  jmp     short loc_1800BD20A
0x1800bd1f1  mov     eax, cs:dword_1801AB110
0x1800bd1f7  cmp     eax, 3
0x1800bd1fa  jbe     short loc_1800BD221
0x1800bd1fc  lea     rdx, dword_1801895EC
0x1800bd203  lea     rcx, dword_1801AB110
0x1800bd20a  lea     rax, [rsp+378h+var_348]
0x1800bd20f  mov     qword ptr [rsp+378h+var_358], rax; int
0x1800bd214  mov     [rsp+378h+var_348], 80090029h
0x1800bd21c  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800bd221  mov     rcx, [rsp+378h]; this
0x1800bd229  mov     r9d, 80090029h; char *
0x1800bd22f  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800bd236  mov     edx, 0E90h; void *
0x1800bd23b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bd240  nop
0x1800bd241  lea     rcx, [rsp+378h+var_318]
0x1800bd246  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginGetOperationSigningPublicKeyTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>>(void)
0x1800bd24b  nop
0x1800bd24c  lea     rcx, [rsp+378h+var_340]
0x1800bd251  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginGetOperationSigningPublicKeyTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>,wil::err_returncode_policy>(void)
0x1800bd256  mov     eax, 80090029h
0x1800bd25b  jmp     loc_1800BD603
0x1800bd260  mov     [rsp+378h+var_344], r14b
0x1800bd265  call    IsWinStationIsSessionRemoteablePresent
0x1800bd26a  test    al, al
0x1800bd26c  jz      loc_1800BD347
0x1800bd272  lea     r8, [rsp+378h+var_344]
0x1800bd277  or      edx, 0FFFFFFFFh
0x1800bd27a  xor     ecx, ecx
0x1800bd27c  call    cs:__imp_WinStationIsSessionRemoteable
0x1800bd282  test    al, al
0x1800bd284  jz      loc_1800BD347
0x1800bd28a  cmp     [rsp+378h+var_344], r14b
0x1800bd28f  jz      loc_1800BD347
0x1800bd295  lea     rcx, aWebauthnplugin_87; "WebAuthNPluginGetOperationSigningPublic"...
0x1800bd29c  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800bd2a1  mov     r8, rax
0x1800bd2a4  mov     edx, 4
0x1800bd2a9  lea     rcx, [rsp+378h+var_340]
0x1800bd2ae  call    ?complete_and_ignore@?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(ushort,char const *)
0x1800bd2b3  mov     rcx, r15
0x1800bd2b6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(void)
0x1800bd2bb  test    al, al
0x1800bd2bd  jz      short loc_1800BD2D8
0x1800bd2bf  call    ?get@?$static_lazy@VFidoPluginProvider@@@details@wil@@QEAAPEAVFidoPluginProvider@@P6AXXZ@Z; wil::details::static_lazy<FidoPluginProvider>::get(void (*)(void))
0x1800bd2c4  mov     rcx, [rax+10h]
0x1800bd2c8  mov     eax, [rcx]
0x1800bd2ca  cmp     eax, 3
0x1800bd2cd  jbe     short loc_1800BD308
0x1800bd2cf  lea     rdx, byte_1801894D9
0x1800bd2d6  jmp     short loc_1800BD2F1
0x1800bd2d8  mov     eax, cs:dword_1801AB110
0x1800bd2de  cmp     eax, 3
0x1800bd2e1  jbe     short loc_1800BD308
0x1800bd2e3  lea     rdx, word_180189532
0x1800bd2ea  lea     rcx, dword_1801AB110
0x1800bd2f1  lea     rax, [rsp+378h+var_348]
0x1800bd2f6  mov     qword ptr [rsp+378h+var_358], rax; int
0x1800bd2fb  mov     [rsp+378h+var_348], 80090029h
0x1800bd303  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800bd308  mov     rcx, [rsp+378h]; this
0x1800bd310  mov     r9d, 80090029h; char *
0x1800bd316  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800bd31d  mov     edx, 0EA6h; void *
0x1800bd322  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bd327  nop
0x1800bd328  lea     rcx, [rsp+378h+var_318]
0x1800bd32d  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginGetOperationSigningPublicKeyTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>>(void)
0x1800bd332  nop
0x1800bd333  lea     rcx, [rsp+378h+var_340]
0x1800bd338  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginGetOperationSigningPublicKeyTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>,wil::err_returncode_policy>(void)
0x1800bd33d  mov     eax, 80090029h
0x1800bd342  jmp     loc_1800BD603
0x1800bd347  xor     edx, edx; Val
0x1800bd349  lea     r8d, [rdx+50h]; Size
0x1800bd34d  lea     rcx, [rsp+378h+sz]; void *
0x1800bd355  call    memset_0
0x1800bd35a  mov     r8d, 28h ; '('; cchMax
0x1800bd360  lea     rdx, [rsp+378h+sz]; lpsz
0x1800bd368  mov     rcx, rbx; rguid
0x1800bd36b  call    cs:__imp_StringFromGUID2
0x1800bd371  test    eax, eax
0x1800bd373  jnz     loc_1800BD42B
0x1800bd379  lea     rcx, aWebauthnplugin_66; "WebAuthNPluginGetOperationSigningPublic"...
0x1800bd380  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800bd385  mov     r8, rax
0x1800bd388  mov     edx, 2
0x1800bd38d  lea     rcx, [rsp+378h+var_340]
0x1800bd392  call    ?complete_and_ignore@?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(ushort,char const *)
0x1800bd397  mov     rcx, r15
0x1800bd39a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(void)
0x1800bd39f  test    al, al
0x1800bd3a1  jz      short loc_1800BD3BC
0x1800bd3a3  call    ?get@?$static_lazy@VFidoPluginProvider@@@details@wil@@QEAAPEAVFidoPluginProvider@@P6AXXZ@Z; wil::details::static_lazy<FidoPluginProvider>::get(void (*)(void))
0x1800bd3a8  mov     rcx, [rax+10h]
0x1800bd3ac  mov     eax, [rcx]
0x1800bd3ae  cmp     eax, 3
0x1800bd3b1  jbe     short loc_1800BD3EC
0x1800bd3b3  lea     rdx, byte_180189417
0x1800bd3ba  jmp     short loc_1800BD3D5
0x1800bd3bc  mov     eax, cs:dword_1801AB110
0x1800bd3c2  cmp     eax, 3
0x1800bd3c5  jbe     short loc_1800BD3EC
0x1800bd3c7  lea     rdx, dword_180189474
0x1800bd3ce  lea     rcx, dword_1801AB110
0x1800bd3d5  lea     rax, [rsp+378h+var_348]
0x1800bd3da  mov     qword ptr [rsp+378h+var_358], rax; int
0x1800bd3df  mov     [rsp+378h+var_348], 80090027h
0x1800bd3e7  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800bd3ec  mov     rcx, [rsp+378h]; this
0x1800bd3f4  mov     r9d, 80090027h; char *
0x1800bd3fa  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800bd401  mov     edx, 0EBCh; void *
0x1800bd406  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bd40b  nop
0x1800bd40c  lea     rcx, [rsp+378h+var_318]
0x1800bd411  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginGetOperationSigningPublicKeyTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>>(void)
0x1800bd416  nop
0x1800bd417  lea     rcx, [rsp+378h+var_340]
0x1800bd41c  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginGetOperationSigningPublicKeyTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>,wil::err_returncode_policy>(void)
0x1800bd421  mov     eax, 80090027h
0x1800bd426  jmp     loc_1800BD603
0x1800bd42b  xor     edx, edx; Val
0x1800bd42d  mov     r8d, 238h; Size
0x1800bd433  lea     rcx, [rsp+378h+var_2C8]; void *
0x1800bd43b  call    memset_0
0x1800bd440  lea     rax, [rsp+378h+sz]
0x1800bd448  mov     [rsp+378h+var_1C8], rax
0x1800bd450  lea     rdx, [rsp+378h+var_338]
0x1800bd455  lea     rcx, [rsp+378h+var_340]
0x1800bd45a  call    ?data@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginGetOperationSigningPublicKeyTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginGetOperationSigningPublicKeyTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>>::data(void)
0x1800bd45f  nop
0x1800bd460  mov     rcx, [rsp+378h+var_338]
0x1800bd465  add     rcx, 110h
0x1800bd46c  lea     rax, [rsp+378h+sz]
0x1800bd474  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800bd478  inc     r8
0x1800bd47b  cmp     [rax+r8*2], r14w
0x1800bd480  jnz     short loc_1800BD478
0x1800bd482  lea     rdx, [rsp+378h+sz]
0x1800bd48a  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800bd48f  lea     rcx, [rsp+378h+var_338]
0x1800bd494  call    ?close@?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginGetOperationSigningPublicKeyTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>>::close(void)
0x1800bd499  mov     [rsp+378h+var_348], r14d
0x1800bd49e  mov     [rsp+378h+var_330], r14
0x1800bd4a3  lea     rdx, [rsp+378h+var_2D8]
0x1800bd4ab  lea     rcx, [rsp+378h+var_340]
0x1800bd4b0  call    ?test_id@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest@@U1@@details@tip2@@@tip2@@QEBA?AU_GUID@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::test_id(void)
0x1800bd4b5  movups  xmm1, xmmword ptr [rax]
0x1800bd4b8  movdqu  xmmword ptr [rsp+378h+var_328.Data1], xmm1
0x1800bd4be  lea     rax, [rsp+378h+var_330]
0x1800bd4c3  mov     qword ptr [rsp+378h+var_358], rax; unsigned __int8 **
0x1800bd4c8  lea     r9, [rsp+378h+var_348]; unsigned int *
0x1800bd4cd  lea     r8, [rsp+378h+var_2C8]; struct _CTAPCBOR_RPC_REQUEST *
0x1800bd4d5  lea     rdx, [rsp+378h+var_328]; struct _GUID *
0x1800bd4da  mov     ecx, 70h ; 'p'; unsigned int
0x1800bd4df  call    ?I_EncodeAndSendRpcRequest@@YAJKU_GUID@@AEAU_CTAPCBOR_RPC_REQUEST@@PEAKPEAPEAE@Z; I_EncodeAndSendRpcRequest(ulong,_GUID,_CTAPCBOR_RPC_REQUEST &,ulong *,uchar * *)
0x1800bd4e4  mov     ebx, eax
0x1800bd4e6  test    eax, eax
0x1800bd4e8  jns     loc_1800BD5C2
0x1800bd4ee  mov     rcx, [rsp+378h+var_340]
0x1800bd4f3  test    rcx, rcx
0x1800bd4f6  jz      short loc_1800BD530
0x1800bd4f8  add     rcx, 8
0x1800bd4fc  call    ?is_running@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::is_running(void)
0x1800bd501  test    al, al
0x1800bd503  jz      short loc_1800BD530
0x1800bd505  lea     rcx, aWebauthnplugin_99; "WebAuthNPluginGetOperationSigningPublic"...
0x1800bd50c  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800bd511  mov     r8, rax
0x1800bd514  mov     edx, 1
0x1800bd519  mov     r9d, ebx
0x1800bd51c  lea     rcx, [rsp+378h+var_340]
0x1800bd521  call    ??$set_flag_value@J@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginGetOperationSigningPublicKeyTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBDJ@Z; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>>::set_flag_value<long>(ushort,char const *,long)
0x1800bd526  lea     rcx, [rsp+378h+var_340]
0x1800bd52b  call    ?complete@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginCallbackTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::complete(void)
0x1800bd530  mov     rcx, r15
0x1800bd533  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(void)
0x1800bd538  test    al, al
0x1800bd53a  jz      short loc_1800BD555
0x1800bd53c  call    ?get@?$static_lazy@VFidoPluginProvider@@@details@wil@@QEAAPEAVFidoPluginProvider@@P6AXXZ@Z; wil::details::static_lazy<FidoPluginProvider>::get(void (*)(void))
0x1800bd541  mov     rcx, [rax+10h]
0x1800bd545  mov     eax, [rcx]
0x1800bd547  cmp     eax, 3
0x1800bd54a  jbe     short loc_1800BD581
0x1800bd54c  lea     rdx, byte_180189347
0x1800bd553  jmp     short loc_1800BD56E
0x1800bd555  mov     eax, cs:dword_1801AB110
0x1800bd55b  cmp     eax, 3
0x1800bd55e  jbe     short loc_1800BD581
0x1800bd560  lea     rdx, byte_1801893AB
0x1800bd567  lea     rcx, dword_1801AB110
0x1800bd56e  lea     rax, [rsp+378h+var_348]
0x1800bd573  mov     qword ptr [rsp+378h+var_358], rax; int
0x1800bd578  mov     [rsp+378h+var_348], ebx
0x1800bd57c  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800bd581  mov     rcx, [rsp+378h]; this
0x1800bd589  mov     r9d, ebx; char *
0x1800bd58c  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800bd593  mov     edx, 0EE2h; void *
0x1800bd598  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bd59d  nop
0x1800bd59e  lea     rcx, [rsp+378h+var_338]
0x1800bd5a3  call    ??1?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginGetOperationSigningPublicKeyTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>>(void)
0x1800bd5a8  nop
0x1800bd5a9  lea     rcx, [rsp+378h+var_318]
  ... truncated ...
```
