# ServiceMain

- ea: `0x180011630`
- end: `0x180011b4f`
- name: `ServiceMain`
- size: `1311`
- prototype: `void()`
- caller_count: `0`
- callee_count: `36`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x1800018ac`
- `0x1800018d8`
- `0x180003ab0`
- `0x180003ebc`
- `0x18000768c`
- `0x18000cd2c`
- `0x18000d67c`
- `0x18000d908`
- `0x18000e744`
- `0x18000e77c`
- `0x18000e79c`
- `0x18000e9f0`
- `0x18000f634`
- `0x18000f720`
- `0x18000f8c8`
- `0x18000fbbc`
- `0x18000fc54`
- `0x18000fcec`
- `0x18001054c`
- `0x1800107b0`
- `0x180010f1c`
- `0x1800110b4`
- `0x180011130`
- `0x180011238`
- `0x180011274`
- `0x1800115fc`
- `0x180011630`
- `0x180013ad0`
- `0x18001794c`
- `0x180025c68`
- `0x180025e00`
- `0x180025ebc`
- `0x180026494`
- `0x1800264d0`
- `0x1800271dc`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180011818`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180011818`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x180011679`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x180011679`

## string_xrefs

- `0x1800116b6`: `onecoreuap\windows\directx\dxg\gpm\service\service.cpp`
- `0x180011a6b`: `onecoreuap\windows\directx\dxg\gpm\service\service.cpp`
- `0x1800116c7`: `ServiceMain`

## pseudocode

```c
void ServiceMain()
{
  const char *v0; // r9
  __int64 v1; // rdx
  __int64 v2; // r8
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // rdx
  int IsEnabled; // edi
  const struct _tlgProvider_t *v7; // rax
  const unsigned __int16 *v8; // rdx
  int v9; // r8d
  int v10; // r9d
  const unsigned __int16 *v11; // rdx
  dxg::svc::ServiceRefCount *v12; // rcx
  unsigned int v13; // r8d
  _DWORD *v14; // rdi
  const unsigned __int16 *v15; // r8
  const unsigned __int16 *v16; // r9
  std::_Ref_count_base *v17; // rcx
  ServiceEtwThreadHelper *v18; // rax
  ServiceEtwThreadHelper *v19; // rdx
  unsigned int started; // edi
  __int64 v21; // rcx
  LPVOID *ppv; // [rsp+20h] [rbp-148h]
  char *v23; // [rsp+28h] [rbp-140h]
  HKEY ServiceParameterKey_NoExcept; // [rsp+60h] [rbp-108h] BYREF
  __int64 v25; // [rsp+68h] [rbp-100h] BYREF
  _DWORD v26[4]; // [rsp+70h] [rbp-F8h] BYREF
  struct _GUID v27; // [rsp+80h] [rbp-E8h] BYREF
  int v28; // [rsp+90h] [rbp-D8h] BYREF
  int v29; // [rsp+94h] [rbp-D4h] BYREF
  int v30; // [rsp+98h] [rbp-D0h] BYREF
  _QWORD v31[8]; // [rsp+A0h] [rbp-C8h] BYREF
  _BYTE v32[80]; // [rsp+E0h] [rbp-88h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+130h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_RedirectionGuard>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_GPM_RedirectionGuard>::GetImpl'::`2'::impl) )
  {
    v26[0] = 1;
    if ( !(unsigned int)SetProcessMitigationPolicy(16, v26, 4) )
    {
      v27 = GUID_NULL;
      TelemetrySink::LogDiagnostic(
        (TelemetrySink *)&g::TelemetrySink,
        L"Failed to set Process Mitigation Policy for Redirection Trust.",
        &v27);
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0x186,
        (unsigned int)"onecoreuap\\windows\\directx\\dxg\\gpm\\service\\service.cpp",
        v0);
    }
  }
  gpm::TraceProvider::WatchCurrentThread(v32, "ServiceMain");
  try
  {
    LOBYTE(v2) = 3;
    LOBYTE(v1) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_BlitModeTracking>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_GPM_BlitModeTracking>::GetImpl'::`2'::impl,
      v1,
      v2);
    LOBYTE(v3) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_MultiMon>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_GPM_MultiMon>::GetImpl'::`2'::impl,
      v3);
    LOBYTE(v4) = 3;
    LOBYTE(v5) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_CreatePSOTracking>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_GPM_CreatePSOTracking>::GetImpl'::`2'::impl,
      v5,
      v4);
    IsEnabled = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_ResidencyTracking>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_GPM_ResidencyTracking>::GetImpl'::`2'::impl);
    v7 = gpm::TraceProvider::Provider();
    if ( *(_DWORD *)v7 > 5u && (unsigned __int8)tlgKeywordOn(v7, 0x400000000000LL) )
    {
      v26[0] = IsEnabled;
      v28 = 1;
      v29 = 1;
      v30 = 1;
      LODWORD(ServiceParameterKey_NoExcept) = 1;
      LODWORD(v25) = 1;
      *(_QWORD *)&v27.Data1 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v9,
        (unsigned int)&byte_180039B9F,
        v9,
        v10,
        (__int64)&v27,
        (__int64)&v25,
        (__int64)&ServiceParameterKey_NoExcept,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v28,
        (__int64)v26);
    }
    dxg::svc::Host::Host(&ServiceStatus, v8);
    g::ApiFactoryRegistrationCookie = 0;
    g::pContextCallback = 0;
    if ( CoCreateInstance(&CLSID_ContextSwitcher, 0, 1u, &IID_IContextCallback, &g::pContextCallback) >= 0
      && (int)dxg::svc::ServiceRefCount::Initialize(v12) >= 0 )
    {
      v25 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
      if ( (int)CreateGraphicsPerformanceMonitorClassFactory(&v25) >= 0 )
        (*(void (__fastcall **)(LPVOID, __int64 (__fastcall *)(LPUNKNOWN), __int64, GUID *, int, _QWORD))(*(_QWORD *)g::pContextCallback + 24LL))(
          g::pContextCallback,
          ConnectCallback,
          v25,
          &IID_IContextCallback,
          5,
          0);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
    }
    ServiceParameterKey_NoExcept = dxg::svc::CreateServiceParameterKey_NoExcept(v12, v11, v13);
    g::config = dxg::svc::ParameterReader::ReadDWORD(
                  (dxg::svc::ParameterReader *)&ServiceParameterKey_NoExcept,
                  "IntervalSecs",
                  0x1Eu);
    dword_180042D54 = dxg::svc::ParameterReader::ReadDWORD(
                        (dxg::svc::ParameterReader *)&ServiceParameterKey_NoExcept,
                        "TimeoutSecs",
                        0x1Eu);
    dword_180042D5C = dxg::svc::ParameterReader::ReadDWORD(
                        (dxg::svc::ParameterReader *)&ServiceParameterKey_NoExcept,
                        "BufferSize",
                        0);
    dword_180042D60 = dxg::svc::ParameterReader::ReadDWORD(
                        (dxg::svc::ParameterReader *)&ServiceParameterKey_NoExcept,
                        "MinimumBuffers",
                        0);
    dword_180042D64 = dxg::svc::ParameterReader::ReadDWORD(
                        (dxg::svc::ParameterReader *)&ServiceParameterKey_NoExcept,
                        "MaximumBuffers",
                        0);
    dword_180042D68 = dxg::svc::ParameterReader::ReadDWORD(
                        (dxg::svc::ParameterReader *)&ServiceParameterKey_NoExcept,
                        "FlushTimer",
                        0);
    v14 = operator new(0x340u);
    *(_QWORD *)&v27.Data1 = v14;
    v14[2] = 1;
    v14[3] = 1;
    *(_QWORD *)v14 = &std::_Ref_count_obj2<ServiceTraceConsumer>::`vftable';
    PresentTraceConsumerCore::PresentTraceConsumerCore(
      (PresentTraceConsumerCore *)(v14 + 4),
      (const struct PresentTraceConsumerCore::Config *)&g::config,
      v15,
      v16);
    *((_QWORD *)v14 + 2) = &ServiceTraceConsumer::`vftable'{for `ITraceConsumer'};
    *((_QWORD *)v14 + 3) = &ServiceTraceConsumer::`vftable'{for `ITelemetryCounters'};
    g::spTraceConsumer = (PresentTraceConsumerCore *)(v14 + 4);
    v17 = qword_180043010;
    qword_180043010 = (std::_Ref_count_base *)v14;
    if ( v17 )
      std::_Ref_count_base::_Decref(v17);
    v18 = (ServiceEtwThreadHelper *)operator new(0x10u);
    *(_QWORD *)v18 = 0;
    *((_BYTE *)v18 + 8) = 0;
    if ( ServiceEtwThreadHelper::s_instanceExists )
      __fastfail(7u);
    ServiceEtwThreadHelper::s_instanceExists = 1;
    *(_QWORD *)&v27.Data1 = 0;
    v19 = g::serviceEtwThreadHelper;
    g::serviceEtwThreadHelper = v18;
    if ( v19 )
      std::default_delete<ServiceEtwThreadHelper>::operator()();
    std::unique_ptr<ServiceEtwThreadHelper>::~unique_ptr<ServiceEtwThreadHelper>(&v27);
    ServiceEtwThreadHelper::Initialize(g::serviceEtwThreadHelper);
    started = StartWnfTelemetry();
    if ( (started & 0x80000000) != 0 )
    {
      v27 = GUID_NULL;
      TelemetrySink::LogDiagnostic((TelemetrySink *)&g::TelemetrySink, L"Failed to register for Wnf.", &v27);
      MicrosoftTelemetryAssertTriggeredArgs("Failed to register for Wnf", started, started);
      wil::details::in1diag3::Log_NtStatusMsg(
        retaddr,
        (void *)0x1CE,
        (unsigned int)"onecoreuap\\windows\\directx\\dxg\\gpm\\service\\service.cpp",
        (const char *)started,
        (int)"Failed to register for Wnf.",
        v23);
    }
    v31[0] = &std::_Func_impl_no_alloc<void (*)(void),void,>::`vftable';
    v31[1] = ShutdownCallback;
    v31[7] = v31;
    dxg::svc::Host::Detach(&ServiceStatus);
    if ( !(unsigned __int8)std::_State_manager<int>::valid(&g::StartEtwThread) )
      std::_Throw_future_error2(4);
    LODWORD(v25) = 1;
    if ( !(unsigned __int8)std::_State_manager<int>::valid(v21) )
      std::_Throw_future_error2(4);
    std::_Associated_state<int>::_Set_value(g::StartEtwThread, &v25);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&ServiceParameterKey_NoExcept);
    dxg::svc::Host::~Host(&ServiceStatus);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtExceptionMsg(
      retaddr,
      (void *)0x1D7,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\gpm\\service\\service.cpp",
      "Exception thrown while configuring service at startup.",
      (const char *)ppv);
  }
  wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v32);
}

```

## disassembly

```asm
0x180011630  mov     [rsp+arg_0], rbx
0x180011635  mov     [rsp+arg_8], rsi
0x18001163a  push    rdi
0x18001163b  sub     rsp, 160h
0x180011642  mov     rax, cs:__security_cookie
0x180011649  xor     rax, rsp
0x18001164c  mov     [rsp+168h+var_18], rax
0x180011654  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_GPM_RedirectionGuard@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_RedirectionGuard@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_RedirectionGuard> `wil::Feature<__WilFeatureTraits_Feature_GPM_RedirectionGuard>::GetImpl(void)'::`2'::impl
0x18001165b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_RedirectionGuard@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_RedirectionGuard>::__private_IsEnabled(void)
0x180011660  mov     ebx, 1
0x180011665  test    al, al
0x180011667  jz      short loc_1800116C7
0x180011669  mov     [rsp+168h+var_F8], ebx
0x18001166d  lea     r8d, [rbx+3]
0x180011671  lea     rdx, [rsp+168h+var_F8]
0x180011676  lea     ecx, [rbx+0Fh]
0x180011679  call    cs:__imp_SetProcessMitigationPolicy
0x18001167f  test    eax, eax
0x180011681  jnz     short loc_1800116C7
0x180011683  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18001168a  movdqu  xmmword ptr [rsp+168h+var_E8.Data1], xmm0
0x180011693  lea     r8, [rsp+168h+var_E8]; struct _GUID
0x18001169b  lea     rdx, aFailedToSetPro; "Failed to set Process Mitigation Policy"...
0x1800116a2  lea     rcx, ?TelemetrySink@g@@3U0@A; this
0x1800116a9  call    ?LogDiagnostic@TelemetrySink@@UEAAXPEBGU_GUID@@@Z; TelemetrySink::LogDiagnostic(ushort const *,_GUID)
0x1800116ae  mov     rcx, [rsp+168h]; this
0x1800116b6  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\directx\\dxg\\gpm"...
0x1800116bd  mov     edx, 186h; void *
0x1800116c2  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1800116c7  lea     rdx, aServicemain_0; "ServiceMain"
0x1800116ce  lea     rcx, [rsp+168h+var_88]
0x1800116d6  call    ?WatchCurrentThread@TraceProvider@gpm@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; gpm::TraceProvider::WatchCurrentThread(char const *)
0x1800116db  nop
0x1800116dc  mov     r8b, 3
0x1800116df  mov     dl, bl
0x1800116e1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_GPM_BlitModeTracking@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_BlitModeTracking@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_BlitModeTracking> `wil::Feature<__WilFeatureTraits_Feature_GPM_BlitModeTracking>::GetImpl(void)'::`2'::impl
0x1800116e8  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_BlitModeTracking@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_BlitModeTracking>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800116ed  mov     dl, bl
0x1800116ef  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_GPM_MultiMon@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_MultiMon@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_MultiMon> `wil::Feature<__WilFeatureTraits_Feature_GPM_MultiMon>::GetImpl(void)'::`2'::impl
0x1800116f6  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_MultiMon@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_MultiMon>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800116fb  mov     r8b, 3
0x1800116fe  mov     dl, bl
0x180011700  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_GPM_CreatePSOTracking@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_CreatePSOTracking@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_CreatePSOTracking> `wil::Feature<__WilFeatureTraits_Feature_GPM_CreatePSOTracking>::GetImpl(void)'::`2'::impl
0x180011707  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_CreatePSOTracking@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_CreatePSOTracking>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001170c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_GPM_ResidencyTracking@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_ResidencyTracking@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_ResidencyTracking> `wil::Feature<__WilFeatureTraits_Feature_GPM_ResidencyTracking>::GetImpl(void)'::`2'::impl
0x180011713  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_ResidencyTracking@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_ResidencyTracking>::__private_IsEnabled(void)
0x180011718  movzx   edi, al
0x18001171b  call    ?Provider@TraceProvider@gpm@@SAPEBU_tlgProvider_t@@XZ; gpm::TraceProvider::Provider(void)
0x180011720  mov     r8, rax
0x180011723  mov     ecx, [rax]
0x180011725  cmp     ecx, 5
0x180011728  jbe     loc_1800117D6
0x18001172e  mov     rdx, 400000000000h
0x180011738  mov     rcx, rax
0x18001173b  call    _tlgKeywordOn
0x180011740  test    al, al
0x180011742  jz      loc_1800117D6
0x180011748  mov     [rsp+168h+var_F8], edi
0x18001174c  mov     [rsp+168h+var_D8], ebx
0x180011753  mov     [rsp+168h+var_D4], ebx
0x18001175a  mov     [rsp+168h+var_D0], ebx
0x180011761  mov     dword ptr [rsp+168h+var_108], ebx
0x180011765  mov     dword ptr [rsp+168h+var_100], ebx
0x180011769  mov     qword ptr [rsp+168h+var_E8.Data1], 1000000h
0x180011775  lea     rax, [rsp+168h+var_F8]
0x18001177a  mov     [rsp+168h+var_118], rax
0x18001177f  lea     rax, [rsp+168h+var_D8]
0x180011787  mov     [rsp+168h+var_120], rax
0x18001178c  lea     rax, [rsp+168h+var_D4]
0x180011794  mov     [rsp+168h+var_128], rax
0x180011799  lea     rax, [rsp+168h+var_D0]
0x1800117a1  mov     [rsp+168h+var_130], rax
0x1800117a6  lea     rax, [rsp+168h+var_108]
0x1800117ab  mov     [rsp+168h+var_138], rax
0x1800117b0  lea     rax, [rsp+168h+var_100]
0x1800117b5  mov     [rsp+168h+var_140], rax
0x1800117ba  lea     rax, [rsp+168h+var_E8]
0x1800117c2  mov     [rsp+168h+ppv], rax
0x1800117c7  lea     rdx, byte_180039B9F
0x1800117ce  mov     rcx, r8
0x1800117d1  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@44444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800117d6  lea     rcx, [rsp+168h+ServiceStatus]; lpServiceStatus
0x1800117de  call    ??0Host@svc@dxg@@QEAA@PEBG@Z; dxg::svc::Host::Host(ushort const *)
0x1800117e3  nop
0x1800117e4  mov     cs:?ApiFactoryRegistrationCookie@g@@3KA, 0; ulong g::ApiFactoryRegistrationCookie
0x1800117ee  mov     cs:?pContextCallback@g@@3PEAUIContextCallback@@EA, 0; IContextCallback * g::pContextCallback
0x1800117f9  lea     rax, ?pContextCallback@g@@3PEAUIContextCallback@@EA; IContextCallback * g::pContextCallback
0x180011800  mov     [rsp+168h+ppv], rax; ppv
0x180011805  lea     r9, IID_IContextCallback; riid
0x18001180c  mov     r8d, ebx; dwClsContext
0x18001180f  xor     edx, edx; pUnkOuter
0x180011811  lea     rcx, CLSID_ContextSwitcher; rclsid
0x180011818  call    cs:__imp_CoCreateInstance
0x18001181e  test    eax, eax
0x180011820  js      short loc_18001188E
0x180011822  call    ?Initialize@ServiceRefCount@svc@dxg@@QEAAJXZ; dxg::svc::ServiceRefCount::Initialize(void)
0x180011827  test    eax, eax
0x180011829  js      short loc_18001188E
0x18001182b  mov     [rsp+168h+var_100], 0
0x180011834  lea     rcx, [rsp+168h+var_100]
0x180011839  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001183e  lea     rcx, [rsp+168h+var_100]
0x180011843  call    CreateGraphicsPerformanceMonitorClassFactory
0x180011848  test    eax, eax
0x18001184a  js      short loc_180011884
0x18001184c  mov     rcx, cs:?pContextCallback@g@@3PEAUIContextCallback@@EA; IContextCallback * g::pContextCallback
0x180011853  mov     rax, [rcx]
0x180011856  mov     [rsp+168h+var_140], 0; char *
0x18001185f  mov     dword ptr [rsp+168h+ppv], 5
0x180011867  lea     r9, IID_IContextCallback
0x18001186e  mov     r8, [rsp+168h+var_100]
0x180011873  lea     rdx, ?ConnectCallback@@YAJPEAUtagComCallData@@@Z; ConnectCallback(tagComCallData *)
0x18001187a  mov     rax, [rax+18h]
0x18001187e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011883  nop
0x180011884  lea     rcx, [rsp+168h+var_100]
0x180011889  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001188e  call    ?CreateServiceParameterKey_NoExcept@svc@dxg@@YAPEAUHKEY__@@PEBGK@Z; dxg::svc::CreateServiceParameterKey_NoExcept(ushort const *,ulong)
0x180011893  mov     [rsp+168h+var_108], rax
0x180011898  mov     edi, 1Eh
0x18001189d  mov     r8d, edi; unsigned int
0x1800118a0  lea     rdx, aIntervalsecs; "IntervalSecs"
0x1800118a7  lea     rcx, [rsp+168h+var_108]; this
0x1800118ac  call    ?ReadDWORD@ParameterReader@svc@dxg@@QEBAKPEBDK@Z; dxg::svc::ParameterReader::ReadDWORD(char const *,ulong)
0x1800118b1  mov     cs:?config@g@@3UConfig@PresentTraceConsumerCore@@A, eax; PresentTraceConsumerCore::Config g::config
0x1800118b7  mov     r8d, edi; unsigned int
0x1800118ba  lea     rdx, aTimeoutsecs; "TimeoutSecs"
0x1800118c1  lea     rcx, [rsp+168h+var_108]; this
0x1800118c6  call    ?ReadDWORD@ParameterReader@svc@dxg@@QEBAKPEBDK@Z; dxg::svc::ParameterReader::ReadDWORD(char const *,ulong)
0x1800118cb  mov     cs:dword_180042D54, eax
0x1800118d1  xor     r8d, r8d; unsigned int
0x1800118d4  lea     rdx, aBuffersize; "BufferSize"
0x1800118db  lea     rcx, [rsp+168h+var_108]; this
0x1800118e0  call    ?ReadDWORD@ParameterReader@svc@dxg@@QEBAKPEBDK@Z; dxg::svc::ParameterReader::ReadDWORD(char const *,ulong)
0x1800118e5  mov     cs:dword_180042D5C, eax
0x1800118eb  xor     r8d, r8d; unsigned int
0x1800118ee  lea     rdx, aMinimumbuffers; "MinimumBuffers"
0x1800118f5  lea     rcx, [rsp+168h+var_108]; this
0x1800118fa  call    ?ReadDWORD@ParameterReader@svc@dxg@@QEBAKPEBDK@Z; dxg::svc::ParameterReader::ReadDWORD(char const *,ulong)
0x1800118ff  mov     cs:dword_180042D60, eax
0x180011905  xor     r8d, r8d; unsigned int
0x180011908  lea     rdx, aMaximumbuffers; "MaximumBuffers"
0x18001190f  lea     rcx, [rsp+168h+var_108]; this
0x180011914  call    ?ReadDWORD@ParameterReader@svc@dxg@@QEBAKPEBDK@Z; dxg::svc::ParameterReader::ReadDWORD(char const *,ulong)
0x180011919  mov     cs:dword_180042D64, eax
0x18001191f  xor     r8d, r8d; unsigned int
0x180011922  lea     rdx, aFlushtimer; "FlushTimer"
0x180011929  lea     rcx, [rsp+168h+var_108]; this
0x18001192e  call    ?ReadDWORD@ParameterReader@svc@dxg@@QEBAKPEBDK@Z; dxg::svc::ParameterReader::ReadDWORD(char const *,ulong)
0x180011933  mov     cs:dword_180042D68, eax
0x180011939  mov     ecx, 340h; Size
0x18001193e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011943  mov     rdi, rax
0x180011946  mov     qword ptr [rsp+168h+var_E8.Data1], rax
0x18001194e  mov     [rax+8], ebx
0x180011951  mov     [rax+0Ch], ebx
0x180011954  lea     rax, ??_7?$_Ref_count_obj2@UServiceTraceConsumer@@@std@@6B@; const std::_Ref_count_obj2<ServiceTraceConsumer>::`vftable'
0x18001195b  mov     [rdi], rax
0x18001195e  lea     rsi, [rdi+10h]
0x180011962  lea     rdx, ?config@g@@3UConfig@PresentTraceConsumerCore@@A; struct PresentTraceConsumerCore::Config *
0x180011969  mov     rcx, rsi; this
0x18001196c  call    ??0PresentTraceConsumerCore@@QEAA@AEBUConfig@0@PEBG1@Z; PresentTraceConsumerCore::PresentTraceConsumerCore(PresentTraceConsumerCore::Config const &,ushort const *,ushort const *)
0x180011971  lea     rax, ??_7ServiceTraceConsumer@@6BITraceConsumer@@@; const ServiceTraceConsumer::`vftable'{for `ITraceConsumer'}
0x180011978  mov     [rsi], rax
0x18001197b  lea     rax, ??_7ServiceTraceConsumer@@6BITelemetryCounters@@@; const ServiceTraceConsumer::`vftable'{for `ITelemetryCounters'}
0x180011982  mov     [rsi+8], rax
0x180011986  mov     cs:?spTraceConsumer@g@@3V?$shared_ptr@UServiceTraceConsumer@@@std@@A, rsi; std::shared_ptr<ServiceTraceConsumer> g::spTraceConsumer
0x18001198d  mov     rcx, cs:qword_180043010; this
0x180011994  mov     cs:qword_180043010, rdi
0x18001199b  test    rcx, rcx
0x18001199e  jz      short loc_1800119A5
0x1800119a0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800119a5  mov     ecx, 10h; Size
0x1800119aa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800119af  mov     qword ptr [rax], 0
0x1800119b6  mov     byte ptr [rax+8], 0
0x1800119ba  cmp     cs:?s_instanceExists@ServiceEtwThreadHelper@@2_NA, 0; bool ServiceEtwThreadHelper::s_instanceExists
0x1800119c1  jz      short loc_1800119CA
0x1800119c3  mov     ecx, 7
0x1800119c8  int     29h; Win8: RtlFailFast(ecx)
0x1800119ca  mov     cs:?s_instanceExists@ServiceEtwThreadHelper@@2_NA, bl; bool ServiceEtwThreadHelper::s_instanceExists
0x1800119d0  mov     qword ptr [rsp+168h+var_E8.Data1], 0
0x1800119dc  mov     rdx, cs:?serviceEtwThreadHelper@g@@3V?$unique_ptr@VServiceEtwThreadHelper@@U?$default_delete@VServiceEtwThreadHelper@@@std@@@std@@A; std::unique_ptr<ServiceEtwThreadHelper> g::serviceEtwThreadHelper
0x1800119e3  mov     cs:?serviceEtwThreadHelper@g@@3V?$unique_ptr@VServiceEtwThreadHelper@@U?$default_delete@VServiceEtwThreadHelper@@@std@@@std@@A, rax; std::unique_ptr<ServiceEtwThreadHelper> g::serviceEtwThreadHelper
0x1800119ea  test    rdx, rdx
0x1800119ed  jz      short loc_1800119F4
0x1800119ef  call    ??R?$default_delete@VServiceEtwThreadHelper@@@std@@QEBAXPEAVServiceEtwThreadHelper@@@Z; std::default_delete<ServiceEtwThreadHelper>::operator()(ServiceEtwThreadHelper *)
0x1800119f4  lea     rcx, [rsp+168h+var_E8]
0x1800119fc  call    ??1?$unique_ptr@VServiceEtwThreadHelper@@U?$default_delete@VServiceEtwThreadHelper@@@std@@@std@@QEAA@XZ; std::unique_ptr<ServiceEtwThreadHelper>::~unique_ptr<ServiceEtwThreadHelper>(void)
0x180011a01  mov     rcx, cs:?serviceEtwThreadHelper@g@@3V?$unique_ptr@VServiceEtwThreadHelper@@U?$default_delete@VServiceEtwThreadHelper@@@std@@@std@@A; this
0x180011a08  call    ?Initialize@ServiceEtwThreadHelper@@QEAAXXZ; ServiceEtwThreadHelper::Initialize(void)
0x180011a0d  call    ?StartWnfTelemetry@@YAJXZ; StartWnfTelemetry(void)
0x180011a12  mov     edi, eax
0x180011a14  test    eax, eax
0x180011a16  jns     short loc_180011A7C
0x180011a18  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180011a1f  movdqu  xmmword ptr [rsp+168h+var_E8.Data1], xmm0
0x180011a28  lea     r8, [rsp+168h+var_E8]; struct _GUID
0x180011a30  lea     rdx, aFailedToRegist; "Failed to register for Wnf."
0x180011a37  lea     rcx, ?TelemetrySink@g@@3U0@A; this
0x180011a3e  call    ?LogDiagnostic@TelemetrySink@@UEAAXPEBGU_GUID@@@Z; TelemetrySink::LogDiagnostic(ushort const *,_GUID)
0x180011a43  mov     r8d, edi
0x180011a46  mov     edx, edi
0x180011a48  lea     rcx, aFailedToRegist_0; "Failed to register for Wnf"
0x180011a4f  call    MicrosoftTelemetryAssertTriggeredArgs
0x180011a54  mov     rcx, [rsp+168h]; this
0x180011a5c  lea     rax, aFailedToRegist_1; "Failed to register for Wnf."
0x180011a63  mov     [rsp+168h+ppv], rax; int
0x180011a68  mov     r9d, edi; char *
0x180011a6b  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\directx\\dxg\\gpm"...
0x180011a72  mov     edx, 1CEh; void *
0x180011a77  call    ?Log_NtStatusMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x180011a7c  lea     rax, ??_7?$_Func_impl_no_alloc@P6AXXZX$$V@std@@6B@; const std::_Func_impl_no_alloc<void (*)(void),void,>::`vftable'
0x180011a83  mov     [rsp+168h+var_C8], rax
0x180011a8b  lea     rax, ?ShutdownCallback@@YAXXZ; ShutdownCallback(void)
0x180011a92  mov     [rsp+168h+var_C0], rax
0x180011a9a  lea     rax, [rsp+168h+var_C8]
0x180011aa2  mov     [rsp+168h+var_90], rax
0x180011aaa  lea     rdx, [rsp+168h+var_C8]
0x180011ab2  lea     rcx, [rsp+168h+ServiceStatus]; lpServiceStatus
0x180011aba  call    ?Detach@Host@svc@dxg@@QEAAXV?$function@$$A6AXXZ@std@@@Z; dxg::svc::Host::Detach(std::function<void (void)>)
0x180011abf  lea     rcx, ?StartEtwThread@g@@3V?$promise@X@std@@A; std::promise<void> g::StartEtwThread
0x180011ac6  call    ?valid@?$_State_manager@H@std@@QEBA_NXZ; std::_State_manager<int>::valid(void)
0x180011acb  test    al, al
0x180011acd  jz      short loc_180011B39
0x180011acf  mov     dword ptr [rsp+168h+var_100], ebx
0x180011ad3  call    ?valid@?$_State_manager@H@std@@QEBA_NXZ; std::_State_manager<int>::valid(void)
0x180011ad8  test    al, al
0x180011ada  jz      short loc_180011B43
0x180011adc  lea     rdx, [rsp+168h+var_100]
0x180011ae1  mov     rcx, cs:?StartEtwThread@g@@3V?$promise@X@std@@A; std::promise<void> g::StartEtwThread
0x180011ae8  call    ?_Set_value@?$_Associated_state@H@std@@QEAAX$$QEAH_N@Z; std::_Associated_state<int>::_Set_value(int &&,bool)
0x180011aed  nop
0x180011aee  lea     rcx, [rsp+168h+var_108]
0x180011af3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180011af8  nop
0x180011af9  lea     rcx, [rsp+168h+ServiceStatus]; lpServiceStatus
0x180011b01  call    ??1Host@svc@dxg@@QEAA@XZ; dxg::svc::Host::~Host(void)
0x180011b06  nop
0x180011b07  lea     rcx, [rsp+168h+var_88]; this
0x180011b0f  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x180011b14  mov     rcx, [rsp+168h+var_18]
0x180011b1c  xor     rcx, rsp; StackCookie
0x180011b1f  call    __security_check_cookie
0x180011b24  lea     r11, [rsp+168h+var_8]
0x180011b2c  mov     rbx, [r11+10h]
0x180011b30  mov     rsi, [r11+18h]
0x180011b34  mov     rsp, r11
0x180011b37  pop     rdi
0x180011b38  retn
0x180011b39  mov     ecx, 4
0x180011b3e  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x180011b43  mov     ecx, 4
0x180011b48  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
```
