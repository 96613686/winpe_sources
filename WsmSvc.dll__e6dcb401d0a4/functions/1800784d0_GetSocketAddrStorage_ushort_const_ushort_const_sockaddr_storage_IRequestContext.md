# GetSocketAddrStorage(ushort const *,ushort const *,sockaddr_storage *,IRequestContext *)

- ea: `0x1800784d0`
- end: `0x1800789b0`
- name: `?GetSocketAddrStorage@@YAHPEBG0PEAUsockaddr_storage@@PEAVIRequestContext@@@Z`
- size: `1248`
- prototype: `__int64 __fastcall(LPCWCH lpWideCharStr, LPCWCH, struct sockaddr_storage *, struct IRequestContext *)`
- caller_count: `6`
- callee_count: `9`
- tags: `authz_impersonation, service_task`

## callers

- `0x180077d2c`
- `0x180101610`
- `0x18018ede8`
- `0x18019dc28`
- `0x18019fbf0`
- `0x1801a0710`

## callees

- `0x180005d10`
- `0x180008920`
- `0x18004a900`
- `0x1800784d0`
- `0x18010d8c6`
- `0x1801123a8`
- `0x1801ba152`
- `0x1801ba1b0`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007877e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180078981`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007877e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180078981`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078753`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800787c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078753`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800787c3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800785b2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800785de`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800785b2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800785de`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18007862d`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180078666`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18007862d`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180078666`
- `WS2_32!getaddrinfo` at `0x1800786e1`
- `WS2_32!getaddrinfo` at `0x1800786e1`
- `WS2_32!freeaddrinfo` at `0x18007870b`
- `WS2_32!freeaddrinfo` at `0x18007870b`
- `WS2_32!__imp_WSAStartup` at `0x18007868e`
- `WS2_32!__imp_WSAStartup` at `0x18007868e`
- `WS2_32!__imp_WSACleanup` at `0x180078711`
- `WS2_32!__imp_WSACleanup` at `0x180078711`

## string_xrefs

- `0x18007885b`: `onecore\admin\wmi\wmx\binaries\service\wsmanmemory.cpp`
- `0x180078886`: `onecore\admin\wmi\wmx\binaries\service\wsmanmemory.cpp`

## pseudocode

```c

```
