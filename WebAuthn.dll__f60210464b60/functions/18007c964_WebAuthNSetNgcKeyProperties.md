# WebAuthNSetNgcKeyProperties

- ea: `0x18007c964`
- end: `0x18007cc67`
- name: `WebAuthNSetNgcKeyProperties`
- size: `771`
- prototype: `__int64 __usercall@<rax>(NCRYPT_HANDLE hObject@<rcx>, int, __int64, __int64, __int64, __int64, int, PBYTE pbInput, PBYTE, DWORD cbInput, int, PBYTE, DWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800513cc`

## callees

- `0x1800350b4`
- `0x180036da4`
- `0x180046768`
- `0x18007c964`
- `0x180134070`
- `0x1801340d4`
- `0x180139d80`
- `0x18013c064`

## import_xrefs

- `ngcutils!NgcSetNCryptDwordProperty` at `0x18007c988`
- `ngcutils!NgcSetNCryptDwordProperty` at `0x18007c9d5`
- `ngcutils!NgcSetNCryptDwordProperty` at `0x18007ca0f`
- `ngcutils!NgcSetNCryptDwordProperty` at `0x18007c988`
- `ngcutils!NgcSetNCryptDwordProperty` at `0x18007c9d5`
- `ngcutils!NgcSetNCryptDwordProperty` at `0x18007ca0f`
- `ngcutils!NgcSetNCryptUiPolicy` at `0x18007ca52`
- `ngcutils!NgcSetNCryptUiPolicy` at `0x18007ca52`
- `ngcutils!NgcSetNCryptBoolProperty` at `0x18007ca37`
- `ngcutils!NgcSetNCryptBoolProperty` at `0x18007cbc6`
- `ngcutils!NgcSetNCryptBoolProperty` at `0x18007ca37`
- `ngcutils!NgcSetNCryptBoolProperty` at `0x18007cbc6`
- `ngcutils!NgcSetNCryptWindowHandle` at `0x18007c9ee`
- `ngcutils!NgcSetNCryptWindowHandle` at `0x18007c9ee`
- `ncrypt!NCryptSetProperty` at `0x18007ca8c`
- `ncrypt!NCryptSetProperty` at `0x18007cac7`
- `ncrypt!NCryptSetProperty` at `0x18007cb0c`
- `ncrypt!NCryptSetProperty` at `0x18007cb76`
- `ncrypt!NCryptSetProperty` at `0x18007cc32`
- `ncrypt!NCryptSetProperty` at `0x18007ca8c`
- `ncrypt!NCryptSetProperty` at `0x18007cac7`
- `ncrypt!NCryptSetProperty` at `0x18007cb0c`
- `ncrypt!NCryptSetProperty` at `0x18007cb76`
- `ncrypt!NCryptSetProperty` at `0x18007cc32`

## string_xrefs

- `0x18007c99d`: `onecore\ds\security\fido\webauthn\dll\webauthnncrypt.cpp`
- `0x18007cb21`: `onecore\ds\security\fido\webauthn\dll\webauthnncrypt.cpp`
- `0x18007cc42`: `onecore\ds\security\fido\webauthn\dll\webauthnncrypt.cpp`
- `0x18007ca05`: `NgcCacheType`
- `0x18007ca2a`: `PinCacheIsGestureRequired`

## pseudocode

```c

```
