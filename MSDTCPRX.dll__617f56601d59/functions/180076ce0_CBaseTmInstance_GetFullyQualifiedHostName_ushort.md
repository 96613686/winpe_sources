# CBaseTmInstance::GetFullyQualifiedHostName(ushort * *)

- ea: `0x180076ce0`
- end: `0x180076dd4`
- name: `?GetFullyQualifiedHostName@CBaseTmInstance@@UEAAJPEAPEAG@Z`
- size: `244`
- prototype: `__int64 __fastcall(CBaseTmInstance *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006324`
- `0x18000d5f4`
- `0x180076ce0`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180076dc4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180076dc4`
- `WS2_32!GetAddrInfoW` at `0x180076d65`
- `WS2_32!GetAddrInfoW` at `0x180076d65`
- `WS2_32!FreeAddrInfoW` at `0x180076dad`
- `WS2_32!FreeAddrInfoW` at `0x180076dad`
- `WS2_32!__imp_WSAGetLastError` at `0x180076d6f`
- `WS2_32!__imp_WSAGetLastError` at `0x180076d6f`

## string_xrefs

- `0x180076d1a`: `CBaseTmInstance::GetFullyQualifiedHostName (com\complus\dtc\shared\util\basetminstance.cpp@190): GetFullyQualitifedHostName, o_wszFullyQualifiedHostName != NULL`

## pseudocode

```c

```
