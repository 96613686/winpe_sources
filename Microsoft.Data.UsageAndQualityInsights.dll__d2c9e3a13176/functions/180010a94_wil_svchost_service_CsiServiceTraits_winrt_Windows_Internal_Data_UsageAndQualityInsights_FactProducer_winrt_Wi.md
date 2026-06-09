# wil::svchost_service<CsiServiceTraits,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactProducer,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactConsumer,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestAPI,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestConfigurationRegistration>::main(void)

- ea: `0x180010a94`
- end: `0x180010b1e`
- name: `?main@?$svchost_service@UCsiServiceTraits@@UFactProducer@UsageAndQualityInsights@Data@Internal@Windows@winrt@@UFactConsumer@34567@UUQIMaintenanceTaskRun@Private@34567@UTestAPI@Private@34567@UTestConfigurationRegistration@Private@34567@@wil@@QEAAXXZ`
- size: `138`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180010740`

## callees

- `0x180010a94`
- `0x180010d9c`
- `0x180011358`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180010ad5`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180010ad5`

## string_xrefs

- `0x180010aa3`: `onecore\internal\sdk\inc\wil\cppwinrtservice.h`

## pseudocode

```c
__int64 __fastcall wil::svchost_service<CsiServiceTraits,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactProducer,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactConsumer,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestAPI,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestConfigurationRegistration>::main(
        __int64 a1,
        const struct winrt::impl::slim_source_location *a2)
{
  SERVICE_STATUS_HANDLE v2; // rax
  const struct winrt::impl::slim_source_location *v3; // rdx
  LPVOID *v4; // rcx
  __int64 result; // rax
  const winrt::hresult_error *v6; // [rsp+20h] [rbp-28h] BYREF
  int v7; // [rsp+28h] [rbp-20h] BYREF
  const char *v8; // [rsp+30h] [rbp-18h]
  __int64 v9; // [rsp+38h] [rbp-10h]

  v7 = 383;
  v8 = "onecore\\internal\\sdk\\inc\\wil\\cppwinrtservice.h";
  v9 = 0;
  if ( !g_service )
    winrt::throw_last_error((winrt *)&v7, a2);
  v2 = RegisterServiceCtrlHandlerExW(
         L"wuqisvc",
         `wil::svchost_service<CsiServiceTraits,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactProducer,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactConsumer,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestAPI,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestConfigurationRegistration>::main'::`2'::_lambda_1_::_lambda_invoker_cdecl_,
         &g_service);
  qword_18015A020 = (__int64)v2;
  v7 = 390;
  v8 = "onecore\\internal\\sdk\\inc\\wil\\cppwinrtservice.h";
  v9 = 0;
  if ( !v2 )
    winrt::throw_last_error((winrt *)&v7, v3);
  try
  {
    result = wil::svchost_service<CsiServiceTraits,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactProducer,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactConsumer,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestAPI,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestConfigurationRegistration>::start(v4);
  }
  catch ( const winrt::hresult_error *v6 )
  {
    return wil::svchost_service<CsiServiceTraits,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactProducer,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactConsumer,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestAPI,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestConfigurationRegistration>::stop(
             &g_service,
             *((unsigned int *)v6 + 3));
  }
  return result;
}

```

## disassembly

```asm
0x180010a94  mov     rax, rsp
0x180010a97  push    rdi
0x180010a98  sub     rsp, 40h
0x180010a9c  mov     dword ptr [rax-20h], 17Fh
0x180010aa3  lea     rdi, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\cppwi"...
0x180010aaa  mov     [rax-18h], rdi
0x180010aae  mov     qword ptr [rax-10h], 0
0x180010ab6  cmp     cs:?g_service@@3V?$svchost_service@UCsiServiceTraits@@UFactProducer@UsageAndQualityInsights@Data@Internal@Windows@winrt@@UFactConsumer@34567@UUQIMaintenanceTaskRun@Private@34567@UTestAPI@Private@34567@UTestConfigurationRegistration@Private@34567@@wil@@A, 0; wil::svchost_service<CsiServiceTraits,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactProducer,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactConsumer,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestAPI,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestConfigurationRegistration> g_service
0x180010abe  jz      short loc_180010B09
0x180010ac0  lea     r8, ?g_service@@3V?$svchost_service@UCsiServiceTraits@@UFactProducer@UsageAndQualityInsights@Data@Internal@Windows@winrt@@UFactConsumer@34567@UUQIMaintenanceTaskRun@Private@34567@UTestAPI@Private@34567@UTestConfigurationRegistration@Private@34567@@wil@@A; lpContext
0x180010ac7  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??main@?$svchost_service@UCsiServiceTraits@@UFactProducer@UsageAndQualityInsights@Data@Internal@Windows@winrt@@UFactConsumer@34567@UUQIMaintenanceTaskRun@Private@34567@UTestAPI@Private@34567@UTestConfigurationRegistration@Private@34567@@wil@@QEAAXXZ@SA@KKPEAX0@Z; lpHandlerProc
0x180010ace  lea     rcx, ServiceName; "wuqisvc"
0x180010ad5  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180010adb  mov     cs:qword_18015A020, rax
0x180010ae2  mov     [rsp+48h+var_20], 186h
0x180010aea  mov     [rsp+48h+var_18], rdi
0x180010aef  mov     [rsp+48h+var_10], 0
0x180010af8  test    rax, rax
0x180010afb  jz      short loc_180010B13
0x180010afd  call    ?start@?$svchost_service@UCsiServiceTraits@@UFactProducer@UsageAndQualityInsights@Data@Internal@Windows@winrt@@UFactConsumer@34567@UUQIMaintenanceTaskRun@Private@34567@UTestAPI@Private@34567@UTestConfigurationRegistration@Private@34567@@wil@@AEAAXXZ; wil::svchost_service<CsiServiceTraits,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactProducer,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactConsumer,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestAPI,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestConfigurationRegistration>::start(void)
0x180010b02  nop
0x180010b03  add     rsp, 40h
0x180010b07  pop     rdi
0x180010b08  retn
0x180010b09  lea     rcx, [rax-20h]; this
0x180010b0d  call    ?throw_last_error@winrt@@YAXAEBUslim_source_location@impl@1@@Z; winrt::throw_last_error(winrt::impl::slim_source_location const &)
0x180010b13  lea     rcx, [rsp+48h+var_20]; this
0x180010b18  call    ?throw_last_error@winrt@@YAXAEBUslim_source_location@impl@1@@Z; winrt::throw_last_error(winrt::impl::slim_source_location const &)
```
