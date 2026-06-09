# PrepareAesCfb

- ea: `0x180166388`
- end: `0x1801664d6`
- name: `PrepareAesCfb`
- size: `334`
- prototype: `__int64 __fastcall(PUCHAR pbSecret, ULONG cbSecret)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1801664e0`
- `0x1801666b0`

## callees

- `0x180166388`

## import_xrefs

- `bcrypt!BCryptGenerateSymmetricKey` at `0x180166404`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180166404`
- `bcrypt!BCryptSetProperty` at `0x180166436`
- `bcrypt!BCryptSetProperty` at `0x180166465`
- `bcrypt!BCryptSetProperty` at `0x180166436`
- `bcrypt!BCryptSetProperty` at `0x180166465`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1801664ba`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1801664ba`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1801663cf`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1801663cf`
- `bcrypt!BCryptDestroyKey` at `0x1801664a3`
- `bcrypt!BCryptDestroyKey` at `0x1801664a3`

## pseudocode

```c

```
