# Microsoft::Diagnostics::Utils::Os::QueryObjectSecurityDescriptorAsString(void *,_SE_OBJECT_TYPE,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x1800193cc`
- end: `0x180019573`
- name: `?QueryObjectSecurityDescriptorAsString@Os@Utils@Diagnostics@Microsoft@@CAJPEAXW4_SE_OBJECT_TYPE@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `423`
- prototype: `__int64 __fastcall(HANDLE handle, SE_OBJECT_TYPE ObjectType)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180019600`
- `0x1801e206c`

## callees

- `0x1800193cc`
- `0x18002b318`
- `0x18002be90`
- `0x18002cb04`
- `0x18002df00`
- `0x180064e6c`
- `0x18008abf4`
- `0x1800f9c3c`
- `0x1801b7bd0`
- `0x18020aac0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019475`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001953b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001954c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019475`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001953b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001954c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x1800194b0`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x1800194b0`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x180019443`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x180019443`

## pseudocode

```c

```
