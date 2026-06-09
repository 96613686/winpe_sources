# OSIntegration::DEH::CapabilityAuthorizationHandler::FilterAllCapabilitiesFromManifest(void)

- ea: `0x1800ea030`
- end: `0x1800ea6c1`
- name: `?FilterAllCapabilitiesFromManifest@CapabilityAuthorizationHandler@DEH@OSIntegration@@AEAAJXZ`
- size: `1681`
- prototype: `__int64 __fastcall(OSIntegration::DEH::CapabilityAuthorizationHandler *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180089df0`

## callees

- `0x180098bf4`
- `0x1800a52e0`
- `0x1800a572c`
- `0x1800ad5f8`
- `0x1800ea030`
- `0x1800ea6c8`
- `0x180130ca0`
- `0x180130d50`
- `0x180130e00`
- `0x180130f38`
- `0x1801316c0`
- `0x180136188`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800ea1ab`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800ea1ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ea0bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ea0d1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ea131`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ea143`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ea169`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ea20b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ea21d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ea23b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ea24d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ea273`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ea285`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ea2a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ea2b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ea378`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ea3f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ea425`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ea437`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ea4a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ea522`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ea54e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ea560`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ea5d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ea64d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ea65f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ea68c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ea69e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ea0bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ea0d1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ea131`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ea143`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ea169`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ea20b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ea21d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ea23b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ea24d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ea273`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ea285`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ea2a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ea2b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ea378`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ea3f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ea425`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ea437`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ea4a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ea522`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ea54e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ea560`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ea5d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ea64d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ea65f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ea68c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ea69e`

## pseudocode

```c

```
