# WebAuthNAuthenticatorMakeCredential

- ea: `0x18007a550`
- end: `0x18007bc29`
- name: `WebAuthNAuthenticatorMakeCredential`
- size: `5849`
- prototype: ``
- caller_count: `0`
- callee_count: `51`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002220`
- `0x180019938`
- `0x1800291e8`
- `0x180044658`
- `0x1800463d4`
- `0x180046768`
- `0x1800467e0`
- `0x180046820`
- `0x18004f5b4`
- `0x180055188`
- `0x180067c90`
- `0x180067e24`
- `0x180068018`
- `0x1800681f8`
- `0x18006823c`
- `0x180069e50`
- `0x18006a458`
- `0x18006b0c8`
- `0x18006b150`
- `0x18006b1d8`
- `0x18006cfd4`
- `0x180072a34`
- `0x1800745c0`
- `0x180075264`
- `0x180075380`
- `0x180075b38`
- `0x180075b54`
- `0x180075d78`
- `0x180075db0`
- `0x180075dd8`
- `0x180075e80`
- `0x1800761b4`
- `0x180076234`
- `0x180076328`
- `0x18007655c`
- `0x1800766cc`
- `0x1800769c8`
- `0x180077ea8`
- `0x180077f4c`
- `0x1800780a0`
- `0x1800793ec`
- `0x180079444`
- `0x1800794d8`
- `0x180079530`
- `0x18007969c`
- `0x18007a550`
- `0x180095468`
- `0x1800c0e30`
- `0x1800c0e78`
- `0x1800c0f88`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18007ad18`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18007ad3e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18007b84a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18007b870`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18007ad18`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18007ad3e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18007b84a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18007b870`
- `RPCRT4!UuidCreate` at `0x18007a761`
- `RPCRT4!UuidCreate` at `0x18007b197`
- `RPCRT4!UuidCreate` at `0x18007a761`
- `RPCRT4!UuidCreate` at `0x18007b197`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x18007a78a`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x18007b1db`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x18007a78a`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x18007b1db`

## pseudocode

```c
// Hidden C++ exception states: #wind=18 #try_helpers=1
__int64 __fastcall WebAuthNAuthenticatorMakeCredential(
        HWND a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        struct _WEBAUTHN_CLIENT_DATA *a5,
        struct _WEBAUTHN_AUTHENTICATOR_MAKE_CREDENTIAL_OPTIONS *a6,
        struct _WEBAUTHN_CREDENTIAL_ATTESTATION **a7)
{
  const char *v10; // rdx
  __int64 v11; // r8
  const char *v12; // rax
  wil::TraceLoggingProviderFido **v13; // rax
  wil::TraceLoggingProviderFido **v14; // r14
  wil::TraceLoggingProviderFido **v15; // rax
  wil::TraceLoggingProviderFido **v16; // r14
  wil::TraceLoggingProviderFido **v17; // rax
  wil::TraceLoggingProviderFido **v18; // r14
  __int64 v19; // r8
  __int64 v20; // r9
  _DWORD *v21; // r9
  char IsEnabled; // al
  __int64 v23; // rcx
  int v24; // r8d
  __int64 v25; // rdx
  const unsigned __int16 **v26; // r14
  unsigned int v27; // ebx
  __int64 v28; // rcx
  int v29; // eax
  int v30; // eax
  char v31; // al
  int v32; // ecx
  unsigned int CredentialCtap; // ebx
  __int64 v34; // rdx
  _QWORD *v36; // rax
  bool v37; // zf
  const char *v38; // rdx
  __int64 v39; // r8
  const char *v40; // rax
  wil::TraceLoggingProviderFido **v41; // rax
  wil::TraceLoggingProviderFido **v42; // r14
  wil::TraceLoggingProviderFido **v43; // rax
  wil::TraceLoggingProviderFido **v44; // r14
  wil::TraceLoggingProviderFido **v45; // rax
  wil::TraceLoggingProviderFido **v46; // r14
  __int64 v47; // rdx
  __int64 v48; // r8
  __int64 v49; // r8
  __int64 v50; // r9
  _DWORD *v51; // r9
  __int64 v52; // rax
  __int64 v53; // rcx
  int v54; // r8d
  const unsigned __int16 **v55; // r14
  unsigned int v56; // ebx
  __int64 v57; // rcx
  char v58; // al
  __int64 v59; // rdx
  int v60; // ecx
  __int64 v61; // rdx
  char v62; // [rsp+60h] [rbp-578h] BYREF
  char v63[3]; // [rsp+61h] [rbp-577h] BYREF
  int v64; // [rsp+64h] [rbp-574h] BYREF
  int v65; // [rsp+68h] [rbp-570h] BYREF
  char v66[8]; // [rsp+70h] [rbp-568h] BYREF
  __int64 v67; // [rsp+78h] [rbp-560h] BYREF
  __int64 v68; // [rsp+80h] [rbp-558h] BYREF
  int v69; // [rsp+88h] [rbp-550h] BYREF
  int v70; // [rsp+8Ch] [rbp-54Ch] BYREF
  int v71; // [rsp+90h] [rbp-548h] BYREF
  int v72; // [rsp+94h] [rbp-544h] BYREF
  wil::TraceLoggingProviderFido *v73; // [rsp+98h] [rbp-540h] BYREF
  char v74; // [rsp+A0h] [rbp-538h]
  wil::TraceLoggingProviderFido *v75; // [rsp+A8h] [rbp-530h] BYREF
  char v76; // [rsp+B0h] [rbp-528h]
  wil::TraceLoggingProviderFido *v77; // [rsp+B8h] [rbp-520h] BYREF
  char v78; // [rsp+C0h] [rbp-518h]
  int v79; // [rsp+C8h] [rbp-510h] BYREF
  int v80; // [rsp+CCh] [rbp-50Ch] BYREF
  int v81; // [rsp+D0h] [rbp-508h] BYREF
  int v82; // [rsp+D4h] [rbp-504h] BYREF
  int v83; // [rsp+D8h] [rbp-500h] BYREF
  int v84; // [rsp+DCh] [rbp-4FCh] BYREF
  struct _GUID *v85; // [rsp+E0h] [rbp-4F8h] BYREF
  struct _GUID *p_Uuid; // [rsp+E8h] [rbp-4F0h] BYREF
  __int64 v87; // [rsp+F0h] [rbp-4E8h] BYREF
  int v88; // [rsp+F8h] [rbp-4E0h] BYREF
  int v89; // [rsp+FCh] [rbp-4DCh] BYREF
  __int64 v90; // [rsp+100h] [rbp-4D8h] BYREF
  HWND v91; // [rsp+108h] [rbp-4D0h]
  const unsigned __int16 *v92; // [rsp+110h] [rbp-4C8h] BYREF
  const unsigned __int16 *v93; // [rsp+118h] [rbp-4C0h] BYREF
  int *v94; // [rsp+120h] [rbp-4B8h] BYREF
  int *v95; // [rsp+128h] [rbp-4B0h]
  int *v96; // [rsp+130h] [rbp-4A8h]
  __int64 *v97; // [rsp+138h] [rbp-4A0h]
  int *v98; // [rsp+140h] [rbp-498h]
  char v99; // [rsp+148h] [rbp-490h]
  struct _GUID *v100; // [rsp+150h] [rbp-488h] BYREF
  const unsigned __int16 *v101; // [rsp+158h] [rbp-480h] BYREF
  struct _GUID *v102; // [rsp+160h] [rbp-478h] BYREF
  const unsigned __int16 *v103; // [rsp+168h] [rbp-470h] BYREF
  struct _WEBAUTHN_CREDENTIAL_ATTESTATION **v104; // [rsp+170h] [rbp-468h]
  _QWORD v105[10]; // [rsp+180h] [rbp-458h] BYREF
  char v106; // [rsp+1D0h] [rbp-408h]
  char v107[8]; // [rsp+1E0h] [rbp-3F8h] BYREF
  char v108[8]; // [rsp+1E8h] [rbp-3F0h] BYREF
  _QWORD v109[9]; // [rsp+1F0h] [rbp-3E8h] BYREF
  __int16 v110; // [rsp+238h] [rbp-3A0h]
  _BYTE v111[64]; // [rsp+240h] [rbp-398h] BYREF
  UUID Uuid; // [rsp+280h] [rbp-358h] BYREF
  UUID v113; // [rsp+290h] [rbp-348h] BYREF
  int v114; // [rsp+2A0h] [rbp-338h] BYREF
  char v115; // [rsp+2A4h] [rbp-334h]
  char v116; // [rsp+2A8h] [rbp-330h] BYREF
  _DWORD v117[4]; // [rsp+2B8h] [rbp-320h] BYREF
  int v118; // [rsp+2C8h] [rbp-310h] BYREF
  char v119; // [rsp+2CCh] [rbp-30Ch]
  char v120; // [rsp+2D0h] [rbp-308h] BYREF
  _DWORD v121[4]; // [rsp+2E0h] [rbp-2F8h] BYREF
  _QWORD v122[42]; // [rsp+2F0h] [rbp-2E8h] BYREF
  _BYTE v123[336]; // [rsp+440h] [rbp-198h] BYREF

  v91 = a1;
  v104 = a7;
  tip2::start<tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>>>(v66);
  *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>>::operator->(
                           v66,
                           &v93)
            + 272LL) = 0;
  tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>>(&v93);
  v78 = 0;
  v76 = 0;
  v74 = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SharedPasskeyDependencies>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SharedPasskeyDependencies>::GetImpl'::`2'::impl) )
  {
    v65 = 0;
    Uuid = 0;
    p_Uuid = 0;
    v82 = 0;
    v72 = 1;
    v71 = 1;
    v88 = 0;
    v62 = 0;
    v89 = 0;
    v70 = 0;
    v93 = &dword_18015030C;
    v81 = 0;
    v80 = 0;
    v87 = 0;
    *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNAuthenticatorTest,_tip_WebAuthNAuthenticatorTest>>::operator->(
                             &v87,
                             &v92)
              + 272LL) = 1;
    tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNAuthenticatorTest,_tip_WebAuthNAuthenticatorTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNAuthenticatorTest,_tip_WebAuthNAuthenticatorTest>>(&v92);
    tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNAuthenticatorTest,_tip_WebAuthNAuthenticatorTest>>::start(
      &v87,
      &v113);
    tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNAuthenticatorTest,_tip_WebAuthNAuthenticatorTest>>::watch_errors(
      &v87,
      v111);
    *a7 = 0;
    v94 = &v82;
    v95 = &v81;
    v96 = &v80;
    v97 = &v87;
    v98 = &v65;
    v99 = 1;
    if ( (unsigned __int8)tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::operator bool(v66) )
      Uuid = *(UUID *)tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::test_id(
                        v66,
                        &v113);
    else
      UuidCreate(&Uuid);
    p_Uuid = &Uuid;
    if ( (unsigned __int8)IsWinStationIsSessionRemoteablePresent()
      && (unsigned __int8)WinStationIsSessionRemoteable(0, 0xFFFFFFFFLL, &v62)
      && v62 )
    {
      v88 = 1;
      v12 = tip2::details::reason_string((tip2::details *)"WebAuthNUIPerformanceTest::reason::remote_session", v10);
      tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(
        v66,
        4,
        v12);
    }
    if ( a6 && *(_DWORD *)a6 >= 5u && *((_DWORD *)a6 + 23) )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(
                              `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl,
                              v10,
                              v11) )
      {
        v13 = (wil::TraceLoggingProviderFido **)FidoTraceProvider::Suppress(v107);
        v14 = v13;
        if ( v78 )
        {
          if ( v77 )
          {
            wil::TraceLoggingProviderFido::RemoveSuppression(v77);
            v77 = 0;
          }
          v77 = *v14;
          *v14 = 0;
        }
        else
        {
          v77 = 0;
          v77 = *v13;
          *v13 = 0;
          v78 = 1;
        }
        wil::TraceLoggingProviderFido::SuppressionReverter::~SuppressionReverter((wil::TraceLoggingProviderFido::SuppressionReverter *)v107);
        v15 = (wil::TraceLoggingProviderFido **)FidoRestrictedCoreProvider::Suppress(&v100);
        v16 = v15;
        if ( v76 )
        {
          if ( v75 )
          {
            wil::TraceLoggingProviderFido::RemoveSuppression(v75);
            v75 = 0;
          }
          v75 = *v16;
          *v16 = 0;
        }
        else
        {
          v75 = 0;
          v75 = *v15;
          *v15 = 0;
          v76 = 1;
        }
        wil::TraceLoggingProviderFido::SuppressionReverter::~SuppressionReverter((wil::TraceLoggingProviderFido::SuppressionReverter *)&v100);
        v17 = (wil::TraceLoggingProviderFido **)FidoPluginProvider::Suppress(&v101);
        v18 = v17;
        if ( v74 )
        {
          if ( v73 )
          {
            wil::TraceLoggingProviderFido::RemoveSuppression(v73);
            v73 = 0;
          }
          v73 = *v18;
          *v18 = 0;
        }
        else
        {
          v73 = 0;
          v73 = *v17;
          *v17 = 0;
          v74 = 1;
        }
        wil::TraceLoggingProviderFido::SuppressionReverter::~SuppressionReverter((wil::TraceLoggingProviderFido::SuppressionReverter *)&v101);
      }
      else
      {
        I_DisableTraceLogging();
        v80 = 1;
      }
      if ( !(unsigned int)I_IsDebugModeConfigured() )
      {
        I_DisableEventLogging();
        v81 = 1;
      }
    }
    v114 = 0;
    v115 = 0;
    _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,140737488355328,5,_TlgReflectorTag_Param0IsHProvider>,140737488355328,5>::zInternalStart(&v114);
    if ( (unsigned int)dword_1801AB180 > 5
      && (unsigned __int8)tlgKeywordOn(&dword_1801AB180, 0x800000000000LL, v19, v20) )
    {
      v84 = v71;
      v83 = v72;
      v68 = __PAIR64__(v88, v70);
      v101 = v93;
      v100 = p_Uuid;
      v67 = __PAIR64__(v89, v65);
      if ( v115 && (v117[0] || v117[1] || v117[2] || v117[3]) )
        v21 = v117;
      else
        LODWORD(v21) = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1801AB180,
        (unsigned int)byte_1801856AB,
        (unsigned int)&v116,
        (_DWORD)v21,
        (__int64)&v67,
        (__int64)&v100,
        (__int64)&v101,
        (__int64)&v67 + 4,
        (__int64)&v68,
        (__int64)&v83,
        (__int64)&v84,
        (__int64)&v68 + 4);
    }
    v109[0] = &v114;
    v109[1] = &v65;
    v109[2] = &p_Uuid;
    v109[3] = &v93;
    v109[4] = &v89;
    v109[5] = &v70;
    v109[6] = &v72;
    v109[7] = &v71;
    v109[8] = &v88;
    v110 = 258;
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_MakeCredentialPRF>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_MakeCredentialPRF>::GetImpl'::`2'::impl);
    v25 = 0;
    if ( IsEnabled )
    {
      if ( !a2 )
        goto LABEL_61;
      if ( !*(_DWORD *)a2 )
        goto LABEL_61;
      v26 = (const unsigned __int16 **)(a2 + 8);
      if ( !*(_QWORD *)(a2 + 8)
        || !a3
        || !*(_DWORD *)a3
        || !*(_DWORD *)(a3 + 4)
        || !*(_QWORD *)(a3 + 8)
        || !a4
        || !*(_DWORD *)a4
        || !*(_QWORD *)(a4 + 8)
        || !a5
        || !*(_DWORD *)a5
        || !*((_QWORD *)a5 + 2)
        || !*((_QWORD *)a5 + 1)
        || !*((_DWORD *)a5 + 1)
        || !v91 )
      {
        goto LABEL_61;
      }
      if ( a6 )
      {
        if ( !*(_DWORD *)a6 )
        {
LABEL_61:
          v27 = -2146893785;
          v65 = -2146893785;
          if ( Microsoft_Windows_WebAuthNEnableBits < 0 )
          {
            McTemplateU0jsdd_EventWriteTransfer(
              v23,
              (unsigned int)EVENT_WEBAUTHN_ERROR,
              (_DWORD)p_Uuid,
              (unsigned int)"WebAuthNAuthenticatorMakeCredentialParametersCheck",
              39,
              39);
            v27 = v65;
          }
LABEL_94:
          wil::details::ScopeExitFnGuard__WebAuthNAuthenticatorMakeCredential_::_69_::_lambda_4___::operator()(
            v109,
            v25);
          _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,140737488355328,5,_TlgReflectorTag_Param0IsHProvider>,140737488355328,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,140737488355328,5,_TlgReflectorTag_Param0IsHProvider>,140737488355328,5>(&v114);
          v99 = 0;
          WebAuthNAuthenticatorMakeCredential_::_69_::_lambda_3_::operator()(&v94);
          tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNAuthenticatorTest,_tip_WebAuthNAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNAuthenticatorTest,_tip_WebAuthNAuthenticatorTest>>(v111);
          wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNAuthenticatorTest,_tip_WebAuthNAuthenticatorTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNAuthenticatorTest,_tip_WebAuthNAuthenticatorTest>,wil::err_returncode_policy>(&v87);
          std::_Optional_destruct_base<wil::TraceLoggingProviderFido::SuppressionReverter,0>::~_Optional_destruct_base<wil::TraceLoggingProviderFido::SuppressionReverter,0>(&v73);
          std::_Optional_destruct_base<wil::TraceLoggingProviderFido::SuppressionReverter,0>::~_Optional_destruct_base<wil::TraceLoggingProviderFido::SuppressionReverter,0>(&v75);
          std::_Optional_destruct_base<wil::TraceLoggingProviderFido::SuppressionReverter,0>::~_Optional_destruct_base<wil::TraceLoggingProviderFido::SuppressionReverter,0>(&v77);
          wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>,wil::err_returncode_policy>(v66);
          return v27;
        }
        goto LABEL_86;
      }
LABEL_87:
      v93 = *v26;
      if ( !_InterlockedExchange(&dword_1801AF098, 1) )
      {
        v82 = 1;
        CredentialCtap = I_WebAuthNAuthenticatorMakeCredentialCtap(
                           p_Uuid,
                           v91,
                           (const struct _WEBAUTHN_RP_ENTITY_INFORMATION *)a2,
                           (const struct _WEBAUTHN_USER_ENTITY_INFORMATION *)a3,
                           (const struct _WEBAUTHN_COSE_CREDENTIAL_PARAMETERS *)a4,
                           a5,
                           a6,
                           v104);
        v65 = CredentialCtap;
        wil::details::ScopeExitFnGuard__WebAuthNAuthenticatorMakeCredential_::_69_::_lambda_4___::operator()(v109, v34);
        _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,140737488355328,5,_TlgReflectorTag_Param0IsHProvider>,140737488355328,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,140737488355328,5,_TlgReflectorTag_Param0IsHProvider>,140737488355328,5>(&v114);
        v99 = 0;
        WebAuthNAuthenticatorMakeCredential_::_69_::_lambda_3_::operator()(&v94);
        tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNAuthenticatorTest,_tip_WebAuthNAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNAuthenticatorTest,_tip_WebAuthNAuthenticatorTest>>(v111);
        wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNAuthenticatorTest,_tip_WebAuthNAuthenticatorTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNAuthenticatorTest,_tip_WebAuthNAuthenticatorTest>,wil::err_returncode_policy>(&v87);
        std::_Optional_destruct_base<wil::TraceLoggingProviderFido::SuppressionReverter,0>::~_Optional_destruct_base<wil::TraceLoggingProviderFido::SuppressionReverter,0>(&v73);
        std::_Optional_destruct_base<wil::TraceLoggingProviderFido::SuppressionReverter,0>::~_Optional_destruct_base<wil::TraceLoggingProviderFido::SuppressionReverter,0>(&v75);
        std::_Optional_destruct_base<wil::TraceLoggingProviderFido::SuppressionReverter,0>::~_Optional_destruct_base<wil::TraceLoggingProviderFido::SuppressionReverter,0>(&v77);
        wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>,wil::err_returncode_policy>(v66);
        return CredentialCtap;
      }
      v31 = -(char)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl);
      v27 = v31 != 0 ? -2147023105 : -2147417829;
      v65 = v27;
      if ( Microsoft_Windows_WebAuthNEnableBits < 0 )
      {
        McTemplateU0jsdd_EventWriteTransfer(
          v32,
          (unsigned int)EVENT_WEBAUTHN_ERROR,
          (_DWORD)p_Uuid,
          (unsigned int)"WebAuthNAuthenticatorMakeCredentialActiveCheck",
          v31 != 0 ? -1 : 27,
          v31 != 0 ? -1 : 27);
        v27 = v65;
      }
      goto LABEL_94;
    }
    if ( a2 )
    {
      if ( *(_DWORD *)a2 )
      {
        v26 = (const unsigned __int16 **)(a2 + 8);
        if ( *(_QWORD *)(a2 + 8) )
        {
          if ( a3 )
          {
            if ( *(_DWORD *)a3 )
            {
              if ( *(_DWORD *)(a3 + 4) )
              {
                if ( *(_QWORD *)(a3 + 8) )
                {
                  v28 = *(_QWORD *)(a3 + 24);
                  if ( !v28 || (v29 = _o__wcsnicmp(v28, L"http://", 7), v25 = 0, v29) )
                  {
                    v23 = *(_QWORD *)(a2 + 24);
                    if ( !v23 || (v30 = _o__wcsnicmp(v23, L"http://", 7), v25 = 0, v30) )
                    {
                      if ( a4
                        && *(_DWORD *)a4
                        && *(_QWORD *)(a4 + 8)
                        && a5
                        && *(_DWORD *)a5
                        && *((_QWORD *)a5 + 2)
                        && *((_QWORD *)a5 + 1)
                        && *((_DWORD *)a5 + 1)
                        && v91 )
                      {
                        if ( !a6 )
                          goto LABEL_87;
                        if ( *(_DWORD *)a6 )
                        {
LABEL_86:
                          v89 = *(_DWORD *)a6;
                          v70 = *((_DWORD *)a6 + 10);
                          CheckAttachmentOption((_DWORD)p_Uuid, v70, v24, (unsigned int)&v72, (__int64)&v71);
                          goto LABEL_87;
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    v27 = -2146893785;
    v65 = -2146893785;
    if ( Microsoft_Windows_WebAuthNEnableBits < 0 )
    {
      McTemplateU0jsdd_EventWriteTransfer(
        v23,
        (unsigned int)EVENT_WEBAUTHN_ERROR,
        (_DWORD)p_Uuid,
        (unsigned int)"WebAuthNAuthenticatorMakeCredentialParametersCheck",
        39,
        39);
      v27 = v65;
    }
    goto LABEL_94;
  }
  v64 = 0;
  v113 = 0;
  v85 = 0;
  v68 = 1;
  v69 = 0;
  v63[0] = 0;
  v79 = 0;
  v67 = 0x100000000LL;
  v92 = &dword_18015030C;
  v84 = 0;
  v83 = 0;
  v90 = 0;
  v36 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNAuthenticatorMakeCredentialTest,_tip_WebAuthNAuthenticatorMakeCredentialTest>>::ensure_data(&v90);
  tip2::details::shared_data<1,0,0>::start(*v36 + 8LL, &Uuid);
  tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNAuthenticatorMakeCredentialTest,_tip_WebAuthNAuthenticatorMakeCredentialTest>>::watch_errors(
    &v90,
    v109);
  *a7 = 0;
  v94 = (int *)&v68 + 1;
  v95 = &v84;
  v96 = &v83;
  v97 = &v90;
  v98 = &v64;
  v99 = 1;
  if ( (unsigned __int8)tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::operator bool(v66) )
    v113 = *(UUID *)tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::test_id(
                      v66,
                      &Uuid);
  else
    UuidCreate(&v113);
  v85 = &v113;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
  {
    v37 = !ShouldSendRequestToRemoteSession(0);
  }
  else
  {
    if ( !(unsigned __int8)IsWinStationIsSessionRemoteablePresent()
      || !(unsigned __int8)WinStationIsSessionRemoteable(0, 0xFFFFFFFFLL, v63) )
    {
      goto LABEL_105;
    }
    v37 = v63[0] == 0;
  }
  if ( !v37 )
  {
    v69 = 1;
    v40 = tip2::details::reason_string((tip2::details *)"WebAuthNUIPerformanceTest::reason::remote_session", v38);
    tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(
      v66,
      4,
      v40);
  }
LABEL_105:
  if ( a6 && *(_DWORD *)a6 >= 5u && *((_DWORD *)a6 + 23) )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(
                            `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl,
                            v38,
                            v39) )
    {
      v41 = (wil::TraceLoggingProviderFido **)FidoTraceProvider::Suppress(v108);
      v42 = v41;
      if ( v78 )
      {
        if ( v77 )
        {
          wil::TraceLoggingProviderFido::RemoveSuppression(v77);
          v77 = 0;
        }
        v77 = *v42;
        *v42 = 0;
      }
      else
      {
        v77 = 0;
        v77 = *v41;
        *v41 = 0;
        v78 = 1;
      }
      wil::TraceLoggingProviderFido::SuppressionReverter::~SuppressionReverter((wil::TraceLoggingProviderFido::SuppressionReverter *)v108);
      v43 = (wil::TraceLoggingProviderFido **)FidoRestrictedCoreProvider::Suppress(&v102);
      v44 = v43;
      if ( v76 )
      {
        if ( v75 )
        {
          wil::TraceLoggingProviderFido::RemoveSuppression(v75);
          v75 = 0;
        }
        v75 = *v44;
        *v44 = 0;
      }
      else
      {
        v75 = 0;
        v75 = *v43;
        *v43 = 0;
        v76 = 1;
      }
      wil::TraceLoggingProviderFido::SuppressionReverter::~SuppressionReverter((wil::TraceLoggingProviderFido::SuppressionReverter *)&v102);
      v45 = (wil::TraceLoggingProviderFido **)FidoPluginProvider::Suppress(&v103);
      v46 = v45;
      if ( v74 )
      {
        if ( v73 )
        {
          wil::TraceLoggingProviderFido::RemoveSuppression(v73);
          v73 = 0;
        }
        v73 = *v46;
        *v46 = 0;
      }
      else
      {
        v73 = 0;
        v73 = *v45;
        *v45 = 0;
        v74 = 1;
      }
      wil::TraceLoggingProviderFido::SuppressionReverter::~SuppressionReverter((wil::TraceLoggingProviderFido::SuppressionReverter *)&v103);
    }
    else
    {
      I_DisableTraceLogging();
      v83 = 1;
    }
    if ( !(unsigned int)I_IsDebugModeConfigured() )
    {
      I_DisableEventLogging();
      v84 = 1;
    }
  }
  wil::ActivityBase<FidoTraceProvider,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FidoTraceProvider,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v122);
  v122[0] = &FidoTraceProvider::WebMakeCredential::`vftable';
  v118 = 0;
  v119 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl,
                          v47,
                          v48) )
  {
    v52 = FidoTraceProvider::WebMakeCredential::Start<long &,_GUID &,unsigned short const * &,unsigned long &,unsigned long &,int &,int &,int &>(
            (FidoTraceProvider::WebMakeCredential *)v123,
            (__int64)&v79,
            (__int64)&v67,
            (__int64)&v68,
            (__int64)&v67 + 4,
            (__int64)&v69);
    FidoTraceProvider::WebMakeCredential::operator=(v122, v52);
    FidoTraceProvider::WebMakeCredential::~WebMakeCredential((FidoTraceProvider::WebMakeCredential *)v123);
  }
  else
  {
    _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,140737488355328,5,_TlgReflectorTag_Param0IsHProvider>,140737488355328,5>::zInternalStart(&v118);
    if ( (unsigned int)dword_1801AB180 > 5
      && (unsigned __int8)tlgKeywordOn(&dword_1801AB180, 0x800000000000LL, v49, v50) )
    {
      v82 = v69;
      v81 = HIDWORD(v67);
      v80 = v68;
      v72 = v67;
      v71 = v79;
      v103 = v92;
      v102 = v85;
      v70 = v64;
      if ( v119 && (v121[0] || v121[1] || v121[2] || v121[3]) )
        v51 = v121;
      else
        LODWORD(v51) = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1801AB180,
        (unsigned int)byte_18018572B,
        (unsigned int)&v120,
        (_DWORD)v51,
        (__int64)&v70,
        (__int64)&v102,
        (__int64)&v103,
        (__int64)&v71,
        (__int64)&v72,
        (__int64)&v80,
        (__int64)&v81,
        (__int64)&v82);
    }
  }
  v105[0] = v122;
  v105[1] = &v64;
  v105[2] = &v85;
  v105[3] = &v92;
  v105[4] = &v79;
  v105[5] = &v67;
  v105[6] = &v68;
  v105[7] = (char *)&v67 + 4;
  v105[8] = &v69;
  v105[9] = &v118;
  v106 = 1;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MakeCredentialPRF>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_MakeCredentialPRF>::GetImpl'::`2'::impl) )
  {
    if ( !a2 )
      goto LABEL_196;
    if ( !*(_DWORD *)a2 )
      goto LABEL_196;
    v55 = (const unsigned __int16 **)(a2 + 8);
    if ( !*(_QWORD *)(a2 + 8) )
      goto LABEL_196;
    if ( !a3 )
      goto LABEL_196;
    if ( !*(_DWORD *)a3 )
      goto LABEL_196;
    if ( !*(_DWORD *)(a3 + 4) )
      goto LABEL_196;
    if ( !*(_QWORD *)(a3 + 8) )
      goto LABEL_196;
    v57 = *(_QWORD *)(a3 + 24);
    if ( v57 )
    {
      if ( !(unsigned int)_o__wcsnicmp(v57, L"http://", 7) )
        goto LABEL_196;
    }
    v53 = *(_QWORD *)(a2 + 24);
    if ( v53 )
    {
      if ( !(unsigned int)_o__wcsnicmp(v53, L"http://", 7) )
        goto LABEL_196;
    }
    if ( !a4
      || !*(_DWORD *)a4
      || !*(_QWORD *)(a4 + 8)
      || !a5
      || !*(_DWORD *)a5
      || !*((_QWORD *)a5 + 2)
      || !*((_QWORD *)a5 + 1)
      || !*((_DWORD *)a5 + 1)
      || !v91 )
    {
      goto LABEL_196;
    }
    if ( !a6 )
      goto LABEL_187;
    if ( !*(_DWORD *)a6 )
    {
LABEL_196:
      v56 = -2146893785;
      v64 = -2146893785;
      if ( Microsoft_Windows_WebAuthNEnableBits < 0 )
      {
        McTemplateU0jsdd_EventWriteTransfer(
          v53,
          (unsigned int)EVENT_WEBAUTHN_ERROR,
          (_DWORD)v85,
          (unsigned int)"WebAuthNAuthenticatorMakeCredentialParametersCheck",
          39,
          39);
        v56 = v64;
      }
      if ( v106 )
      {
        v106 = 0;
        WebAuthNAuthenticatorMakeCredential_::_6_::_lambda_2_::operator()(v105, 0);
      }
      goto LABEL_200;
    }
    goto LABEL_186;
  }
  if ( !a2 )
    goto LABEL_159;
  if ( !*(_DWORD *)a2 )
    goto LABEL_159;
  v55 = (const unsigned __int16 **)(a2 + 8);
  if ( !*(_QWORD *)(a2 + 8)
    || !a3
    || !*(_DWORD *)a3
    || !*(_DWORD *)(a3 + 4)
    || !*(_QWORD *)(a3 + 8)
    || !a4
    || !*(_DWORD *)a4
    || !*(_QWORD *)(a4 + 8)
    || !a5
    || !*(_DWORD *)a5
    || !*((_QWORD *)a5 + 2)
    || !*((_QWORD *)a5 + 1)
    || !*((_DWORD *)a5 + 1)
    || !v91 )
  {
    goto LABEL_159;
  }
  if ( !a6 )
  {
LABEL_187:
    v92 = *v55;
    if ( _InterlockedExchange(&dword_1801AF098, 1) )
    {
      v58 = -(char)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl);
      v56 = v58 != 0 ? -2147023105 : -2147417829;
      v64 = v56;
      if ( Microsoft_Windows_WebAuthNEnableBits < 0 )
      {
        McTemplateU0jsdd_EventWriteTransfer(
          v60,
          (unsigned int)EVENT_WEBAUTHN_ERROR,
          (_DWORD)v85,
          (unsigned int)"WebAuthNAuthenticatorMakeCredentialActiveCheck",
          v58 != 0 ? -1 : 27,
          v58 != 0 ? -1 : 27);
        v56 = v64;
      }
      if ( v106 )
      {
        v106 = 0;
        WebAuthNAuthenticatorMakeCredential_::_6_::_lambda_2_::operator()(v105, v59);
      }
    }
    else
    {
      HIDWORD(v68) = 1;
      v56 = I_WebAuthNAuthenticatorMakeCredentialCtap(
              v85,
              v91,
              (const struct _WEBAUTHN_RP_ENTITY_INFORMATION *)a2,
              (const struct _WEBAUTHN_USER_ENTITY_INFORMATION *)a3,
              (const struct _WEBAUTHN_COSE_CREDENTIAL_PARAMETERS *)a4,
              a5,
              a6,
              v104);
      v64 = v56;
      if ( v106 )
      {
        v106 = 0;
        WebAuthNAuthenticatorMakeCredential_::_6_::_lambda_2_::operator()(v105, v61);
      }
    }
    goto LABEL_200;
  }
  if ( *(_DWORD *)a6 )
  {
LABEL_186:
    v79 = *(_DWORD *)a6;
    LODWORD(v67) = *((_DWORD *)a6 + 10);
    CheckAttachmentOption((_DWORD)v85, v67, v54, (unsigned int)&v68, (__int64)&v67 + 4);
    goto LABEL_187;
  }
LABEL_159:
  v56 = -2146893785;
  v64 = -2146893785;
  if ( Microsoft_Windows_WebAuthNEnableBits < 0 )
  {
    McTemplateU0jsdd_EventWriteTransfer(
      v53,
      (unsigned int)EVENT_WEBAUTHN_ERROR,
      (_DWORD)v85,
      (unsigned int)"WebAuthNAuthenticatorMakeCredentialParametersCheck",
      39,
      39);
    v56 = v64;
  }
  if ( v106 )
  {
    v106 = 0;
    WebAuthNAuthenticatorMakeCredential_::_6_::_lambda_2_::operator()(v105, 0);
  }
LABEL_200:
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,140737488355328,5,_TlgReflectorTag_Param0IsHProvider>,140737488355328,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,140737488355328,5,_TlgReflectorTag_Param0IsHProvider>,140737488355328,5>(&v118);
  FidoTraceProvider::WebMakeCredential::~WebMakeCredential((FidoTraceProvider::WebMakeCredential *)v122);
  v99 = 0;
  WebAuthNAuthenticatorMakeCredential_::_6_::_lambda_1_::operator()(&v94);
  tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNAuthenticatorMakeCredentialTest,_tip_WebAuthNAuthenticatorMakeCredentialTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNAuthenticatorMakeCredentialTest,_tip_WebAuthNAuthenticatorMakeCredentialTest>>(v109);
  wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNAuthenticatorMakeCredentialTest,_tip_WebAuthNAuthenticatorMakeCredentialTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNAuthenticatorMakeCredentialTest,_tip_WebAuthNAuthenticatorMakeCredentialTest>,wil::err_returncode_policy>(&v90);
  std::_Optional_destruct_base<wil::TraceLoggingProviderFido::SuppressionReverter,0>::~_Optional_destruct_base<wil::TraceLoggingProviderFido::SuppressionReverter,0>(&v73);
  std::_Optional_destruct_base<wil::TraceLoggingProviderFido::SuppressionReverter,0>::~_Optional_destruct_base<wil::TraceLoggingProviderFido::SuppressionReverter,0>(&v75);
  std::_Optional_destruct_base<wil::TraceLoggingProviderFido::SuppressionReverter,0>::~_Optional_destruct_base<wil::TraceLoggingProviderFido::SuppressionReverter,0>(&v77);
  wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>,wil::err_returncode_policy>(v66);
  return v56;
}

```

## disassembly

```asm
0x18007a550  push    rbx
0x18007a552  push    rsi
0x18007a553  push    rdi
0x18007a554  push    r12
0x18007a556  push    r13
0x18007a558  push    r14
0x18007a55a  push    r15
0x18007a55c  sub     rsp, 5A0h
0x18007a563  mov     rax, cs:__security_cookie
0x18007a56a  xor     rax, rsp
0x18007a56d  mov     [rsp+5D8h+var_48], rax
0x18007a575  mov     r12, r9
0x18007a578  mov     r15, r8
0x18007a57b  mov     r13, rdx
0x18007a57e  mov     [rsp+5D8h+var_4D0], rcx
0x18007a586  mov     rbx, [rsp+5D8h+arg_20]
0x18007a58e  mov     rsi, [rsp+5D8h+arg_28]
0x18007a596  mov     r14, [rsp+5D8h+arg_30]
0x18007a59e  mov     [rsp+5D8h+var_468], r14
0x18007a5a6  lea     rcx, [rsp+5D8h+var_568]
0x18007a5ab  call    ??$start@V?$tip_test@V?$merged_data@U_tip_WebAuthNUIPerformanceTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?AV?$tip_test@V?$merged_data@U_tip_WebAuthNUIPerformanceTest@@U1@@details@tip2@@@0@XZ; tip2::start<tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>>>(void)
0x18007a5b0  nop
0x18007a5b1  lea     rdx, [rsp+5D8h+var_4C0]
0x18007a5b9  lea     rcx, [rsp+5D8h+var_568]
0x18007a5be  call    ??C?$tip_test@V?$merged_data@U_tip_WebAuthNUIPerformanceTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_WebAuthNUIPerformanceTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>>::operator->(void)
0x18007a5c3  mov     rcx, [rax]
0x18007a5c6  xor     edi, edi
0x18007a5c8  mov     [rcx+110h], edi
0x18007a5ce  lea     rcx, [rsp+5D8h+var_4C0]
0x18007a5d6  call    ??1?$test_data_control@V?$merged_data@U_tip_WebAuthNUIPerformanceTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>>(void)
0x18007a5db  mov     [rsp+5D8h+var_518], dil
0x18007a5e3  mov     [rsp+5D8h+var_528], dil
0x18007a5eb  mov     [rsp+5D8h+var_538], dil
0x18007a5f3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SharedPasskeyDependencies@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SharedPasskeyDependencies@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SharedPasskeyDependencies> `wil::Feature<__WilFeatureTraits_Feature_SharedPasskeyDependencies>::GetImpl(void)'::`2'::impl
0x18007a5fa  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SharedPasskeyDependencies@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SharedPasskeyDependencies>::__private_IsEnabled(void)
0x18007a5ff  xor     ecx, ecx
0x18007a601  xorps   xmm0, xmm0
0x18007a604  lea     edi, [rcx+1]
0x18007a607  test    al, al
0x18007a609  lea     rax, dword_18015030C
0x18007a610  jnz     loc_18007B071
0x18007a616  mov     [rsp+5D8h+var_570], ecx
0x18007a61a  movups  xmmword ptr [rsp+5D8h+Uuid.Data1], xmm0
0x18007a622  mov     [rsp+5D8h+var_4F0], rcx
0x18007a62a  mov     [rsp+5D8h+var_504], ecx
0x18007a631  mov     [rsp+5D8h+var_544], edi
0x18007a638  mov     [rsp+5D8h+var_548], edi
0x18007a63f  mov     [rsp+5D8h+var_4E0], ecx
0x18007a646  mov     [rsp+5D8h+var_578], cl
0x18007a64a  mov     [rsp+5D8h+var_4DC], ecx
0x18007a651  mov     dword ptr [rsp+5D8h+var_550+4], ecx
0x18007a658  mov     [rsp+5D8h+var_4C0], rax
0x18007a660  mov     [rsp+5D8h+var_508], ecx
0x18007a667  mov     dword ptr [rsp+5D8h+var_510+4], ecx
0x18007a66e  mov     [rsp+5D8h+var_4E8], rcx
0x18007a676  lea     rdx, [rsp+5D8h+var_4C8]
0x18007a67e  lea     rcx, [rsp+5D8h+var_4E8]
0x18007a686  call    ??C?$tip_test@V?$merged_data@U_tip_WebAuthNAuthenticatorTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_WebAuthNAuthenticatorTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNAuthenticatorTest,_tip_WebAuthNAuthenticatorTest>>::operator->(void)
0x18007a68b  mov     rcx, [rax]
0x18007a68e  mov     [rcx+110h], edi
0x18007a694  lea     rcx, [rsp+5D8h+var_4C8]
0x18007a69c  call    ??1?$test_data_control@V?$merged_data@U_tip_WebAuthNAuthenticatorTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNAuthenticatorTest,_tip_WebAuthNAuthenticatorTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNAuthenticatorTest,_tip_WebAuthNAuthenticatorTest>>(void)
0x18007a6a1  lea     rdx, [rsp+5D8h+var_348]
0x18007a6a9  lea     rcx, [rsp+5D8h+var_4E8]
0x18007a6b1  call    ?start@?$tip_test@V?$merged_data@U_tip_WebAuthNAuthenticatorTest@@U1@@details@tip2@@@tip2@@QEAA?AU_GUID@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNAuthenticatorTest,_tip_WebAuthNAuthenticatorTest>>::start(void)
0x18007a6b6  lea     rdx, [rsp+5D8h+var_398]
0x18007a6be  lea     rcx, [rsp+5D8h+var_4E8]
0x18007a6c6  call    ?watch_errors@?$tip_test@V?$merged_data@U_tip_WebAuthNAuthenticatorTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_WebAuthNAuthenticatorTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNAuthenticatorTest,_tip_WebAuthNAuthenticatorTest>>::watch_errors(void)
0x18007a6cb  nop
0x18007a6cc  mov     qword ptr [r14], 0
0x18007a6d3  lea     rax, [rsp+5D8h+var_504]
0x18007a6db  mov     [rsp+5D8h+var_4B8], rax
0x18007a6e3  lea     rax, [rsp+5D8h+var_508]
0x18007a6eb  mov     [rsp+5D8h+var_4B0], rax
0x18007a6f3  lea     rax, [rsp+5D8h+var_510+4]
0x18007a6fb  mov     [rsp+5D8h+var_4A8], rax
0x18007a703  lea     rax, [rsp+5D8h+var_4E8]
0x18007a70b  mov     [rsp+5D8h+var_4A0], rax
0x18007a713  lea     rax, [rsp+5D8h+var_570]
0x18007a718  mov     [rsp+5D8h+var_498], rax
0x18007a720  mov     [rsp+5D8h+var_490], dil
0x18007a728  lea     rcx, [rsp+5D8h+var_568]
0x18007a72d  call    ??B?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEBA_NXZ; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::operator bool(void)
0x18007a732  xor     r14d, r14d
0x18007a735  test    al, al
0x18007a737  jz      short loc_18007A759
0x18007a739  lea     rdx, [rsp+5D8h+var_348]
0x18007a741  lea     rcx, [rsp+5D8h+var_568]
0x18007a746  call    ?test_id@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest@@U1@@details@tip2@@@tip2@@QEBA?AU_GUID@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::test_id(void)
0x18007a74b  movups  xmm1, xmmword ptr [rax]
0x18007a74e  movdqu  xmmword ptr [rsp+5D8h+Uuid.Data1], xmm1
0x18007a757  jmp     short loc_18007A767
0x18007a759  lea     rcx, [rsp+5D8h+Uuid]; Uuid
0x18007a761  call    cs:__imp_UuidCreate
0x18007a767  lea     rax, [rsp+5D8h+Uuid]
0x18007a76f  mov     [rsp+5D8h+var_4F0], rax
0x18007a777  call    IsWinStationIsSessionRemoteablePresent
0x18007a77c  test    al, al
0x18007a77e  jz      short loc_18007A7C0
0x18007a780  lea     r8, [rsp+5D8h+var_578]
0x18007a785  or      edx, 0FFFFFFFFh
0x18007a788  xor     ecx, ecx
0x18007a78a  call    cs:__imp_WinStationIsSessionRemoteable
0x18007a790  test    al, al
0x18007a792  jz      short loc_18007A7C0
0x18007a794  cmp     [rsp+5D8h+var_578], r14b
0x18007a799  jz      short loc_18007A7C0
0x18007a79b  mov     [rsp+5D8h+var_4E0], edi
0x18007a7a2  lea     rcx, aWebauthnuiperf_3; "WebAuthNUIPerformanceTest::reason::remo"...
0x18007a7a9  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18007a7ae  mov     r8, rax
0x18007a7b1  mov     edx, 4
0x18007a7b6  lea     rcx, [rsp+5D8h+var_568]
0x18007a7bb  call    ?complete_and_ignore@?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(ushort,char const *)
0x18007a7c0  test    rsi, rsi
0x18007a7c3  jz      loc_18007A96C
0x18007a7c9  cmp     dword ptr [rsi], 5
0x18007a7cc  jb      loc_18007A96C
0x18007a7d2  cmp     [rsi+5Ch], r14d
0x18007a7d6  jz      loc_18007A96C
0x18007a7dc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2> `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl(void)'::`2'::impl
0x18007a7e3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(void)
0x18007a7e8  test    al, al
0x18007a7ea  jz      loc_18007A94B
0x18007a7f0  lea     rcx, [rsp+5D8h+var_3F8]
0x18007a7f8  call    ?Suppress@FidoTraceProvider@@SA?AVSuppressionReverter@TraceLoggingProviderFido@wil@@XZ; FidoTraceProvider::Suppress(void)
0x18007a7fd  mov     r14, rax
0x18007a800  xor     edx, edx
0x18007a802  cmp     [rsp+5D8h+var_518], dl
0x18007a809  jz      short loc_18007A837
0x18007a80b  mov     rcx, [rsp+5D8h+var_520]; this
0x18007a813  test    rcx, rcx
0x18007a816  jz      short loc_18007A827
0x18007a818  call    ?RemoveSuppression@TraceLoggingProviderFido@wil@@IEAAXXZ; wil::TraceLoggingProviderFido::RemoveSuppression(void)
0x18007a81d  xor     edx, edx
0x18007a81f  mov     [rsp+5D8h+var_520], rdx
0x18007a827  mov     rcx, [r14]
0x18007a82a  mov     [rsp+5D8h+var_520], rcx
0x18007a832  mov     [r14], rdx
0x18007a835  jmp     short loc_18007A855
0x18007a837  mov     [rsp+5D8h+var_520], rdx
0x18007a83f  mov     rax, [rax]
0x18007a842  mov     [rsp+5D8h+var_520], rax
0x18007a84a  mov     [r14], rdx
0x18007a84d  mov     [rsp+5D8h+var_518], dil
0x18007a855  lea     rcx, [rsp+5D8h+var_3F8]; this
0x18007a85d  call    ??1SuppressionReverter@TraceLoggingProviderFido@wil@@QEAA@XZ; wil::TraceLoggingProviderFido::SuppressionReverter::~SuppressionReverter(void)
0x18007a862  lea     rcx, [rsp+5D8h+var_488]
0x18007a86a  call    ?Suppress@FidoRestrictedCoreProvider@@SA?AVSuppressionReverter@TraceLoggingProviderFido@wil@@XZ; FidoRestrictedCoreProvider::Suppress(void)
0x18007a86f  mov     r14, rax
0x18007a872  xor     edx, edx
0x18007a874  cmp     [rsp+5D8h+var_528], dl
0x18007a87b  jz      short loc_18007A8A9
0x18007a87d  mov     rcx, [rsp+5D8h+var_530]; this
0x18007a885  test    rcx, rcx
0x18007a888  jz      short loc_18007A899
0x18007a88a  call    ?RemoveSuppression@TraceLoggingProviderFido@wil@@IEAAXXZ; wil::TraceLoggingProviderFido::RemoveSuppression(void)
0x18007a88f  xor     edx, edx
0x18007a891  mov     [rsp+5D8h+var_530], rdx
0x18007a899  mov     rcx, [r14]
0x18007a89c  mov     [rsp+5D8h+var_530], rcx
0x18007a8a4  mov     [r14], rdx
0x18007a8a7  jmp     short loc_18007A8C7
0x18007a8a9  mov     [rsp+5D8h+var_530], rdx
0x18007a8b1  mov     rax, [rax]
0x18007a8b4  mov     [rsp+5D8h+var_530], rax
0x18007a8bc  mov     [r14], rdx
0x18007a8bf  mov     [rsp+5D8h+var_528], dil
0x18007a8c7  lea     rcx, [rsp+5D8h+var_488]; this
0x18007a8cf  call    ??1SuppressionReverter@TraceLoggingProviderFido@wil@@QEAA@XZ; wil::TraceLoggingProviderFido::SuppressionReverter::~SuppressionReverter(void)
0x18007a8d4  lea     rcx, [rsp+5D8h+var_480]
0x18007a8dc  call    ?Suppress@FidoPluginProvider@@SA?AVSuppressionReverter@TraceLoggingProviderFido@wil@@XZ; FidoPluginProvider::Suppress(void)
0x18007a8e1  mov     r14, rax
0x18007a8e4  xor     edx, edx
0x18007a8e6  cmp     [rsp+5D8h+var_538], dl
0x18007a8ed  jz      short loc_18007A91B
0x18007a8ef  mov     rcx, [rsp+5D8h+var_540]; this
0x18007a8f7  test    rcx, rcx
0x18007a8fa  jz      short loc_18007A90B
0x18007a8fc  call    ?RemoveSuppression@TraceLoggingProviderFido@wil@@IEAAXXZ; wil::TraceLoggingProviderFido::RemoveSuppression(void)
0x18007a901  xor     edx, edx
0x18007a903  mov     [rsp+5D8h+var_540], rdx
0x18007a90b  mov     rcx, [r14]
0x18007a90e  mov     [rsp+5D8h+var_540], rcx
0x18007a916  mov     [r14], rdx
0x18007a919  jmp     short loc_18007A939
0x18007a91b  mov     [rsp+5D8h+var_540], rdx
0x18007a923  mov     rax, [rax]
0x18007a926  mov     [rsp+5D8h+var_540], rax
0x18007a92e  mov     [r14], rdx
0x18007a931  mov     [rsp+5D8h+var_538], dil
0x18007a939  lea     rcx, [rsp+5D8h+var_480]; this
0x18007a941  call    ??1SuppressionReverter@TraceLoggingProviderFido@wil@@QEAA@XZ; wil::TraceLoggingProviderFido::SuppressionReverter::~SuppressionReverter(void)
0x18007a946  xor     r14d, r14d
0x18007a949  jmp     short loc_18007A957
0x18007a94b  call    ?I_DisableTraceLogging@@YAXXZ; I_DisableTraceLogging(void)
0x18007a950  mov     dword ptr [rsp+5D8h+var_510+4], edi
0x18007a957  call    ?I_IsDebugModeConfigured@@YAHXZ; I_IsDebugModeConfigured(void)
0x18007a95c  test    eax, eax
0x18007a95e  jnz     short loc_18007A96C
0x18007a960  call    ?I_DisableEventLogging@@YAXXZ; I_DisableEventLogging(void)
0x18007a965  mov     [rsp+5D8h+var_508], edi
0x18007a96c  mov     [rsp+5D8h+var_338], r14d
0x18007a974  mov     [rsp+5D8h+var_334], r14b
0x18007a97c  lea     rcx, [rsp+5D8h+var_338]
0x18007a984  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0IAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0IAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,140737488355328,5,_TlgReflectorTag_Param0IsHProvider>,140737488355328,5>::zInternalStart(void)
0x18007a989  mov     eax, cs:dword_1801AB180
0x18007a98f  cmp     eax, 5
0x18007a992  jbe     loc_18007AADD
0x18007a998  mov     rdx, 800000000000h
0x18007a9a2  lea     rcx, dword_1801AB180
0x18007a9a9  call    _tlgKeywordOn
0x18007a9ae  test    al, al
0x18007a9b0  jz      loc_18007AADD
0x18007a9b6  mov     eax, [rsp+5D8h+var_4E0]
0x18007a9bd  mov     dword ptr [rsp+5D8h+var_558+4], eax
0x18007a9c4  mov     eax, [rsp+5D8h+var_548]
0x18007a9cb  mov     [rsp+5D8h+var_4FC], eax
0x18007a9d2  mov     eax, [rsp+5D8h+var_544]
0x18007a9d9  mov     [rsp+5D8h+var_500], eax
0x18007a9e0  mov     eax, dword ptr [rsp+5D8h+var_550+4]
0x18007a9e7  mov     dword ptr [rsp+5D8h+var_558], eax
0x18007a9ee  mov     eax, [rsp+5D8h+var_4DC]
0x18007a9f5  mov     dword ptr [rsp+5D8h+var_560+4], eax
0x18007a9f9  mov     rax, [rsp+5D8h+var_4C0]
0x18007aa01  mov     [rsp+5D8h+var_480], rax
0x18007aa09  mov     rax, [rsp+5D8h+var_4F0]
0x18007aa11  mov     [rsp+5D8h+var_488], rax
0x18007aa19  mov     eax, [rsp+5D8h+var_570]
0x18007aa1d  mov     dword ptr [rsp+5D8h+var_560], eax
0x18007aa21  cmp     [rsp+5D8h+var_334], r14b
0x18007aa29  jz      short loc_18007AA5D
0x18007aa2b  cmp     [rsp+5D8h+var_320], r14d
0x18007aa33  jnz     short loc_18007AA53
0x18007aa35  cmp     [rsp+5D8h+var_31C], r14d
0x18007aa3d  jnz     short loc_18007AA53
0x18007aa3f  cmp     [rsp+5D8h+var_318], r14d
0x18007aa47  jnz     short loc_18007AA53
0x18007aa49  cmp     [rsp+5D8h+var_314], r14d
0x18007aa51  jz      short loc_18007AA5D
0x18007aa53  lea     r9, [rsp+5D8h+var_320]
0x18007aa5b  jmp     short loc_18007AA60
0x18007aa5d  mov     r9, r14
0x18007aa60  lea     rax, [rsp+5D8h+var_558+4]
0x18007aa68  mov     [rsp+5D8h+var_580], rax
0x18007aa6d  lea     rax, [rsp+5D8h+var_4FC]
0x18007aa75  mov     [rsp+5D8h+var_588], rax
0x18007aa7a  lea     rax, [rsp+5D8h+var_500]
0x18007aa82  mov     [rsp+5D8h+var_590], rax
0x18007aa87  lea     rax, [rsp+5D8h+var_558]
0x18007aa8f  mov     [rsp+5D8h+var_598], rax
0x18007aa94  lea     rax, [rsp+5D8h+var_560+4]
0x18007aa99  mov     [rsp+5D8h+var_5A0], rax
0x18007aa9e  lea     rax, [rsp+5D8h+var_480]
0x18007aaa6  mov     [rsp+5D8h+var_5A8], rax
0x18007aaab  lea     rax, [rsp+5D8h+var_488]
0x18007aab3  mov     [rsp+5D8h+var_5B0], rax
0x18007aab8  lea     rax, [rsp+5D8h+var_560]
0x18007aabd  mov     [rsp+5D8h+var_5B8], rax
0x18007aac2  lea     r8, [rsp+5D8h+var_330]
0x18007aaca  lea     rdx, byte_1801856AB
0x18007aad1  lea     rcx, dword_1801AB180
0x18007aad8  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U1@U1@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@33333@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18007aadd  lea     rax, [rsp+5D8h+var_338]
0x18007aae5  mov     [rsp+5D8h+var_3E8], rax
0x18007aaed  lea     rax, [rsp+5D8h+var_570]
0x18007aaf2  mov     [rsp+5D8h+var_3E0], rax
0x18007aafa  lea     rax, [rsp+5D8h+var_4F0]
0x18007ab02  mov     [rsp+5D8h+var_3D8], rax
0x18007ab0a  lea     rax, [rsp+5D8h+var_4C0]
0x18007ab12  mov     [rsp+5D8h+var_3D0], rax
0x18007ab1a  lea     rax, [rsp+5D8h+var_4DC]
0x18007ab22  mov     [rsp+5D8h+var_3C8], rax
0x18007ab2a  lea     rax, [rsp+5D8h+var_550+4]
0x18007ab32  mov     [rsp+5D8h+var_3C0], rax
0x18007ab3a  lea     rax, [rsp+5D8h+var_544]
0x18007ab42  mov     [rsp+5D8h+var_3B8], rax
0x18007ab4a  lea     rax, [rsp+5D8h+var_548]
0x18007ab52  mov     [rsp+5D8h+var_3B0], rax
0x18007ab5a  lea     rax, [rsp+5D8h+var_4E0]
0x18007ab62  mov     [rsp+5D8h+var_3A8], rax
0x18007ab6a  mov     [rsp+5D8h+var_3A0], 102h
0x18007ab74  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_MakeCredentialPRF@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_MakeCredentialPRF@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MakeCredentialPRF> `wil::Feature<__WilFeatureTraits_Feature_MakeCredentialPRF>::GetImpl(void)'::`2'::impl
0x18007ab7b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_MakeCredentialPRF@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MakeCredentialPRF>::__private_IsEnabled(void)
0x18007ab80  xor     edx, edx
0x18007ab82  test    al, al
0x18007ab84  jz      loc_18007ACBC
0x18007ab8a  test    r13, r13
0x18007ab8d  jz      short loc_18007ABFB
0x18007ab8f  cmp     [r13+0], edi
0x18007ab93  jb      short loc_18007ABFB
0x18007ab95  lea     r14, [r13+8]
0x18007ab99  cmp     [r14], rdx
0x18007ab9c  jz      short loc_18007ABFB
0x18007ab9e  test    r15, r15
0x18007aba1  jz      short loc_18007ABFB
0x18007aba3  cmp     [r15], edi
0x18007aba6  jb      short loc_18007ABFB
0x18007aba8  cmp     [r15+4], edx
0x18007abac  jz      short loc_18007ABFB
  ... truncated ...
```
