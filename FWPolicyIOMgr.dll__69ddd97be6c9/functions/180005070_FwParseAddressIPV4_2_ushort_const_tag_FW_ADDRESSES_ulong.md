# FwParseAddressIPV4_2(ushort const *,_tag_FW_ADDRESSES *,ulong)

- ea: `0x180005070`
- end: `0x180005357`
- name: `?FwParseAddressIPV4_2@@YAJPEBGPEAU_tag_FW_ADDRESSES@@K@Z`
- size: `743`
- prototype: `__int64 __fastcall(PCWSTR S, struct _tag_FW_ADDRESSES *, unsigned int)`
- caller_count: `7`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180005050`
- `0x180005b30`
- `0x180005de4`
- `0x1800258b0`
- `0x180025910`
- `0x180026790`
- `0x180026af0`

## callees

- `0x1800042c4`
- `0x180005070`
- `0x18001f650`

## import_xrefs

- `ntdll!RtlIpv4StringToAddressW` at `0x18000522b`
- `ntdll!RtlIpv4StringToAddressW` at `0x180005270`
- `ntdll!RtlIpv4StringToAddressW` at `0x18000522b`
- `ntdll!RtlIpv4StringToAddressW` at `0x180005270`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800050d1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800051c8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800051ff`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800050d1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800051c8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800051ff`
- `WS2_32!__imp_ntohl` at `0x180005247`
- `WS2_32!__imp_ntohl` at `0x18000528c`
- `WS2_32!__imp_ntohl` at `0x180005247`
- `WS2_32!__imp_ntohl` at `0x18000528c`
- `fwbase!FwArrayAppend` at `0x180005199`
- `fwbase!FwArrayAppend` at `0x180005199`
- `fwbase!FwIpV4SubNetDecode` at `0x180005176`
- `fwbase!FwIpV4SubNetDecode` at `0x180005176`
- `fwbase!FwNtStatusToHResult` at `0x180005233`
- `fwbase!FwNtStatusToHResult` at `0x180005278`
- `fwbase!FwNtStatusToHResult` at `0x180005233`
- `fwbase!FwNtStatusToHResult` at `0x180005278`

## pseudocode

```c

```
