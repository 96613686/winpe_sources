# CtapHybridInternal::ParseAndDecryptDataSection(std::span<uchar const,-1>,std::span<uchar const,-1>,std::span<uchar const,-1>)

- ea: `0x1801286c0`
- end: `0x180128a5f`
- name: `?ParseAndDecryptDataSection@CtapHybridInternal@@YA?AV?$optional@UUnpackedAdvertisementData@CtapHybridInternal@@@std@@V?$span@$$CBE$0?0@3@00@Z`
- size: `927`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180024694`

## callees

- `0x180017724`
- `0x18004aa68`
- `0x18004ac74`
- `0x18008e458`
- `0x180091540`
- `0x18009359c`
- `0x18010c27c`
- `0x1801245bc`
- `0x1801286c0`
- `0x18013c090`

## import_xrefs

- `bcrypt!BCryptImportKey` at `0x180128905`
- `bcrypt!BCryptImportKey` at `0x180128905`
- `bcrypt!BCryptHash` at `0x180128830`
- `bcrypt!BCryptHash` at `0x180128830`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1801288b0`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1801288b0`
- `bcrypt!BCryptDecrypt` at `0x180128957`
- `bcrypt!BCryptDecrypt` at `0x1801289b1`
- `bcrypt!BCryptDecrypt` at `0x180128957`
- `bcrypt!BCryptDecrypt` at `0x1801289b1`

## string_xrefs

- `0x1801287c9`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybridble.cpp`

## pseudocode

```c

```
