# FwParseAddressIPV6_2(ushort const *,_tag_FW_ADDRESSES *,ulong)

- ea: `0x1800057b0`
- end: `0x180005b1f`
- name: `?FwParseAddressIPV6_2@@YAJPEBGPEAU_tag_FW_ADDRESSES@@K@Z`
- size: `879`
- prototype: `__int64 __fastcall(LPCWSTR lpString1, struct _tag_FW_ADDRESSES *, unsigned int)`
- caller_count: `8`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180005760`
- `0x180005790`
- `0x180005de4`
- `0x1800258d0`
- `0x180025930`
- `0x180025ce0`
- `0x1800267c0`
- `0x180026b10`

## callees

- `0x1800042c4`
- `0x1800057b0`
- `0x180005c20`
- `0x18001f650`
- `0x180039bac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswdigit` at `0x1800058e4`
- `api-ms-win-crt-private-l1-1-0!_o_iswdigit` at `0x1800058e4`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x1800058ff`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x1800058ff`
- `ntdll!RtlIpv6StringToAddressW` at `0x180005882`
- `ntdll!RtlIpv6StringToAddressW` at `0x180005aa2`
- `ntdll!RtlIpv6StringToAddressW` at `0x180005882`
- `ntdll!RtlIpv6StringToAddressW` at `0x180005aa2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000581d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000581d`
- `fwbase!FwArrayAppend` at `0x18000593d`
- `fwbase!FwArrayAppend` at `0x1800059ab`
- `fwbase!FwArrayAppend` at `0x18000593d`
- `fwbase!FwArrayAppend` at `0x1800059ab`
- `fwbase!FwNtStatusToHResult` at `0x18000588a`
- `fwbase!FwNtStatusToHResult` at `0x180005aaa`
- `fwbase!FwNtStatusToHResult` at `0x18000588a`
- `fwbase!FwNtStatusToHResult` at `0x180005aaa`

## pseudocode

```c

```
