# DeviceCastle::Library::Internal::DatabasePersistence::EnsureOwnerFile(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18004e650`
- end: `0x18004e8bf`
- name: `?EnsureOwnerFile@DatabasePersistence@Internal@Library@DeviceCastle@@AEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `623`
- prototype: `__int64 __fastcall(DeviceCastle::Library::Internal::DatabasePersistence *this, void *Src)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config`

## callers

- `0x18004e8c8`

## callees

- `0x1800049a0`
- `0x180013274`
- `0x18003c35c`
- `0x180048060`
- `0x180048aac`
- `0x18004e650`
- `0x18004ed7c`
- `0x180050bbc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e7ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e806`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e7ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e806`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004e7bf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004e7bf`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18004e7f9`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18004e7f9`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18004e6c4`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18004e6c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004e7b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004e838`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004e887`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004e7b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004e838`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004e887`

## string_xrefs

- `0x18004e765`: `OwnerSid`
- `0x18004e6a6`: `\OwnerInfo.json`

## pseudocode

```c

```
