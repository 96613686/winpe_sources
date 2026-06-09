# I_EncodeRpcRequest(ulong,ulong,ulong,ulong,_GUID *,_CTAPCBOR_DEVICE_INFO_LIST *,ulong,uchar *,_WEBAUTHN_CTAP_RPC_PROTECTED *,ulong,uchar const *,ushort const *,_CTAPCBOR_RPC_REQUEST *,ulong *,uchar * *)

- ea: `0x18000c5ec`
- end: `0x18000c9c8`
- name: `?I_EncodeRpcRequest@@YAJKKKKPEAU_GUID@@PEAU_CTAPCBOR_DEVICE_INFO_LIST@@KPEAEPEAU_WEBAUTHN_CTAP_RPC_PROTECTED@@KPEBEPEBGPEAU_CTAPCBOR_RPC_REQUEST@@PEAKPEAPEAE@Z`
- size: `988`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, unsigned int, unsigned int, struct _GUID *, struct _CTAPCBOR_DEVICE_INFO_LIST *, unsigned int, unsigned __int8 *, struct _WEBAUTHN_CTAP_RPC_PROTECTED *, unsigned int, const unsigned __int8 *, const unsigned __int16 *, struct _CTAPCBOR_RPC_REQUEST *, unsigned int *, unsigned __int8 **)`
- caller_count: `18`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000c13c`
- `0x18000c2c4`
- `0x18000c450`
- `0x18000c5ec`
- `0x18001c760`
- `0x180026e50`
- `0x180031984`
- `0x180036978`
- `0x18004a868`
- `0x18004b070`
- `0x18004b32c`
- `0x18004b4b0`
- `0x18004b77c`
- `0x18004b928`
- `0x180087944`
- `0x18008ba90`
- `0x180096290`
- `0x1800b4170`

## callees

- `0x18000c5ec`
- `0x18000c9d0`
- `0x18000ca00`
- `0x18000f6a0`
- `0x18001c0d4`
- `0x1800205e4`
- `0x18002a2f0`
- `0x180031708`
- `0x18004baa4`
- `0x1800537a4`
- `0x1800d73d0`
- `0x18013c090`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c7ff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c87a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c99d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c7ff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c87a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c99d`

## string_xrefs

- `0x18000c860`: `onecore\ds\security\fido\webauthn\dll\webauthnctap.cpp`
- `0x18000c88e`: `onecore\ds\security\fido\webauthn\dll\webauthnctap.cpp`
- `0x18000c90d`: `onecore\ds\security\fido\webauthn\dll\webauthnctap.cpp`
- `0x18000c96d`: `onecore\ds\security\fido\webauthn\dll\webauthnctap.cpp`

## pseudocode

```c

```
