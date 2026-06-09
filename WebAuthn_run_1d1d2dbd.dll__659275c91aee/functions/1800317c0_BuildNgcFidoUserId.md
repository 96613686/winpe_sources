# BuildNgcFidoUserId

- ea: `0x1800317c0`
- end: `0x18003197b`
- name: `BuildNgcFidoUserId`
- size: `443`
- prototype: `__int64 __fastcall(BYTE *pbBinary, DWORD cbBinary, BYTE *, DWORD, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180089b74`

## callees

- `0x180017764`
- `0x180017a88`
- `0x18002bbf4`
- `0x180031708`
- `0x1800317c0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003188d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003188d`
- `CRYPT32!CryptBinaryToStringW` at `0x180031804`
- `CRYPT32!CryptBinaryToStringW` at `0x180031856`
- `CRYPT32!CryptBinaryToStringW` at `0x1800318cf`
- `CRYPT32!CryptBinaryToStringW` at `0x18003191e`
- `CRYPT32!CryptBinaryToStringW` at `0x180031804`
- `CRYPT32!CryptBinaryToStringW` at `0x180031856`
- `CRYPT32!CryptBinaryToStringW` at `0x1800318cf`
- `CRYPT32!CryptBinaryToStringW` at `0x18003191e`

## string_xrefs

- `0x18003182b`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`

## pseudocode

```c

```
