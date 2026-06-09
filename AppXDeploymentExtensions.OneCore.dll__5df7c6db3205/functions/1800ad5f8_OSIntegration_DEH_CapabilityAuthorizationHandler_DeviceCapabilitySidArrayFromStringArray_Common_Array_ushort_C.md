# OSIntegration::DEH::CapabilityAuthorizationHandler::DeviceCapabilitySidArrayFromStringArray(Common::Array<ushort,Common::ContainerOperations<ushort,ushort>,Common::NoKey,Common::ContainerOperations<Common::NoKey,ushort>,Common::ArrayOperations<ushort,Common::NoKey>> const &,wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,unsigned __int64> &)

- ea: `0x1800ad5f8`
- end: `0x1800ad811`
- name: `?DeviceCapabilitySidArrayFromStringArray@CapabilityAuthorizationHandler@DEH@OSIntegration@@CAJAEBV?$Array@GV?$ContainerOperations@GG@Common@@VNoKey@2@V?$ContainerOperations@VNoKey@Common@@G@2@V?$ArrayOperations@GVNoKey@Common@@@2@@Common@@AEAV?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U12@_K@wil@@@Z`
- size: `537`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800809e0`
- `0x1800ea030`

## callees

- `0x180067050`
- `0x18007ef50`
- `0x1800853cc`
- `0x180098bf4`
- `0x1800a021c`
- `0x1800ad5f8`
- `0x1800f0260`
- `0x1800f10e4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800ad6ea`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800ad6ea`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800ad688`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800ad688`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ad74a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ad790`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ad7a2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ad7cf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ad7e1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ad74a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ad790`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ad7a2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ad7cf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ad7e1`

## pseudocode

```c

```
