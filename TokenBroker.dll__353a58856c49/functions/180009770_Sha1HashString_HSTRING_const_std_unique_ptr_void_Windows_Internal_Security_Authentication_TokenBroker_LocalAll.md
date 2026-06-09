# Sha1HashString(HSTRING__ * const,std::unique_ptr<void *,Windows::Internal::Security::Authentication::TokenBroker::LocalAllocDeleter> &,ulong *)

- ea: `0x180009770`
- end: `0x180009a9d`
- name: `?Sha1HashString@@YAJQEAUHSTRING__@@AEAV?$unique_ptr@PEAXULocalAllocDeleter@TokenBroker@Authentication@Security@Internal@Windows@@@std@@PEAK@Z`
- size: `813`
- prototype: `__int64 __fastcall(HSTRING string, __int64, _DWORD *)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180008fb0`
- `0x180111d50`

## callees

- `0x180009770`
- `0x18000bd40`
- `0x180034e20`
- `0x1800506f8`
- `0x18007f4cc`
- `0x18008e690`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800098f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800098f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180009859`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180009859`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18000982a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18000982a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180009a8d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180009a8d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009974`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009974`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800098e8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800098e8`
- `bcrypt!BCryptHashData` at `0x18000986c`
- `bcrypt!BCryptHashData` at `0x18000986c`
- `bcrypt!BCryptCreateHash` at `0x1800097ea`
- `bcrypt!BCryptCreateHash` at `0x1800097ea`
- `bcrypt!BCryptFinishHash` at `0x18000994d`
- `bcrypt!BCryptFinishHash` at `0x18000994d`
- `bcrypt!BCryptDestroyHash` at `0x180009914`
- `bcrypt!BCryptDestroyHash` at `0x180009983`
- `bcrypt!BCryptDestroyHash` at `0x1800099a6`
- `bcrypt!BCryptDestroyHash` at `0x1800099d7`
- `bcrypt!BCryptDestroyHash` at `0x180009914`
- `bcrypt!BCryptDestroyHash` at `0x180009983`
- `bcrypt!BCryptDestroyHash` at `0x1800099a6`
- `bcrypt!BCryptDestroyHash` at `0x1800099d7`
- `bcrypt!BCryptGetProperty` at `0x1800098ba`
- `bcrypt!BCryptGetProperty` at `0x1800098ba`

## string_xrefs

- `0x18000980c`: `onecore\ds\security\tokenbroker\datastore\lib\utils.cpp`
- `0x18000987a`: `onecore\ds\security\tokenbroker\datastore\lib\utils.cpp`
- `0x1800098c8`: `onecore\ds\security\tokenbroker\datastore\lib\utils.cpp`
- `0x18000995b`: `onecore\ds\security\tokenbroker\datastore\lib\utils.cpp`
- `0x1800099bc`: `onecore\ds\security\tokenbroker\datastore\lib\utils.cpp`

## pseudocode

```c

```
