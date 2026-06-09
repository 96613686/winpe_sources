# IpAddress::GetInterfaceIndex(ushort,uint,ulong,MacAddress const &)

- ea: `0x180086c3c`
- end: `0x180087036`
- name: `?GetInterfaceIndex@IpAddress@@SAKGIKAEBVMacAddress@@@Z`
- size: `1018`
- prototype: `static unsigned int(unsigned __int16, unsigned int, unsigned int, const struct MacAddress *)`
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180117640`
- `0x1801c8168`

## callees

- `0x180001b68`
- `0x18005f0c0`
- `0x18005ffc4`
- `0x180061240`
- `0x1800653f0`
- `0x18007e864`
- `0x180086c3c`
- `0x18008802c`
- `0x18008b50c`

## import_xrefs

- `NSI!NsiFreeTable` at `0x180086f6c`
- `NSI!NsiFreeTable` at `0x180086f6c`
- `NSI!NsiAllocateAndGetTable` at `0x180086d2b`
- `NSI!NsiAllocateAndGetTable` at `0x180086d2b`
- `IPHLPAPI!GetIfEntry2` at `0x180086d90`
- `IPHLPAPI!GetIfEntry2` at `0x180086d90`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180086f7f`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180086f7f`

## string_xrefs

- `0x180086feb`: `onecore\vm\dv\net\hns\service\common\helperlib\src\ipaddress.cpp`
- `0x180087024`: `onecore\vm\dv\net\hns\service\common\helperlib\src\ipaddress.cpp`
- `0x180086fdf`: `Unable to get IP interface index by compartment Id %u and isolation Id %u`

## pseudocode

```c

```
