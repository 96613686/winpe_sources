# PrepareAesCfb

- ea: `0x1800aec34`
- end: `0x1800aed5d`
- name: `PrepareAesCfb`
- size: `297`
- prototype: `__int64 __fastcall(PUCHAR pbSecret, ULONG cbSecret)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800aed70`
- `0x1800aef30`

## callees

- `0x1800aec34`

## import_xrefs

- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800aed48`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800aed48`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800aec7b`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800aec7b`
- `bcrypt!BCryptDestroyKey` at `0x1800aed37`
- `bcrypt!BCryptDestroyKey` at `0x1800aed37`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x1800aecaa`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x1800aecaa`
- `bcrypt!BCryptSetProperty` at `0x1800aecd6`
- `bcrypt!BCryptSetProperty` at `0x1800aecff`
- `bcrypt!BCryptSetProperty` at `0x1800aecd6`
- `bcrypt!BCryptSetProperty` at `0x1800aecff`

## pseudocode

```c

```
