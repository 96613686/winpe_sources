# Windows::Compat::Shared::Telemetry::TelemetryProvider::InitializeProviders(bool)

- ea: `0x18001fc0c`
- end: `0x18001fded`
- name: `?InitializeProviders@TelemetryProvider@Telemetry@Shared@Compat@Windows@@IEAAX_N@Z`
- size: `481`
- prototype: `void __fastcall(Windows::Compat::Shared::Telemetry::TelemetryProvider *__hidden this, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180002300`

## callees

- `0x180001160`
- `0x18001fc0c`
- `0x180020250`
- `0x180020370`

## import_xrefs

- `ntdll!WinSqmIsOptedInEx` at `0x18001fc8c`
- `ntdll!WinSqmIsOptedInEx` at `0x18001fdaf`
- `ntdll!WinSqmIsOptedInEx` at `0x18001fc8c`
- `ntdll!WinSqmIsOptedInEx` at `0x18001fdaf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001fd06`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001fd06`

## string_xrefs

- `0x18001fcd4`: `CommercialDataOptIn`

## pseudocode

```c

```
