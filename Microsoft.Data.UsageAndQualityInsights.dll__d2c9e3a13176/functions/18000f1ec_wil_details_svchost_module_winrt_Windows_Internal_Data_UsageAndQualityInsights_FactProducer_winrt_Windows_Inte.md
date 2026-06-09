# `wil::details::svchost_module<winrt::Windows::Internal::Data::UsageAndQualityInsights::FactProducer,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactConsumer,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestAPI,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestConfigurationRegistration>::RunInContext<`wil::details::svchost_module<winrt::Windows::Internal::Data::UsageAndQualityInsights::FactProducer,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactConsumer,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestAPI,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestConfigurationRegistration>::unregister_and_stop_and_wait(void)'::`2'::_lambda_1_>(`wil::details::svchost_module<winrt::Windows::Internal::Data::UsageAndQualityInsights::FactProducer,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactConsumer,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestAPI,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestConfigurationRegistration>::unregister_and_stop_and_wait(void)'::`2'::_lambda_1_ &&)'::`2'::_lambda_1_::operator()(tagComCallData *)

- ea: `0x18000f1ec`
- end: `0x18000f281`
- name: `??R_lambda_1_@?1???$RunInContext@V_lambda_1_@?1??unregister_and_stop_and_wait@?$svchost_module@UFactProducer@UsageAndQualityInsights@Data@Internal@Windows@winrt@@UFactConsumer@23456@UUQIMaintenanceTaskRun@Private@23456@UTestAPI@923456@UTestConfigurationRegistration@923456@@details@wil@@AEAAXXZ@@?$svchost_module@UFactProducer@UsageAndQualityInsights@Data@Internal@Windows@winrt@@UFactConsumer@23456@UUQIMaintenanceTaskRun@Private@23456@UTestAPI@923456@UTestConfigurationRegistration@923456@@details@wil@@AEAAX$$QEAV0?1??unregister_and_stop_and_wait@123@AEAAXXZ@@Z@QEBAJPEAUtagComCallData@@@Z`
- size: `149`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000d2c0`

## callees

- `0x18000f1ec`
- `0x18001112c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f210`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f210`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f223`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f223`
- `api-ms-win-core-com-l1-1-0!CoDisconnectContext` at `0x18000f251`
- `api-ms-win-core-com-l1-1-0!CoDisconnectContext` at `0x18000f251`
- `api-ms-win-core-winrt-l1-1-0!RoRevokeActivationFactories` at `0x18000f21b`
- `api-ms-win-core-winrt-l1-1-0!RoRevokeActivationFactories` at `0x18000f21b`

## string_xrefs

- `0x18000f239`: `onecore\internal\sdk\inc\wil\cppwinrtservice.h`

## pseudocode

```c

```
