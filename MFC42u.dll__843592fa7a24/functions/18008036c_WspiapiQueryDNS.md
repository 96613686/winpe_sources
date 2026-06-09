# WspiapiQueryDNS

- ea: `0x18008036c`
- end: `0x180080443`
- name: `WspiapiQueryDNS`
- size: `215`
- prototype: `int __stdcall(const char *pszNodeName, int iSocketType, int iProtocol, WORD wPort, char pszAlias[1025], struct addrinfo **pptResult)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180080178`

## callees

- `0x1800802e4`
- `0x18008036c`

## import_xrefs

- `msvcrt!strncpy_s` at `0x180080403`
- `msvcrt!strncpy_s` at `0x180080403`
- `WS2_32!__imp_gethostbyname` at `0x1800803a0`
- `WS2_32!__imp_gethostbyname` at `0x1800803a0`
- `WS2_32!__imp_WSAGetLastError` at `0x18008040d`
- `WS2_32!__imp_WSAGetLastError` at `0x18008040d`

## pseudocode

```c

```
