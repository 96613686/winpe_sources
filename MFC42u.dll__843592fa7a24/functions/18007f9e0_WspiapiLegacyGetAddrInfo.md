# WspiapiLegacyGetAddrInfo

- ea: `0x18007f9e0`
- end: `0x18007fd2b`
- name: `WspiapiLegacyGetAddrInfo`
- size: `843`
- prototype: `int __stdcall(const char *pszNodeName, const char *pszServiceName, const struct addrinfo *ptHints, struct addrinfo **pptResult)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x18007f980`
- `0x18007f9e0`
- `0x180080178`
- `0x1800802e4`
- `0x18008044c`

## import_xrefs

- `msvcrt!strtoul` at `0x18007fac5`
- `msvcrt!strtoul` at `0x18007fac5`
- `WS2_32!__imp_htonl` at `0x18007fc41`
- `WS2_32!__imp_htonl` at `0x18007fc41`
- `WS2_32!__imp_htons` at `0x18007fae1`
- `WS2_32!__imp_htons` at `0x18007fae1`
- `WS2_32!__imp_inet_addr` at `0x18007fbe0`
- `WS2_32!__imp_inet_addr` at `0x18007fbe0`
- `WS2_32!__imp_inet_ntoa` at `0x18007fc7f`
- `WS2_32!__imp_inet_ntoa` at `0x18007fc7f`
- `WS2_32!__imp_getservbyname` at `0x18007fb1f`
- `WS2_32!__imp_getservbyname` at `0x18007fb55`
- `WS2_32!__imp_getservbyname` at `0x18007fb1f`
- `WS2_32!__imp_getservbyname` at `0x18007fb55`

## pseudocode

```c

```
