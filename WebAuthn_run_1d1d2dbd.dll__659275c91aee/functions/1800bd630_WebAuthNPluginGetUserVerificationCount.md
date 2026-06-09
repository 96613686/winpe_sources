# WebAuthNPluginGetUserVerificationCount

- ea: `0x1800bd630`
- end: `0x1800bdba6`
- name: `WebAuthNPluginGetUserVerificationCount`
- size: `1398`
- prototype: `__int64 __fastcall(GUID *rguid)`
- caller_count: `0`
- callee_count: `23`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800021d8`
- `0x180003d08`
- `0x180007f90`
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
- `0x1800bd630`
- `0x18013c090`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800bd92a`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800bd92a`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x1800bd83b`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x1800bd83b`

## string_xrefs

- `0x1800bd67b`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800bd6a6`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800bd7f3`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800bd8d5`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800bd9b9`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800bdb0f`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800bd938`: `WebAuthNPluginPerformUVTest::reason::invalid_parameters`
- `0x1800bd772`: `WebAuthNPluginPerformUVTest::reason::remote_session`
- `0x1800bd854`: `WebAuthNPluginPerformUVTest::reason::remote_session`
- `0x1800bda80`: `WebAuthNPluginPerformUVTest::reason::uv_get_count_failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall WebAuthNPluginGetUserVerificationCount(GUID *rguid, _DWORD *a2)
{
  _DWORD *v5; // rcx
  const char *v6; // rdx
  const char *v7; // rax
  int v8; // r8d
  int v9; // r9d
  int *v10; // rcx
  void *v11; // rdx
  const char *v12; // rdx
  const char *v13; // rax
  int v14; // r8d
  int v15; // r9d
  int *v16; // rcx
  void *v17; // rdx
  const char *v18; // rdx
  const char *v19; // rax
  int v20; // r8d
  int v21; // r9d
  int *v22; // rcx
  void *v23; // rdx
  signed int v24; // ebx
  const char *v25; // rdx
  const char *v26; // rax
  int v27; // r8d
  int v28; // r9d
  int *v29; // rcx
  void *v30; // rdx
  unsigned __int8 *v31; // rcx
  int v32; // [rsp+20h] [rbp-338h]
  int v33; // [rsp+20h] [rbp-338h]
  unsigned int v34; // [rsp+30h] [rbp-328h] BYREF
  _BYTE v35[4]; // [rsp+34h] [rbp-324h] BYREF
  _QWORD v36[2]; // [rsp+38h] [rbp-320h] BYREF
  unsigned __int8 *v37; // [rsp+48h] [rbp-310h] BYREF
  struct _GUID v38; // [rsp+50h] [rbp-308h] BYREF
  _BYTE v39[64]; // [rsp+60h] [rbp-2F8h] BYREF
  _BYTE v40[16]; // [rsp+A0h] [rbp-2B8h] BYREF
  _BYTE v41[256]; // [rsp+B0h] [rbp-2A8h] BYREF
  OLECHAR *v42; // [rsp+1B0h] [rbp-1A8h]
  int v43; // [rsp+210h] [rbp-148h]
  OLECHAR sz[40]; // [rsp+2F0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+358h] [rbp+0h]

  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::GetImpl'::`2'::impl) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD41,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
      (const char *)0x80004001LL,
      v32);
    return 2147500033LL;
  }
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD42,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
      (const char *)0x80090027LL,
      v32);
    return 2148073511LL;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl) )
  {
    v5 = *(_DWORD **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
    if ( *v5 > 4u )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        v5,
        &unk_180189DD8,
        0);
  }
  else if ( (unsigned int)dword_1801AB110 > 4 )
  {
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_1801AB110,
      &unk_180189CE6,
      0);
  }
  v36[0] = 0;
  tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::start_and_watch_errors(
    v36,
    v39);
  v35[0] = 0;
  memset_0(v41, 0, 0x238u);
  *a2 = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
  {
    if ( !(unsigned __int8)IsWinStationIsSessionRemoteablePresent()
      || !(unsigned __int8)WinStationIsSessionRemoteable(0, 0xFFFFFFFFLL, v35)
      || !v35[0] )
    {
      goto LABEL_29;
    }
    v13 = tip2::details::reason_string((tip2::details *)"WebAuthNPluginPerformUVTest::reason::remote_session", v12);
    tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(
      v36,
      2,
      v13);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl) )
    {
      v16 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
      if ( (unsigned int)*v16 > 3 )
      {
        v17 = &unk_180189C91;
LABEL_27:
        v34 = -2146893783;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (_DWORD)v16,
          (_DWORD)v17,
          v14,
          v15,
          (__int64)&v34);
      }
    }
    else if ( (unsigned int)dword_1801AB110 > 3 )
    {
      v17 = &unk_180189B7E;
      v16 = &dword_1801AB110;
      goto LABEL_27;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD7F,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
      (const char *)0x80090029LL,
      v32);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>(v39);
    wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>(v36);
    return 2148073513LL;
  }
  if ( ShouldSendRequestToRemoteSession(0) )
  {
    v7 = tip2::details::reason_string((tip2::details *)"WebAuthNPluginPerformUVTest::reason::remote_session", v6);
    tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(
      v36,
      2,
      v7);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl) )
    {
      v10 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
      if ( (unsigned int)*v10 > 3 )
      {
        v11 = &unk_180189D25;
LABEL_17:
        v34 = -2146893783;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (_DWORD)v10,
          (_DWORD)v11,
          v8,
          v9,
          (__int64)&v34);
      }
    }
    else if ( (unsigned int)dword_1801AB110 > 3 )
    {
      v11 = &unk_180189C34;
      v10 = &dword_1801AB110;
      goto LABEL_17;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6A,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
      (const char *)0x80090029LL,
      v32);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>(v39);
    wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>(v36);
    return 2148073513LL;
  }
LABEL_29:
  memset_0(sz, 0, sizeof(sz));
  if ( !StringFromGUID2(rguid, sz, 40) )
  {
    v19 = tip2::details::reason_string((tip2::details *)"WebAuthNPluginPerformUVTest::reason::invalid_parameters", v18);
    tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(
      v36,
      9,
      v19);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl) )
    {
      v22 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
      if ( (unsigned int)*v22 > 3 )
      {
        v23 = &unk_180189BDB;
LABEL_35:
        v34 = -2146893785;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (_DWORD)v22,
          (_DWORD)v23,
          v20,
          v21,
          (__int64)&v34);
      }
    }
    else if ( (unsigned int)dword_1801AB110 > 3 )
    {
      v23 = &unk_180189ABD;
      v22 = &dword_1801AB110;
      goto LABEL_35;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD94,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
      (const char *)0x80090027LL,
      v32);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>(v39);
    wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>(v36);
    return 2148073511LL;
  }
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl);
  v43 = 2;
  v42 = sz;
  v34 = 0;
  v37 = 0;
  v38 = *(struct _GUID *)tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::test_id(
                           v36,
                           v40);
  v24 = I_EncodeAndSendRpcRequest(0x6Du, &v38, (struct _CTAPCBOR_RPC_REQUEST *)v41, &v34, &v37);
  if ( v36[0] && (unsigned __int8)tip2::details::shared_data<1,0,0>::is_running(v36[0] + 8LL) )
  {
    if ( v24 < 0 )
    {
      v26 = tip2::details::reason_string(
              (tip2::details *)"WebAuthNPluginPerformUVTest::reason::uv_get_count_failed",
              v25);
      tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::set_flag_value<long>(
        v36,
        7,
        v26,
        (unsigned int)v24);
    }
    tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::complete(v36);
  }
  if ( v24 < 0 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl) )
    {
      v29 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
      if ( (unsigned int)*v29 > 3 )
      {
        v30 = &unk_180189B1E;
LABEL_48:
        v34 = v24;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (_DWORD)v29,
          (_DWORD)v30,
          v27,
          v28,
          (__int64)&v34);
      }
    }
    else if ( (unsigned int)dword_1801AB110 > 3 )
    {
      v30 = &unk_180189A55;
      v29 = &dword_1801AB110;
      goto LABEL_48;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDBD,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
      (const char *)(unsigned int)v24,
      v33);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>(v39);
    wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>(v36);
    return (unsigned int)v24;
  }
  v31 = v37;
  if ( v34 >= 4 && v37 )
  {
    *a2 = *(_DWORD *)v37;
LABEL_54:
    FidoFree(v31);
    goto LABEL_55;
  }
  *a2 = 0;
  if ( v31 )
    goto LABEL_54;
LABEL_55:
  tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>(v39);
  wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>(v36);
  return 0;
}

```

## disassembly

```asm
0x1800bd630  mov     [rsp+arg_10], rbx
0x1800bd635  mov     [rsp+arg_18], rdi
0x1800bd63a  push    r14
0x1800bd63c  sub     rsp, 350h
0x1800bd643  mov     rax, cs:__security_cookie
0x1800bd64a  xor     rax, rsp
0x1800bd64d  mov     [rsp+358h+var_18], rax
0x1800bd655  mov     rdi, rdx
0x1800bd658  mov     rbx, rcx
0x1800bd65b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PasskeyPluginAuthenticators@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PasskeyPluginAuthenticators@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators> `wil::Feature<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::GetImpl(void)'::`2'::impl
0x1800bd662  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PasskeyPluginAuthenticators@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::__private_IsEnabled(void)
0x1800bd667  test    al, al
0x1800bd669  jnz     short loc_1800BD693
0x1800bd66b  mov     rcx, [rsp+358h]; this
0x1800bd673  mov     ebx, 80004001h
0x1800bd678  mov     r9d, ebx; char *
0x1800bd67b  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800bd682  mov     edx, 0D41h; void *
0x1800bd687  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bd68c  mov     eax, ebx
0x1800bd68e  jmp     loc_1800BDB7F
0x1800bd693  test    rdi, rdi
0x1800bd696  jnz     short loc_1800BD6C1
0x1800bd698  mov     rcx, [rsp+358h]; this
0x1800bd6a0  mov     r9d, 80090027h; char *
0x1800bd6a6  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800bd6ad  mov     edx, 0D42h; void *
0x1800bd6b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bd6b7  mov     eax, 80090027h
0x1800bd6bc  jmp     loc_1800BDB7F
0x1800bd6c1  lea     r14, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2> `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl(void)'::`2'::impl
0x1800bd6c8  mov     rcx, r14
0x1800bd6cb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(void)
0x1800bd6d0  test    al, al
0x1800bd6d2  jz      short loc_1800BD6F5
0x1800bd6d4  call    ?get@?$static_lazy@VFidoPluginProvider@@@details@wil@@QEAAPEAVFidoPluginProvider@@P6AXXZ@Z; wil::details::static_lazy<FidoPluginProvider>::get(void (*)(void))
0x1800bd6d9  mov     rcx, [rax+10h]
0x1800bd6dd  mov     eax, [rcx]
0x1800bd6df  cmp     eax, 4
0x1800bd6e2  jbe     short loc_1800BD716
0x1800bd6e4  xor     r8d, r8d
0x1800bd6e7  lea     rdx, unk_180189DD8
0x1800bd6ee  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800bd6f3  jmp     short loc_1800BD716
0x1800bd6f5  mov     eax, cs:dword_1801AB110
0x1800bd6fb  cmp     eax, 4
0x1800bd6fe  jbe     short loc_1800BD716
0x1800bd700  xor     r8d, r8d
0x1800bd703  lea     rdx, unk_180189CE6
0x1800bd70a  lea     rcx, dword_1801AB110
0x1800bd711  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800bd716  mov     [rsp+358h+var_320], 0
0x1800bd71f  lea     rdx, [rsp+358h+var_2F8]
0x1800bd724  lea     rcx, [rsp+358h+var_320]
0x1800bd729  call    ?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginPerformUVTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginPerformUVTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::start_and_watch_errors(void)
0x1800bd72e  nop
0x1800bd72f  mov     [rsp+358h+var_324], 0
0x1800bd734  xor     edx, edx; Val
0x1800bd736  mov     r8d, 238h; Size
0x1800bd73c  lea     rcx, [rsp+358h+var_2A8]; void *
0x1800bd744  call    memset_0
0x1800bd749  mov     dword ptr [rdi], 0
0x1800bd74f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl(void)'::`2'::impl
0x1800bd756  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x1800bd75b  test    al, al
0x1800bd75d  jz      loc_1800BD824
0x1800bd763  xor     ecx, ecx; unsigned __int8 *
0x1800bd765  call    ?ShouldSendRequestToRemoteSession@@YA_NPEAE@Z; ShouldSendRequestToRemoteSession(uchar *)
0x1800bd76a  test    al, al
0x1800bd76c  jz      loc_1800BD906
0x1800bd772  lea     rcx, aWebauthnplugin_61; "WebAuthNPluginPerformUVTest::reason::re"...
0x1800bd779  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800bd77e  mov     r8, rax
0x1800bd781  mov     edx, 2
0x1800bd786  lea     rcx, [rsp+358h+var_320]
0x1800bd78b  call    ?complete_and_ignore@?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(ushort,char const *)
0x1800bd790  mov     rcx, r14
0x1800bd793  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(void)
0x1800bd798  test    al, al
0x1800bd79a  jz      short loc_1800BD7B5
0x1800bd79c  call    ?get@?$static_lazy@VFidoPluginProvider@@@details@wil@@QEAAPEAVFidoPluginProvider@@P6AXXZ@Z; wil::details::static_lazy<FidoPluginProvider>::get(void (*)(void))
0x1800bd7a1  mov     rcx, [rax+10h]
0x1800bd7a5  mov     eax, [rcx]
0x1800bd7a7  cmp     eax, 3
0x1800bd7aa  jbe     short loc_1800BD7E5
0x1800bd7ac  lea     rdx, unk_180189D25
0x1800bd7b3  jmp     short loc_1800BD7CE
0x1800bd7b5  mov     eax, cs:dword_1801AB110
0x1800bd7bb  cmp     eax, 3
0x1800bd7be  jbe     short loc_1800BD7E5
0x1800bd7c0  lea     rdx, unk_180189C34
0x1800bd7c7  lea     rcx, dword_1801AB110
0x1800bd7ce  lea     rax, [rsp+358h+var_328]
0x1800bd7d3  mov     qword ptr [rsp+358h+var_338], rax; int
0x1800bd7d8  mov     [rsp+358h+var_328], 80090029h
0x1800bd7e0  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800bd7e5  mov     rcx, [rsp+358h]; this
0x1800bd7ed  mov     r9d, 80090029h; char *
0x1800bd7f3  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800bd7fa  mov     edx, 0D6Ah; void *
0x1800bd7ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bd804  nop
0x1800bd805  lea     rcx, [rsp+358h+var_2F8]
0x1800bd80a  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginPerformUVTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>(void)
0x1800bd80f  nop
0x1800bd810  lea     rcx, [rsp+358h+var_320]
0x1800bd815  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginPerformUVTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>(void)
0x1800bd81a  mov     eax, 80090029h
0x1800bd81f  jmp     loc_1800BDB7F
0x1800bd824  call    IsWinStationIsSessionRemoteablePresent
0x1800bd829  test    al, al
0x1800bd82b  jz      loc_1800BD906
0x1800bd831  lea     r8, [rsp+358h+var_324]
0x1800bd836  or      edx, 0FFFFFFFFh
0x1800bd839  xor     ecx, ecx
0x1800bd83b  call    cs:__imp_WinStationIsSessionRemoteable
0x1800bd841  test    al, al
0x1800bd843  jz      loc_1800BD906
0x1800bd849  cmp     [rsp+358h+var_324], 0
0x1800bd84e  jz      loc_1800BD906
0x1800bd854  lea     rcx, aWebauthnplugin_61; "WebAuthNPluginPerformUVTest::reason::re"...
0x1800bd85b  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800bd860  mov     r8, rax
0x1800bd863  mov     edx, 2
0x1800bd868  lea     rcx, [rsp+358h+var_320]
0x1800bd86d  call    ?complete_and_ignore@?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(ushort,char const *)
0x1800bd872  mov     rcx, r14
0x1800bd875  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(void)
0x1800bd87a  test    al, al
0x1800bd87c  jz      short loc_1800BD897
0x1800bd87e  call    ?get@?$static_lazy@VFidoPluginProvider@@@details@wil@@QEAAPEAVFidoPluginProvider@@P6AXXZ@Z; wil::details::static_lazy<FidoPluginProvider>::get(void (*)(void))
0x1800bd883  mov     rcx, [rax+10h]
0x1800bd887  mov     eax, [rcx]
0x1800bd889  cmp     eax, 3
0x1800bd88c  jbe     short loc_1800BD8C7
0x1800bd88e  lea     rdx, unk_180189C91
0x1800bd895  jmp     short loc_1800BD8B0
0x1800bd897  mov     eax, cs:dword_1801AB110
0x1800bd89d  cmp     eax, 3
0x1800bd8a0  jbe     short loc_1800BD8C7
0x1800bd8a2  lea     rdx, unk_180189B7E
0x1800bd8a9  lea     rcx, dword_1801AB110
0x1800bd8b0  lea     rax, [rsp+358h+var_328]
0x1800bd8b5  mov     qword ptr [rsp+358h+var_338], rax; int
0x1800bd8ba  mov     [rsp+358h+var_328], 80090029h
0x1800bd8c2  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800bd8c7  mov     rcx, [rsp+358h]; this
0x1800bd8cf  mov     r9d, 80090029h; char *
0x1800bd8d5  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800bd8dc  mov     edx, 0D7Fh; void *
0x1800bd8e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bd8e6  nop
0x1800bd8e7  lea     rcx, [rsp+358h+var_2F8]
0x1800bd8ec  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginPerformUVTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>(void)
0x1800bd8f1  nop
0x1800bd8f2  lea     rcx, [rsp+358h+var_320]
0x1800bd8f7  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginPerformUVTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>(void)
0x1800bd8fc  mov     eax, 80090029h
0x1800bd901  jmp     loc_1800BDB7F
0x1800bd906  xor     edx, edx; Val
0x1800bd908  lea     r8d, [rdx+50h]; Size
0x1800bd90c  lea     rcx, [rsp+358h+sz]; void *
0x1800bd914  call    memset_0
0x1800bd919  mov     r8d, 28h ; '('; cchMax
0x1800bd91f  lea     rdx, [rsp+358h+sz]; lpsz
0x1800bd927  mov     rcx, rbx; rguid
0x1800bd92a  call    cs:__imp_StringFromGUID2
0x1800bd930  test    eax, eax
0x1800bd932  jnz     loc_1800BD9EA
0x1800bd938  lea     rcx, aWebauthnplugin_98; "WebAuthNPluginPerformUVTest::reason::in"...
0x1800bd93f  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800bd944  mov     r8, rax
0x1800bd947  mov     edx, 9
0x1800bd94c  lea     rcx, [rsp+358h+var_320]
0x1800bd951  call    ?complete_and_ignore@?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(ushort,char const *)
0x1800bd956  mov     rcx, r14
0x1800bd959  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(void)
0x1800bd95e  test    al, al
0x1800bd960  jz      short loc_1800BD97B
0x1800bd962  call    ?get@?$static_lazy@VFidoPluginProvider@@@details@wil@@QEAAPEAVFidoPluginProvider@@P6AXXZ@Z; wil::details::static_lazy<FidoPluginProvider>::get(void (*)(void))
0x1800bd967  mov     rcx, [rax+10h]
0x1800bd96b  mov     eax, [rcx]
0x1800bd96d  cmp     eax, 3
0x1800bd970  jbe     short loc_1800BD9AB
0x1800bd972  lea     rdx, unk_180189BDB
0x1800bd979  jmp     short loc_1800BD994
0x1800bd97b  mov     eax, cs:dword_1801AB110
0x1800bd981  cmp     eax, 3
0x1800bd984  jbe     short loc_1800BD9AB
0x1800bd986  lea     rdx, unk_180189ABD
0x1800bd98d  lea     rcx, dword_1801AB110
0x1800bd994  lea     rax, [rsp+358h+var_328]
0x1800bd999  mov     qword ptr [rsp+358h+var_338], rax; int
0x1800bd99e  mov     [rsp+358h+var_328], 80090027h
0x1800bd9a6  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800bd9ab  mov     rcx, [rsp+358h]; this
0x1800bd9b3  mov     r9d, 80090027h; char *
0x1800bd9b9  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800bd9c0  mov     edx, 0D94h; void *
0x1800bd9c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bd9ca  nop
0x1800bd9cb  lea     rcx, [rsp+358h+var_2F8]
0x1800bd9d0  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginPerformUVTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>(void)
0x1800bd9d5  nop
0x1800bd9d6  lea     rcx, [rsp+358h+var_320]
0x1800bd9db  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginPerformUVTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>(void)
0x1800bd9e0  mov     eax, 80090027h
0x1800bd9e5  jmp     loc_1800BDB7F
0x1800bd9ea  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl(void)'::`2'::impl
0x1800bd9f1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x1800bd9f6  mov     [rsp+358h+var_148], 2
0x1800bda01  lea     rax, [rsp+358h+sz]
0x1800bda09  mov     [rsp+358h+var_1A8], rax
0x1800bda11  mov     [rsp+358h+var_328], 0
0x1800bda19  mov     [rsp+358h+var_310], 0
0x1800bda22  lea     rdx, [rsp+358h+var_2B8]
0x1800bda2a  lea     rcx, [rsp+358h+var_320]
0x1800bda2f  call    ?test_id@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest@@U1@@details@tip2@@@tip2@@QEBA?AU_GUID@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::test_id(void)
0x1800bda34  movups  xmm1, xmmword ptr [rax]
0x1800bda37  movdqu  xmmword ptr [rsp+358h+var_308.Data1], xmm1
0x1800bda3d  lea     rax, [rsp+358h+var_310]
0x1800bda42  mov     qword ptr [rsp+358h+var_338], rax; unsigned __int8 **
0x1800bda47  lea     r9, [rsp+358h+var_328]; unsigned int *
0x1800bda4c  lea     r8, [rsp+358h+var_2A8]; struct _CTAPCBOR_RPC_REQUEST *
0x1800bda54  lea     rdx, [rsp+358h+var_308]; struct _GUID *
0x1800bda59  mov     ecx, 6Dh ; 'm'; unsigned int
0x1800bda5e  call    ?I_EncodeAndSendRpcRequest@@YAJKU_GUID@@AEAU_CTAPCBOR_RPC_REQUEST@@PEAKPEAPEAE@Z; I_EncodeAndSendRpcRequest(ulong,_GUID,_CTAPCBOR_RPC_REQUEST &,ulong *,uchar * *)
0x1800bda63  mov     ebx, eax
0x1800bda65  mov     rcx, [rsp+358h+var_320]
0x1800bda6a  test    rcx, rcx
0x1800bda6d  jz      short loc_1800BDAAB
0x1800bda6f  add     rcx, 8
0x1800bda73  call    ?is_running@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::is_running(void)
0x1800bda78  test    al, al
0x1800bda7a  jz      short loc_1800BDAAB
0x1800bda7c  test    ebx, ebx
0x1800bda7e  jns     short loc_1800BDAA1
0x1800bda80  lea     rcx, aWebauthnplugin_78; "WebAuthNPluginPerformUVTest::reason::uv"...
0x1800bda87  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800bda8c  mov     r8, rax
0x1800bda8f  mov     edx, 7
0x1800bda94  mov     r9d, ebx
0x1800bda97  lea     rcx, [rsp+358h+var_320]
0x1800bda9c  call    ??$set_flag_value@J@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginPerformUVTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBDJ@Z; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::set_flag_value<long>(ushort,char const *,long)
0x1800bdaa1  lea     rcx, [rsp+358h+var_320]
0x1800bdaa6  call    ?complete@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginCallbackTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::complete(void)
0x1800bdaab  test    ebx, ebx
0x1800bdaad  jns     loc_1800BDB3A
0x1800bdab3  mov     rcx, r14
0x1800bdab6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(void)
0x1800bdabb  test    al, al
0x1800bdabd  jz      short loc_1800BDAD8
0x1800bdabf  call    ?get@?$static_lazy@VFidoPluginProvider@@@details@wil@@QEAAPEAVFidoPluginProvider@@P6AXXZ@Z; wil::details::static_lazy<FidoPluginProvider>::get(void (*)(void))
0x1800bdac4  mov     rcx, [rax+10h]
0x1800bdac8  mov     eax, [rcx]
0x1800bdaca  cmp     eax, 3
0x1800bdacd  jbe     short loc_1800BDB04
0x1800bdacf  lea     rdx, unk_180189B1E
0x1800bdad6  jmp     short loc_1800BDAF1
0x1800bdad8  mov     eax, cs:dword_1801AB110
0x1800bdade  cmp     eax, 3
0x1800bdae1  jbe     short loc_1800BDB04
0x1800bdae3  lea     rdx, unk_180189A55
0x1800bdaea  lea     rcx, dword_1801AB110
0x1800bdaf1  lea     rax, [rsp+358h+var_328]
0x1800bdaf6  mov     qword ptr [rsp+358h+var_338], rax; int
0x1800bdafb  mov     [rsp+358h+var_328], ebx
0x1800bdaff  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800bdb04  mov     rcx, [rsp+358h]; this
0x1800bdb0c  mov     r9d, ebx; char *
0x1800bdb0f  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800bdb16  mov     edx, 0DBDh; void *
0x1800bdb1b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bdb20  nop
0x1800bdb21  lea     rcx, [rsp+358h+var_2F8]
0x1800bdb26  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginPerformUVTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>(void)
0x1800bdb2b  nop
0x1800bdb2c  lea     rcx, [rsp+358h+var_320]
0x1800bdb31  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginPerformUVTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>(void)
0x1800bdb36  mov     eax, ebx
0x1800bdb38  jmp     short loc_1800BDB7F
0x1800bdb3a  mov     rcx, [rsp+358h+var_310]; void *
0x1800bdb3f  cmp     [rsp+358h+var_328], 4
0x1800bdb44  jb      short loc_1800BDB51
0x1800bdb46  test    rcx, rcx
0x1800bdb49  jz      short loc_1800BDB51
0x1800bdb4b  mov     eax, [rcx]
0x1800bdb4d  mov     [rdi], eax
0x1800bdb4f  jmp     short loc_1800BDB5C
0x1800bdb51  mov     dword ptr [rdi], 0
0x1800bdb57  test    rcx, rcx
0x1800bdb5a  jz      short loc_1800BDB62
0x1800bdb5c  call    ?FidoFree@@YAXPEAX@Z; FidoFree(void *)
0x1800bdb61  nop
0x1800bdb62  lea     rcx, [rsp+358h+var_2F8]
0x1800bdb67  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginPerformUVTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>(void)
0x1800bdb6c  nop
0x1800bdb6d  lea     rcx, [rsp+358h+var_320]
0x1800bdb72  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginPerformUVTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>(void)
0x1800bdb77  xor     eax, eax
  ... truncated ...
```
