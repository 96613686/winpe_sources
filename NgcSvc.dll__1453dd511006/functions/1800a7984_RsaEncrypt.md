# RsaEncrypt

- ea: `0x1800a7984`
- end: `0x1800a7b6c`
- name: `RsaEncrypt`
- size: `488`
- prototype: `__int64 __fastcall(PUCHAR pbInput, ULONG cbInput, PUCHAR, ULONG, PUCHAR pbOutput, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800a0474`

## callees

- `0x18000782c`
- `0x180033350`
- `0x180033c84`
- `0x18004826c`
- `0x180050b30`
- `0x1800527ac`
- `0x180069b58`
- `0x18008f8f8`
- `0x1800a7984`

## import_xrefs

- `bcrypt!BCryptImportKeyPair` at `0x1800a7a2e`
- `bcrypt!BCryptImportKeyPair` at `0x1800a7a2e`
- `bcrypt!BCryptDestroyKey` at `0x1800a79f3`
- `bcrypt!BCryptDestroyKey` at `0x1800a79f3`
- `bcrypt!BCryptEncrypt` at `0x1800a7a7b`
- `bcrypt!BCryptEncrypt` at `0x1800a7b12`
- `bcrypt!BCryptEncrypt` at `0x1800a7a7b`
- `bcrypt!BCryptEncrypt` at `0x1800a7b12`

## string_xrefs

- `0x1800a7a8e`: `onecore\ds\security\devicecredential\service\util\dcautil.cpp`
- `0x1800a7abd`: `onecore\ds\security\devicecredential\service\util\dcautil.cpp`
- `0x1800a7b20`: `onecore\ds\security\devicecredential\service\util\dcautil.cpp`

## pseudocode

```c

```
