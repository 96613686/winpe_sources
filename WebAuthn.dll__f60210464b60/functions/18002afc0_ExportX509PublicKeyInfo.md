# ExportX509PublicKeyInfo

- ea: `0x18002afc0`
- end: `0x18002b1af`
- name: `ExportX509PublicKeyInfo`
- size: `495`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002f9b0`

## callees

- `0x180007f90`
- `0x18002a2f0`
- `0x18002a6c0`
- `0x18002afc0`
- `0x18002bbf4`
- `0x180031708`
- `0x180036da4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002b091`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002b091`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b176`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b176`
- `CRYPT32!CryptExportPublicKeyInfoFromBCryptKeyHandle` at `0x18002b052`
- `CRYPT32!CryptExportPublicKeyInfoFromBCryptKeyHandle` at `0x18002b0ce`
- `CRYPT32!CryptExportPublicKeyInfoFromBCryptKeyHandle` at `0x18002b052`
- `CRYPT32!CryptExportPublicKeyInfoFromBCryptKeyHandle` at `0x18002b0ce`
- `CRYPT32!CryptEncodeObjectEx` at `0x18002b11e`
- `CRYPT32!CryptEncodeObjectEx` at `0x18002b11e`
- `bcrypt!BCryptDestroyKey` at `0x18002b167`
- `bcrypt!BCryptDestroyKey` at `0x18002b167`

## string_xrefs

- `0x18002aff8`: `onecore\ds\security\fido\webauthn\dll\webauthnctap.cpp`

## pseudocode

```c

```
