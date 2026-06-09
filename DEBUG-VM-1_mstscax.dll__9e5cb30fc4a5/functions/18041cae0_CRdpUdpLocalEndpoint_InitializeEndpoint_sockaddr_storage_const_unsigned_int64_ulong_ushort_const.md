# CRdpUdpLocalEndpoint::InitializeEndpoint(sockaddr_storage const &,unsigned __int64,ulong,ushort const *)

- ea: `0x18041cae0`
- end: `0x18041d5cb`
- name: `?InitializeEndpoint@CRdpUdpLocalEndpoint@@MEAAJAEBUsockaddr_storage@@_KKPEBG@Z`
- size: `2795`
- prototype: `int(CRdpUdpLocalEndpoint *__hidden this, const struct sockaddr_storage *, unsigned __int64, unsigned int, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x1800011f4`
- `0x1800054f4`
- `0x180006e84`
- `0x1800096d4`
- `0x180412170`
- `0x18041cae0`
- `0x18041de7c`
- `0x180688fc0`
- `0x18068c010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18041cc37`
- `KERNEL32!GetLastError` at `0x18041cc37`
- `KERNEL32!CreateEventW` at `0x18041cc28`
- `KERNEL32!CreateEventW` at `0x18041cc28`
- `WS2_32!WSAIoctl` at `0x18041d366`
- `WS2_32!WSAIoctl` at `0x18041d44c`
- `WS2_32!WSAIoctl` at `0x18041d366`
- `WS2_32!WSAIoctl` at `0x18041d44c`
- `WS2_32!WSAEventSelect` at `0x18041cdab`
- `WS2_32!WSAEventSelect` at `0x18041cdab`
- `WS2_32!__imp_bind` at `0x18041cf41`
- `WS2_32!__imp_bind` at `0x18041cf41`
- `WS2_32!__imp_connect` at `0x18041d1cd`
- `WS2_32!__imp_connect` at `0x18041d1cd`
- `WS2_32!__imp_getsockname` at `0x18041d282`
- `WS2_32!__imp_getsockname` at `0x18041d282`
- `WS2_32!__imp_setsockopt` at `0x18041cea4`
- `WS2_32!__imp_setsockopt` at `0x18041cff3`
- `WS2_32!__imp_setsockopt` at `0x18041cea4`
- `WS2_32!__imp_setsockopt` at `0x18041cff3`
- `WS2_32!__imp_socket` at `0x18041cb66`
- `WS2_32!__imp_socket` at `0x18041cb66`
- `WS2_32!__imp_WSAGetLastError` at `0x18041cb76`
- `WS2_32!__imp_WSAGetLastError` at `0x18041cdc8`
- `WS2_32!__imp_WSAGetLastError` at `0x18041ceb3`
- `WS2_32!__imp_WSAGetLastError` at `0x18041cf50`
- `WS2_32!__imp_WSAGetLastError` at `0x18041d002`
- `WS2_32!__imp_WSAGetLastError` at `0x18041d1dd`
- `WS2_32!__imp_WSAGetLastError` at `0x18041d296`
- `WS2_32!__imp_WSAGetLastError` at `0x18041d37a`
- `WS2_32!__imp_WSAGetLastError` at `0x18041d460`
- `WS2_32!__imp_WSAGetLastError` at `0x18041d530`
- `WS2_32!__imp_WSAGetLastError` at `0x18041cb76`
- `WS2_32!__imp_WSAGetLastError` at `0x18041cdc8`
- `WS2_32!__imp_WSAGetLastError` at `0x18041ceb3`
- `WS2_32!__imp_WSAGetLastError` at `0x18041cf50`
- `WS2_32!__imp_WSAGetLastError` at `0x18041d002`
- `WS2_32!__imp_WSAGetLastError` at `0x18041d1dd`
- `WS2_32!__imp_WSAGetLastError` at `0x18041d296`
- `WS2_32!__imp_WSAGetLastError` at `0x18041d37a`
- `WS2_32!__imp_WSAGetLastError` at `0x18041d460`
- `WS2_32!__imp_WSAGetLastError` at `0x18041d530`

## string_xrefs

- `0x18041cc5b`: `Failed to create socket event`
- `0x18041cb9a`: `Failed to create socket`
- `0x18041ccfb`: `Failed to create shared handle in CRdpUdpLocalEndpoint::InitializeEndpoint`

## pseudocode

```c

```
