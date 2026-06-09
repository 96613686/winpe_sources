# I_GetEccPublicKeyBlobFromNCryptKeyHandle

- ea: `0x180021fcc`
- end: `0x180022110`
- name: `I_GetEccPublicKeyBlobFromNCryptKeyHandle`
- size: `324`
- prototype: `__int64 __fastcall(NCRYPT_KEY_HANDLE hKey)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180020718`

## callees

- `0x1800205e4`
- `0x180021fcc`
- `0x180031708`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180022079`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180022079`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800220e9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800220e9`
- `ncrypt!NCryptExportKey` at `0x18002201c`
- `ncrypt!NCryptExportKey` at `0x1800220c1`
- `ncrypt!NCryptExportKey` at `0x18002201c`
- `ncrypt!NCryptExportKey` at `0x1800220c1`

## string_xrefs

- `0x18002202d`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x18002205c`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x1800220d2`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`

## pseudocode

```c

```
