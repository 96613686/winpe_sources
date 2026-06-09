# OSIntegration::DEH::CapabilityAuthorizationHandler::CapabilitySidArrayFromStringArray(ushort const * *,ulong,wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,unsigned __int64> &)

- ea: `0x1800a52e0`
- end: `0x1800a54fc`
- name: `?CapabilitySidArrayFromStringArray@CapabilityAuthorizationHandler@DEH@OSIntegration@@CAJPEAPEBGKAEAV?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U12@_K@wil@@@Z`
- size: `540`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800ea030`

## callees

- `0x180067050`
- `0x18007ef50`
- `0x180098bf4`
- `0x1800a021c`
- `0x1800a52e0`
- `0x1800a5970`
- `0x1800f0260`

## import_xrefs

- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x1800a5351`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x1800a5351`
- `ntdll!RtlInitUnicodeString` at `0x1800a533f`
- `ntdll!RtlInitUnicodeString` at `0x1800a533f`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800a5390`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800a5390`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800a5363`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800a5363`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a53f4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a5443`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a5483`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a5495`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a54c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a54d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a53f4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a5443`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a5483`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a5495`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a54c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a54d8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a5370`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a5370`

## pseudocode

```c

```
