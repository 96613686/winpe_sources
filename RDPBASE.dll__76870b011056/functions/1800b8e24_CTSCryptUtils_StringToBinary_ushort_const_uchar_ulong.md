# CTSCryptUtils::StringToBinary(ushort const *,uchar * *,ulong *)

- ea: `0x1800b8e24`
- end: `0x1800b9103`
- name: `?StringToBinary@CTSCryptUtils@@SAJPEBGPEAPEAEPEAK@Z`
- size: `735`
- prototype: `__int64 __fastcall(LPCWSTR pszString, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800ecc38`

## callees

- `0x180004970`
- `0x180071a60`
- `0x1800787d4`
- `0x180078820`
- `0x1800923f8`
- `0x1800b8e24`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b8f58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b9044`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b8f58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b9044`
- `CRYPT32!CryptStringToBinaryW` at `0x1800b8f4a`
- `CRYPT32!CryptStringToBinaryW` at `0x1800b9036`
- `CRYPT32!CryptStringToBinaryW` at `0x1800b8f4a`
- `CRYPT32!CryptStringToBinaryW` at `0x1800b9036`

## string_xrefs

- `0x1800b8f91`: `onecore\termsrv\rdpplatform\common\cryptutil\base\tscryptutils.cpp`
- `0x1800b9079`: `onecore\termsrv\rdpplatform\common\cryptutil\base\tscryptutils.cpp`

## pseudocode

```c

```
