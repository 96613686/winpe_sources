# I_NgcGetAccountInformationFromFidoKey

- ea: `0x18002c328`
- end: `0x18002c43c`
- name: `I_NgcGetAccountInformationFromFidoKey`
- size: `276`
- prototype: `__int64 __fastcall(NCRYPT_HANDLE hObject)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002be64`
- `0x180083e50`

## callees

- `0x1800205e4`
- `0x18002c328`
- `0x180031708`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002c39b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002c39b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c415`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c415`
- `ncrypt!NCryptGetProperty` at `0x18002c368`
- `ncrypt!NCryptGetProperty` at `0x18002c3ed`
- `ncrypt!NCryptGetProperty` at `0x18002c368`
- `ncrypt!NCryptGetProperty` at `0x18002c3ed`

## string_xrefs

- `0x18002c379`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x18002c3ae`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x18002c3fe`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`

## pseudocode

```c

```
