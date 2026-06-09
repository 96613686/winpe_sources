# ValidateIPOnlyString(ushort const *,ushort *,IRequestContext *)

- ea: `0x180078038`
- end: `0x1800784ca`
- name: `?ValidateIPOnlyString@@YAHPEBGPEAGPEAVIRequestContext@@@Z`
- size: `1170`
- prototype: `__int64 __fastcall(LPCWCH lpWideCharStr, LPWSTR, struct IRequestContext *)`
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, service_task`

## callers

- `0x180079254`
- `0x1800d6670`
- `0x180122b7c`

## callees

- `0x180005d10`
- `0x180008920`
- `0x18004a900`
- `0x180078038`
- `0x1801123a8`
- `0x1801ba152`
- `0x1801ba1b0`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180078219`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007843c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180078219`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007843c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800781bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800783bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800781bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800783bf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180078121`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007816e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180078121`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007816e`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800781b1`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800781b1`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800783b5`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800783b5`
- `WS2_32!getnameinfo` at `0x18007835e`
- `WS2_32!getnameinfo` at `0x18007835e`
- `WS2_32!getaddrinfo` at `0x1800782d1`
- `WS2_32!getaddrinfo` at `0x1800782d1`
- `WS2_32!freeaddrinfo` at `0x18007842a`
- `WS2_32!freeaddrinfo` at `0x18007842a`
- `WS2_32!__imp_WSAStartup` at `0x180078254`
- `WS2_32!__imp_WSAStartup` at `0x180078254`
- `WS2_32!__imp_WSACleanup` at `0x180078430`
- `WS2_32!__imp_WSACleanup` at `0x180078430`

## string_xrefs

- `0x180078103`: `onecore\admin\wmi\wmx\binaries\service\wsmanmemory.cpp`
- `0x180078150`: `onecore\admin\wmi\wmx\binaries\service\wsmanmemory.cpp`

## pseudocode

```c

```
