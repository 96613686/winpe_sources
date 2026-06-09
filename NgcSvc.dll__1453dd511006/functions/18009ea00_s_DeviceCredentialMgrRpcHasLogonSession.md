# s_DeviceCredentialMgrRpcHasLogonSession

- ea: `0x18009ea00`
- end: `0x18009eb6b`
- name: `s_DeviceCredentialMgrRpcHasLogonSession`
- size: `363`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18000782c`
- `0x18009b4f4`
- `0x18009ea00`
- `0x1800c40f0`

## import_xrefs

- `ntdll!RtlIsMultiSessionSku` at `0x18009ea51`
- `ntdll!RtlIsMultiSessionSku` at `0x18009ea51`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x18009ea72`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x18009ea72`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x18009ea9e`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x18009eb4f`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x18009ea9e`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x18009eb4f`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x18009eb41`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x18009eb41`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x18009eaea`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x18009eaea`

## string_xrefs

- `0x18009ea26`: `onecore\ds\security\devicecredential\service\lib\devicecredentialrpcimpl.cpp`
- `0x18009ea82`: `onecore\ds\security\devicecredential\service\lib\devicecredentialrpcimpl.cpp`

## pseudocode

```c

```
