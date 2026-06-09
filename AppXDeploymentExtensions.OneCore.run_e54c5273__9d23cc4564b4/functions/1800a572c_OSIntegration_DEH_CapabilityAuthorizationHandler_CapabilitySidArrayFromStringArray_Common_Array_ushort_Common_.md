# OSIntegration::DEH::CapabilityAuthorizationHandler::CapabilitySidArrayFromStringArray(Common::Array<ushort,Common::ContainerOperations<ushort,ushort>,Common::NoKey,Common::ContainerOperations<Common::NoKey,ushort>,Common::ArrayOperations<ushort,Common::NoKey>> const &,wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,unsigned __int64> &)

- ea: `0x1800a572c`
- end: `0x1800a5969`
- name: `?CapabilitySidArrayFromStringArray@CapabilityAuthorizationHandler@DEH@OSIntegration@@CAJAEBV?$Array@GV?$ContainerOperations@GG@Common@@VNoKey@2@V?$ContainerOperations@VNoKey@Common@@G@2@V?$ArrayOperations@GVNoKey@Common@@@2@@Common@@AEAV?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U12@_K@wil@@@Z`
- size: `573`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800809e0`
- `0x1800ea030`

## callees

- `0x180067050`
- `0x18007ef50`
- `0x180098bf4`
- `0x1800a021c`
- `0x1800a572c`
- `0x1800a5970`
- `0x1800f0260`
- `0x1800f10e4`

## import_xrefs

- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x1800a57b7`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x1800a57b7`
- `ntdll!RtlInitUnicodeString` at `0x1800a57a5`
- `ntdll!RtlInitUnicodeString` at `0x1800a57a5`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800a57f6`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800a57f6`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800a57c9`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800a57c9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a585a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a58a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a58e9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a58fb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a5928`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a593a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a585a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a58a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a58e9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a58fb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a5928`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a593a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a57d6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a57d6`

## pseudocode

```c

```
