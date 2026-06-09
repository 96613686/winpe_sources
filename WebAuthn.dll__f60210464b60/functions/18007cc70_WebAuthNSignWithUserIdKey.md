# WebAuthNSignWithUserIdKey

- ea: `0x18007cc70`
- end: `0x18007cf2c`
- name: `WebAuthNSignWithUserIdKey`
- size: `700`
- prototype: `__int64 __usercall@<rax>(NCRYPT_HANDLE hObject@<rcx>, HLOCAL hMem, __int64, __int64, __int64, int, __int64, int, PBYTE pbInput, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18007cf34`

## callees

- `0x18001687c`
- `0x1800350b4`
- `0x180036da4`
- `0x18007cc70`
- `0x18007d01c`
- `0x1801340d4`
- `0x180139d80`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007cef9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007cef9`
- `ngcutils!NgcSetNCryptUiPolicy` at `0x18007cd20`
- `ngcutils!NgcSetNCryptUiPolicy` at `0x18007cd20`
- `ngcutils!NgcSetNCryptBoolProperty` at `0x18007ce56`
- `ngcutils!NgcSetNCryptBoolProperty` at `0x18007ce56`
- `ngcutils!NgcSetNCryptWindowHandle` at `0x18007ccf0`
- `ngcutils!NgcSetNCryptWindowHandle` at `0x18007ccf0`
- `ncrypt!NCryptSetProperty` at `0x18007cd57`
- `ncrypt!NCryptSetProperty` at `0x18007cd99`
- `ncrypt!NCryptSetProperty` at `0x18007ce03`
- `ncrypt!NCryptSetProperty` at `0x18007cd57`
- `ncrypt!NCryptSetProperty` at `0x18007cd99`
- `ncrypt!NCryptSetProperty` at `0x18007ce03`

## string_xrefs

- `0x18007cca0`: `onecore\ds\security\fido\webauthn\dll\webauthnncrypt.cpp`
- `0x18007cd05`: `onecore\ds\security\fido\webauthn\dll\webauthnncrypt.cpp`
- `0x18007cdae`: `onecore\ds\security\fido\webauthn\dll\webauthnncrypt.cpp`
- `0x18007ced0`: `onecore\ds\security\fido\webauthn\dll\webauthnncrypt.cpp`

## pseudocode

```c

```
