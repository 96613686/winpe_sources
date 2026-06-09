# Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfo::CreateNewFile(std::unique_ptr<void *,Windows::Internal::Security::Authentication::TokenBroker::FileHandleDeleter> &)

- ea: `0x1801114bc`
- end: `0x18011167b`
- name: `?CreateNewFile@StoredObjectInfo@TokenBroker@Authentication@Security@Internal@Windows@@AEBAJAEAV?$unique_ptr@PEAXUFileHandleDeleter@TokenBroker@Authentication@Security@Internal@Windows@@@std@@@Z`
- size: `447`
- prototype: `__int64 __fastcall(HSTRING *this, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180076ad0`

## callees

- `0x180040980`
- `0x18004e850`
- `0x18004fdbc`
- `0x1801113bc`
- `0x1801114bc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180111529`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180111529`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801114e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180111519`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011158d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801115be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801114e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180111519`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011158d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801115be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180111607`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180111607`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801115e7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801115e7`

## pseudocode

```c

```
