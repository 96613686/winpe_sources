# FwpsConstructIpHeaderForTransportPacket0

- ea: `0x18000b810`
- end: `0x18000ba8c`
- name: `FwpsConstructIpHeaderForTransportPacket0`
- size: `636`
- prototype: `NTSTATUS __stdcall(NET_BUFFER_LIST *netBufferList, ULONG headerIncludeHeaderLength, ADDRESS_FAMILY addressFamily, const UCHAR *sourceAddress, const UCHAR *remoteAddress, IPPROTO nextProtocol, UINT64 endpointHandle, const WSACMSGHDR *controlData, ULONG controlDataLength, UINT32 flags, PVOID reserved, IF_INDEX interfaceIndex, IF_INDEX subInterfaceIndex)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180004904`
- `0x180004a60`
- `0x18000b810`
- `0x180020400`

## import_xrefs

- `ntoskrnl!MmBadPointer` at `0x18000b8a0`

## pseudocode

```c

```
