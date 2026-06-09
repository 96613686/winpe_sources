# Sha256HashString(HSTRING__ * const,std::unique_ptr<void *,Windows::Internal::Security::Authentication::TokenBroker::LocalAllocDeleter> &,ulong *)

- ea: `0x18006fb0c`
- end: `0x18006fd49`
- name: `?Sha256HashString@@YAJQEAUHSTRING__@@AEAV?$unique_ptr@PEAXULocalAllocDeleter@TokenBroker@Authentication@Security@Internal@Windows@@@std@@PEAK@Z`
- size: `573`
- prototype: `__int64 __fastcall(HSTRING string)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180071b10`

## callees

- `0x18000bd40`
- `0x180034e8c`
- `0x180047294`
- `0x180048694`
- `0x18004e850`
- `0x1800506f8`
- `0x18006fb0c`
- `0x18007f4cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006fc75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006fc75`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006fbdd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006fbdd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18006fba8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18006fba8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006fcbe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006fcbe`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006fc67`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006fc67`
- `bcrypt!BCryptHashData` at `0x18006fbf1`
- `bcrypt!BCryptHashData` at `0x18006fbf1`
- `bcrypt!BCryptCreateHash` at `0x18006fb86`
- `bcrypt!BCryptCreateHash` at `0x18006fb86`
- `bcrypt!BCryptFinishHash` at `0x18006fc97`
- `bcrypt!BCryptFinishHash` at `0x18006fc97`
- `bcrypt!BCryptGetProperty` at `0x18006fc4e`
- `bcrypt!BCryptGetProperty` at `0x18006fc4e`

## string_xrefs

- `0x18006fc07`: `onecore\ds\security\tokenbroker\datastore\lib\utils.cpp`
- `0x18006fca5`: `onecore\ds\security\tokenbroker\datastore\lib\utils.cpp`
- `0x18006fcef`: `onecore\ds\security\tokenbroker\datastore\lib\utils.cpp`

## pseudocode

```c

```
