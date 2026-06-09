# WebAuthNPluginPerformUserVerification

- ea: `0x1800be150`
- end: `0x1800be88b`
- name: `WebAuthNPluginPerformUserVerification`
- size: `1851`
- prototype: ``
- caller_count: `0`
- callee_count: `22`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180003d08`
- `0x180003f18`
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
- `0x1800b134c`
- `0x1800b29c0`
- `0x1800b30b4`
- `0x1800b4170`
- `0x1800b7d38`
- `0x1800be150`
- `0x1800be8a0`
- `0x18013c090`

## import_xrefs

- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x1800be318`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x1800be318`

## string_xrefs

- `0x1800be19b`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800be1da`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800be208`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800be236`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800be3b2`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800be566`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800be635`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800be6e9`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800be7c2`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800be803`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800be741`: `WebAuthNPluginPerformUVTest::reason::invalid_parameters`
- `0x1800be331`: `WebAuthNPluginPerformUVTest::reason::remote_session`
- `0x1800be4bc`: `WebAuthNPluginPerformUVTest::reason::uv_failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall WebAuthNPluginPerformUserVerification(__int64 a1, _DWORD *a2, unsigned __int8 **a3)
{
  int v7; // r8d
  int v8; // r9d
  int *v9; // rcx
  void *v10; // rdx
  const char *v11; // rdx
  const char *v12; // rax
  int v13; // r8d
  int v14; // r9d
  int *v15; // rcx
  void *v16; // rdx
  const char *v17; // rdx
  _QWORD *v18; // rcx
  int v19; // ebx
  const char *v20; // rdx
  const char *v21; // rax
  int v22; // r8d
  int v23; // r9d
  int *v24; // rcx
  void *v25; // rdx
  int v26; // r8d
  int v27; // r9d
  int *v28; // rcx
  void *v29; // rdx
  int v30; // r8d
  int v31; // r9d
  int *v32; // rcx
  void *v33; // rdx
  const char *v34; // rax
  int v35; // r8d
  int v36; // r9d
  int *v37; // rcx
  void *v38; // rdx
  int v39; // [rsp+20h] [rbp-2F8h]
  int v40; // [rsp+20h] [rbp-2F8h]
  unsigned int v41[2]; // [rsp+30h] [rbp-2E8h] BYREF
  _BYTE v42[8]; // [rsp+38h] [rbp-2E0h] BYREF
  __int64 v43; // [rsp+40h] [rbp-2D8h] BYREF
  unsigned __int8 *v44; // [rsp+48h] [rbp-2D0h] BYREF
  _QWORD v45[8]; // [rsp+50h] [rbp-2C8h] BYREF
  struct _GUID v46; // [rsp+90h] [rbp-288h] BYREF
  _BYTE v47[16]; // [rsp+A0h] [rbp-278h] BYREF
  _BYTE v48[344]; // [rsp+B0h] [rbp-268h] BYREF
  const char *v49; // [rsp+208h] [rbp-110h]
  int v50; // [rsp+210h] [rbp-108h]
  __int128 v51; // [rsp+214h] [rbp-104h]
  __int64 v52; // [rsp+228h] [rbp-F0h]
  __int64 v53; // [rsp+230h] [rbp-E8h]
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+0h]

  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::GetImpl'::`2'::impl) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC27,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
      (const char *)0x80004001LL,
      v39);
    return 2147500033LL;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
  {
    if ( a1 )
    {
      v45[0] = *(_QWORD *)a1;
      v45[1] = *(_QWORD *)(a1 + 8);
      v45[2] = *(_QWORD *)(a1 + 16);
      v45[3] = *(_QWORD *)(a1 + 24);
      v45[4] = 0;
      v45[5] = 0;
      return WebAuthNPluginPerformUserVerification2(v45, a2, a3);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC2B,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
        (const char *)0x80090027LL,
        v39);
      return 2148073511LL;
    }
  }
  if ( !a1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC39,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
      (const char *)0x80090027LL,
      v39);
    return 2148073511LL;
  }
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC3A,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
      (const char *)0x80090027LL,
      v39);
    return 2148073511LL;
  }
  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC3B,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
      (const char *)0x80090027LL,
      v39);
    return 2148073511LL;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl) )
  {
    v9 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
    if ( (unsigned int)*v9 > 4 )
    {
      v10 = &unk_18018A225;
LABEL_15:
      v44 = *(unsigned __int8 **)(a1 + 24);
      *(_QWORD *)v41 = *(_QWORD *)(a1 + 16);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v9,
        (_DWORD)v10,
        v7,
        v8,
        (__int64)v41,
        (__int64)&v44);
    }
  }
  else if ( (unsigned int)dword_1801AB110 > 4 )
  {
    v10 = &unk_18018A27D;
    v9 = &dword_1801AB110;
    goto LABEL_15;
  }
  v43 = 0;
  tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::start_and_watch_errors(
    &v43,
    v45);
  v42[0] = 0;
  memset_0(v48, 0, 0x238u);
  *a3 = 0;
  *a2 = 0;
  if ( (unsigned __int8)IsWinStationIsSessionRemoteablePresent()
    && (unsigned __int8)WinStationIsSessionRemoteable(0, 0xFFFFFFFFLL, v42)
    && v42[0] )
  {
    v12 = tip2::details::reason_string((tip2::details *)"WebAuthNPluginPerformUVTest::reason::remote_session", v11);
    tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(
      &v43,
      2,
      v12);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl) )
    {
      v15 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
      if ( (unsigned int)*v15 > 3 )
      {
        v16 = &unk_18018A175;
LABEL_24:
        v41[0] = -2146893783;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (_DWORD)v15,
          (_DWORD)v16,
          v13,
          v14,
          (__int64)v41);
      }
    }
    else if ( (unsigned int)dword_1801AB110 > 3 )
    {
      v16 = &unk_18018A1C9;
      v15 = &dword_1801AB110;
      goto LABEL_24;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC67,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
      (const char *)0x80090029LL,
      v39);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>(v45);
    wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>(&v43);
    return 2148073513LL;
  }
  v17 = *(const char **)a1;
  if ( !*(_QWORD *)a1
    || (v18 = *(_QWORD **)(a1 + 8), *v18 == *(_QWORD *)&GUID_NULL.Data1) && v18[1] == *(_QWORD *)GUID_NULL.Data4 )
  {
    v34 = tip2::details::reason_string((tip2::details *)"WebAuthNPluginPerformUVTest::reason::invalid_parameters", v17);
    tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(
      &v43,
      9,
      v34);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl) )
    {
      v37 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
      if ( (unsigned int)*v37 > 3 )
      {
        v38 = &unk_18018A0BD;
LABEL_68:
        v41[0] = -2146893785;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (_DWORD)v37,
          (_DWORD)v38,
          v35,
          v36,
          (__int64)v41);
      }
    }
    else if ( (unsigned int)dword_1801AB110 > 3 )
    {
      v38 = &unk_18018A115;
      v37 = &dword_1801AB110;
      goto LABEL_68;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC7A,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
      (const char *)0x80090027LL,
      v39);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>(v45);
    wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>(&v43);
    return 2148073511LL;
  }
  v51 = *(_OWORD *)v18;
  v49 = v17;
  v50 = 1;
  v52 = *(_QWORD *)(a1 + 16);
  v53 = *(_QWORD *)(a1 + 24);
  v41[0] = 0;
  v44 = 0;
  v46 = *(struct _GUID *)tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::test_id(
                           &v43,
                           v47);
  v19 = I_EncodeAndSendRpcRequest(0x6Du, &v46, (struct _CTAPCBOR_RPC_REQUEST *)v48, v41, &v44);
  if ( v43 && (unsigned __int8)tip2::details::shared_data<1,0,0>::is_running(v43 + 8) )
  {
    if ( v19 < 0 )
    {
      v21 = tip2::details::reason_string((tip2::details *)"WebAuthNPluginPerformUVTest::reason::uv_failed", v20);
      tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::set_flag_value<long>(
        &v43,
        6,
        v21,
        (unsigned int)v19);
    }
    tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::complete(&v43);
  }
  if ( v19 == -2147023673 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl) )
    {
      v24 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
      if ( (unsigned int)*v24 > 3 )
      {
        v25 = &unk_180189FF7;
LABEL_40:
        v41[0] = -2146893770;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (_DWORD)v24,
          (_DWORD)v25,
          v22,
          v23,
          (__int64)v41);
      }
    }
    else if ( (unsigned int)dword_1801AB110 > 3 )
    {
      v25 = &unk_18018A056;
      v24 = &dword_1801AB110;
      goto LABEL_40;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCA1,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
        (const char *)0x80090036LL,
        v40);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>(v45);
    wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>(&v43);
    return 2148073526LL;
  }
  if ( v19 != -2147009196 )
  {
    if ( v19 >= 0 )
    {
      *a2 = v41[0];
      *a3 = v44;
      tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>(v45);
      wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>(&v43);
      return 0;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl) )
    {
      v32 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
      if ( (unsigned int)*v32 > 3 )
      {
        v33 = &unk_180189E6B;
LABEL_60:
        v41[0] = v19;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (_DWORD)v32,
          (_DWORD)v33,
          v30,
          v31,
          (__int64)v41);
      }
    }
    else if ( (unsigned int)dword_1801AB110 > 3 )
    {
      v33 = &unk_180189ECA;
      v32 = &dword_1801AB110;
      goto LABEL_60;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCCD,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
      (const char *)(unsigned int)v19,
      v40);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>(v45);
    wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>(&v43);
    return (unsigned int)v19;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl) )
  {
    v28 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
    if ( (unsigned int)*v28 > 3 )
    {
      v29 = &unk_180189F31;
LABEL_50:
      v41[0] = -2147024891;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (_DWORD)v28,
        (_DWORD)v29,
        v26,
        v27,
        (__int64)v41);
    }
  }
  else if ( (unsigned int)dword_1801AB110 > 3 )
  {
    v29 = &unk_180189F90;
    v28 = &dword_1801AB110;
    goto LABEL_50;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCB8,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
      (const char *)0x80070005LL,
      v40);
  tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>(v45);
  wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>(&v43);
  return 2147942405LL;
}

```

## disassembly

```asm
0x1800be150  mov     [rsp+arg_18], rbx
0x1800be155  push    rsi
0x1800be156  push    rdi
0x1800be157  push    r15
0x1800be159  sub     rsp, 300h
0x1800be160  mov     rax, cs:__security_cookie
0x1800be167  xor     rax, rsp
0x1800be16a  mov     [rsp+318h+var_28], rax
0x1800be172  mov     rsi, r8
0x1800be175  mov     rdi, rdx
0x1800be178  mov     rbx, rcx
0x1800be17b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PasskeyPluginAuthenticators@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PasskeyPluginAuthenticators@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators> `wil::Feature<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::GetImpl(void)'::`2'::impl
0x1800be182  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PasskeyPluginAuthenticators@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::__private_IsEnabled(void)
0x1800be187  test    al, al
0x1800be189  jnz     short loc_1800BE1B3
0x1800be18b  mov     rcx, [rsp+318h]; this
0x1800be193  mov     ebx, 80004001h
0x1800be198  mov     r9d, ebx; char *
0x1800be19b  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800be1a2  mov     edx, 0C27h; void *
0x1800be1a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be1ac  mov     eax, ebx
0x1800be1ae  jmp     loc_1800BE866
0x1800be1b3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl(void)'::`2'::impl
0x1800be1ba  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x1800be1bf  test    al, al
0x1800be1c1  jnz     loc_1800BE7F0
0x1800be1c7  test    rbx, rbx
0x1800be1ca  jnz     short loc_1800BE1F5
0x1800be1cc  mov     rcx, [rsp+318h]; this
0x1800be1d4  mov     r9d, 80090027h; char *
0x1800be1da  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800be1e1  mov     edx, 0C39h; void *
0x1800be1e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be1eb  mov     eax, 80090027h
0x1800be1f0  jmp     loc_1800BE866
0x1800be1f5  test    rdi, rdi
0x1800be1f8  jnz     short loc_1800BE223
0x1800be1fa  mov     rcx, [rsp+318h]; this
0x1800be202  mov     r9d, 80090027h; char *
0x1800be208  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800be20f  mov     edx, 0C3Ah; void *
0x1800be214  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be219  mov     eax, 80090027h
0x1800be21e  jmp     loc_1800BE866
0x1800be223  test    rsi, rsi
0x1800be226  jnz     short loc_1800BE251
0x1800be228  mov     rcx, [rsp+318h]; this
0x1800be230  mov     r9d, 80090027h; char *
0x1800be236  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800be23d  mov     edx, 0C3Bh; void *
0x1800be242  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be247  mov     eax, 80090027h
0x1800be24c  jmp     loc_1800BE866
0x1800be251  lea     r15, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2> `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl(void)'::`2'::impl
0x1800be258  mov     rcx, r15
0x1800be25b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(void)
0x1800be260  test    al, al
0x1800be262  jz      short loc_1800BE27D
0x1800be264  call    ?get@?$static_lazy@VFidoPluginProvider@@@details@wil@@QEAAPEAVFidoPluginProvider@@P6AXXZ@Z; wil::details::static_lazy<FidoPluginProvider>::get(void (*)(void))
0x1800be269  mov     rcx, [rax+10h]
0x1800be26d  mov     eax, [rcx]
0x1800be26f  cmp     eax, 4
0x1800be272  jbe     short loc_1800BE2C1
0x1800be274  lea     rdx, unk_18018A225
0x1800be27b  jmp     short loc_1800BE296
0x1800be27d  mov     eax, cs:dword_1801AB110
0x1800be283  cmp     eax, 4
0x1800be286  jbe     short loc_1800BE2C1
0x1800be288  lea     rdx, unk_18018A27D
0x1800be28f  lea     rcx, dword_1801AB110
0x1800be296  mov     rax, [rbx+18h]
0x1800be29a  mov     [rsp+318h+var_2D0], rax
0x1800be29f  mov     rax, [rbx+10h]
0x1800be2a3  mov     qword ptr [rsp+318h+var_2E8], rax
0x1800be2a8  lea     rax, [rsp+318h+var_2D0]
0x1800be2ad  mov     [rsp+318h+var_2F0], rax
0x1800be2b2  lea     rax, [rsp+318h+var_2E8]
0x1800be2b7  mov     [rsp+318h+var_2F8], rax
0x1800be2bc  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800be2c1  mov     [rsp+318h+var_2D8], 0
0x1800be2ca  lea     rdx, [rsp+318h+var_2C8]
0x1800be2cf  lea     rcx, [rsp+318h+var_2D8]
0x1800be2d4  call    ?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginPerformUVTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginPerformUVTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::start_and_watch_errors(void)
0x1800be2d9  nop
0x1800be2da  mov     [rsp+318h+var_2E0], 0
0x1800be2df  xor     edx, edx; Val
0x1800be2e1  mov     r8d, 238h; Size
0x1800be2e7  lea     rcx, [rsp+318h+var_268]; void *
0x1800be2ef  call    memset_0
0x1800be2f4  mov     qword ptr [rsi], 0
0x1800be2fb  mov     dword ptr [rdi], 0
0x1800be301  call    IsWinStationIsSessionRemoteablePresent
0x1800be306  test    al, al
0x1800be308  jz      loc_1800BE3E3
0x1800be30e  lea     r8, [rsp+318h+var_2E0]
0x1800be313  or      edx, 0FFFFFFFFh
0x1800be316  xor     ecx, ecx
0x1800be318  call    cs:__imp_WinStationIsSessionRemoteable
0x1800be31e  test    al, al
0x1800be320  jz      loc_1800BE3E3
0x1800be326  cmp     [rsp+318h+var_2E0], 0
0x1800be32b  jz      loc_1800BE3E3
0x1800be331  lea     rcx, aWebauthnplugin_61; "WebAuthNPluginPerformUVTest::reason::re"...
0x1800be338  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800be33d  mov     r8, rax
0x1800be340  mov     edx, 2
0x1800be345  lea     rcx, [rsp+318h+var_2D8]
0x1800be34a  call    ?complete_and_ignore@?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(ushort,char const *)
0x1800be34f  mov     rcx, r15
0x1800be352  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(void)
0x1800be357  test    al, al
0x1800be359  jz      short loc_1800BE374
0x1800be35b  call    ?get@?$static_lazy@VFidoPluginProvider@@@details@wil@@QEAAPEAVFidoPluginProvider@@P6AXXZ@Z; wil::details::static_lazy<FidoPluginProvider>::get(void (*)(void))
0x1800be360  mov     rcx, [rax+10h]
0x1800be364  mov     eax, [rcx]
0x1800be366  cmp     eax, 3
0x1800be369  jbe     short loc_1800BE3A4
0x1800be36b  lea     rdx, unk_18018A175
0x1800be372  jmp     short loc_1800BE38D
0x1800be374  mov     eax, cs:dword_1801AB110
0x1800be37a  cmp     eax, 3
0x1800be37d  jbe     short loc_1800BE3A4
0x1800be37f  lea     rdx, unk_18018A1C9
0x1800be386  lea     rcx, dword_1801AB110
0x1800be38d  lea     rax, [rsp+318h+var_2E8]
0x1800be392  mov     [rsp+318h+var_2F8], rax; int
0x1800be397  mov     [rsp+318h+var_2E8], 80090029h
0x1800be39f  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800be3a4  mov     rcx, [rsp+318h]; this
0x1800be3ac  mov     r9d, 80090029h; char *
0x1800be3b2  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800be3b9  mov     edx, 0C67h; void *
0x1800be3be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be3c3  nop
0x1800be3c4  lea     rcx, [rsp+318h+var_2C8]
0x1800be3c9  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginPerformUVTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>(void)
0x1800be3ce  nop
0x1800be3cf  lea     rcx, [rsp+318h+var_2D8]
0x1800be3d4  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginPerformUVTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>(void)
0x1800be3d9  mov     eax, 80090029h
0x1800be3de  jmp     loc_1800BE866
0x1800be3e3  mov     rdx, [rbx]; char *
0x1800be3e6  test    rdx, rdx
0x1800be3e9  jz      loc_1800BE741
0x1800be3ef  mov     rcx, [rbx+8]
0x1800be3f3  mov     rax, [rcx]
0x1800be3f6  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800be3fd  jnz     short loc_1800BE410
0x1800be3ff  mov     rax, [rcx+8]
0x1800be403  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800be40a  jz      loc_1800BE741
0x1800be410  movups  xmm0, xmmword ptr [rcx]
0x1800be413  movdqu  [rsp+318h+var_104], xmm0
0x1800be41c  mov     [rsp+318h+var_110], rdx
0x1800be424  mov     [rsp+318h+var_108], 1
0x1800be42f  mov     rax, [rbx+10h]
0x1800be433  mov     [rsp+318h+var_F0], rax
0x1800be43b  mov     rax, [rbx+18h]
0x1800be43f  mov     [rsp+318h+var_E8], rax
0x1800be447  mov     [rsp+318h+var_2E8], 0
0x1800be44f  mov     [rsp+318h+var_2D0], 0
0x1800be458  lea     rdx, [rsp+318h+var_278]
0x1800be460  lea     rcx, [rsp+318h+var_2D8]
0x1800be465  call    ?test_id@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest@@U1@@details@tip2@@@tip2@@QEBA?AU_GUID@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::test_id(void)
0x1800be46a  movups  xmm1, xmmword ptr [rax]
0x1800be46d  movdqu  xmmword ptr [rsp+318h+var_288.Data1], xmm1
0x1800be476  lea     rax, [rsp+318h+var_2D0]
0x1800be47b  mov     [rsp+318h+var_2F8], rax; unsigned __int8 **
0x1800be480  lea     r9, [rsp+318h+var_2E8]; unsigned int *
0x1800be485  lea     r8, [rsp+318h+var_268]; struct _CTAPCBOR_RPC_REQUEST *
0x1800be48d  lea     rdx, [rsp+318h+var_288]; struct _GUID *
0x1800be495  mov     ecx, 6Dh ; 'm'; unsigned int
0x1800be49a  call    ?I_EncodeAndSendRpcRequest@@YAJKU_GUID@@AEAU_CTAPCBOR_RPC_REQUEST@@PEAKPEAPEAE@Z; I_EncodeAndSendRpcRequest(ulong,_GUID,_CTAPCBOR_RPC_REQUEST &,ulong *,uchar * *)
0x1800be49f  mov     ebx, eax
0x1800be4a1  mov     rcx, [rsp+318h+var_2D8]
0x1800be4a6  test    rcx, rcx
0x1800be4a9  jz      short loc_1800BE4E7
0x1800be4ab  add     rcx, 8
0x1800be4af  call    ?is_running@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::is_running(void)
0x1800be4b4  test    al, al
0x1800be4b6  jz      short loc_1800BE4E7
0x1800be4b8  test    ebx, ebx
0x1800be4ba  jns     short loc_1800BE4DD
0x1800be4bc  lea     rcx, aWebauthnplugin_129; "WebAuthNPluginPerformUVTest::reason::uv"...
0x1800be4c3  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800be4c8  mov     r8, rax
0x1800be4cb  mov     edx, 6
0x1800be4d0  mov     r9d, ebx
0x1800be4d3  lea     rcx, [rsp+318h+var_2D8]
0x1800be4d8  call    ??$set_flag_value@J@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginPerformUVTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBDJ@Z; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::set_flag_value<long>(ushort,char const *,long)
0x1800be4dd  lea     rcx, [rsp+318h+var_2D8]
0x1800be4e2  call    ?complete@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginCallbackTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::complete(void)
0x1800be4e7  cmp     ebx, 800704C7h
0x1800be4ed  jnz     loc_1800BE5B6
0x1800be4f3  mov     rcx, r15
0x1800be4f6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(void)
0x1800be4fb  test    al, al
0x1800be4fd  jz      short loc_1800BE518
0x1800be4ff  call    ?get@?$static_lazy@VFidoPluginProvider@@@details@wil@@QEAAPEAVFidoPluginProvider@@P6AXXZ@Z; wil::details::static_lazy<FidoPluginProvider>::get(void (*)(void))
0x1800be504  mov     rcx, [rax+10h]
0x1800be508  mov     eax, [rcx]
0x1800be50a  cmp     eax, 3
0x1800be50d  jbe     short loc_1800BE548
0x1800be50f  lea     rdx, unk_180189FF7
0x1800be516  jmp     short loc_1800BE531
0x1800be518  mov     eax, cs:dword_1801AB110
0x1800be51e  cmp     eax, 3
0x1800be521  jbe     short loc_1800BE548
0x1800be523  lea     rdx, unk_18018A056
0x1800be52a  lea     rcx, dword_1801AB110
0x1800be531  lea     rax, [rsp+318h+var_2E8]
0x1800be536  mov     [rsp+318h+var_2F8], rax; int
0x1800be53b  mov     [rsp+318h+var_2E8], 80090036h
0x1800be543  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800be548  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl(void)'::`2'::impl
0x1800be54f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x1800be554  test    al, al
0x1800be556  jz      short loc_1800BE597
0x1800be558  mov     rcx, [rsp+318h]; this
0x1800be560  mov     r9d, 80090036h; char *
0x1800be566  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800be56d  mov     edx, 0CA1h; void *
0x1800be572  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be577  nop
0x1800be578  lea     rcx, [rsp+318h+var_2C8]
0x1800be57d  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginPerformUVTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>(void)
0x1800be582  nop
0x1800be583  lea     rcx, [rsp+318h+var_2D8]
0x1800be588  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginPerformUVTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>(void)
0x1800be58d  mov     eax, 80090036h
0x1800be592  jmp     loc_1800BE866
0x1800be597  lea     rcx, [rsp+318h+var_2C8]
0x1800be59c  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginPerformUVTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>(void)
0x1800be5a1  nop
0x1800be5a2  lea     rcx, [rsp+318h+var_2D8]
0x1800be5a7  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginPerformUVTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>(void)
0x1800be5ac  mov     eax, 80090036h
0x1800be5b1  jmp     loc_1800BE866
0x1800be5b6  cmp     ebx, 80073D54h
0x1800be5bc  jnz     loc_1800BE685
0x1800be5c2  mov     rcx, r15
0x1800be5c5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(void)
0x1800be5ca  test    al, al
0x1800be5cc  jz      short loc_1800BE5E7
0x1800be5ce  call    ?get@?$static_lazy@VFidoPluginProvider@@@details@wil@@QEAAPEAVFidoPluginProvider@@P6AXXZ@Z; wil::details::static_lazy<FidoPluginProvider>::get(void (*)(void))
0x1800be5d3  mov     rcx, [rax+10h]
0x1800be5d7  mov     eax, [rcx]
0x1800be5d9  cmp     eax, 3
0x1800be5dc  jbe     short loc_1800BE617
0x1800be5de  lea     rdx, unk_180189F31
0x1800be5e5  jmp     short loc_1800BE600
0x1800be5e7  mov     eax, cs:dword_1801AB110
0x1800be5ed  cmp     eax, 3
0x1800be5f0  jbe     short loc_1800BE617
0x1800be5f2  lea     rdx, unk_180189F90
0x1800be5f9  lea     rcx, dword_1801AB110
0x1800be600  lea     rax, [rsp+318h+var_2E8]
0x1800be605  mov     [rsp+318h+var_2F8], rax; int
0x1800be60a  mov     [rsp+318h+var_2E8], 80070005h
0x1800be612  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800be617  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl(void)'::`2'::impl
0x1800be61e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x1800be623  test    al, al
0x1800be625  jz      short loc_1800BE666
0x1800be627  mov     rcx, [rsp+318h]; this
0x1800be62f  mov     r9d, 80070005h; char *
0x1800be635  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800be63c  mov     edx, 0CB8h; void *
0x1800be641  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be646  nop
0x1800be647  lea     rcx, [rsp+318h+var_2C8]
0x1800be64c  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginPerformUVTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>(void)
0x1800be651  nop
0x1800be652  lea     rcx, [rsp+318h+var_2D8]
0x1800be657  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginPerformUVTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>(void)
0x1800be65c  mov     eax, 80070005h
0x1800be661  jmp     loc_1800BE866
0x1800be666  lea     rcx, [rsp+318h+var_2C8]
0x1800be66b  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginPerformUVTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>(void)
0x1800be670  nop
0x1800be671  lea     rcx, [rsp+318h+var_2D8]
0x1800be676  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginPerformUVTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>(void)
0x1800be67b  mov     eax, 80070005h
0x1800be680  jmp     loc_1800BE866
0x1800be685  test    ebx, ebx
0x1800be687  jns     loc_1800BE717
0x1800be68d  mov     rcx, r15
0x1800be690  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(void)
0x1800be695  test    al, al
0x1800be697  jz      short loc_1800BE6B2
0x1800be699  call    ?get@?$static_lazy@VFidoPluginProvider@@@details@wil@@QEAAPEAVFidoPluginProvider@@P6AXXZ@Z; wil::details::static_lazy<FidoPluginProvider>::get(void (*)(void))
0x1800be69e  mov     rcx, [rax+10h]
0x1800be6a2  mov     eax, [rcx]
0x1800be6a4  cmp     eax, 3
0x1800be6a7  jbe     short loc_1800BE6DE
0x1800be6a9  lea     rdx, unk_180189E6B
0x1800be6b0  jmp     short loc_1800BE6CB
0x1800be6b2  mov     eax, cs:dword_1801AB110
0x1800be6b8  cmp     eax, 3
  ... truncated ...
```
