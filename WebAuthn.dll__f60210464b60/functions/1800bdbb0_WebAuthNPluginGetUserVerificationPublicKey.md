# WebAuthNPluginGetUserVerificationPublicKey

- ea: `0x1800bdbb0`
- end: `0x1800be13f`
- name: `WebAuthNPluginGetUserVerificationPublicKey`
- size: `1423`
- prototype: `__int64 __fastcall(GUID *rguid)`
- caller_count: `0`
- callee_count: `22`
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
- `0x180095468`
- `0x1800b134c`
- `0x1800b29c0`
- `0x1800b30b4`
- `0x1800b4170`
- `0x1800b7d38`
- `0x1800bdbb0`
- `0x18013c090`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800bdedf`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800bdedf`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x1800bddf0`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x1800bddf0`

## string_xrefs

- `0x1800bdbfb`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800bdc26`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800bdc54`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800bdda8`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800bde8a`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800bdf6e`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800be0c4`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800bdeed`: `WebAuthNPluginPerformUVTest::reason::invalid_parameters`
- `0x1800bdd27`: `WebAuthNPluginPerformUVTest::reason::remote_session`
- `0x1800bde09`: `WebAuthNPluginPerformUVTest::reason::remote_session`
- `0x1800be035`: `WebAuthNPluginPerformUVTest::reason::uv_get_public_key_failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall WebAuthNPluginGetUserVerificationPublicKey(GUID *rguid, unsigned int *a2, unsigned __int8 **a3)
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
  __int16 *v17; // rdx
  const char *v18; // rdx
  const char *v19; // rax
  __int64 v20; // rdx
  __int64 v21; // r8
  int v22; // r8d
  int v23; // r9d
  int *v24; // rcx
  char *v25; // rdx
  const char *v26; // rdx
  const char *v27; // rax
  __int64 v28; // rdx
  __int64 v29; // r8
  int v30; // r8d
  int v31; // r9d
  int *v32; // rcx
  __int16 *v33; // rdx
  const char *v34; // rdx
  signed int v35; // ebx
  __int64 v36; // r8
  const char *v37; // rax
  int v38; // r8d
  int v39; // r9d
  int *v40; // rcx
  __int16 *v41; // rdx
  int v42; // [rsp+20h] [rbp-348h]
  int v43; // [rsp+20h] [rbp-348h]
  unsigned int v44; // [rsp+30h] [rbp-338h] BYREF
  _BYTE v45[4]; // [rsp+34h] [rbp-334h] BYREF
  _QWORD v46[2]; // [rsp+38h] [rbp-330h] BYREF
  unsigned __int8 *v47; // [rsp+48h] [rbp-320h] BYREF
  struct _GUID v48; // [rsp+50h] [rbp-318h] BYREF
  _BYTE v49[64]; // [rsp+60h] [rbp-308h] BYREF
  _BYTE v50[16]; // [rsp+A0h] [rbp-2C8h] BYREF
  _BYTE v51[256]; // [rsp+B0h] [rbp-2B8h] BYREF
  OLECHAR *v52; // [rsp+1B0h] [rbp-1B8h]
  int v53; // [rsp+210h] [rbp-158h]
  OLECHAR sz[40]; // [rsp+2F0h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+368h] [rbp+0h]

  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::__private_IsEnabled(
                           `wil::Feature<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::GetImpl'::`2'::impl,
                           a2,
                           a3) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDDA,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
      (const char *)0x80004001LL,
      v42);
    return 2147500033LL;
  }
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDDB,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
      (const char *)0x80090027LL,
      v42);
    return 2148073511LL;
  }
  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDDC,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
      (const char *)0x80090027LL,
      v42);
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
        &dword_1801899D4,
        0);
  }
  else if ( (unsigned int)dword_1801AB110 > 4 )
  {
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_1801AB110,
      word_180189A12,
      0);
  }
  v46[0] = 0;
  tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::start_and_watch_errors(
    v46,
    v49);
  v45[0] = 0;
  memset_0(v51, 0, 0x238u);
  *a2 = 0;
  *a3 = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
  {
    if ( !(unsigned __int8)IsWinStationIsSessionRemoteablePresent()
      || !(unsigned __int8)WinStationIsSessionRemoteable(0, 0xFFFFFFFFLL, v45)
      || !v45[0] )
    {
      goto LABEL_31;
    }
    v19 = tip2::details::reason_string((tip2::details *)"WebAuthNPluginPerformUVTest::reason::remote_session", v18);
    tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(
      v46,
      2,
      v19);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(
                            `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl,
                            v20,
                            v21) )
    {
      v24 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
      if ( (unsigned int)*v24 > 3 )
      {
        v25 = (char *)&unk_180189860;
LABEL_29:
        v44 = -2146893783;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (_DWORD)v24,
          (_DWORD)v25,
          v22,
          v23,
          (__int64)&v44);
      }
    }
    else if ( (unsigned int)dword_1801AB110 > 3 )
    {
      v25 = byte_1801898B9;
      v24 = &dword_1801AB110;
      goto LABEL_29;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE1A,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
      (const char *)0x80090029LL,
      v42);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>(v49);
    wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>(v46);
    return 2148073513LL;
  }
  if ( ShouldSendRequestToRemoteSession(0) )
  {
    v11 = tip2::details::reason_string((tip2::details *)"WebAuthNPluginPerformUVTest::reason::remote_session", v10);
    tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(
      v46,
      2,
      v11);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(
                            `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl,
                            v12,
                            v13) )
    {
      v16 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
      if ( (unsigned int)*v16 > 3 )
      {
        v17 = word_18018991A;
LABEL_19:
        v44 = -2146893783;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (_DWORD)v16,
          (_DWORD)v17,
          v14,
          v15,
          (__int64)&v44);
      }
    }
    else if ( (unsigned int)dword_1801AB110 > 3 )
    {
      v17 = (__int16 *)byte_180189973;
      v16 = &dword_1801AB110;
      goto LABEL_19;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE05,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
      (const char *)0x80090029LL,
      v42);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>(v49);
    wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>(v46);
    return 2148073513LL;
  }
LABEL_31:
  memset_0(sz, 0, sizeof(sz));
  if ( !StringFromGUID2(rguid, sz, 40) )
  {
    v27 = tip2::details::reason_string((tip2::details *)"WebAuthNPluginPerformUVTest::reason::invalid_parameters", v26);
    tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(
      v46,
      9,
      v27);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(
                            `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl,
                            v28,
                            v29) )
    {
      v32 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
      if ( (unsigned int)*v32 > 3 )
      {
        v33 = &word_18018979E;
LABEL_37:
        v44 = -2146893785;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (_DWORD)v32,
          (_DWORD)v33,
          v30,
          v31,
          (__int64)&v44);
      }
    }
    else if ( (unsigned int)dword_1801AB110 > 3 )
    {
      v33 = (__int16 *)byte_1801897FB;
      v32 = &dword_1801AB110;
      goto LABEL_37;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE2F,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
      (const char *)0x80090027LL,
      v42);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>(v49);
    wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>(v46);
    return 2148073511LL;
  }
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl);
  v53 = 3;
  v52 = sz;
  v44 = 0;
  v47 = 0;
  v48 = *(struct _GUID *)tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::test_id(
                           v46,
                           v50);
  v35 = I_EncodeAndSendRpcRequest(0x6Du, &v48, (struct _CTAPCBOR_RPC_REQUEST *)v51, &v44, &v47);
  if ( v46[0] && (unsigned __int8)tip2::details::shared_data<1,0,0>::is_running(v46[0] + 8LL) )
  {
    if ( v35 < 0 )
    {
      v37 = tip2::details::reason_string(
              (tip2::details *)"WebAuthNPluginPerformUVTest::reason::uv_get_public_key_failed",
              v34);
      tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::set_flag_value<long>(
        v46,
        8,
        v37,
        (unsigned int)v35);
    }
    tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::complete(v46);
  }
  if ( v35 < 0 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(
                            `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl,
                            v34,
                            v36) )
    {
      v40 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
      if ( (unsigned int)*v40 > 3 )
      {
        v41 = &word_1801896CE;
LABEL_50:
        v44 = v35;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (_DWORD)v40,
          (_DWORD)v41,
          v38,
          v39,
          (__int64)&v44);
      }
    }
    else if ( (unsigned int)dword_1801AB110 > 3 )
    {
      v41 = word_180189732;
      v40 = &dword_1801AB110;
      goto LABEL_50;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE58,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
      (const char *)(unsigned int)v35,
      v43);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>(v49);
    wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>(v46);
    return (unsigned int)v35;
  }
  *a2 = v44;
  *a3 = v47;
  tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>(v49);
  wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>(v46);
  return 0;
}

```

## disassembly

```asm
0x1800bdbb0  mov     [rsp+arg_18], rbx
0x1800bdbb5  push    rsi
0x1800bdbb6  push    rdi
0x1800bdbb7  push    r15
0x1800bdbb9  sub     rsp, 350h
0x1800bdbc0  mov     rax, cs:__security_cookie
0x1800bdbc7  xor     rax, rsp
0x1800bdbca  mov     [rsp+368h+var_28], rax
0x1800bdbd2  mov     rsi, r8
0x1800bdbd5  mov     rdi, rdx
0x1800bdbd8  mov     rbx, rcx
0x1800bdbdb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PasskeyPluginAuthenticators@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PasskeyPluginAuthenticators@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators> `wil::Feature<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::GetImpl(void)'::`2'::impl
0x1800bdbe2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PasskeyPluginAuthenticators@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::__private_IsEnabled(void)
0x1800bdbe7  test    al, al
0x1800bdbe9  jnz     short loc_1800BDC13
0x1800bdbeb  mov     rcx, [rsp+368h]; this
0x1800bdbf3  mov     ebx, 80004001h
0x1800bdbf8  mov     r9d, ebx; char *
0x1800bdbfb  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800bdc02  mov     edx, 0DDAh; void *
0x1800bdc07  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bdc0c  mov     eax, ebx
0x1800bdc0e  jmp     loc_1800BE11A
0x1800bdc13  test    rdi, rdi
0x1800bdc16  jnz     short loc_1800BDC41
0x1800bdc18  mov     rcx, [rsp+368h]; this
0x1800bdc20  mov     r9d, 80090027h; char *
0x1800bdc26  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800bdc2d  mov     edx, 0DDBh; void *
0x1800bdc32  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bdc37  mov     eax, 80090027h
0x1800bdc3c  jmp     loc_1800BE11A
0x1800bdc41  test    rsi, rsi
0x1800bdc44  jnz     short loc_1800BDC6F
0x1800bdc46  mov     rcx, [rsp+368h]; this
0x1800bdc4e  mov     r9d, 80090027h; char *
0x1800bdc54  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800bdc5b  mov     edx, 0DDCh; void *
0x1800bdc60  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bdc65  mov     eax, 80090027h
0x1800bdc6a  jmp     loc_1800BE11A
0x1800bdc6f  lea     r15, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2> `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl(void)'::`2'::impl
0x1800bdc76  mov     rcx, r15
0x1800bdc79  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(void)
0x1800bdc7e  test    al, al
0x1800bdc80  jz      short loc_1800BDCA3
0x1800bdc82  call    ?get@?$static_lazy@VFidoPluginProvider@@@details@wil@@QEAAPEAVFidoPluginProvider@@P6AXXZ@Z; wil::details::static_lazy<FidoPluginProvider>::get(void (*)(void))
0x1800bdc87  mov     rcx, [rax+10h]
0x1800bdc8b  mov     eax, [rcx]
0x1800bdc8d  cmp     eax, 4
0x1800bdc90  jbe     short loc_1800BDCC4
0x1800bdc92  xor     r8d, r8d
0x1800bdc95  lea     rdx, dword_1801899D4
0x1800bdc9c  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800bdca1  jmp     short loc_1800BDCC4
0x1800bdca3  mov     eax, cs:dword_1801AB110
0x1800bdca9  cmp     eax, 4
0x1800bdcac  jbe     short loc_1800BDCC4
0x1800bdcae  xor     r8d, r8d
0x1800bdcb1  lea     rdx, word_180189A12
0x1800bdcb8  lea     rcx, dword_1801AB110
0x1800bdcbf  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800bdcc4  mov     [rsp+368h+var_330], 0
0x1800bdccd  lea     rdx, [rsp+368h+var_308]
0x1800bdcd2  lea     rcx, [rsp+368h+var_330]
0x1800bdcd7  call    ?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginPerformUVTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginPerformUVTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::start_and_watch_errors(void)
0x1800bdcdc  nop
0x1800bdcdd  mov     [rsp+368h+var_334], 0
0x1800bdce2  xor     edx, edx; Val
0x1800bdce4  mov     r8d, 238h; Size
0x1800bdcea  lea     rcx, [rsp+368h+var_2B8]; void *
0x1800bdcf2  call    memset_0
0x1800bdcf7  mov     dword ptr [rdi], 0
0x1800bdcfd  mov     qword ptr [rsi], 0
0x1800bdd04  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl(void)'::`2'::impl
0x1800bdd0b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x1800bdd10  test    al, al
0x1800bdd12  jz      loc_1800BDDD9
0x1800bdd18  xor     ecx, ecx; unsigned __int8 *
0x1800bdd1a  call    ?ShouldSendRequestToRemoteSession@@YA_NPEAE@Z; ShouldSendRequestToRemoteSession(uchar *)
0x1800bdd1f  test    al, al
0x1800bdd21  jz      loc_1800BDEBB
0x1800bdd27  lea     rcx, aWebauthnplugin_61; "WebAuthNPluginPerformUVTest::reason::re"...
0x1800bdd2e  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800bdd33  mov     r8, rax
0x1800bdd36  mov     edx, 2
0x1800bdd3b  lea     rcx, [rsp+368h+var_330]
0x1800bdd40  call    ?complete_and_ignore@?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(ushort,char const *)
0x1800bdd45  mov     rcx, r15
0x1800bdd48  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(void)
0x1800bdd4d  test    al, al
0x1800bdd4f  jz      short loc_1800BDD6A
0x1800bdd51  call    ?get@?$static_lazy@VFidoPluginProvider@@@details@wil@@QEAAPEAVFidoPluginProvider@@P6AXXZ@Z; wil::details::static_lazy<FidoPluginProvider>::get(void (*)(void))
0x1800bdd56  mov     rcx, [rax+10h]
0x1800bdd5a  mov     eax, [rcx]
0x1800bdd5c  cmp     eax, 3
0x1800bdd5f  jbe     short loc_1800BDD9A
0x1800bdd61  lea     rdx, word_18018991A
0x1800bdd68  jmp     short loc_1800BDD83
0x1800bdd6a  mov     eax, cs:dword_1801AB110
0x1800bdd70  cmp     eax, 3
0x1800bdd73  jbe     short loc_1800BDD9A
0x1800bdd75  lea     rdx, byte_180189973
0x1800bdd7c  lea     rcx, dword_1801AB110
0x1800bdd83  lea     rax, [rsp+368h+var_338]
0x1800bdd88  mov     qword ptr [rsp+368h+var_348], rax; int
0x1800bdd8d  mov     [rsp+368h+var_338], 80090029h
0x1800bdd95  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800bdd9a  mov     rcx, [rsp+368h]; this
0x1800bdda2  mov     r9d, 80090029h; char *
0x1800bdda8  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800bddaf  mov     edx, 0E05h; void *
0x1800bddb4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bddb9  nop
0x1800bddba  lea     rcx, [rsp+368h+var_308]
0x1800bddbf  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginPerformUVTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>(void)
0x1800bddc4  nop
0x1800bddc5  lea     rcx, [rsp+368h+var_330]
0x1800bddca  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginPerformUVTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>(void)
0x1800bddcf  mov     eax, 80090029h
0x1800bddd4  jmp     loc_1800BE11A
0x1800bddd9  call    IsWinStationIsSessionRemoteablePresent
0x1800bddde  test    al, al
0x1800bdde0  jz      loc_1800BDEBB
0x1800bdde6  lea     r8, [rsp+368h+var_334]
0x1800bddeb  or      edx, 0FFFFFFFFh
0x1800bddee  xor     ecx, ecx
0x1800bddf0  call    cs:__imp_WinStationIsSessionRemoteable
0x1800bddf6  test    al, al
0x1800bddf8  jz      loc_1800BDEBB
0x1800bddfe  cmp     [rsp+368h+var_334], 0
0x1800bde03  jz      loc_1800BDEBB
0x1800bde09  lea     rcx, aWebauthnplugin_61; "WebAuthNPluginPerformUVTest::reason::re"...
0x1800bde10  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800bde15  mov     r8, rax
0x1800bde18  mov     edx, 2
0x1800bde1d  lea     rcx, [rsp+368h+var_330]
0x1800bde22  call    ?complete_and_ignore@?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(ushort,char const *)
0x1800bde27  mov     rcx, r15
0x1800bde2a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(void)
0x1800bde2f  test    al, al
0x1800bde31  jz      short loc_1800BDE4C
0x1800bde33  call    ?get@?$static_lazy@VFidoPluginProvider@@@details@wil@@QEAAPEAVFidoPluginProvider@@P6AXXZ@Z; wil::details::static_lazy<FidoPluginProvider>::get(void (*)(void))
0x1800bde38  mov     rcx, [rax+10h]
0x1800bde3c  mov     eax, [rcx]
0x1800bde3e  cmp     eax, 3
0x1800bde41  jbe     short loc_1800BDE7C
0x1800bde43  lea     rdx, unk_180189860
0x1800bde4a  jmp     short loc_1800BDE65
0x1800bde4c  mov     eax, cs:dword_1801AB110
0x1800bde52  cmp     eax, 3
0x1800bde55  jbe     short loc_1800BDE7C
0x1800bde57  lea     rdx, byte_1801898B9
0x1800bde5e  lea     rcx, dword_1801AB110
0x1800bde65  lea     rax, [rsp+368h+var_338]
0x1800bde6a  mov     qword ptr [rsp+368h+var_348], rax; int
0x1800bde6f  mov     [rsp+368h+var_338], 80090029h
0x1800bde77  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800bde7c  mov     rcx, [rsp+368h]; this
0x1800bde84  mov     r9d, 80090029h; char *
0x1800bde8a  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800bde91  mov     edx, 0E1Ah; void *
0x1800bde96  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bde9b  nop
0x1800bde9c  lea     rcx, [rsp+368h+var_308]
0x1800bdea1  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginPerformUVTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>(void)
0x1800bdea6  nop
0x1800bdea7  lea     rcx, [rsp+368h+var_330]
0x1800bdeac  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginPerformUVTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>(void)
0x1800bdeb1  mov     eax, 80090029h
0x1800bdeb6  jmp     loc_1800BE11A
0x1800bdebb  xor     edx, edx; Val
0x1800bdebd  lea     r8d, [rdx+50h]; Size
0x1800bdec1  lea     rcx, [rsp+368h+sz]; void *
0x1800bdec9  call    memset_0
0x1800bdece  mov     r8d, 28h ; '('; cchMax
0x1800bded4  lea     rdx, [rsp+368h+sz]; lpsz
0x1800bdedc  mov     rcx, rbx; rguid
0x1800bdedf  call    cs:__imp_StringFromGUID2
0x1800bdee5  test    eax, eax
0x1800bdee7  jnz     loc_1800BDF9F
0x1800bdeed  lea     rcx, aWebauthnplugin_98; "WebAuthNPluginPerformUVTest::reason::in"...
0x1800bdef4  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800bdef9  mov     r8, rax
0x1800bdefc  mov     edx, 9
0x1800bdf01  lea     rcx, [rsp+368h+var_330]
0x1800bdf06  call    ?complete_and_ignore@?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(ushort,char const *)
0x1800bdf0b  mov     rcx, r15
0x1800bdf0e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(void)
0x1800bdf13  test    al, al
0x1800bdf15  jz      short loc_1800BDF30
0x1800bdf17  call    ?get@?$static_lazy@VFidoPluginProvider@@@details@wil@@QEAAPEAVFidoPluginProvider@@P6AXXZ@Z; wil::details::static_lazy<FidoPluginProvider>::get(void (*)(void))
0x1800bdf1c  mov     rcx, [rax+10h]
0x1800bdf20  mov     eax, [rcx]
0x1800bdf22  cmp     eax, 3
0x1800bdf25  jbe     short loc_1800BDF60
0x1800bdf27  lea     rdx, word_18018979E
0x1800bdf2e  jmp     short loc_1800BDF49
0x1800bdf30  mov     eax, cs:dword_1801AB110
0x1800bdf36  cmp     eax, 3
0x1800bdf39  jbe     short loc_1800BDF60
0x1800bdf3b  lea     rdx, byte_1801897FB
0x1800bdf42  lea     rcx, dword_1801AB110
0x1800bdf49  lea     rax, [rsp+368h+var_338]
0x1800bdf4e  mov     qword ptr [rsp+368h+var_348], rax; int
0x1800bdf53  mov     [rsp+368h+var_338], 80090027h
0x1800bdf5b  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800bdf60  mov     rcx, [rsp+368h]; this
0x1800bdf68  mov     r9d, 80090027h; char *
0x1800bdf6e  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800bdf75  mov     edx, 0E2Fh; void *
0x1800bdf7a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bdf7f  nop
0x1800bdf80  lea     rcx, [rsp+368h+var_308]
0x1800bdf85  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginPerformUVTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>(void)
0x1800bdf8a  nop
0x1800bdf8b  lea     rcx, [rsp+368h+var_330]
0x1800bdf90  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginPerformUVTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>(void)
0x1800bdf95  mov     eax, 80090027h
0x1800bdf9a  jmp     loc_1800BE11A
0x1800bdf9f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl(void)'::`2'::impl
0x1800bdfa6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x1800bdfab  mov     [rsp+368h+var_158], 3
0x1800bdfb6  lea     rax, [rsp+368h+sz]
0x1800bdfbe  mov     [rsp+368h+var_1B8], rax
0x1800bdfc6  mov     [rsp+368h+var_338], 0
0x1800bdfce  mov     [rsp+368h+var_320], 0
0x1800bdfd7  lea     rdx, [rsp+368h+var_2C8]
0x1800bdfdf  lea     rcx, [rsp+368h+var_330]
0x1800bdfe4  call    ?test_id@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest@@U1@@details@tip2@@@tip2@@QEBA?AU_GUID@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::test_id(void)
0x1800bdfe9  movups  xmm1, xmmword ptr [rax]
0x1800bdfec  movdqu  xmmword ptr [rsp+368h+var_318.Data1], xmm1
0x1800bdff2  lea     rax, [rsp+368h+var_320]
0x1800bdff7  mov     qword ptr [rsp+368h+var_348], rax; unsigned __int8 **
0x1800bdffc  lea     r9, [rsp+368h+var_338]; unsigned int *
0x1800be001  lea     r8, [rsp+368h+var_2B8]; struct _CTAPCBOR_RPC_REQUEST *
0x1800be009  lea     rdx, [rsp+368h+var_318]; struct _GUID *
0x1800be00e  mov     ecx, 6Dh ; 'm'; unsigned int
0x1800be013  call    ?I_EncodeAndSendRpcRequest@@YAJKU_GUID@@AEAU_CTAPCBOR_RPC_REQUEST@@PEAKPEAPEAE@Z; I_EncodeAndSendRpcRequest(ulong,_GUID,_CTAPCBOR_RPC_REQUEST &,ulong *,uchar * *)
0x1800be018  mov     ebx, eax
0x1800be01a  mov     rcx, [rsp+368h+var_330]
0x1800be01f  test    rcx, rcx
0x1800be022  jz      short loc_1800BE060
0x1800be024  add     rcx, 8
0x1800be028  call    ?is_running@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::is_running(void)
0x1800be02d  test    al, al
0x1800be02f  jz      short loc_1800BE060
0x1800be031  test    ebx, ebx
0x1800be033  jns     short loc_1800BE056
0x1800be035  lea     rcx, aWebauthnplugin_92; "WebAuthNPluginPerformUVTest::reason::uv"...
0x1800be03c  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800be041  mov     r8, rax
0x1800be044  mov     edx, 8
0x1800be049  mov     r9d, ebx
0x1800be04c  lea     rcx, [rsp+368h+var_330]
0x1800be051  call    ??$set_flag_value@J@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginPerformUVTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBDJ@Z; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::set_flag_value<long>(ushort,char const *,long)
0x1800be056  lea     rcx, [rsp+368h+var_330]
0x1800be05b  call    ?complete@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginCallbackTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::complete(void)
0x1800be060  test    ebx, ebx
0x1800be062  jns     loc_1800BE0EF
0x1800be068  mov     rcx, r15
0x1800be06b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(void)
0x1800be070  test    al, al
0x1800be072  jz      short loc_1800BE08D
0x1800be074  call    ?get@?$static_lazy@VFidoPluginProvider@@@details@wil@@QEAAPEAVFidoPluginProvider@@P6AXXZ@Z; wil::details::static_lazy<FidoPluginProvider>::get(void (*)(void))
0x1800be079  mov     rcx, [rax+10h]
0x1800be07d  mov     eax, [rcx]
0x1800be07f  cmp     eax, 3
0x1800be082  jbe     short loc_1800BE0B9
0x1800be084  lea     rdx, word_1801896CE
0x1800be08b  jmp     short loc_1800BE0A6
0x1800be08d  mov     eax, cs:dword_1801AB110
0x1800be093  cmp     eax, 3
0x1800be096  jbe     short loc_1800BE0B9
0x1800be098  lea     rdx, word_180189732
0x1800be09f  lea     rcx, dword_1801AB110
0x1800be0a6  lea     rax, [rsp+368h+var_338]
0x1800be0ab  mov     qword ptr [rsp+368h+var_348], rax; int
0x1800be0b0  mov     [rsp+368h+var_338], ebx
0x1800be0b4  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800be0b9  mov     rcx, [rsp+368h]; this
0x1800be0c1  mov     r9d, ebx; char *
0x1800be0c4  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800be0cb  mov     edx, 0E58h; void *
0x1800be0d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be0d5  nop
0x1800be0d6  lea     rcx, [rsp+368h+var_308]
0x1800be0db  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginPerformUVTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>(void)
0x1800be0e0  nop
0x1800be0e1  lea     rcx, [rsp+368h+var_330]
0x1800be0e6  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginPerformUVTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>(void)
0x1800be0eb  mov     eax, ebx
0x1800be0ed  jmp     short loc_1800BE11A
0x1800be0ef  mov     eax, [rsp+368h+var_338]
0x1800be0f3  mov     [rdi], eax
0x1800be0f5  mov     rax, [rsp+368h+var_320]
0x1800be0fa  mov     [rsi], rax
0x1800be0fd  lea     rcx, [rsp+368h+var_308]
0x1800be102  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginPerformUVTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>(void)
0x1800be107  nop
  ... truncated ...
```
