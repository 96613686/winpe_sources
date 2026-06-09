# CComMgrIo::SetupListenerSocket(unsigned __int64 &,addrinfo *)

- ea: `0x1800b5b84`
- end: `0x1800b5cf7`
- name: `?SetupListenerSocket@CComMgrIo@@AEAAJAEA_KPEAUaddrinfo@@@Z`
- size: `371`
- prototype: `__int64 __fastcall(CComMgrIo *__hidden this, unsigned __int64 *, struct addrinfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800b5d00`

## callees

- `0x18000f8dc`
- `0x18001f438`
- `0x1800b5b84`

## import_xrefs

- `WS2_32!__imp_bind` at `0x1800b5c50`
- `WS2_32!__imp_bind` at `0x1800b5c50`
- `WS2_32!__imp_closesocket` at `0x1800b5baf`
- `WS2_32!__imp_closesocket` at `0x1800b5baf`
- `WS2_32!__imp_listen` at `0x1800b5c70`
- `WS2_32!__imp_listen` at `0x1800b5c70`
- `WS2_32!__imp_setsockopt` at `0x1800b5c07`
- `WS2_32!__imp_setsockopt` at `0x1800b5c30`
- `WS2_32!__imp_setsockopt` at `0x1800b5c07`
- `WS2_32!__imp_setsockopt` at `0x1800b5c30`
- `WS2_32!__imp_socket` at `0x1800b5bbf`
- `WS2_32!__imp_socket` at `0x1800b5bbf`
- `WS2_32!__imp_WSAGetLastError` at `0x1800b5bce`
- `WS2_32!__imp_WSAGetLastError` at `0x1800b5c83`
- `WS2_32!__imp_WSAGetLastError` at `0x1800b5bce`
- `WS2_32!__imp_WSAGetLastError` at `0x1800b5c83`

## string_xrefs

- `0x1800b5c9c`: `com\complus\dtc\dtc\tipgw\commgr\src\commgrio.cpp`

## pseudocode

```c

```
