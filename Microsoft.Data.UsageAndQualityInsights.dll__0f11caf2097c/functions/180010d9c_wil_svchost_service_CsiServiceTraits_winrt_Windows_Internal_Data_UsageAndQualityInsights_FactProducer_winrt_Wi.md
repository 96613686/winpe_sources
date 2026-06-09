# wil::svchost_service<CsiServiceTraits,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactProducer,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactConsumer,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestAPI,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestConfigurationRegistration>::start(void)

- ea: `0x180010d9c`
- end: `0x18001102b`
- name: `?start@?$svchost_service@UCsiServiceTraits@@UFactProducer@UsageAndQualityInsights@Data@Internal@Windows@winrt@@UFactConsumer@34567@UUQIMaintenanceTaskRun@Private@34567@UTestAPI@Private@34567@UTestConfigurationRegistration@Private@34567@@wil@@AEAAXXZ`
- size: `655`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180010a94`

## callees

- `0x180003870`
- `0x1800038b8`
- `0x18000c268`
- `0x18000e604`
- `0x18000ef68`
- `0x180010788`
- `0x1800107b0`
- `0x180010920`
- `0x180010d9c`
- `0x18001112c`
- `0x1800113b8`
- `0x180014c40`
- `0x18001ba58`
- `0x180022c20`
- `0x180108010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180010e10`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180010e10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010e22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010e34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010ee2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010f8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010e22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010e34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010ee2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010f8b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010e53`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010eff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010f9e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010e53`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010eff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010f9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010e3f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010e3f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x180010f96`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x180010f96`
- `combase!__imp_CoGetSharedServiceId` at `0x180010deb`
- `combase!__imp_CoGetSharedServiceId` at `0x180010deb`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180010e7b`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180010e7b`

## string_xrefs

- `0x180011019`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180010e9d`: `pre_start_service`
- `0x180010dd4`: `onecore\internal\sdk\inc\wil\cppwinrtservice.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::svchost_service<CsiServiceTraits,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactProducer,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactConsumer,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestAPI,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestConfigurationRegistration>::start(
        void (__fastcall ***a1)(void *, __int64))
{
  int SharedServiceId; // eax
  void *v2; // rdx
  HANDLE Event; // rdi
  unsigned int v4; // r8d
  const char *v5; // r9
  HANDLE v6; // rbx
  DWORD LastError; // esi
  const char *v8; // r9
  int v9; // eax
  UsageAndQualityInsights::Utilities *v10; // rcx
  __int64 *updated; // rdi
  __int64 v12; // r14
  void (__fastcall ***v13)(_QWORD, __int64); // rsi
  DWORD v14; // ebx
  void *v15; // rax
  void *v16; // rbx
  void (__fastcall *v17)(HANDLE *, const WCHAR *, HANDLE, __int64 (__fastcall *)(), __int64 *, int); // r14
  HANDLE v18; // rsi
  HANDLE v19; // rdi
  DWORD v20; // ebx
  int v22; // [rsp+40h] [rbp-28h] BYREF
  const char *v23; // [rsp+48h] [rbp-20h]
  __int64 v24; // [rsp+50h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+30h]
  void (__fastcall ***v26)(void *, __int64); // [rsp+A0h] [rbp+38h] BYREF

  v26 = a1;
  wil::svchost_service<CsiServiceTraits,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactProducer,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactConsumer,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestAPI,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestConfigurationRegistration>::update_status(
    &g_service,
    2);
  LODWORD(v26) = 0;
  v22 = 147;
  v23 = "onecore\\internal\\sdk\\inc\\wil\\cppwinrtservice.h";
  v24 = 0;
  SharedServiceId = CoGetSharedServiceId(&v26);
  if ( SharedServiceId < 0 )
    winrt::throw_hresult((unsigned int)SharedServiceId, &v22);
  wil::details::g_service_id = (unsigned int)v26;
  Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
  if ( !Event )
    wil::details::in1diag3::Throw_GetLastError(retaddr, v2, v4, v5);
  GetLastError();
  v6 = hObject;
  if ( hObject )
  {
    LastError = GetLastError();
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v8);
    SetLastError(LastError);
  }
  hObject = Event;
  v22 = 468;
  v23 = "onecore\\internal\\sdk\\inc\\wil\\cppwinrtservice.h";
  v24 = 0;
  v9 = CoRegisterServerShutdownDelay(Event, 60000);
  if ( v9 < 0 )
    winrt::throw_hresult((unsigned int)v9, &v22);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UsageAndQualityInsights>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_UsageAndQualityInsights>::GetImpl'::`2'::impl) )
  {
    UsageAndQualityInsightsTraceLogging::TraceLoggingInfo("pre_start_service");
    if ( !UsageAndQualityInsights::Utilities::IsPolicyRestricted(v10) )
    {
      GetServiceObj(&v22);
      updated = (__int64 *)UsageAndQualityInsights::Ingestion::WnfListener::CreateMetricEventGroupUpdateSubscription(&v26);
      if ( &g_subscription != updated )
      {
        v12 = *updated;
        v13 = (void (__fastcall ***)(_QWORD, __int64))g_subscription;
        if ( g_subscription )
        {
          v14 = GetLastError();
          (**v13)(v13, 1);
          SetLastError(v14);
        }
        g_subscription = v12;
        *updated = 0;
      }
      if ( v26 )
        (**v26)(v26, 1);
    }
  }
  v26 = (void (__fastcall ***)(void *, __int64))operator new(0x18u);
  v15 = (void *)wil::details::svchost_module<winrt::Windows::Internal::Data::UsageAndQualityInsights::FactProducer,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactConsumer,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestAPI,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestConfigurationRegistration>::svchost_module<winrt::Windows::Internal::Data::UsageAndQualityInsights::FactProducer,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactConsumer,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestAPI,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestConfigurationRegistration>(v26);
  v16 = qword_18015A018;
  qword_18015A018 = v15;
  if ( v16 )
  {
    wil::details::svchost_module<winrt::Windows::Internal::Data::UsageAndQualityInsights::FactProducer,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactConsumer,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestAPI,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestConfigurationRegistration>::~svchost_module<winrt::Windows::Internal::Data::UsageAndQualityInsights::FactProducer,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactConsumer,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestAPI,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestConfigurationRegistration>(v16);
    operator delete(v16, 0x18u);
  }
  v17 = *(void (__fastcall **)(HANDLE *, const WCHAR *, HANDLE, __int64 (__fastcall *)(), __int64 *, int))(g_service + 192);
  v18 = hObject;
  v19 = WaitHandle;
  if ( WaitHandle )
  {
    v20 = GetLastError();
    UnregisterWait(v19);
    SetLastError(v20);
  }
  WaitHandle = 0;
  v17(
    &WaitHandle,
    L"wuqisvc",
    v18,
    `wil::svchost_service<CsiServiceTraits,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactProducer,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactConsumer,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestAPI,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestConfigurationRegistration>::start'::`2'::_lambda_1_::_lambda_invoker_cdecl_,
    &g_service,
    8);
  return wil::svchost_service<CsiServiceTraits,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactProducer,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactConsumer,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestAPI,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestConfigurationRegistration>::update_status(
           &g_service,
           4);
}

```

## disassembly

```asm
0x180010d9c  mov     [rsp-30h+arg_0], rcx
0x180010da1  push    rbp
0x180010da2  push    rbx
0x180010da3  push    rsi
0x180010da4  push    rdi
0x180010da5  push    r13
0x180010da7  push    r14
0x180010da9  mov     rbp, rsp
0x180010dac  sub     rsp, 68h
0x180010db0  xor     r8d, r8d
0x180010db3  lea     edx, [r8+2]
0x180010db7  lea     r13, ?g_service@@3V?$svchost_service@UCsiServiceTraits@@UFactProducer@UsageAndQualityInsights@Data@Internal@Windows@winrt@@UFactConsumer@34567@UUQIMaintenanceTaskRun@Private@34567@UTestAPI@Private@34567@UTestConfigurationRegistration@Private@34567@@wil@@A; wil::svchost_service<CsiServiceTraits,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactProducer,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactConsumer,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestAPI,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestConfigurationRegistration> g_service
0x180010dbe  mov     rcx, r13
0x180010dc1  call    ?update_status@?$svchost_service@UCsiServiceTraits@@UFactProducer@UsageAndQualityInsights@Data@Internal@Windows@winrt@@UFactConsumer@34567@UUQIMaintenanceTaskRun@Private@34567@UTestAPI@Private@34567@UTestConfigurationRegistration@Private@34567@@wil@@AEAAXKK@Z; wil::svchost_service<CsiServiceTraits,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactProducer,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactConsumer,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestAPI,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestConfigurationRegistration>::update_status(ulong,ulong)
0x180010dc6  mov     dword ptr [rbp+arg_0], 0
0x180010dcd  mov     [rbp+var_28], 93h
0x180010dd4  lea     r14, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\cppwi"...
0x180010ddb  mov     [rbp+var_20], r14
0x180010ddf  mov     [rbp+var_18], 0
0x180010de7  lea     rcx, [rbp+arg_0]
0x180010deb  call    cs:__imp_CoGetSharedServiceId
0x180010df1  test    eax, eax
0x180010df3  js      loc_18001100D
0x180010df9  mov     eax, dword ptr [rbp+arg_0]
0x180010dfc  mov     cs:?g_service_id@details@wil@@3KA, eax; ulong wil::details::g_service_id
0x180010e02  xor     edx, edx; lpName
0x180010e04  xor     ecx, ecx; lpEventAttributes
0x180010e06  mov     r9d, 1F0003h; dwDesiredAccess
0x180010e0c  lea     r8d, [rdx+1]; dwFlags
0x180010e10  call    cs:__imp_CreateEventExW
0x180010e16  mov     rdi, rax
0x180010e19  test    rax, rax
0x180010e1c  jz      loc_180011003
0x180010e22  call    cs:__imp_GetLastError
0x180010e28  mov     rbx, cs:hObject
0x180010e2f  test    rbx, rbx
0x180010e32  jz      short loc_180010E59
0x180010e34  call    cs:__imp_GetLastError
0x180010e3a  mov     esi, eax
0x180010e3c  mov     rcx, rbx; hObject
0x180010e3f  call    cs:__imp_CloseHandle
0x180010e45  mov     rcx, [rbp+30h]; this
0x180010e49  test    eax, eax
0x180010e4b  jz      loc_180011019
0x180010e51  mov     ecx, esi; dwErrCode
0x180010e53  call    cs:__imp_SetLastError
0x180010e59  mov     cs:hObject, rdi
0x180010e60  mov     [rbp+var_28], 1D4h
0x180010e67  mov     [rbp+var_20], r14
0x180010e6b  mov     [rbp+var_18], 0
0x180010e73  mov     edx, 0EA60h
0x180010e78  mov     rcx, rdi
0x180010e7b  call    cs:__imp_CoRegisterServerShutdownDelay
0x180010e81  test    eax, eax
0x180010e83  js      loc_180010FF7
0x180010e89  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UsageAndQualityInsights@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UsageAndQualityInsights@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UsageAndQualityInsights> `wil::Feature<__WilFeatureTraits_Feature_UsageAndQualityInsights>::GetImpl(void)'::`2'::impl
0x180010e90  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UsageAndQualityInsights@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UsageAndQualityInsights>::__private_IsEnabled(void)
0x180010e95  test    al, al
0x180010e97  jz      loc_180010F2C
0x180010e9d  lea     rcx, aPreStartServic; "pre_start_service"
0x180010ea4  call    ?TraceLoggingInfo@UsageAndQualityInsightsTraceLogging@@SAXPEBDZZ; UsageAndQualityInsightsTraceLogging::TraceLoggingInfo(char const *,...)
0x180010ea9  call    ?IsPolicyRestricted@Utilities@UsageAndQualityInsights@@YA_NXZ; UsageAndQualityInsights::Utilities::IsPolicyRestricted(void)
0x180010eae  test    al, al
0x180010eb0  jnz     short loc_180010F2C
0x180010eb2  lea     rcx, [rbp+var_28]
0x180010eb6  call    ?GetServiceObj@@YA?AV?$optional@V?$reference_wrapper@VUQIService@@@std@@@std@@XZ; GetServiceObj(void)
0x180010ebb  lea     rcx, [rbp+arg_0]
0x180010ebf  call    ?CreateMetricEventGroupUpdateSubscription@WnfListener@Ingestion@UsageAndQualityInsights@@SA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; UsageAndQualityInsights::Ingestion::WnfListener::CreateMetricEventGroupUpdateSubscription(void)
0x180010ec4  mov     rdi, rax
0x180010ec7  lea     rax, ?g_subscription@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>> g_subscription
0x180010ece  cmp     rax, rdi
0x180010ed1  jz      short loc_180010F13
0x180010ed3  mov     r14, [rdi]
0x180010ed6  mov     rsi, cs:?g_subscription@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>> g_subscription
0x180010edd  test    rsi, rsi
0x180010ee0  jz      short loc_180010F05
0x180010ee2  call    cs:__imp_GetLastError
0x180010ee8  mov     ebx, eax
0x180010eea  mov     rdx, [rsi]
0x180010eed  mov     rax, [rdx]
0x180010ef0  mov     edx, 1
0x180010ef5  mov     rcx, rsi
0x180010ef8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010efd  mov     ecx, ebx; dwErrCode
0x180010eff  call    cs:__imp_SetLastError
0x180010f05  mov     cs:?g_subscription@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@wil@@A, r14; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>> g_subscription
0x180010f0c  mov     qword ptr [rdi], 0
0x180010f13  mov     rcx, [rbp+arg_0]
0x180010f17  test    rcx, rcx
0x180010f1a  jz      short loc_180010F2C
0x180010f1c  mov     rax, [rcx]
0x180010f1f  mov     edx, 1
0x180010f24  mov     rax, [rax]
0x180010f27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f2c  mov     edi, 18h
0x180010f31  mov     ecx, edi; Size
0x180010f33  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010f38  mov     [rbp+arg_0], rax
0x180010f3c  mov     rcx, rax
0x180010f3f  call    ??0?$svchost_module@UFactProducer@UsageAndQualityInsights@Data@Internal@Windows@winrt@@UFactConsumer@23456@UUQIMaintenanceTaskRun@Private@23456@UTestAPI@923456@UTestConfigurationRegistration@923456@@details@wil@@QEAA@XZ; wil::details::svchost_module<winrt::Windows::Internal::Data::UsageAndQualityInsights::FactProducer,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactConsumer,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestAPI,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestConfigurationRegistration>::svchost_module<winrt::Windows::Internal::Data::UsageAndQualityInsights::FactProducer,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactConsumer,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestAPI,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestConfigurationRegistration>(void)
0x180010f44  nop
0x180010f45  mov     rbx, cs:qword_18015A018
0x180010f4c  mov     cs:qword_18015A018, rax
0x180010f53  test    rbx, rbx
0x180010f56  jz      short loc_180010F6A
0x180010f58  mov     rcx, rbx
0x180010f5b  call    ??1?$svchost_module@UFactProducer@UsageAndQualityInsights@Data@Internal@Windows@winrt@@UFactConsumer@23456@UUQIMaintenanceTaskRun@Private@23456@UTestAPI@923456@UTestConfigurationRegistration@923456@@details@wil@@QEAA@XZ; wil::details::svchost_module<winrt::Windows::Internal::Data::UsageAndQualityInsights::FactProducer,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactConsumer,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestAPI,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestConfigurationRegistration>::~svchost_module<winrt::Windows::Internal::Data::UsageAndQualityInsights::FactProducer,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactConsumer,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestAPI,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestConfigurationRegistration>(void)
0x180010f60  mov     edx, edi; unsigned __int64
0x180010f62  mov     rcx, rbx; void *
0x180010f65  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180010f6a  mov     rax, cs:?g_service@@3V?$svchost_service@UCsiServiceTraits@@UFactProducer@UsageAndQualityInsights@Data@Internal@Windows@winrt@@UFactConsumer@34567@UUQIMaintenanceTaskRun@Private@34567@UTestAPI@Private@34567@UTestConfigurationRegistration@Private@34567@@wil@@A; wil::svchost_service<CsiServiceTraits,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactProducer,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactConsumer,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestAPI,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestConfigurationRegistration> g_service
0x180010f71  mov     r14, [rax+0C0h]
0x180010f78  mov     rsi, cs:hObject
0x180010f7f  mov     rdi, cs:WaitHandle
0x180010f86  test    rdi, rdi
0x180010f89  jz      short loc_180010FA4
0x180010f8b  call    cs:__imp_GetLastError
0x180010f91  mov     ebx, eax
0x180010f93  mov     rcx, rdi; WaitHandle
0x180010f96  call    cs:__imp_UnregisterWait
0x180010f9c  mov     ecx, ebx; dwErrCode
0x180010f9e  call    cs:__imp_SetLastError
0x180010fa4  mov     cs:WaitHandle, 0
0x180010faf  mov     [rsp+68h+var_40], 8
0x180010fb7  mov     [rsp+68h+var_48], r13
0x180010fbc  lea     r9, ?_lambda_invoker_cdecl_@_lambda_1_@?1??start@?$svchost_service@UCsiServiceTraits@@UFactProducer@UsageAndQualityInsights@Data@Internal@Windows@winrt@@UFactConsumer@34567@UUQIMaintenanceTaskRun@Private@34567@UTestAPI@Private@34567@UTestConfigurationRegistration@Private@34567@@wil@@AEAAXXZ@SA@PEAXE@Z; `wil::svchost_service<CsiServiceTraits,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactProducer,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactConsumer,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestAPI,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestConfigurationRegistration>::start(void)'::`2'::_lambda_1_::_lambda_invoker_cdecl_(void *,uchar)
0x180010fc3  mov     r8, rsi
0x180010fc6  lea     rdx, ServiceName; "wuqisvc"
0x180010fcd  lea     rcx, WaitHandle
0x180010fd4  mov     rax, r14
0x180010fd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010fdc  xor     r8d, r8d
0x180010fdf  lea     edx, [r8+4]
0x180010fe3  mov     rcx, r13
0x180010fe6  add     rsp, 68h
0x180010fea  pop     r14
0x180010fec  pop     r13
0x180010fee  pop     rdi
0x180010fef  pop     rsi
0x180010ff0  pop     rbx
0x180010ff1  pop     rbp
0x180010ff2  jmp     ?update_status@?$svchost_service@UCsiServiceTraits@@UFactProducer@UsageAndQualityInsights@Data@Internal@Windows@winrt@@UFactConsumer@34567@UUQIMaintenanceTaskRun@Private@34567@UTestAPI@Private@34567@UTestConfigurationRegistration@Private@34567@@wil@@AEAAXKK@Z; wil::svchost_service<CsiServiceTraits,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactProducer,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactConsumer,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestAPI,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestConfigurationRegistration>::update_status(ulong,ulong)
0x180010ff7  lea     rdx, [rbp+var_28]
0x180010ffb  mov     ecx, eax
0x180010ffd  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180011003  mov     rcx, [rbp+30h]; this
0x180011007  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18001100d  lea     rdx, [rbp+var_28]
0x180011011  mov     ecx, eax
0x180011013  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180011019  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180011020  mov     edx, 0A0Bh; void *
0x180011025  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
