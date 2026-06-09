# Csl::DuplicateSecurityDescriptor(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)

- ea: `0x18002ec00`
- end: `0x18002ed37`
- name: `?DuplicateSecurityDescriptor@Csl@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `311`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR AbsoluteSecurityDescriptor)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002e95c`
- `0x180082e18`
- `0x180093474`

## callees

- `0x1800069db`
- `0x18000da88`
- `0x18000dab0`
- `0x18002ec00`

## import_xrefs

- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x18002ecd3`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x18002ecd3`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18002ec18`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18002ec18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ec98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ec98`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ecb7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ecb7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002ec2f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002ec2f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002eca9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ed01`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ed15`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002eca9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ed01`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ed15`

## string_xrefs

- `0x18002ec4b`: `onecore\base\gendrv\silos\csl\lib\cslsecurity.cpp`
- `0x18002ece8`: `onecore\base\gendrv\silos\csl\lib\cslsecurity.cpp`

## pseudocode

```c

```
