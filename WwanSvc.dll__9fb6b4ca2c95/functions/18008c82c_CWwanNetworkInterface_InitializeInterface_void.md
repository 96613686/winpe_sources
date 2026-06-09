# CWwanNetworkInterface::InitializeInterface(void)

- ea: `0x18008c82c`
- end: `0x18008cf99`
- name: `?InitializeInterface@CWwanNetworkInterface@@QEAAKXZ`
- size: `1901`
- prototype: `unsigned int __fastcall(struct _GUID *this)`
- caller_count: `1`
- callee_count: `21`
- tags: `service_task, broker_com_uri`

## callers

- `0x180072f68`

## callees

- `0x1800085d0`
- `0x1800094f4`
- `0x18000f0f4`
- `0x180012300`
- `0x180013288`
- `0x180013ad0`
- `0x180014f1c`
- `0x1800159b0`
- `0x180015d6c`
- `0x18001bfe4`
- `0x18001c2ec`
- `0x18001ce84`
- `0x18001d640`
- `0x1800769a4`
- `0x18007a0fc`
- `0x18008a5bc`
- `0x18008a6fc`
- `0x18008c82c`
- `0x18008d844`
- `0x18008da2c`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18008c8fb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18008c8fb`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x18008c953`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x18008c953`

## string_xrefs

- `0x18008c890`: `onecoreuap\net\wwan\service\core\wwannetworkinterface.cpp`
- `0x18008cdee`: ` Underlying device is UDE virtual device, set fIsD3ColdSupported = TRUE as a temporary workaround since UDE doesn't allow to query physical device D3 capability right now`
- `0x18008ceb3`: `Attempting to set the NIC aoac compliance to %d`
- `0x18008cf55`: ` WwanInterfaceInit Completed`
- `0x18008cf01`: `Setting NIC aoac compliance failed [%d]`

## pseudocode

```c

```
