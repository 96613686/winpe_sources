# RsaDecrypt

- ea: `0x1800a7788`
- end: `0x1800a797d`
- name: `RsaDecrypt`
- size: `501`
- prototype: `__int64 __fastcall(PUCHAR pbInput, ULONG cbInput, PUCHAR, ULONG, PUCHAR pbOutput, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800a0950`

## callees

- `0x18000782c`
- `0x180033350`
- `0x180033c84`
- `0x18004826c`
- `0x180050b30`
- `0x1800527ac`
- `0x180069b58`
- `0x18008f8f8`
- `0x1800a58dc`
- `0x1800a7788`

## import_xrefs

- `bcrypt!BCryptImportKeyPair` at `0x1800a7836`
- `bcrypt!BCryptImportKeyPair` at `0x1800a7836`
- `bcrypt!BCryptDecrypt` at `0x1800a7883`
- `bcrypt!BCryptDecrypt` at `0x1800a791a`
- `bcrypt!BCryptDecrypt` at `0x1800a7883`
- `bcrypt!BCryptDecrypt` at `0x1800a791a`
- `bcrypt!BCryptDestroyKey` at `0x1800a77fb`
- `bcrypt!BCryptDestroyKey` at `0x1800a77fb`

## string_xrefs

- `0x1800a7896`: `onecore\ds\security\devicecredential\service\util\dcautil.cpp`
- `0x1800a78c5`: `onecore\ds\security\devicecredential\service\util\dcautil.cpp`
- `0x1800a7928`: `onecore\ds\security\devicecredential\service\util\dcautil.cpp`

## pseudocode

```c

```
