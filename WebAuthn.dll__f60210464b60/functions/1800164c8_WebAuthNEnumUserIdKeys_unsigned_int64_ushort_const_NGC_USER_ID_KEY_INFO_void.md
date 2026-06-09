# WebAuthNEnumUserIdKeys(unsigned __int64,ushort const *,_NGC_USER_ID_KEY_INFO * *,void * *)

- ea: `0x1800164c8`
- end: `0x18001682b`
- name: `?WebAuthNEnumUserIdKeys@@YAJ_KPEBGPEAPEAU_NGC_USER_ID_KEY_INFO@@PEAPEAX@Z`
- size: `867`
- prototype: `__int64 __fastcall(NCRYPT_PROV_HANDLE hProvider, const unsigned __int16 *, struct _NGC_USER_ID_KEY_INFO **, void **)`
- caller_count: `4`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001fa64`
- `0x18001fe74`
- `0x180083e50`
- `0x180085a2c`

## callees

- `0x1800164c8`
- `0x180016834`
- `0x18001687c`
- `0x180018cc0`
- `0x1800205e4`
- `0x180036da4`
- `0x18004fe20`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800165d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001667e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800166a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016793`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800167b0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800167d7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800165d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001667e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800166a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016793`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800167b0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800167d7`
- `ncrypt!NCryptEnumKeys` at `0x18001662d`
- `ncrypt!NCryptEnumKeys` at `0x18001662d`
- `ncrypt!NCryptFreeBuffer` at `0x180016697`
- `ncrypt!NCryptFreeBuffer` at `0x180016746`
- `ncrypt!NCryptFreeBuffer` at `0x180016785`
- `ncrypt!NCryptFreeBuffer` at `0x1800167c9`
- `ncrypt!NCryptFreeBuffer` at `0x180016697`
- `ncrypt!NCryptFreeBuffer` at `0x180016746`
- `ncrypt!NCryptFreeBuffer` at `0x180016785`
- `ncrypt!NCryptFreeBuffer` at `0x1800167c9`

## string_xrefs

- `0x180016505`: `onecore\ds\security\fido\webauthn\dll\webauthnncrypt.cpp`
- `0x180016532`: `onecore\ds\security\fido\webauthn\dll\webauthnncrypt.cpp`
- `0x18001655f`: `onecore\ds\security\fido\webauthn\dll\webauthnncrypt.cpp`
- `0x1800165bc`: `onecore\ds\security\fido\webauthn\dll\webauthnncrypt.cpp`
- `0x18001665a`: `onecore\ds\security\fido\webauthn\dll\webauthnncrypt.cpp`
- `0x180016718`: `onecore\ds\security\fido\webauthn\dll\webauthnncrypt.cpp`
- `0x1800167f4`: `onecore\ds\security\fido\webauthn\dll\webauthnncrypt.cpp`

## pseudocode

```c

```
