# FindMatchingEndpoint(IMMDeviceEnumerator *,ushort *,IMMDevice * *)

- ea: `0x18005a948`
- end: `0x18005ab57`
- name: `?FindMatchingEndpoint@@YAJPEAUIMMDeviceEnumerator@@PEAGPEAPEAUIMMDevice@@@Z`
- size: `527`
- prototype: `__int64 __fastcall(struct IMMDeviceEnumerator *, unsigned __int16 *, struct IMMDevice **)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180039ef4`
- `0x18003a6c8`

## callees

- `0x180006b0c`
- `0x180010da8`
- `0x180023fbc`
- `0x18005a948`
- `0x180068010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005aaaf`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005aaaf`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005aad6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005ab22`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005aad6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005ab22`

## string_xrefs

- `0x18005a9ce`: `avcore\audiocore\server\audioendpointbuilder\dll\audmig.cpp`
- `0x18005ab07`: `avcore\audiocore\server\audioendpointbuilder\dll\audmig.cpp`

## pseudocode

```c

```
