# RDP_RC4SetKey

- ea: `0x18014cdc0`
- end: `0x18014ce76`
- name: `RDP_RC4SetKey`
- size: `182`
- prototype: `__int64 __fastcall(BCRYPT_KEY_HANDLE *phKey, PUCHAR pbSecret, ULONG cbSecret)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18014c8e0`
- `0x18014cab0`

## callees

- `0x18014cdc0`

## import_xrefs

- `bcrypt!BCryptDestroyKey` at `0x18014ce32`
- `bcrypt!BCryptDestroyKey` at `0x18014ce32`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18014ce1f`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18014ce1f`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18014ce60`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18014ce60`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18014cdfc`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18014cdfc`

## pseudocode

```c

```
