# IPHelper::UpdateInterface(ushort,_NET_LUID_LH const &,uint,bool,ulong)

- ea: `0x18008c4b0`
- end: `0x18008c666`
- name: `?UpdateInterface@IPHelper@@SAXGAEBT_NET_LUID_LH@@I_NK@Z`
- size: `438`
- prototype: `void __fastcall(unsigned __int16, const union _NET_LUID_LH *, unsigned int, bool, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180117640`
- `0x1801d4024`

## callees

- `0x18005f0c0`
- `0x18005ffc4`
- `0x1800759d8`
- `0x180075aac`
- `0x18007cbc8`
- `0x18008b50c`
- `0x18008c4b0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18008c589`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18008c589`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18008c60f`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18008c60f`
- `IPHLPAPI!InitializeIpInterfaceEntry` at `0x18008c55b`
- `IPHLPAPI!InitializeIpInterfaceEntry` at `0x18008c55b`
- `IPHLPAPI!GetIpInterfaceEntry` at `0x18008c575`
- `IPHLPAPI!GetIpInterfaceEntry` at `0x18008c575`
- `IPHLPAPI!SetIpInterfaceEntry` at `0x18008c5cc`
- `IPHLPAPI!SetIpInterfaceEntry` at `0x18008c5cc`

## string_xrefs

- `0x18008c63f`: `onecore\vm\dv\net\hns\service\common\helperlib\src\iphelper.cpp`
- `0x18008c654`: `onecore\vm\dv\net\hns\service\common\helperlib\src\iphelper.cpp`
- `0x18008c4f1`: `IPHelper::UpdateInterface`
- `0x18008c5f9`: `IPHelper::UpdateInterface`

## pseudocode

```c

```
