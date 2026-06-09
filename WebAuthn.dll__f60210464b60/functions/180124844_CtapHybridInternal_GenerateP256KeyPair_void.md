# CtapHybridInternal::GenerateP256KeyPair(void)

- ea: `0x180124844`
- end: `0x180124a0b`
- name: `?GenerateP256KeyPair@CtapHybridInternal@@YA?AV?$tuple@V?$unique_ptr@UP256BCryptPrivateKey@CtapHybridInternal@@Uhlocal_secure_deleter@wil@@@wistd@@V?$unique_ptr@UP256BCryptPublicKey@CtapHybridInternal@@Uhlocal_secure_deleter@wil@@@2@@std@@XZ`
- size: `455`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180107d20`

## callees

- `0x18004ac74`
- `0x18005db14`
- `0x18009359c`
- `0x180124614`
- `0x180124690`
- `0x180124844`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801249b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801249f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801249b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801249f0`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18012499b`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x1801249d3`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18012499b`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x1801249d3`
- `bcrypt!BCryptGenerateKeyPair` at `0x18012486c`
- `bcrypt!BCryptGenerateKeyPair` at `0x18012486c`
- `bcrypt!BCryptFinalizeKeyPair` at `0x180124895`
- `bcrypt!BCryptFinalizeKeyPair` at `0x180124895`
- `bcrypt!BCryptExportKey` at `0x1801248f3`
- `bcrypt!BCryptExportKey` at `0x18012494a`
- `bcrypt!BCryptExportKey` at `0x1801248f3`
- `bcrypt!BCryptExportKey` at `0x18012494a`

## string_xrefs

- `0x18012487d`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybridcrypto.cpp`
- `0x1801248a6`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybridcrypto.cpp`
- `0x180124904`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybridcrypto.cpp`
- `0x18012495b`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybridcrypto.cpp`

## pseudocode

```c

```
