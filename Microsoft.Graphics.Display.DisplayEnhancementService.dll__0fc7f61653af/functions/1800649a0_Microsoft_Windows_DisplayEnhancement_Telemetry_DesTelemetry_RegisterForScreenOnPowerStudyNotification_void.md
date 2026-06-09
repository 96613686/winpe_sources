# Microsoft::Windows::DisplayEnhancement::Telemetry::DesTelemetry::RegisterForScreenOnPowerStudyNotification(void)

- ea: `0x1800649a0`
- end: `0x180064a29`
- name: `?RegisterForScreenOnPowerStudyNotification@DesTelemetry@Telemetry@DisplayEnhancement@Windows@Microsoft@@AEAAXXZ`
- size: `137`
- prototype: `void __fastcall(Microsoft::Windows::DisplayEnhancement::Telemetry::DesTelemetry *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180061884`

## callees

- `0x18001c68c`
- `0x180064274`

## import_xrefs

- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800649ee`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800649ee`

## string_xrefs

- `0x1800649f9`: `onecoreuap\drivers\mobilepc\displayenhancement\service\telemetry\lib\destelemetry.cpp`

## pseudocode

```c

```
