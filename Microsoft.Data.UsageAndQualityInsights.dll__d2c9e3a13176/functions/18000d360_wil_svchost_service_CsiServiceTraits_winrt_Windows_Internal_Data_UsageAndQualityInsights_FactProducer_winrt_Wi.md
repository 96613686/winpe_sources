# `wil::svchost_service<CsiServiceTraits,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactProducer,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactConsumer,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestAPI,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestConfigurationRegistration>::main(void)'::`2'::_lambda_1_::_lambda_invoker_cdecl_(ulong,ulong,void *,void *)

- ea: `0x18000d360`
- end: `0x18000d4af`
- name: `?_lambda_invoker_cdecl_@_lambda_1_@?1??main@?$svchost_service@UCsiServiceTraits@@UFactProducer@UsageAndQualityInsights@Data@Internal@Windows@winrt@@UFactConsumer@34567@UUQIMaintenanceTaskRun@Private@34567@UTestAPI@Private@34567@UTestConfigurationRegistration@Private@34567@@wil@@QEAAXXZ@SA@KKPEAX0@Z`
- size: `335`
- prototype: `DWORD __stdcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x1800079a4`
- `0x18000c268`
- `0x18000d360`
- `0x18000e3a4`
- `0x1800107b0`
- `0x180010920`
- `0x1800109fc`
- `0x1800113b8`
- `0x18001ba58`
- `0x18001bddc`
- `0x180108010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000d38e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000d38e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000d456`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000d456`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d41e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d41e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d440`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d440`

## string_xrefs

- `0x18000d48b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000d49d`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000d3d1`: `try_service_stop`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall `wil::svchost_service<CsiServiceTraits,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactProducer,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactConsumer,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestAPI,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestConfigurationRegistration>::main'::`2'::_lambda_1_::_lambda_invoker_cdecl_(
        DWORD dwControl,
        DWORD dwEventType,
        LPVOID lpEventData,
        HANDLE *lpContext)
{
  DWORD v5; // ecx
  DWORD v6; // ecx
  unsigned int v7; // ebx
  DWORD v8; // eax
  const char *v9; // r9
  char v10; // dl
  winrt *v11; // rcx
  void (__fastcall ***v12)(_QWORD, __int64); // rdi
  DWORD LastError; // ebp
  const char *v14; // r9
  UQIService *v16; // [rsp+20h] [rbp-38h] BYREF
  char v17; // [rsp+28h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v5 = dwControl - 1;
  if ( v5 )
  {
    v6 = v5 - 3;
    if ( v6 )
    {
      if ( v6 == 28 )
      {
        v8 = WaitForSingleObjectEx(lpContext[2], 0, 0);
        if ( v8 == 258 )
        {
          v10 = 0;
        }
        else
        {
          if ( v8 )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0xB0F,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
              v9);
          v10 = 1;
        }
        return v10 != 0 ? 0x45B : 0;
      }
      else
      {
        return 120;
      }
    }
    else
    {
      return 0;
    }
  }
  else
  {
    wil::svchost_service<CsiServiceTraits,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactProducer,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactConsumer,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestAPI,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestConfigurationRegistration>::update_status(
      (__int64)lpContext,
      3u,
      0);
    UsageAndQualityInsightsTraceLogging::TraceLoggingInfo("try_service_stop");
    v7 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UsageAndQualityInsights>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UsageAndQualityInsights>::GetImpl'::`2'::impl) )
    {
      GetServiceObj(&v16);
      if ( v17 )
        UQIService::OnShutdown((struct _RTL_CRITICAL_SECTION *)v16);
    }
    if ( (unsigned __int8)wil::svchost_service_traits__UsageAndQualityInsights::Constants::UQI_SERVICE_NAME__c_defaultShutdownDelay_::try_stop_service_winrt::Windows::Internal::Data::UsageAndQualityInsights::FactProducer_winrt::Windows::Internal::Data::UsageAndQualityInsights::FactConsumer_winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun_winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestAPI_winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestConfigurationRegistration_() )
    {
      v12 = (void (__fastcall ***)(_QWORD, __int64))g_subscription;
      if ( g_subscription )
      {
        LastError = GetLastError();
        (**v12)(v12, 1);
        SetLastError(LastError);
      }
      g_subscription = 0;
      winrt::clear_factory_cache(v11);
      if ( !SetEvent(lpContext[2]) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA01,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v14);
    }
    else
    {
      wil::svchost_service<CsiServiceTraits,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactProducer,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactConsumer,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestAPI,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestConfigurationRegistration>::update_status(
        (__int64)lpContext,
        4u,
        0);
      return 170;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18000d360  push    rbx
0x18000d362  push    rbp
0x18000d363  push    rsi
0x18000d364  push    rdi
0x18000d365  sub     rsp, 38h
0x18000d369  mov     rsi, r9
0x18000d36c  sub     ecx, 1
0x18000d36f  jz      short loc_18000D3C2
0x18000d371  sub     ecx, 3
0x18000d374  jz      short loc_18000D3BB
0x18000d376  cmp     ecx, 1Ch
0x18000d379  jz      short loc_18000D385
0x18000d37b  mov     ebx, 78h ; 'x'
0x18000d380  jmp     loc_18000D47B
0x18000d385  xor     r8d, r8d; bAlertable
0x18000d388  xor     edx, edx; dwMilliseconds
0x18000d38a  mov     rcx, [r9+10h]; hHandle
0x18000d38e  call    cs:__imp_WaitForSingleObjectEx
0x18000d394  cmp     eax, 102h
0x18000d399  jz      short loc_18000D3A8
0x18000d39b  test    eax, eax
0x18000d39d  jnz     loc_18000D486
0x18000d3a3  lea     edx, [rax+1]
0x18000d3a6  jmp     short loc_18000D3AC
0x18000d3a8  xor     ebx, ebx
0x18000d3aa  mov     dl, bl
0x18000d3ac  neg     dl
0x18000d3ae  sbb     ebx, ebx
0x18000d3b0  and     ebx, 45Bh
0x18000d3b6  jmp     loc_18000D47B
0x18000d3bb  xor     ebx, ebx
0x18000d3bd  jmp     loc_18000D47B
0x18000d3c2  xor     r8d, r8d
0x18000d3c5  lea     edx, [r8+3]
0x18000d3c9  mov     rcx, rsi
0x18000d3cc  call    ?update_status@?$svchost_service@UCsiServiceTraits@@UFactProducer@UsageAndQualityInsights@Data@Internal@Windows@winrt@@UFactConsumer@34567@UUQIMaintenanceTaskRun@Private@34567@UTestAPI@Private@34567@UTestConfigurationRegistration@Private@34567@@wil@@AEAAXKK@Z; wil::svchost_service<CsiServiceTraits,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactProducer,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactConsumer,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestAPI,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestConfigurationRegistration>::update_status(ulong,ulong)
0x18000d3d1  lea     rcx, aTryServiceStop; "try_service_stop"
0x18000d3d8  call    ?TraceLoggingInfo@UsageAndQualityInsightsTraceLogging@@SAXPEBDZZ; UsageAndQualityInsightsTraceLogging::TraceLoggingInfo(char const *,...)
0x18000d3dd  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UsageAndQualityInsights@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UsageAndQualityInsights@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UsageAndQualityInsights> `wil::Feature<__WilFeatureTraits_Feature_UsageAndQualityInsights>::GetImpl(void)'::`2'::impl
0x18000d3e4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UsageAndQualityInsights@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UsageAndQualityInsights>::__private_IsEnabled(void)
0x18000d3e9  xor     ebx, ebx
0x18000d3eb  test    al, al
0x18000d3ed  jz      short loc_18000D409
0x18000d3ef  lea     rcx, [rsp+58h+var_38]
0x18000d3f4  call    ?GetServiceObj@@YA?AV?$optional@V?$reference_wrapper@VUQIService@@@std@@@std@@XZ; GetServiceObj(void)
0x18000d3f9  cmp     [rsp+58h+var_30], bl
0x18000d3fd  jz      short loc_18000D409
0x18000d3ff  mov     rcx, [rsp+58h+var_38]; this
0x18000d404  call    ?OnShutdown@UQIService@@QEAAXXZ; UQIService::OnShutdown(void)
0x18000d409  call    wil__svchost_service_traits__UsageAndQualityInsights__Constants__UQI_SERVICE_NAME__c_defaultShutdownDelay___try_stop_service_winrt__Windows__Internal__Data__UsageAndQualityInsights__FactProducer_winrt__Windows__Internal__Data__UsageAndQualityInsights__FactConsumer_winrt__Windows__Internal__Data__UsageAndQualityInsights__Private__UQIMaintenanceTaskRun_winrt__Windows__Internal__Data__UsageAndQualityInsights__Private__TestAPI_winrt__Windows__Internal__Data__UsageAndQualityInsights__Private__TestConfigurationRegistration_
0x18000d40e  test    al, al
0x18000d410  jz      short loc_18000D467
0x18000d412  mov     rdi, cs:?g_subscription@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>> g_subscription
0x18000d419  test    rdi, rdi
0x18000d41c  jz      short loc_18000D446
0x18000d41e  call    cs:__imp_GetLastError
0x18000d424  mov     ebp, eax
0x18000d426  test    rdi, rdi
0x18000d429  jz      short loc_18000D43E
0x18000d42b  mov     rdx, [rdi]
0x18000d42e  mov     rax, [rdx]
0x18000d431  mov     edx, 1
0x18000d436  mov     rcx, rdi
0x18000d439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d43e  mov     ecx, ebp; dwErrCode
0x18000d440  call    cs:__imp_SetLastError
0x18000d446  mov     cs:?g_subscription@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@wil@@A, rbx; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>> g_subscription
0x18000d44d  call    ?clear_factory_cache@winrt@@YAXXZ; winrt::clear_factory_cache(void)
0x18000d452  mov     rcx, [rsi+10h]; hEvent
0x18000d456  call    cs:__imp_SetEvent
0x18000d45c  mov     rcx, [rsp+58h]; this
0x18000d461  test    eax, eax
0x18000d463  jz      short loc_18000D49D
0x18000d465  jmp     short loc_18000D47B
0x18000d467  xor     r8d, r8d
0x18000d46a  lea     edx, [r8+4]
0x18000d46e  mov     rcx, rsi
0x18000d471  call    ?update_status@?$svchost_service@UCsiServiceTraits@@UFactProducer@UsageAndQualityInsights@Data@Internal@Windows@winrt@@UFactConsumer@34567@UUQIMaintenanceTaskRun@Private@34567@UTestAPI@Private@34567@UTestConfigurationRegistration@Private@34567@@wil@@AEAAXKK@Z; wil::svchost_service<CsiServiceTraits,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactProducer,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactConsumer,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestAPI,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestConfigurationRegistration>::update_status(ulong,ulong)
0x18000d476  mov     ebx, 0AAh
0x18000d47b  mov     eax, ebx
0x18000d47d  add     rsp, 38h
0x18000d481  pop     rdi
0x18000d482  pop     rsi
0x18000d483  pop     rbp
0x18000d484  pop     rbx
0x18000d485  retn
0x18000d486  mov     rcx, [rsp+58h]; this
0x18000d48b  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000d492  mov     edx, 0B0Fh; void *
0x18000d497  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000d49d  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000d4a4  mov     edx, 0A01h; void *
0x18000d4a9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
