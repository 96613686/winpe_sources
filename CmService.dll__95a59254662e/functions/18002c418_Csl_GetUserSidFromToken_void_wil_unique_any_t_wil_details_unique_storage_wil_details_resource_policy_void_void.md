# Csl::GetUserSidFromToken(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)

- ea: `0x18002c418`
- end: `0x18002c5ae`
- name: `?GetUserSidFromToken@Csl@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `406`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180018120`
- `0x180019900`
- `0x18001fd1c`
- `0x18002c030`
- `0x18002c110`

## callees

- `0x180004bd0`
- `0x18000da68`
- `0x18000da88`
- `0x18002c418`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002c45d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002c45d`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18002c4d9`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18002c4d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c549`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c549`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c568`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c568`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002c49a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002c49a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c507`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c55a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c57c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c507`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c55a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c57c`

## pseudocode

```c

```
