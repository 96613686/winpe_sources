# I_WebAuthNGetNgcGetCredentialId

- ea: `0x180020718`
- end: `0x180020a73`
- name: `I_WebAuthNGetNgcGetCredentialId`
- size: `859`
- prototype: `__int64 __fastcall(NCRYPT_HANDLE hObject)`
- caller_count: `5`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001fa64`
- `0x18001fe74`
- `0x180082504`
- `0x180085a2c`
- `0x180089b74`

## callees

- `0x18001687c`
- `0x1800205e4`
- `0x180020718`
- `0x180021fcc`
- `0x180022118`
- `0x180022264`
- `0x180022284`
- `0x180031708`
- `0x1800537a4`
- `0x18013c064`
- `0x18013c090`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800209c2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800209c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020a35`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020a43`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020a35`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020a43`
- `bcrypt!BCryptFinishHash` at `0x180020a03`
- `bcrypt!BCryptFinishHash` at `0x180020a03`
- `bcrypt!BCryptHashData` at `0x1800208a9`
- `bcrypt!BCryptHashData` at `0x1800208ce`
- `bcrypt!BCryptHashData` at `0x1800208fc`
- `bcrypt!BCryptHashData` at `0x180020971`
- `bcrypt!BCryptHashData` at `0x18002099f`
- `bcrypt!BCryptHashData` at `0x1800208a9`
- `bcrypt!BCryptHashData` at `0x1800208ce`
- `bcrypt!BCryptHashData` at `0x1800208fc`
- `bcrypt!BCryptHashData` at `0x180020971`
- `bcrypt!BCryptHashData` at `0x18002099f`
- `bcrypt!BCryptCreateHash` at `0x1800207ed`
- `bcrypt!BCryptCreateHash` at `0x1800207ed`
- `ncrypt!NCryptGetProperty` at `0x180020799`
- `ncrypt!NCryptGetProperty` at `0x180020799`

## string_xrefs

- `0x1800207b4`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x1800209da`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`

## pseudocode

```c

```
