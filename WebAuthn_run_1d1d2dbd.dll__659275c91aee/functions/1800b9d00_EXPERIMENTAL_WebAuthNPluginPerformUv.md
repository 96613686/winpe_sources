# EXPERIMENTAL_WebAuthNPluginPerformUv

- ea: `0x1800b9d00`
- end: `0x1800ba32e`
- name: `EXPERIMENTAL_WebAuthNPluginPerformUv`
- size: `1582`
- prototype: ``
- caller_count: `0`
- callee_count: `25`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

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
- `0x180095468`
- `0x18009b6e4`
- `0x1800b1514`
- `0x1800b29c0`
- `0x1800b2ef8`
- `0x1800b30b4`
- `0x1800b35d8`
- `0x1800b4170`
- `0x1800b7d38`
- `0x1800b9d00`
- `0x18013c090`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ba246`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ba246`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x1800b9efb`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x1800b9efb`

## string_xrefs

- `0x1800b9d4e`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800ba21b`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800ba2e3`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800ba267`: `WebAuthNPluginPerformUVTest::reason::invalid_parameters`
- `0x1800b9e6a`: `WebAuthNPluginPerformUVTest::reason::remote_session`
- `0x1800b9f10`: `WebAuthNPluginPerformUVTest::reason::remote_session`
- `0x1800ba0a9`: `WebAuthNPluginPerformUVTest::reason::uv_get_count_failed`
- `0x1800ba078`: `WebAuthNPluginPerformUVTest::reason::uv_failed`
- `0x1800ba0da`: `WebAuthNPluginPerformUVTest::reason::uv_get_public_key_failed`

## pseudocode

```c
__int64 __fastcall EXPERIMENTAL_WebAuthNPluginPerformUv(__int64 *a1, LPVOID *a2)
{
  __int64 v4; // rdx
  int v5; // ebx
  int v6; // r8d
  int v7; // r9d
  _DWORD *v8; // rcx
  int v9; // r8d
  int v10; // r9d
  const char *v11; // rdx
  const char *v12; // rax
  int v13; // r8d
  int v14; // r9d
  int *v15; // rcx
  void *v16; // rdx
  __int64 v17; // rdx
  const char *v18; // rax
  int v19; // r8d
  int v20; // r9d
  int *v21; // rcx
  void *v22; // rdx
  int v23; // ebx
  __int128 v24; // xmm0
  unsigned __int8 **v25; // r8
  unsigned int *v26; // r9
  const char *v27; // rdx
  unsigned int v28; // eax
  char v29; // r9
  const char *v30; // rdx
  unsigned int v31; // eax
  char v32; // r9
  const char *v33; // rdx
  unsigned int v34; // eax
  char v35; // r9
  int v36; // r8d
  int v37; // r9d
  int *v38; // rcx
  void *v39; // rdx
  int v40; // r8d
  int v41; // r9d
  int *v42; // rcx
  void *v43; // rdx
  void *v44; // rcx
  const char *v45; // rax
  int v46; // r8d
  int v47; // r9d
  int *v48; // rcx
  void *v49; // rdx
  int v51; // [rsp+20h] [rbp-E0h]
  int v52; // [rsp+20h] [rbp-E0h]
  _BYTE v53[8]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v54; // [rsp+38h] [rbp-C8h] BYREF
  int v55[4]; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID pv[2]; // [rsp+50h] [rbp-B0h] BYREF
  struct _GUID v57; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v58[64]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v59[344]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v60; // [rsp+208h] [rbp+108h]
  int v61; // [rsp+210h] [rbp+110h]
  __int128 v62; // [rsp+214h] [rbp+114h]
  __int64 v63; // [rsp+228h] [rbp+128h]
  __int64 v64; // [rsp+230h] [rbp+130h]
  wil::details::in1diag3 *retaddr; // [rsp+328h] [rbp+228h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::GetImpl'::`2'::impl) )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
    {
      v4 = 1886;
      goto LABEL_3;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl) )
    {
      v8 = *(_DWORD **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
      if ( *v8 > 4u )
      {
        *(_QWORD *)v55 = a1[4];
        *(_QWORD *)&v57.Data1 = a1[3];
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          (_DWORD)v8,
          (unsigned int)&unk_18018AC65,
          v9,
          v10,
          (__int64)&v57,
          (__int64)v55);
      }
    }
    else if ( (unsigned int)dword_1801AB110 > 4 )
    {
      *(_QWORD *)&v57.Data1 = a1[4];
      *(_QWORD *)v55 = a1[3];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (unsigned int)&dword_1801AB110,
        (unsigned int)&unk_18018ACB8,
        v6,
        v7,
        (__int64)v55,
        (__int64)&v57);
    }
    v54 = 0;
    tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::start_and_watch_errors(
      &v54,
      v58);
    v53[0] = 0;
    memset_0(v59, 0, 0x238u);
    *a2 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
    {
      if ( ShouldSendRequestToRemoteSession(0) )
      {
        v12 = tip2::details::reason_string((tip2::details *)"WebAuthNPluginPerformUVTest::reason::remote_session", v11);
        tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(
          &v54,
          2,
          v12);
        v5 = -2146893783;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl) )
        {
          v15 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
          if ( (unsigned int)*v15 > 3 )
          {
            v16 = &unk_18018ABB7;
LABEL_18:
            v55[0] = -2146893783;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
              (_DWORD)v15,
              (_DWORD)v16,
              v13,
              v14,
              (__int64)v55);
          }
        }
        else if ( (unsigned int)dword_1801AB110 > 3 )
        {
          v16 = &unk_18018AC0A;
          v15 = &dword_1801AB110;
          goto LABEL_18;
        }
        v17 = 1930;
LABEL_70:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v17,
          (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
          (const char *)(unsigned int)v5,
          v51);
        goto LABEL_71;
      }
LABEL_30:
      if ( a1 && *a1 && a1[1] )
      {
        v23 = *((_DWORD *)a1 + 4);
        *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::operator->(
                                 &v54,
                                 &v57)
                  + 272LL) = v23;
        tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>(&v57);
        v24 = *(_OWORD *)a1[1];
        v60 = *a1;
        v61 = *((_DWORD *)a1 + 4);
        v63 = a1[3];
        v64 = a1[4];
        v62 = v24;
        wil::make_unique_cotaskmem<_EXPERIMENTAL_WEBAUTHN_PLUGIN_PERFORM_UV_RESPONSE,>(pv);
        v57 = *(struct _GUID *)tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::test_id(
                                 &v54,
                                 v55);
        v5 = I_EncodeAndSendRpcRequest(0x6Du, &v57, (struct _CTAPCBOR_RPC_REQUEST *)v59, v26, v25);
        if ( v54 && (unsigned __int8)tip2::details::shared_data<1,0,0>::is_running(v54 + 8) )
        {
          if ( v5 < 0 )
          {
            v28 = (unsigned int)tip2::details::reason_string(
                                  (tip2::details *)"WebAuthNPluginPerformUVTest::reason::uv_failed",
                                  v27);
            tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::set_flag_value_if<long>(
              (unsigned int)&v54,
              6,
              v28,
              v5,
              v29);
            v31 = (unsigned int)tip2::details::reason_string(
                                  (tip2::details *)"WebAuthNPluginPerformUVTest::reason::uv_get_count_failed",
                                  v30);
            tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::set_flag_value_if<long>(
              (unsigned int)&v54,
              7,
              v31,
              v5,
              v32);
            v34 = (unsigned int)tip2::details::reason_string(
                                  (tip2::details *)"WebAuthNPluginPerformUVTest::reason::uv_get_public_key_failed",
                                  v33);
            tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::set_flag_value_if<long>(
              (unsigned int)&v54,
              8,
              v34,
              v5,
              v35);
          }
          tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::complete(&v54);
        }
        if ( v5 == -2147023673 )
        {
          v5 = -2146893770;
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl) )
          {
            v38 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
            if ( (unsigned int)*v38 <= 3 )
              goto LABEL_60;
            v39 = &unk_18018A98F;
            goto LABEL_45;
          }
          if ( (unsigned int)dword_1801AB110 <= 3 )
            goto LABEL_60;
          v39 = &unk_18018A9ED;
          goto LABEL_44;
        }
        if ( v5 == -2147009196 )
        {
          v5 = -2147024891;
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl) )
          {
            v38 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
            if ( (unsigned int)*v38 > 3 )
            {
              v39 = &unk_18018A8CB;
              goto LABEL_45;
            }
          }
          else if ( (unsigned int)dword_1801AB110 > 3 )
          {
            v39 = &unk_18018A929;
LABEL_44:
            v38 = &dword_1801AB110;
LABEL_45:
            v55[0] = v5;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
              (_DWORD)v38,
              (_DWORD)v39,
              v36,
              v37,
              (__int64)v55);
          }
LABEL_60:
          v44 = pv[0];
          pv[0] = 0;
          if ( v44 )
            CoTaskMemFree(v44);
          goto LABEL_71;
        }
        if ( v5 >= 0 )
        {
          *a2 = pv[0];
          pv[0] = 0;
LABEL_71:
          tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>(v58);
          wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>(&v54);
          return (unsigned int)v5;
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl) )
        {
          v42 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
          if ( (unsigned int)*v42 > 3 )
          {
            v43 = &unk_18018A807;
LABEL_58:
            v55[0] = v5;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
              (_DWORD)v42,
              (_DWORD)v43,
              v40,
              v41,
              (__int64)v55);
          }
        }
        else if ( (unsigned int)dword_1801AB110 > 3 )
        {
          v43 = &unk_18018A865;
          v42 = &dword_1801AB110;
          goto LABEL_58;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x7F8,
          (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
          (const char *)(unsigned int)v5,
          v52);
        goto LABEL_60;
      }
      v45 = tip2::details::reason_string(
              (tip2::details *)"WebAuthNPluginPerformUVTest::reason::invalid_parameters",
              v11);
      tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(
        &v54,
        9,
        v45);
      v5 = -2146893785;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl) )
      {
        v48 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
        if ( (unsigned int)*v48 > 3 )
        {
          v49 = &unk_18018AA53;
LABEL_68:
          v55[0] = -2146893785;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (_DWORD)v48,
            (_DWORD)v49,
            v46,
            v47,
            (__int64)v55);
        }
      }
      else if ( (unsigned int)dword_1801AB110 > 3 )
      {
        v49 = &unk_18018AAAA;
        v48 = &dword_1801AB110;
        goto LABEL_68;
      }
      v17 = 1971;
      goto LABEL_70;
    }
    if ( !(unsigned __int8)IsWinStationIsSessionRemoteablePresent()
      || !(unsigned __int8)WinStationIsSessionRemoteable(0, 0xFFFFFFFFLL, v53)
      || !v53[0] )
    {
      goto LABEL_30;
    }
    v18 = tip2::details::reason_string((tip2::details *)"WebAuthNPluginPerformUVTest::reason::remote_session", v11);
    tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(
      &v54,
      2,
      v18);
    v5 = -2146893783;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl) )
    {
      v21 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
      if ( (unsigned int)*v21 > 3 )
      {
        v22 = &unk_18018AB09;
LABEL_28:
        v55[0] = -2146893783;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (_DWORD)v21,
          (_DWORD)v22,
          v19,
          v20,
          (__int64)v55);
      }
    }
    else if ( (unsigned int)dword_1801AB110 > 3 )
    {
      v22 = &unk_18018AB5C;
      v21 = &dword_1801AB110;
      goto LABEL_28;
    }
    v17 = 1951;
    goto LABEL_70;
  }
  v4 = 1885;
LABEL_3:
  v5 = -2147467263;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v4,
    (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
    (const char *)0x80004001LL,
    v51);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800b9d00  mov     [rsp-8+arg_10], rbx
0x1800b9d05  push    rbp
0x1800b9d06  push    rsi
0x1800b9d07  push    rdi
0x1800b9d08  push    r12
0x1800b9d0a  push    r15
0x1800b9d0c  lea     rbp, [rsp-200h]
0x1800b9d14  sub     rsp, 300h
0x1800b9d1b  mov     rax, cs:__security_cookie
0x1800b9d22  xor     rax, rsp
0x1800b9d25  mov     [rbp+220h+var_30], rax
0x1800b9d2c  mov     rsi, rdx
0x1800b9d2f  mov     rdi, rcx
0x1800b9d32  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PasskeyPluginAuthenticators@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PasskeyPluginAuthenticators@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators> `wil::Feature<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::GetImpl(void)'::`2'::impl
0x1800b9d39  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PasskeyPluginAuthenticators@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::__private_IsEnabled(void)
0x1800b9d3e  test    al, al
0x1800b9d40  jnz     short loc_1800B9D67
0x1800b9d42  mov     edx, 75Dh; void *
0x1800b9d47  mov     rcx, [rbp+228h]; this
0x1800b9d4e  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800b9d55  mov     ebx, 80004001h
0x1800b9d5a  mov     r9d, ebx; char *
0x1800b9d5d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b9d62  jmp     loc_1800BA306
0x1800b9d67  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl(void)'::`2'::impl
0x1800b9d6e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x1800b9d73  test    al, al
0x1800b9d75  jz      short loc_1800B9D7E
0x1800b9d77  mov     edx, 75Eh
0x1800b9d7c  jmp     short loc_1800B9D47
0x1800b9d7e  lea     r12, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2> `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl(void)'::`2'::impl
0x1800b9d85  mov     rcx, r12
0x1800b9d88  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(void)
0x1800b9d8d  lea     r15, dword_1801AB110
0x1800b9d94  test    al, al
0x1800b9d96  jz      short loc_1800B9DD2
0x1800b9d98  call    ?get@?$static_lazy@VFidoPluginProvider@@@details@wil@@QEAAPEAVFidoPluginProvider@@P6AXXZ@Z; wil::details::static_lazy<FidoPluginProvider>::get(void (*)(void))
0x1800b9d9d  mov     rcx, [rax+10h]
0x1800b9da1  mov     eax, [rcx]
0x1800b9da3  cmp     eax, 4
0x1800b9da6  jbe     short loc_1800B9E12
0x1800b9da8  mov     rax, [rdi+20h]
0x1800b9dac  lea     rdx, unk_18018AC65
0x1800b9db3  mov     qword ptr [rsp+320h+var_2E0], rax
0x1800b9db8  mov     rax, [rdi+18h]
0x1800b9dbc  mov     qword ptr [rsp+320h+var_2C0.Data1], rax
0x1800b9dc1  lea     rax, [rsp+320h+var_2E0]
0x1800b9dc6  mov     [rsp+320h+var_2F8], rax
0x1800b9dcb  lea     rax, [rsp+320h+var_2C0]
0x1800b9dd0  jmp     short loc_1800B9E08
0x1800b9dd2  mov     eax, cs:dword_1801AB110
0x1800b9dd8  cmp     eax, 4
0x1800b9ddb  jbe     short loc_1800B9E12
0x1800b9ddd  mov     rax, [rdi+20h]
0x1800b9de1  lea     rdx, unk_18018ACB8
0x1800b9de8  mov     qword ptr [rsp+320h+var_2C0.Data1], rax
0x1800b9ded  mov     rcx, r15
0x1800b9df0  mov     rax, [rdi+18h]
0x1800b9df4  mov     qword ptr [rsp+320h+var_2E0], rax
0x1800b9df9  lea     rax, [rsp+320h+var_2C0]
0x1800b9dfe  mov     [rsp+320h+var_2F8], rax
0x1800b9e03  lea     rax, [rsp+320h+var_2E0]
0x1800b9e08  mov     [rsp+320h+var_300], rax
0x1800b9e0d  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800b9e12  lea     rdx, [rsp+320h+var_2B0]
0x1800b9e17  mov     [rsp+320h+var_2E8], 0
0x1800b9e20  lea     rcx, [rsp+320h+var_2E8]
0x1800b9e25  call    ?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginPerformUVTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginPerformUVTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::start_and_watch_errors(void)
0x1800b9e2a  xor     edx, edx; Val
0x1800b9e2c  mov     [rsp+320h+var_2F0], 0
0x1800b9e31  mov     r8d, 238h; Size
0x1800b9e37  lea     rcx, [rbp+220h+var_270]; void *
0x1800b9e3b  call    memset_0
0x1800b9e40  mov     qword ptr [rsi], 0
0x1800b9e47  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl(void)'::`2'::impl
0x1800b9e4e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x1800b9e53  test    al, al
0x1800b9e55  jz      loc_1800B9EE4
0x1800b9e5b  xor     ecx, ecx; unsigned __int8 *
0x1800b9e5d  call    ?ShouldSendRequestToRemoteSession@@YA_NPEAE@Z; ShouldSendRequestToRemoteSession(uchar *)
0x1800b9e62  test    al, al
0x1800b9e64  jz      loc_1800B9F8A
0x1800b9e6a  lea     rcx, aWebauthnplugin_61; "WebAuthNPluginPerformUVTest::reason::re"...
0x1800b9e71  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800b9e76  mov     r8, rax
0x1800b9e79  lea     rcx, [rsp+320h+var_2E8]
0x1800b9e7e  mov     edx, 2
0x1800b9e83  call    ?complete_and_ignore@?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(ushort,char const *)
0x1800b9e88  mov     rcx, r12
0x1800b9e8b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(void)
0x1800b9e90  mov     ebx, 80090029h
0x1800b9e95  test    al, al
0x1800b9e97  jz      short loc_1800B9EB2
0x1800b9e99  call    ?get@?$static_lazy@VFidoPluginProvider@@@details@wil@@QEAAPEAVFidoPluginProvider@@P6AXXZ@Z; wil::details::static_lazy<FidoPluginProvider>::get(void (*)(void))
0x1800b9e9e  mov     rcx, [rax+10h]
0x1800b9ea2  mov     eax, [rcx]
0x1800b9ea4  cmp     eax, 3
0x1800b9ea7  jbe     short loc_1800B9EDA
0x1800b9ea9  lea     rdx, unk_18018ABB7
0x1800b9eb0  jmp     short loc_1800B9EC7
0x1800b9eb2  mov     eax, cs:dword_1801AB110
0x1800b9eb8  cmp     eax, 3
0x1800b9ebb  jbe     short loc_1800B9EDA
0x1800b9ebd  lea     rdx, unk_18018AC0A
0x1800b9ec4  mov     rcx, r15
0x1800b9ec7  lea     rax, [rsp+320h+var_2E0]
0x1800b9ecc  mov     [rsp+320h+var_300], rax
0x1800b9ed1  mov     [rsp+320h+var_2E0], ebx
0x1800b9ed5  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800b9eda  mov     edx, 78Ah
0x1800b9edf  jmp     loc_1800BA2DC
0x1800b9ee4  call    IsWinStationIsSessionRemoteablePresent
0x1800b9ee9  test    al, al
0x1800b9eeb  jz      loc_1800B9F8A
0x1800b9ef1  lea     r8, [rsp+320h+var_2F0]
0x1800b9ef6  or      edx, 0FFFFFFFFh
0x1800b9ef9  xor     ecx, ecx
0x1800b9efb  call    cs:__imp_WinStationIsSessionRemoteable
0x1800b9f01  test    al, al
0x1800b9f03  jz      loc_1800B9F8A
0x1800b9f09  cmp     [rsp+320h+var_2F0], 0
0x1800b9f0e  jz      short loc_1800B9F8A
0x1800b9f10  lea     rcx, aWebauthnplugin_61; "WebAuthNPluginPerformUVTest::reason::re"...
0x1800b9f17  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800b9f1c  mov     r8, rax
0x1800b9f1f  lea     rcx, [rsp+320h+var_2E8]
0x1800b9f24  mov     edx, 2
0x1800b9f29  call    ?complete_and_ignore@?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(ushort,char const *)
0x1800b9f2e  mov     rcx, r12
0x1800b9f31  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(void)
0x1800b9f36  mov     ebx, 80090029h
0x1800b9f3b  test    al, al
0x1800b9f3d  jz      short loc_1800B9F58
0x1800b9f3f  call    ?get@?$static_lazy@VFidoPluginProvider@@@details@wil@@QEAAPEAVFidoPluginProvider@@P6AXXZ@Z; wil::details::static_lazy<FidoPluginProvider>::get(void (*)(void))
0x1800b9f44  mov     rcx, [rax+10h]
0x1800b9f48  mov     eax, [rcx]
0x1800b9f4a  cmp     eax, 3
0x1800b9f4d  jbe     short loc_1800B9F80
0x1800b9f4f  lea     rdx, unk_18018AB09
0x1800b9f56  jmp     short loc_1800B9F6D
0x1800b9f58  mov     eax, cs:dword_1801AB110
0x1800b9f5e  cmp     eax, 3
0x1800b9f61  jbe     short loc_1800B9F80
0x1800b9f63  lea     rdx, unk_18018AB5C
0x1800b9f6a  mov     rcx, r15
0x1800b9f6d  lea     rax, [rsp+320h+var_2E0]
0x1800b9f72  mov     [rsp+320h+var_300], rax
0x1800b9f77  mov     [rsp+320h+var_2E0], ebx
0x1800b9f7b  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800b9f80  mov     edx, 79Fh
0x1800b9f85  jmp     loc_1800BA2DC
0x1800b9f8a  test    rdi, rdi
0x1800b9f8d  jz      loc_1800BA267
0x1800b9f93  cmp     qword ptr [rdi], 0
0x1800b9f97  jz      loc_1800BA267
0x1800b9f9d  cmp     qword ptr [rdi+8], 0
0x1800b9fa2  jz      loc_1800BA267
0x1800b9fa8  mov     ebx, [rdi+10h]
0x1800b9fab  lea     rdx, [rsp+320h+var_2C0]
0x1800b9fb0  lea     rcx, [rsp+320h+var_2E8]
0x1800b9fb5  call    ??C?$tip_test@V?$merged_data@U_tip_WebAuthNPluginPerformUVTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginPerformUVTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::operator->(void)
0x1800b9fba  mov     rcx, [rax]
0x1800b9fbd  mov     [rcx+110h], ebx
0x1800b9fc3  lea     rcx, [rsp+320h+var_2C0]
0x1800b9fc8  call    ??1?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginPerformUVTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>(void)
0x1800b9fcd  mov     rax, [rdi+8]
0x1800b9fd1  lea     rcx, [rsp+320h+pv]
0x1800b9fd6  movups  xmm0, xmmword ptr [rax]
0x1800b9fd9  mov     rax, [rdi]
0x1800b9fdc  mov     [rbp+220h+var_118], rax
0x1800b9fe3  mov     eax, [rdi+10h]
0x1800b9fe6  mov     [rbp+220h+var_110], eax
0x1800b9fec  mov     rax, [rdi+18h]
0x1800b9ff0  mov     [rbp+220h+var_F8], rax
0x1800b9ff7  mov     rax, [rdi+20h]
0x1800b9ffb  mov     [rbp+220h+var_F0], rax
0x1800ba002  movdqu  [rbp+220h+var_10C], xmm0
0x1800ba00a  call    ??$make_unique_cotaskmem@U_EXPERIMENTAL_WEBAUTHN_PLUGIN_PERFORM_UV_RESPONSE@@$$V@wil@@YA?AV?$unique_ptr@U_EXPERIMENTAL_WEBAUTHN_PLUGIN_PERFORM_UV_RESPONSE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@XZ; wil::make_unique_cotaskmem<_EXPERIMENTAL_WEBAUTHN_PLUGIN_PERFORM_UV_RESPONSE,>(void)
0x1800ba00f  mov     r9, [rsp+320h+pv]
0x1800ba014  lea     rdx, [rsp+320h+var_2E0]
0x1800ba019  lea     rcx, [rsp+320h+var_2E8]
0x1800ba01e  lea     r8, [r9+8]
0x1800ba022  call    ?test_id@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest@@U1@@details@tip2@@@tip2@@QEBA?AU_GUID@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::test_id(void)
0x1800ba027  mov     [rsp+320h+var_300], r8; unsigned __int8 **
0x1800ba02c  lea     rdx, [rsp+320h+var_2C0]; struct _GUID *
0x1800ba031  lea     r8, [rbp+220h+var_270]; struct _CTAPCBOR_RPC_REQUEST *
0x1800ba035  mov     ecx, 6Dh ; 'm'; unsigned int
0x1800ba03a  movups  xmm1, xmmword ptr [rax]
0x1800ba03d  movdqu  xmmword ptr [rsp+320h+var_2C0.Data1], xmm1
0x1800ba043  call    ?I_EncodeAndSendRpcRequest@@YAJKU_GUID@@AEAU_CTAPCBOR_RPC_REQUEST@@PEAKPEAPEAE@Z; I_EncodeAndSendRpcRequest(ulong,_GUID,_CTAPCBOR_RPC_REQUEST &,ulong *,uchar * *)
0x1800ba048  mov     rcx, [rsp+320h+var_2E8]
0x1800ba04d  mov     ebx, eax
0x1800ba04f  test    rcx, rcx
0x1800ba052  jz      loc_1800BA10E
0x1800ba058  add     rcx, 8
0x1800ba05c  call    ?is_running@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::is_running(void)
0x1800ba061  test    al, al
0x1800ba063  jz      loc_1800BA10E
0x1800ba069  test    ebx, ebx
0x1800ba06b  jns     loc_1800BA104
0x1800ba071  cmp     [rbp+220h+var_110], 1
0x1800ba078  lea     rcx, aWebauthnplugin_129; "WebAuthNPluginPerformUVTest::reason::uv"...
0x1800ba07f  setz    r9b
0x1800ba083  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800ba088  mov     byte ptr [rsp+320h+var_300], r9b
0x1800ba08d  lea     rcx, [rsp+320h+var_2E8]
0x1800ba092  mov     r8, rax
0x1800ba095  mov     edx, 6
0x1800ba09a  mov     r9d, ebx
0x1800ba09d  call    ??$set_flag_value_if@J@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginPerformUVTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBDJ_N@Z; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::set_flag_value_if<long>(ushort,char const *,long,bool)
0x1800ba0a2  cmp     [rbp+220h+var_110], 2
0x1800ba0a9  lea     rcx, aWebauthnplugin_78; "WebAuthNPluginPerformUVTest::reason::uv"...
0x1800ba0b0  setz    r9b
0x1800ba0b4  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800ba0b9  mov     byte ptr [rsp+320h+var_300], r9b
0x1800ba0be  lea     rcx, [rsp+320h+var_2E8]
0x1800ba0c3  mov     r8, rax
0x1800ba0c6  mov     edx, 7
0x1800ba0cb  mov     r9d, ebx
0x1800ba0ce  call    ??$set_flag_value_if@J@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginPerformUVTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBDJ_N@Z; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::set_flag_value_if<long>(ushort,char const *,long,bool)
0x1800ba0d3  cmp     [rbp+220h+var_110], 3
0x1800ba0da  lea     rcx, aWebauthnplugin_92; "WebAuthNPluginPerformUVTest::reason::uv"...
0x1800ba0e1  setz    r9b
0x1800ba0e5  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800ba0ea  mov     byte ptr [rsp+320h+var_300], r9b
0x1800ba0ef  lea     rcx, [rsp+320h+var_2E8]
0x1800ba0f4  mov     r8, rax
0x1800ba0f7  mov     edx, 8
0x1800ba0fc  mov     r9d, ebx
0x1800ba0ff  call    ??$set_flag_value_if@J@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginPerformUVTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBDJ_N@Z; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::set_flag_value_if<long>(ushort,char const *,long,bool)
0x1800ba104  lea     rcx, [rsp+320h+var_2E8]
0x1800ba109  call    ?complete@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginCallbackTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::complete(void)
0x1800ba10e  cmp     ebx, 800704C7h
0x1800ba114  jnz     short loc_1800BA175
0x1800ba116  mov     rcx, r12
0x1800ba119  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(void)
0x1800ba11e  mov     ebx, 80090036h
0x1800ba123  test    al, al
0x1800ba125  jz      short loc_1800BA144
0x1800ba127  call    ?get@?$static_lazy@VFidoPluginProvider@@@details@wil@@QEAAPEAVFidoPluginProvider@@P6AXXZ@Z; wil::details::static_lazy<FidoPluginProvider>::get(void (*)(void))
0x1800ba12c  mov     rcx, [rax+10h]
0x1800ba130  mov     eax, [rcx]
0x1800ba132  cmp     eax, 3
0x1800ba135  jbe     loc_1800BA22F
0x1800ba13b  lea     rdx, unk_18018A98F
0x1800ba142  jmp     short loc_1800BA15D
0x1800ba144  mov     eax, cs:dword_1801AB110
0x1800ba14a  cmp     eax, 3
0x1800ba14d  jbe     loc_1800BA22F
0x1800ba153  lea     rdx, unk_18018A9ED
0x1800ba15a  mov     rcx, r15
0x1800ba15d  lea     rax, [rsp+320h+var_2E0]
0x1800ba162  mov     [rsp+320h+var_300], rax
0x1800ba167  mov     [rsp+320h+var_2E0], ebx
0x1800ba16b  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800ba170  jmp     loc_1800BA22F
0x1800ba175  cmp     ebx, 80073D54h
0x1800ba17b  jnz     short loc_1800BA1BF
0x1800ba17d  mov     rcx, r12
0x1800ba180  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(void)
0x1800ba185  mov     ebx, 80070005h
0x1800ba18a  test    al, al
0x1800ba18c  jz      short loc_1800BA1AB
0x1800ba18e  call    ?get@?$static_lazy@VFidoPluginProvider@@@details@wil@@QEAAPEAVFidoPluginProvider@@P6AXXZ@Z; wil::details::static_lazy<FidoPluginProvider>::get(void (*)(void))
0x1800ba193  mov     rcx, [rax+10h]
0x1800ba197  mov     eax, [rcx]
0x1800ba199  cmp     eax, 3
0x1800ba19c  jbe     loc_1800BA22F
0x1800ba1a2  lea     rdx, unk_18018A8CB
0x1800ba1a9  jmp     short loc_1800BA15D
0x1800ba1ab  mov     eax, cs:dword_1801AB110
0x1800ba1b1  cmp     eax, 3
0x1800ba1b4  jbe     short loc_1800BA22F
0x1800ba1b6  lea     rdx, unk_18018A929
0x1800ba1bd  jmp     short loc_1800BA15A
0x1800ba1bf  test    ebx, ebx
0x1800ba1c1  jns     loc_1800BA251
0x1800ba1c7  mov     rcx, r12
0x1800ba1ca  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(void)
0x1800ba1cf  test    al, al
0x1800ba1d1  jz      short loc_1800BA1EC
0x1800ba1d3  call    ?get@?$static_lazy@VFidoPluginProvider@@@details@wil@@QEAAPEAVFidoPluginProvider@@P6AXXZ@Z; wil::details::static_lazy<FidoPluginProvider>::get(void (*)(void))
0x1800ba1d8  mov     rcx, [rax+10h]
0x1800ba1dc  mov     eax, [rcx]
0x1800ba1de  cmp     eax, 3
0x1800ba1e1  jbe     short loc_1800BA214
0x1800ba1e3  lea     rdx, unk_18018A807
0x1800ba1ea  jmp     short loc_1800BA201
0x1800ba1ec  mov     eax, cs:dword_1801AB110
0x1800ba1f2  cmp     eax, 3
0x1800ba1f5  jbe     short loc_1800BA214
0x1800ba1f7  lea     rdx, unk_18018A865
0x1800ba1fe  mov     rcx, r15
0x1800ba201  lea     rax, [rsp+320h+var_2E0]
0x1800ba206  mov     [rsp+320h+var_300], rax; int
0x1800ba20b  mov     [rsp+320h+var_2E0], ebx
0x1800ba20f  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800ba214  mov     rcx, [rbp+228h]; this
0x1800ba21b  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800ba222  mov     r9d, ebx; char *
  ... truncated ...
```
