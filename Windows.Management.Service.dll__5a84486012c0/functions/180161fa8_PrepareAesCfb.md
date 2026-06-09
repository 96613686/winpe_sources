# PrepareAesCfb

- ea: `0x180161fa8`
- end: `0x1801620d1`
- name: `PrepareAesCfb`
- size: `297`
- prototype: `__int64 __fastcall(PUCHAR pbSecret, ULONG cbSecret)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1801620e0`
- `0x1801622a0`

## callees

- `0x180161fa8`

## import_xrefs

- `bcrypt!BCryptGenerateSymmetricKey` at `0x18016201e`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18016201e`
- `bcrypt!BCryptSetProperty` at `0x18016204a`
- `bcrypt!BCryptSetProperty` at `0x180162073`
- `bcrypt!BCryptSetProperty` at `0x18016204a`
- `bcrypt!BCryptSetProperty` at `0x180162073`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1801620bc`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1801620bc`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180161fef`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180161fef`
- `bcrypt!BCryptDestroyKey` at `0x1801620ab`
- `bcrypt!BCryptDestroyKey` at `0x1801620ab`

## pseudocode

```c

```
