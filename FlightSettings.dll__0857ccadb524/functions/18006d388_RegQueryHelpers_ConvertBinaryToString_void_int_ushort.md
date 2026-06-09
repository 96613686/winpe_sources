# RegQueryHelpers::ConvertBinaryToString(void *,int,ushort * *)

- ea: `0x18006d388`
- end: `0x18006d4ad`
- name: `?ConvertBinaryToString@RegQueryHelpers@@CAJPEAXHPEAPEAG@Z`
- size: `293`
- prototype: `__int64 __fastcall(BYTE *pbBinary, DWORD cbBinary, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18006d7d0`

## callees

- `0x18000cc8c`
- `0x1800254ac`
- `0x180046664`
- `0x18006d388`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d3be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d456`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d3be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d456`
- `CRYPT32!CryptBinaryToStringW` at `0x18006d3b4`
- `CRYPT32!CryptBinaryToStringW` at `0x18006d44c`
- `CRYPT32!CryptBinaryToStringW` at `0x18006d3b4`
- `CRYPT32!CryptBinaryToStringW` at `0x18006d44c`

## string_xrefs

- `0x18006d3e3`: `onecore\base\flighting\common\regvalet\regqueryhelpers.cpp`
- `0x18006d477`: `onecore\base\flighting\common\regvalet\regqueryhelpers.cpp`

## pseudocode

```c

```
