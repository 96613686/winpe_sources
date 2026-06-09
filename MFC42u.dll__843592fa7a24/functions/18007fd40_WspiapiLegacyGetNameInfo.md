# WspiapiLegacyGetNameInfo

- ea: `0x18007fd40`
- end: `0x18007ff97`
- name: `WspiapiLegacyGetNameInfo`
- size: `599`
- prototype: `int __stdcall(const struct sockaddr *ptSocketAddress, socklen_t tSocketLength, char *pszNodeName, size_t tNodeLength, char *pszServiceName, size_t tServiceLength, int iFlags)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x18007fd40`
- `0x1800d1fe0`

## import_xrefs

- `msvcrt!strchr` at `0x18007ff05`
- `msvcrt!strchr` at `0x18007ff05`
- `msvcrt!sprintf_s` at `0x18007fe7f`
- `msvcrt!sprintf_s` at `0x18007fe7f`
- `msvcrt!strcpy_s` at `0x18007fea6`
- `msvcrt!strcpy_s` at `0x18007ff6b`
- `msvcrt!strcpy_s` at `0x18007fea6`
- `msvcrt!strcpy_s` at `0x18007ff6b`
- `WS2_32!__imp_inet_ntoa` at `0x18007ff4b`
- `WS2_32!__imp_inet_ntoa` at `0x18007ff4b`
- `WS2_32!__imp_ntohs` at `0x18007fe64`
- `WS2_32!__imp_ntohs` at `0x18007fe64`
- `WS2_32!__imp_gethostbyaddr` at `0x18007fee1`
- `WS2_32!__imp_gethostbyaddr` at `0x18007fee1`
- `WS2_32!__imp_getservbyport` at `0x18007fe4a`
- `WS2_32!__imp_getservbyport` at `0x18007fe4a`
- `WS2_32!__imp_WSAGetLastError` at `0x18007ff1f`
- `WS2_32!__imp_WSAGetLastError` at `0x18007ff1f`

## pseudocode

```c

```
