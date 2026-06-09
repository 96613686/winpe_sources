# ConvertCacheIdnToAscii(ushort const *,ulong,int,ushort * *)

- ea: `0x180096ef0`
- end: `0x180097265`
- name: `?ConvertCacheIdnToAscii@@YAJPEBGKHPEAPEAG@Z`
- size: `885`
- prototype: `__int64 __fastcall(wchar_t *String1, size_t MaxCount, int, unsigned __int16 **)`
- caller_count: `6`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180018f48`
- `0x18006a6b0`
- `0x18008ce2c`
- `0x1800967e8`
- `0x180097604`
- `0x18013c82c`

## callees

- `0x1800701d0`
- `0x180096ef0`
- `0x180148b48`
- `0x18014a7a0`
- `0x1801c9c19`
- `0x1801e0700`
- `0x1801e1790`
- `0x1801ee010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180096f44`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180096f44`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180097227`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180097227`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18009705a`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18009705a`
- `api-ms-win-core-localization-l1-2-0!IdnToAscii` at `0x180096fa5`
- `api-ms-win-core-localization-l1-2-0!IdnToAscii` at `0x180096ff8`
- `api-ms-win-core-localization-l1-2-0!IdnToAscii` at `0x180097091`
- `api-ms-win-core-localization-l1-2-0!IdnToAscii` at `0x180096fa5`
- `api-ms-win-core-localization-l1-2-0!IdnToAscii` at `0x180096ff8`
- `api-ms-win-core-localization-l1-2-0!IdnToAscii` at `0x180097091`
- `ntdll!RtlIpv6StringToAddressExW` at `0x18009713a`
- `ntdll!RtlIpv6StringToAddressExW` at `0x18009713a`
- `ntdll!RtlIpv4StringToAddressExW` at `0x18009711b`
- `ntdll!RtlIpv4StringToAddressExW` at `0x18009711b`

## pseudocode

```c

```
