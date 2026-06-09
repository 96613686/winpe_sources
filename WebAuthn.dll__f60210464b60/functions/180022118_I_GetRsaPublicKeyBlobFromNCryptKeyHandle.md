# I_GetRsaPublicKeyBlobFromNCryptKeyHandle

- ea: `0x180022118`
- end: `0x18002225c`
- name: `I_GetRsaPublicKeyBlobFromNCryptKeyHandle`
- size: `324`
- prototype: `__int64 __fastcall(NCRYPT_KEY_HANDLE hKey)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180020718`

## callees

- `0x1800205e4`
- `0x180022118`
- `0x180031708`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800221c5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800221c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022235`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022235`
- `ncrypt!NCryptExportKey` at `0x180022168`
- `ncrypt!NCryptExportKey` at `0x18002220d`
- `ncrypt!NCryptExportKey` at `0x180022168`
- `ncrypt!NCryptExportKey` at `0x18002220d`

## string_xrefs

- `0x180022179`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x1800221a8`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x18002221e`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`

## pseudocode

```c

```
