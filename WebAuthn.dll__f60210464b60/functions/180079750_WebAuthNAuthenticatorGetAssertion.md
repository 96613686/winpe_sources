# WebAuthNAuthenticatorGetAssertion

- ea: `0x180079750`
- end: `0x18007a53d`
- name: `WebAuthNAuthenticatorGetAssertion`
- size: `3565`
- prototype: `__int64 __usercall@<rax>(HWND@<rcx>, struct _WEBAUTHN_ASSERTION **)`
- caller_count: `0`
- callee_count: `43`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002220`
- `0x180019938`
- `0x180044658`
- `0x1800463d4`
- `0x1800467e0`
- `0x180046820`
- `0x18004f5b4`
- `0x180055188`
- `0x180067c90`
- `0x180067e24`
- `0x1800681f8`
- `0x18006823c`
- `0x180069a10`
- `0x18006cfd4`
- `0x180072a34`
- `0x180074524`
- `0x180075264`
- `0x180075380`
- `0x180075b38`
- `0x180075b54`
- `0x180075d78`
- `0x180075db0`
- `0x180075dd8`
- `0x180075e54`
- `0x180076134`
- `0x180076234`
- `0x180076270`
- `0x1800763e0`
- `0x1800766cc`
- `0x1800769a4`
- `0x180077ea8`
- `0x180077f4c`
- `0x180078048`
- `0x1800793ec`
- `0x180079444`
- `0x180079480`
- `0x180079530`
- `0x18007969c`
- `0x180079750`
- `0x180095468`
- `0x1800c0e30`
- `0x1800c0f88`
- `0x18013c090`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x180079922`
- `RPCRT4!UuidCreate` at `0x180079ef1`
- `RPCRT4!UuidCreate` at `0x180079922`
- `RPCRT4!UuidCreate` at `0x180079ef1`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x18007994b`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x180079f35`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x18007994b`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x180079f35`

## pseudocode

```c
// Hidden C++ exception states: #wind=15 #try_helpers=1
__int64 __fastcall WebAuthNAuthenticatorGetAssertion(
        HWND a1,
        unsigned __int16 *a2,
        __int64 a3,
        __int64 a4,
        struct _WEBAUTHN_ASSERTION **a5)
{
  char v8; // bl
  char IsEnabled; // al
  const char *v10; // rdx
  const char *v11; // rax
  int v12; // ecx
  __int64 v13; // r8
  __int64 v14; // r9
  unsigned __int16 *v15; // rcx
  int *v16; // r9
  char v17; // al
  int v18; // ecx
  unsigned int v19; // ebx
  unsigned int v21; // ebx
  unsigned int v22; // edi
  _QWORD *v23; // rax
  bool v24; // zf
  const char *v25; // rdx
  const char *v26; // rax
  __int64 v27; // rdx
  __int64 v28; // r8
  int v29; // ecx
  __int64 v30; // r8
  __int64 v31; // r9
  unsigned __int16 *v32; // rcx
  int *v33; // r9
  __int64 v34; // rax
  char v35; // al
  int v36; // ecx
  unsigned int AssertionCtap; // ebx
  unsigned int v38; // edi
  _BYTE v39[4]; // [rsp+60h] [rbp-488h] BYREF
  int v40; // [rsp+64h] [rbp-484h] BYREF
  __int64 v41; // [rsp+68h] [rbp-480h] BYREF
  __int64 v42; // [rsp+70h] [rbp-478h] BYREF
  __int64 v43; // [rsp+78h] [rbp-470h] BYREF
  struct _GUID *p_Uuid; // [rsp+80h] [rbp-468h] BYREF
  __int64 v45; // [rsp+88h] [rbp-460h] BYREF
  _BYTE v46[8]; // [rsp+90h] [rbp-458h] BYREF
  int v47; // [rsp+98h] [rbp-450h] BYREF
  int v48; // [rsp+9Ch] [rbp-44Ch] BYREF
  int v49; // [rsp+A0h] [rbp-448h] BYREF
  unsigned __int16 *v50; // [rsp+A8h] [rbp-440h] BYREF
  int v51; // [rsp+B0h] [rbp-438h] BYREF
  int v52; // [rsp+B4h] [rbp-434h] BYREF
  int v53; // [rsp+B8h] [rbp-430h] BYREF
  __int64 v54; // [rsp+BCh] [rbp-42Ch] BYREF
  int v55; // [rsp+C8h] [rbp-420h] BYREF
  struct _GUID *v56; // [rsp+D0h] [rbp-418h] BYREF
  _QWORD v57[2]; // [rsp+D8h] [rbp-410h] BYREF
  int *v58; // [rsp+E8h] [rbp-400h] BYREF
  int *v59; // [rsp+F0h] [rbp-3F8h]
  int *v60; // [rsp+F8h] [rbp-3F0h]
  __int64 *v61; // [rsp+100h] [rbp-3E8h]
  int *v62; // [rsp+108h] [rbp-3E0h]
  char v63; // [rsp+110h] [rbp-3D8h]
  int *v64; // [rsp+120h] [rbp-3C8h] BYREF
  int *v65; // [rsp+128h] [rbp-3C0h]
  struct _GUID **p_p_Uuid; // [rsp+130h] [rbp-3B8h]
  unsigned __int16 **v67; // [rsp+138h] [rbp-3B0h]
  char *v68; // [rsp+140h] [rbp-3A8h]
  __int64 *v69; // [rsp+148h] [rbp-3A0h]
  __int64 *v70; // [rsp+150h] [rbp-398h]
  char *v71; // [rsp+158h] [rbp-390h]
  __int64 *v72; // [rsp+160h] [rbp-388h]
  int *v73; // [rsp+168h] [rbp-380h]
  char v74; // [rsp+170h] [rbp-378h]
  _BYTE v75[64]; // [rsp+180h] [rbp-368h] BYREF
  int v76; // [rsp+1C0h] [rbp-328h] BYREF
  char v77; // [rsp+1C4h] [rbp-324h]
  _BYTE v78[16]; // [rsp+1C8h] [rbp-320h] BYREF
  int v79; // [rsp+1D8h] [rbp-310h] BYREF
  int v80; // [rsp+1DCh] [rbp-30Ch]
  int v81; // [rsp+1E0h] [rbp-308h]
  int v82; // [rsp+1E4h] [rbp-304h]
  UUID Uuid; // [rsp+1E8h] [rbp-300h] BYREF
  _QWORD v84[42]; // [rsp+200h] [rbp-2E8h] BYREF
  _BYTE v85[336]; // [rsp+350h] [rbp-198h] BYREF

  v50 = a2;
  tip2::start<tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>>>(v46);
  v8 = 1;
  *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>>::operator->(
                           v46,
                           &v45)
            + 272LL) = 1;
  tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>>(&v45);
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_SharedPasskeyDependencies>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SharedPasskeyDependencies>::GetImpl'::`2'::impl);
  v40 = 0;
  p_Uuid = 0;
  v49 = 0;
  v39[0] = 0;
  LODWORD(v42) = 0;
  v48 = 0;
  v47 = 0;
  v45 = 0;
  Uuid = 0;
  if ( IsEnabled )
  {
    LODWORD(v43) = 1;
    HIDWORD(v42) = 1;
    v41 = 0;
    v23 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNAuthenticatorGetAssertionTest,_tip_WebAuthNAuthenticatorGetAssertionTest>>::ensure_data(&v45);
    tip2::details::shared_data<1,0,0>::start(*v23 + 8LL, v57);
    tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNAuthenticatorGetAssertionTest,_tip_WebAuthNAuthenticatorGetAssertionTest>>::watch_errors(
      &v45,
      v75);
    *a5 = 0;
    v58 = &v47;
    v59 = &v48;
    v60 = &v49;
    v61 = &v45;
    v62 = &v40;
    v63 = 1;
    if ( (unsigned __int8)tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::operator bool(v46) )
      Uuid = *(UUID *)tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::test_id(
                        v46,
                        v57);
    else
      UuidCreate(&Uuid);
    p_Uuid = &Uuid;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
    {
      v24 = !ShouldSendRequestToRemoteSession(0);
    }
    else
    {
      if ( !(unsigned __int8)IsWinStationIsSessionRemoteablePresent()
        || !(unsigned __int8)WinStationIsSessionRemoteable(0, 0xFFFFFFFFLL, v39) )
      {
        goto LABEL_53;
      }
      v24 = v39[0] == 0;
    }
    if ( !v24 )
    {
      LODWORD(v41) = 1;
      v26 = tip2::details::reason_string((tip2::details *)"WebAuthNUIPerformanceTest::reason::remote_session", v25);
      tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(
        v46,
        4,
        v26);
    }
LABEL_53:
    if ( a4 )
    {
      if ( *(_DWORD *)a4 >= 6u )
      {
        if ( *(_DWORD *)(a4 + 112) )
        {
          v49 = 1;
          if ( !(unsigned int)I_IsDebugModeConfigured() )
          {
            I_DisableEventLogging();
            v48 = 1;
          }
        }
      }
    }
    wil::ActivityBase<FidoTraceProvider,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FidoTraceProvider,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v84);
    v84[0] = &FidoTraceProvider::WebGetAssertion::`vftable';
    v76 = 0;
    v77 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(
                            `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl,
                            v27,
                            v28) )
    {
      v34 = FidoTraceProvider::WebGetAssertion::Start<long &,_GUID &,unsigned short const * &,unsigned long &,unsigned long &,int &,int &,int &>(
              (FidoTraceProvider::WebGetAssertion *)v85,
              (__int64)&v41 + 4,
              (__int64)&v42,
              (__int64)&v43,
              (__int64)&v42 + 4,
              (__int64)&v41);
      FidoTraceProvider::WebGetAssertion::operator=(v84, v34);
      FidoTraceProvider::WebGetAssertion::~WebGetAssertion((FidoTraceProvider::WebGetAssertion *)v85);
    }
    else
    {
      _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,140737488355328,5,_TlgReflectorTag_Param0IsHProvider>,140737488355328,5>::zInternalStart(&v76);
      if ( (unsigned int)dword_1801AB180 > 5
        && (unsigned __int8)tlgKeywordOn(&dword_1801AB180, 0x800000000000LL, v30, v31) )
      {
        v55 = v41;
        v54 = __PAIR64__(HIDWORD(v42), v43);
        v53 = v42;
        v52 = HIDWORD(v41);
        v32 = (unsigned __int16 *)&dword_18015030C;
        if ( v50 )
          v32 = v50;
        v57[0] = v32;
        v56 = p_Uuid;
        v51 = v40;
        if ( v77 && (v79 || v80 || v81 || v82) )
          v33 = &v79;
        else
          LODWORD(v33) = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (unsigned int)&dword_1801AB180,
          (unsigned int)&byte_180185107,
          (unsigned int)v78,
          (_DWORD)v33,
          (__int64)&v51,
          (__int64)&v56,
          (__int64)v57,
          (__int64)&v52,
          (__int64)&v53,
          (__int64)&v54,
          (__int64)&v54 + 4,
          (__int64)&v55);
      }
    }
    v64 = (int *)v84;
    v65 = &v40;
    p_p_Uuid = &p_Uuid;
    v67 = &v50;
    v68 = (char *)&v41 + 4;
    v69 = &v42;
    v70 = &v43;
    v71 = (char *)&v42 + 4;
    v72 = &v41;
    v73 = &v76;
    v74 = 1;
    if ( v50 && a3 && *(_DWORD *)a3 && *(_QWORD *)(a3 + 16) && *(_QWORD *)(a3 + 8) && *(_DWORD *)(a3 + 4) )
    {
      if ( !a4 )
      {
LABEL_81:
        if ( _InterlockedExchange(&dword_1801AF098, 1) )
        {
          v35 = -(char)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl);
          AssertionCtap = v35 != 0 ? -2147023105 : -2147417829;
          v40 = AssertionCtap;
          if ( Microsoft_Windows_WebAuthNEnableBits < 0 )
          {
            McTemplateU0jsdd_EventWriteTransfer(
              v36,
              (unsigned int)EVENT_WEBAUTHN_ERROR,
              (_DWORD)p_Uuid,
              (unsigned int)"WebAuthNAuthenticatorGetAssertionActiveCheck",
              v35 != 0 ? -1 : 27,
              v35 != 0 ? -1 : 27);
            AssertionCtap = v40;
          }
          if ( v74 )
          {
            v74 = 0;
            WebAuthNAuthenticatorGetAssertion_::_6_::_lambda_2_::operator()(&v64);
          }
        }
        else
        {
          v47 = 1;
          AssertionCtap = I_WebAuthNAuthenticatorGetAssertionCtap(
                            p_Uuid,
                            a1,
                            v50,
                            (const struct _WEBAUTHN_CLIENT_DATA *)a3,
                            (const struct _WEBAUTHN_AUTHENTICATOR_GET_ASSERTION_OPTIONS *)a4,
                            a5);
          v40 = AssertionCtap;
          if ( v74 )
          {
            v74 = 0;
            WebAuthNAuthenticatorGetAssertion_::_6_::_lambda_2_::operator()(&v64);
          }
        }
        _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,140737488355328,5,_TlgReflectorTag_Param0IsHProvider>,140737488355328,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,140737488355328,5,_TlgReflectorTag_Param0IsHProvider>,140737488355328,5>(&v76);
        FidoTraceProvider::WebGetAssertion::~WebGetAssertion((FidoTraceProvider::WebGetAssertion *)v84);
        v63 = 0;
        WebAuthNAuthenticatorGetAssertion_::_6_::_lambda_1_::operator()(&v58);
        tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNAuthenticatorMakeCredentialTest,_tip_WebAuthNAuthenticatorMakeCredentialTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNAuthenticatorMakeCredentialTest,_tip_WebAuthNAuthenticatorMakeCredentialTest>>(v75);
        wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNAuthenticatorMakeCredentialTest,_tip_WebAuthNAuthenticatorMakeCredentialTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNAuthenticatorMakeCredentialTest,_tip_WebAuthNAuthenticatorMakeCredentialTest>,wil::err_returncode_policy>(&v45);
        wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>,wil::err_returncode_policy>(v46);
        return AssertionCtap;
      }
      if ( *(_DWORD *)a4 )
      {
        HIDWORD(v41) = *(_DWORD *)a4;
        LODWORD(v42) = *(_DWORD *)(a4 + 40);
        CheckAttachmentOption((_DWORD)p_Uuid, v42, v30, (unsigned int)&v43, (__int64)&v42 + 4);
        goto LABEL_81;
      }
    }
    v38 = -2146893785;
    v40 = -2146893785;
    if ( Microsoft_Windows_WebAuthNEnableBits < 0 )
    {
      McTemplateU0jsdd_EventWriteTransfer(
        v29,
        (unsigned int)EVENT_WEBAUTHN_ERROR,
        (_DWORD)p_Uuid,
        (unsigned int)"WebAuthNAuthenticatorGetAssertionParametersCheck",
        39,
        39);
      v38 = v40;
      v8 = v74;
    }
    if ( v8 )
    {
      v74 = 0;
      WebAuthNAuthenticatorGetAssertion_::_6_::_lambda_2_::operator()(&v64);
    }
    _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,140737488355328,5,_TlgReflectorTag_Param0IsHProvider>,140737488355328,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,140737488355328,5,_TlgReflectorTag_Param0IsHProvider>,140737488355328,5>(&v76);
    FidoTraceProvider::WebGetAssertion::~WebGetAssertion((FidoTraceProvider::WebGetAssertion *)v84);
    v63 = 0;
    WebAuthNAuthenticatorGetAssertion_::_6_::_lambda_1_::operator()(&v58);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNAuthenticatorMakeCredentialTest,_tip_WebAuthNAuthenticatorMakeCredentialTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNAuthenticatorMakeCredentialTest,_tip_WebAuthNAuthenticatorMakeCredentialTest>>(v75);
    wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNAuthenticatorMakeCredentialTest,_tip_WebAuthNAuthenticatorMakeCredentialTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNAuthenticatorMakeCredentialTest,_tip_WebAuthNAuthenticatorMakeCredentialTest>,wil::err_returncode_policy>(&v45);
    wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>,wil::err_returncode_policy>(v46);
    return v38;
  }
  v41 = 0x100000001LL;
  LODWORD(v43) = 0;
  HIDWORD(v42) = 0;
  *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNAuthenticatorTest,_tip_WebAuthNAuthenticatorTest>>::operator->(
                           &v45,
                           &v55)
            + 272LL) = 2;
  tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNAuthenticatorTest,_tip_WebAuthNAuthenticatorTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNAuthenticatorTest,_tip_WebAuthNAuthenticatorTest>>(&v55);
  tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNAuthenticatorTest,_tip_WebAuthNAuthenticatorTest>>::start(
    &v45,
    v57);
  tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNAuthenticatorTest,_tip_WebAuthNAuthenticatorTest>>::watch_errors(
    &v45,
    v75);
  *a5 = 0;
  v58 = &v49;
  v59 = &v48;
  v60 = &v47;
  v61 = &v45;
  v62 = &v40;
  v63 = 1;
  if ( (unsigned __int8)tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::operator bool(v46) )
    Uuid = *(UUID *)tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::test_id(
                      v46,
                      v57);
  else
    UuidCreate(&Uuid);
  p_Uuid = &Uuid;
  if ( (unsigned __int8)IsWinStationIsSessionRemoteablePresent()
    && (unsigned __int8)WinStationIsSessionRemoteable(0, 0xFFFFFFFFLL, v39)
    && v39[0] )
  {
    LODWORD(v43) = 1;
    v11 = tip2::details::reason_string((tip2::details *)"WebAuthNUIPerformanceTest::reason::remote_session", v10);
    tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(
      v46,
      4,
      v11);
  }
  if ( a4 )
  {
    if ( *(_DWORD *)a4 >= 6u )
    {
      if ( *(_DWORD *)(a4 + 112) )
      {
        v47 = 1;
        if ( !(unsigned int)I_IsDebugModeConfigured() )
        {
          I_DisableEventLogging();
          v48 = 1;
        }
      }
    }
  }
  v76 = 0;
  v77 = 0;
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,140737488355328,5,_TlgReflectorTag_Param0IsHProvider>,140737488355328,5>::zInternalStart(&v76);
  if ( (unsigned int)dword_1801AB180 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1801AB180, 0x800000000000LL, v13, v14) )
  {
    v51 = v43;
    v52 = HIDWORD(v41);
    v53 = v41;
    v54 = v42;
    v15 = (unsigned __int16 *)&dword_18015030C;
    if ( v50 )
      v15 = v50;
    v56 = (struct _GUID *)v15;
    v57[0] = p_Uuid;
    v55 = v40;
    if ( v77 && (v79 || v80 || v81 || v82) )
      v16 = &v79;
    else
      LODWORD(v16) = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (unsigned int)&dword_1801AB180,
      (unsigned int)byte_180185185,
      (unsigned int)v78,
      (_DWORD)v16,
      (__int64)&v55,
      (__int64)v57,
      (__int64)&v56,
      (__int64)&v54 + 4,
      (__int64)&v54,
      (__int64)&v53,
      (__int64)&v52,
      (__int64)&v51);
  }
  v64 = &v76;
  v65 = &v40;
  p_p_Uuid = &p_Uuid;
  v67 = &v50;
  v68 = (char *)&v42 + 4;
  v69 = &v42;
  v70 = &v41;
  v71 = (char *)&v41 + 4;
  v72 = &v43;
  LOWORD(v73) = 258;
  if ( v50 && a3 && *(_DWORD *)a3 && *(_QWORD *)(a3 + 16) && *(_QWORD *)(a3 + 8) && *(_DWORD *)(a3 + 4) )
  {
    if ( !a4 )
      goto LABEL_35;
    if ( *(_DWORD *)a4 )
    {
      HIDWORD(v42) = *(_DWORD *)a4;
      LODWORD(v42) = *(_DWORD *)(a4 + 40);
      CheckAttachmentOption((_DWORD)p_Uuid, v42, v13, (unsigned int)&v41, (__int64)&v41 + 4);
LABEL_35:
      if ( _InterlockedExchange(&dword_1801AF098, 1) )
      {
        v17 = -(char)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl);
        v19 = v17 != 0 ? -2147023105 : -2147417829;
        v40 = v19;
        if ( Microsoft_Windows_WebAuthNEnableBits < 0 )
        {
          McTemplateU0jsdd_EventWriteTransfer(
            v18,
            (unsigned int)EVENT_WEBAUTHN_ERROR,
            (_DWORD)p_Uuid,
            (unsigned int)"WebAuthNAuthenticatorGetAssertionActiveCheck",
            v17 != 0 ? -1 : 27,
            v17 != 0 ? -1 : 27);
          v19 = v40;
        }
        wil::details::ScopeExitFnGuard__WebAuthNAuthenticatorGetAssertion_::_56_::_lambda_4___::operator()(&v64);
        _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,140737488355328,5,_TlgReflectorTag_Param0IsHProvider>,140737488355328,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,140737488355328,5,_TlgReflectorTag_Param0IsHProvider>,140737488355328,5>(&v76);
        v63 = 0;
        WebAuthNAuthenticatorMakeCredential_::_69_::_lambda_3_::operator()(&v58);
        tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNAuthenticatorTest,_tip_WebAuthNAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNAuthenticatorTest,_tip_WebAuthNAuthenticatorTest>>(v75);
        wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNAuthenticatorTest,_tip_WebAuthNAuthenticatorTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNAuthenticatorTest,_tip_WebAuthNAuthenticatorTest>,wil::err_returncode_policy>(&v45);
        wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>,wil::err_returncode_policy>(v46);
        return v19;
      }
      else
      {
        v49 = 1;
        v21 = I_WebAuthNAuthenticatorGetAssertionCtap(
                p_Uuid,
                a1,
                v50,
                (const struct _WEBAUTHN_CLIENT_DATA *)a3,
                (const struct _WEBAUTHN_AUTHENTICATOR_GET_ASSERTION_OPTIONS *)a4,
                a5);
        v40 = v21;
        wil::details::ScopeExitFnGuard__WebAuthNAuthenticatorGetAssertion_::_56_::_lambda_4___::operator()(&v64);
        _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,140737488355328,5,_TlgReflectorTag_Param0IsHProvider>,140737488355328,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,140737488355328,5,_TlgReflectorTag_Param0IsHProvider>,140737488355328,5>(&v76);
        v63 = 0;
        WebAuthNAuthenticatorMakeCredential_::_69_::_lambda_3_::operator()(&v58);
        tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNAuthenticatorTest,_tip_WebAuthNAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNAuthenticatorTest,_tip_WebAuthNAuthenticatorTest>>(v75);
        wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNAuthenticatorTest,_tip_WebAuthNAuthenticatorTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNAuthenticatorTest,_tip_WebAuthNAuthenticatorTest>,wil::err_returncode_policy>(&v45);
        wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>,wil::err_returncode_policy>(v46);
        return v21;
      }
    }
  }
  v22 = -2146893785;
  v40 = -2146893785;
  if ( Microsoft_Windows_WebAuthNEnableBits < 0 )
  {
    McTemplateU0jsdd_EventWriteTransfer(
      v12,
      (unsigned int)EVENT_WEBAUTHN_ERROR,
      (_DWORD)p_Uuid,
      (unsigned int)"WebAuthNAuthenticatorGetAssertionParametersCheck",
      39,
      39);
    v22 = v40;
  }
  wil::details::ScopeExitFnGuard__WebAuthNAuthenticatorGetAssertion_::_56_::_lambda_4___::operator()(&v64);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,140737488355328,5,_TlgReflectorTag_Param0IsHProvider>,140737488355328,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,140737488355328,5,_TlgReflectorTag_Param0IsHProvider>,140737488355328,5>(&v76);
  v63 = 0;
  WebAuthNAuthenticatorMakeCredential_::_69_::_lambda_3_::operator()(&v58);
  tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNAuthenticatorTest,_tip_WebAuthNAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNAuthenticatorTest,_tip_WebAuthNAuthenticatorTest>>(v75);
  wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNAuthenticatorTest,_tip_WebAuthNAuthenticatorTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNAuthenticatorTest,_tip_WebAuthNAuthenticatorTest>,wil::err_returncode_policy>(&v45);
  wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>,wil::err_returncode_policy>(v46);
  return v22;
}

```

## disassembly

```asm
0x180079750  push    rbx
0x180079752  push    rsi
0x180079753  push    rdi
0x180079754  push    r12
0x180079756  push    r14
0x180079758  push    r15
0x18007975a  sub     rsp, 4B8h
0x180079761  mov     rax, cs:__security_cookie
0x180079768  xor     rax, rsp
0x18007976b  mov     [rsp+4E8h+var_48], rax
0x180079773  mov     rdi, r9
0x180079776  mov     rsi, r8
0x180079779  mov     r15, rcx
0x18007977c  mov     [rsp+4E8h+var_440], rdx
0x180079784  mov     r14, [rsp+4E8h+arg_20]
0x18007978c  lea     rcx, [rsp+4E8h+var_458]
0x180079794  call    ??$start@V?$tip_test@V?$merged_data@U_tip_WebAuthNUIPerformanceTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?AV?$tip_test@V?$merged_data@U_tip_WebAuthNUIPerformanceTest@@U1@@details@tip2@@@0@XZ; tip2::start<tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>>>(void)
0x180079799  nop
0x18007979a  lea     rdx, [rsp+4E8h+var_460]
0x1800797a2  lea     rcx, [rsp+4E8h+var_458]
0x1800797aa  call    ??C?$tip_test@V?$merged_data@U_tip_WebAuthNUIPerformanceTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_WebAuthNUIPerformanceTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>>::operator->(void)
0x1800797af  mov     rcx, [rax]
0x1800797b2  mov     ebx, 1
0x1800797b7  mov     [rcx+110h], ebx
0x1800797bd  lea     rcx, [rsp+4E8h+var_460]
0x1800797c5  call    ??1?$test_data_control@V?$merged_data@U_tip_WebAuthNUIPerformanceTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>>(void)
0x1800797ca  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SharedPasskeyDependencies@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SharedPasskeyDependencies@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SharedPasskeyDependencies> `wil::Feature<__WilFeatureTraits_Feature_SharedPasskeyDependencies>::GetImpl(void)'::`2'::impl
0x1800797d1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SharedPasskeyDependencies@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SharedPasskeyDependencies>::__private_IsEnabled(void)
0x1800797d6  xor     r12d, r12d
0x1800797d9  mov     [rsp+4E8h+var_484], r12d
0x1800797de  xorps   xmm0, xmm0
0x1800797e1  mov     [rsp+4E8h+var_468], r12
0x1800797e9  mov     [rsp+4E8h+var_448], r12d
0x1800797f1  mov     [rsp+4E8h+var_488], r12b
0x1800797f6  mov     dword ptr [rsp+4E8h+var_478], r12d
0x1800797fb  mov     [rsp+4E8h+var_44C], r12d
0x180079803  mov     [rsp+4E8h+var_450], r12d
0x18007980b  mov     [rsp+4E8h+var_460], r12
0x180079813  movups  xmmword ptr [rsp+4E8h+Uuid.Data1], xmm0
0x18007981b  test    al, al
0x18007981d  jnz     loc_180079E15
0x180079823  mov     dword ptr [rsp+4E8h+var_480], ebx
0x180079827  mov     dword ptr [rsp+4E8h+var_480+4], ebx
0x18007982b  mov     dword ptr [rsp+4E8h+var_470], r12d
0x180079830  mov     dword ptr [rsp+4E8h+var_478+4], r12d
0x180079835  lea     rdx, [rsp+4E8h+var_420]
0x18007983d  lea     rcx, [rsp+4E8h+var_460]
0x180079845  call    ??C?$tip_test@V?$merged_data@U_tip_WebAuthNAuthenticatorTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_WebAuthNAuthenticatorTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNAuthenticatorTest,_tip_WebAuthNAuthenticatorTest>>::operator->(void)
0x18007984a  mov     rcx, [rax]
0x18007984d  mov     dword ptr [rcx+110h], 2
0x180079857  lea     rcx, [rsp+4E8h+var_420]
0x18007985f  call    ??1?$test_data_control@V?$merged_data@U_tip_WebAuthNAuthenticatorTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNAuthenticatorTest,_tip_WebAuthNAuthenticatorTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNAuthenticatorTest,_tip_WebAuthNAuthenticatorTest>>(void)
0x180079864  lea     rdx, [rsp+4E8h+var_410]
0x18007986c  lea     rcx, [rsp+4E8h+var_460]
0x180079874  call    ?start@?$tip_test@V?$merged_data@U_tip_WebAuthNAuthenticatorTest@@U1@@details@tip2@@@tip2@@QEAA?AU_GUID@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNAuthenticatorTest,_tip_WebAuthNAuthenticatorTest>>::start(void)
0x180079879  lea     rdx, [rsp+4E8h+var_368]
0x180079881  lea     rcx, [rsp+4E8h+var_460]
0x180079889  call    ?watch_errors@?$tip_test@V?$merged_data@U_tip_WebAuthNAuthenticatorTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_WebAuthNAuthenticatorTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNAuthenticatorTest,_tip_WebAuthNAuthenticatorTest>>::watch_errors(void)
0x18007988e  nop
0x18007988f  mov     [r14], r12
0x180079892  lea     rax, [rsp+4E8h+var_448]
0x18007989a  mov     [rsp+4E8h+var_400], rax
0x1800798a2  lea     rax, [rsp+4E8h+var_44C]
0x1800798aa  mov     [rsp+4E8h+var_3F8], rax
0x1800798b2  lea     rax, [rsp+4E8h+var_450]
0x1800798ba  mov     [rsp+4E8h+var_3F0], rax
0x1800798c2  lea     rax, [rsp+4E8h+var_460]
0x1800798ca  mov     [rsp+4E8h+var_3E8], rax
0x1800798d2  lea     rax, [rsp+4E8h+var_484]
0x1800798d7  mov     [rsp+4E8h+var_3E0], rax
0x1800798df  mov     [rsp+4E8h+var_3D8], bl
0x1800798e6  lea     rcx, [rsp+4E8h+var_458]
0x1800798ee  call    ??B?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEBA_NXZ; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::operator bool(void)
0x1800798f3  test    al, al
0x1800798f5  jz      short loc_18007991A
0x1800798f7  lea     rdx, [rsp+4E8h+var_410]
0x1800798ff  lea     rcx, [rsp+4E8h+var_458]
0x180079907  call    ?test_id@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest@@U1@@details@tip2@@@tip2@@QEBA?AU_GUID@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::test_id(void)
0x18007990c  movups  xmm1, xmmword ptr [rax]
0x18007990f  movdqu  xmmword ptr [rsp+4E8h+Uuid.Data1], xmm1
0x180079918  jmp     short loc_180079928
0x18007991a  lea     rcx, [rsp+4E8h+Uuid]; Uuid
0x180079922  call    cs:__imp_UuidCreate
0x180079928  lea     rax, [rsp+4E8h+Uuid]
0x180079930  mov     [rsp+4E8h+var_468], rax
0x180079938  call    IsWinStationIsSessionRemoteablePresent
0x18007993d  test    al, al
0x18007993f  jz      short loc_180079981
0x180079941  lea     r8, [rsp+4E8h+var_488]
0x180079946  or      edx, 0FFFFFFFFh
0x180079949  xor     ecx, ecx
0x18007994b  call    cs:__imp_WinStationIsSessionRemoteable
0x180079951  test    al, al
0x180079953  jz      short loc_180079981
0x180079955  cmp     [rsp+4E8h+var_488], r12b
0x18007995a  jz      short loc_180079981
0x18007995c  mov     dword ptr [rsp+4E8h+var_470], ebx
0x180079960  lea     rcx, aWebauthnuiperf_3; "WebAuthNUIPerformanceTest::reason::remo"...
0x180079967  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18007996c  mov     r8, rax
0x18007996f  mov     edx, 4
0x180079974  lea     rcx, [rsp+4E8h+var_458]
0x18007997c  call    ?complete_and_ignore@?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(ushort,char const *)
0x180079981  test    rdi, rdi
0x180079984  jz      short loc_1800799AD
0x180079986  cmp     dword ptr [rdi], 6
0x180079989  jb      short loc_1800799AD
0x18007998b  cmp     [rdi+70h], r12d
0x18007998f  jz      short loc_1800799AD
0x180079991  mov     [rsp+4E8h+var_450], ebx
0x180079998  call    ?I_IsDebugModeConfigured@@YAHXZ; I_IsDebugModeConfigured(void)
0x18007999d  test    eax, eax
0x18007999f  jnz     short loc_1800799AD
0x1800799a1  call    ?I_DisableEventLogging@@YAXXZ; I_DisableEventLogging(void)
0x1800799a6  mov     [rsp+4E8h+var_44C], ebx
0x1800799ad  mov     [rsp+4E8h+var_328], r12d
0x1800799b5  mov     [rsp+4E8h+var_324], r12b
0x1800799bd  lea     rcx, [rsp+4E8h+var_328]
0x1800799c5  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0IAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0IAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,140737488355328,5,_TlgReflectorTag_Param0IsHProvider>,140737488355328,5>::zInternalStart(void)
0x1800799ca  mov     eax, cs:dword_1801AB180
0x1800799d0  cmp     eax, 5
0x1800799d3  jbe     loc_180079B29
0x1800799d9  mov     rdx, 800000000000h
0x1800799e3  lea     rcx, dword_1801AB180
0x1800799ea  call    _tlgKeywordOn
0x1800799ef  test    al, al
0x1800799f1  jz      loc_180079B29
0x1800799f7  mov     eax, dword ptr [rsp+4E8h+var_470]
0x1800799fb  mov     [rsp+4E8h+var_438], eax
0x180079a02  mov     eax, dword ptr [rsp+4E8h+var_480+4]
0x180079a06  mov     [rsp+4E8h+var_434], eax
0x180079a0d  mov     eax, dword ptr [rsp+4E8h+var_480]
0x180079a11  mov     [rsp+4E8h+var_430], eax
0x180079a18  mov     eax, dword ptr [rsp+4E8h+var_478]
0x180079a1c  mov     dword ptr [rsp+4E8h+var_42C], eax
0x180079a23  mov     eax, dword ptr [rsp+4E8h+var_478+4]
0x180079a27  mov     dword ptr [rsp+4E8h+var_42C+4], eax
0x180079a2e  lea     rcx, dword_18015030C
0x180079a35  mov     rax, [rsp+4E8h+var_440]
0x180079a3d  test    rax, rax
0x180079a40  cmovnz  rcx, rax
0x180079a44  mov     [rsp+4E8h+var_418], rcx
0x180079a4c  mov     rax, [rsp+4E8h+var_468]
0x180079a54  mov     [rsp+4E8h+var_410], rax
0x180079a5c  mov     eax, [rsp+4E8h+var_484]
0x180079a60  mov     [rsp+4E8h+var_420], eax
0x180079a67  cmp     [rsp+4E8h+var_324], r12b
0x180079a6f  jz      short loc_180079AA3
0x180079a71  cmp     [rsp+4E8h+var_310], r12d
0x180079a79  jnz     short loc_180079A99
0x180079a7b  cmp     [rsp+4E8h+var_30C], r12d
0x180079a83  jnz     short loc_180079A99
0x180079a85  cmp     [rsp+4E8h+var_308], r12d
0x180079a8d  jnz     short loc_180079A99
0x180079a8f  cmp     [rsp+4E8h+var_304], r12d
0x180079a97  jz      short loc_180079AA3
0x180079a99  lea     r9, [rsp+4E8h+var_310]
0x180079aa1  jmp     short loc_180079AA6
0x180079aa3  mov     r9, r12
0x180079aa6  lea     rax, [rsp+4E8h+var_438]
0x180079aae  mov     [rsp+4E8h+var_490], rax
0x180079ab3  lea     rax, [rsp+4E8h+var_434]
0x180079abb  mov     [rsp+4E8h+var_498], rax
0x180079ac0  lea     rax, [rsp+4E8h+var_430]
0x180079ac8  mov     [rsp+4E8h+var_4A0], rax
0x180079acd  lea     rax, [rsp+4E8h+var_42C]
0x180079ad5  mov     [rsp+4E8h+var_4A8], rax
0x180079ada  lea     rax, [rsp+4E8h+var_42C+4]
0x180079ae2  mov     [rsp+4E8h+var_4B0], rax
0x180079ae7  lea     rax, [rsp+4E8h+var_418]
0x180079aef  mov     [rsp+4E8h+var_4B8], rax
0x180079af4  lea     rax, [rsp+4E8h+var_410]
0x180079afc  mov     [rsp+4E8h+var_4C0], rax
0x180079b01  lea     rax, [rsp+4E8h+var_420]
0x180079b09  mov     [rsp+4E8h+var_4C8], rax
0x180079b0e  lea     r8, [rsp+4E8h+var_320]
0x180079b16  lea     rdx, byte_180185185
0x180079b1d  lea     rcx, dword_1801AB180
0x180079b24  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U1@U1@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@33333@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180079b29  lea     rax, [rsp+4E8h+var_328]
0x180079b31  mov     [rsp+4E8h+var_3C8], rax
0x180079b39  lea     rax, [rsp+4E8h+var_484]
0x180079b3e  mov     [rsp+4E8h+var_3C0], rax
0x180079b46  lea     rax, [rsp+4E8h+var_468]
0x180079b4e  mov     [rsp+4E8h+var_3B8], rax
0x180079b56  lea     rax, [rsp+4E8h+var_440]
0x180079b5e  mov     [rsp+4E8h+var_3B0], rax
0x180079b66  lea     rax, [rsp+4E8h+var_478+4]
0x180079b6b  mov     [rsp+4E8h+var_3A8], rax
0x180079b73  lea     rax, [rsp+4E8h+var_478]
0x180079b78  mov     [rsp+4E8h+var_3A0], rax
0x180079b80  lea     rax, [rsp+4E8h+var_480]
0x180079b85  mov     [rsp+4E8h+var_398], rax
0x180079b8d  lea     rax, [rsp+4E8h+var_480+4]
0x180079b92  mov     [rsp+4E8h+var_390], rax
0x180079b9a  lea     rax, [rsp+4E8h+var_470]
0x180079b9f  mov     [rsp+4E8h+var_388], rax
0x180079ba7  mov     word ptr [rsp+4E8h+var_380], 102h
0x180079bb1  cmp     [rsp+4E8h+var_440], r12
0x180079bb9  jz      loc_180079D7A
0x180079bbf  test    rsi, rsi
0x180079bc2  jz      loc_180079D7A
0x180079bc8  cmp     [rsi], ebx
0x180079bca  jb      loc_180079D7A
0x180079bd0  cmp     [rsi+10h], r12
0x180079bd4  jz      loc_180079D7A
0x180079bda  cmp     [rsi+8], r12
0x180079bde  jz      loc_180079D7A
0x180079be4  cmp     [rsi+4], r12d
0x180079be8  jz      loc_180079D7A
0x180079bee  test    rdi, rdi
0x180079bf1  jz      short loc_180079C24
0x180079bf3  cmp     [rdi], ebx
0x180079bf5  jb      loc_180079D7A
0x180079bfb  mov     eax, [rdi]
0x180079bfd  mov     dword ptr [rsp+4E8h+var_478+4], eax
0x180079c01  mov     edx, [rdi+28h]
0x180079c04  mov     dword ptr [rsp+4E8h+var_478], edx
0x180079c08  lea     rax, [rsp+4E8h+var_480+4]
0x180079c0d  mov     [rsp+4E8h+var_4C8], rax
0x180079c12  lea     r9, [rsp+4E8h+var_480]
0x180079c17  mov     rcx, [rsp+4E8h+var_468]
0x180079c1f  call    _CheckAttachmentOption
0x180079c24  mov     eax, ebx
0x180079c26  xchg    eax, cs:dword_1801AF098
0x180079c2c  test    eax, eax
0x180079c2e  jz      loc_180079CE6
0x180079c34  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl(void)'::`2'::impl
0x180079c3b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x180079c40  neg     al
0x180079c42  sbb     ebx, ebx
0x180079c44  and     ebx, 605E4h
0x180079c4a  add     ebx, 8001011Bh
0x180079c50  mov     [rsp+4E8h+var_484], ebx
0x180079c54  cmp     cs:Microsoft_Windows_WebAuthNEnableBits, r12b
0x180079c5b  jge     short loc_180079C84
0x180079c5d  mov     dword ptr [rsp+4E8h+var_4C0], ebx
0x180079c61  mov     dword ptr [rsp+4E8h+var_4C8], ebx
0x180079c65  lea     r9, aWebauthnauthen_20; "WebAuthNAuthenticatorGetAssertionActive"...
0x180079c6c  mov     r8, [rsp+4E8h+var_468]
0x180079c74  lea     rdx, EVENT_WEBAUTHN_ERROR
0x180079c7b  call    McTemplateU0jsdd_EventWriteTransfer
0x180079c80  mov     ebx, [rsp+4E8h+var_484]
0x180079c84  lea     rcx, [rsp+4E8h+var_3C8]
0x180079c8c  call    wil__details__ScopeExitFnGuard__WebAuthNAuthenticatorGetAssertion____56____lambda_4_____operator__
0x180079c91  nop
0x180079c92  lea     rcx, [rsp+4E8h+var_328]
0x180079c9a  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0IAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0IAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,140737488355328,5,_TlgReflectorTag_Param0IsHProvider>,140737488355328,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,140737488355328,5,_TlgReflectorTag_Param0IsHProvider>,140737488355328,5>(void)
0x180079c9f  nop
0x180079ca0  mov     [rsp+4E8h+var_3D8], r12b
0x180079ca8  lea     rcx, [rsp+4E8h+var_400]
0x180079cb0  call    _WebAuthNAuthenticatorMakeCredential____69____lambda_3___operator__
0x180079cb5  nop
0x180079cb6  lea     rcx, [rsp+4E8h+var_368]
0x180079cbe  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNAuthenticatorTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNAuthenticatorTest,_tip_WebAuthNAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNAuthenticatorTest,_tip_WebAuthNAuthenticatorTest>>(void)
0x180079cc3  nop
0x180079cc4  lea     rcx, [rsp+4E8h+var_460]
0x180079ccc  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNAuthenticatorTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNAuthenticatorTest,_tip_WebAuthNAuthenticatorTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNAuthenticatorTest,_tip_WebAuthNAuthenticatorTest>,wil::err_returncode_policy>(void)
0x180079cd1  nop
0x180079cd2  lea     rcx, [rsp+4E8h+var_458]
0x180079cda  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNUIPerformanceTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>,wil::err_returncode_policy>(void)
0x180079cdf  mov     eax, ebx
0x180079ce1  jmp     loc_18007A51B
0x180079ce6  mov     [rsp+4E8h+var_448], ebx
0x180079ced  mov     [rsp+4E8h+var_4C0], r14; struct _WEBAUTHN_ASSERTION **
0x180079cf2  mov     [rsp+4E8h+var_4C8], rdi; struct _WEBAUTHN_AUTHENTICATOR_GET_ASSERTION_OPTIONS *
0x180079cf7  mov     r9, rsi; struct _WEBAUTHN_CLIENT_DATA *
0x180079cfa  mov     r8, [rsp+4E8h+var_440]; unsigned __int16 *
0x180079d02  mov     rdx, r15; HWND
0x180079d05  mov     rcx, [rsp+4E8h+var_468]; struct _GUID *
0x180079d0d  call    ?I_WebAuthNAuthenticatorGetAssertionCtap@@YAJPEAU_GUID@@PEAUHWND__@@PEBGPEBU_WEBAUTHN_CLIENT_DATA@@PEBU_WEBAUTHN_AUTHENTICATOR_GET_ASSERTION_OPTIONS@@PEAPEAU_WEBAUTHN_ASSERTION@@@Z; I_WebAuthNAuthenticatorGetAssertionCtap(_GUID *,HWND__ *,ushort const *,_WEBAUTHN_CLIENT_DATA const *,_WEBAUTHN_AUTHENTICATOR_GET_ASSERTION_OPTIONS const *,_WEBAUTHN_ASSERTION * *)
0x180079d12  mov     ebx, eax
0x180079d14  mov     [rsp+4E8h+var_484], eax
0x180079d18  lea     rcx, [rsp+4E8h+var_3C8]
0x180079d20  call    wil__details__ScopeExitFnGuard__WebAuthNAuthenticatorGetAssertion____56____lambda_4_____operator__
0x180079d25  nop
0x180079d26  lea     rcx, [rsp+4E8h+var_328]
0x180079d2e  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0IAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0IAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,140737488355328,5,_TlgReflectorTag_Param0IsHProvider>,140737488355328,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,140737488355328,5,_TlgReflectorTag_Param0IsHProvider>,140737488355328,5>(void)
0x180079d33  nop
0x180079d34  mov     [rsp+4E8h+var_3D8], r12b
0x180079d3c  lea     rcx, [rsp+4E8h+var_400]
0x180079d44  call    _WebAuthNAuthenticatorMakeCredential____69____lambda_3___operator__
0x180079d49  nop
0x180079d4a  lea     rcx, [rsp+4E8h+var_368]
0x180079d52  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNAuthenticatorTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNAuthenticatorTest,_tip_WebAuthNAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNAuthenticatorTest,_tip_WebAuthNAuthenticatorTest>>(void)
0x180079d57  nop
0x180079d58  lea     rcx, [rsp+4E8h+var_460]
0x180079d60  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNAuthenticatorTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNAuthenticatorTest,_tip_WebAuthNAuthenticatorTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNAuthenticatorTest,_tip_WebAuthNAuthenticatorTest>,wil::err_returncode_policy>(void)
0x180079d65  nop
0x180079d66  lea     rcx, [rsp+4E8h+var_458]
0x180079d6e  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNUIPerformanceTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>,wil::err_returncode_policy>(void)
0x180079d73  mov     eax, ebx
0x180079d75  jmp     loc_18007A51B
0x180079d7a  mov     edi, 80090027h
0x180079d7f  mov     [rsp+4E8h+var_484], edi
0x180079d83  cmp     cs:Microsoft_Windows_WebAuthNEnableBits, r12b
0x180079d8a  jge     short loc_180079DB3
0x180079d8c  mov     dword ptr [rsp+4E8h+var_4C0], edi
0x180079d90  mov     dword ptr [rsp+4E8h+var_4C8], edi
0x180079d94  lea     r9, aWebauthnauthen_6; "WebAuthNAuthenticatorGetAssertionParame"...
  ... truncated ...
```
