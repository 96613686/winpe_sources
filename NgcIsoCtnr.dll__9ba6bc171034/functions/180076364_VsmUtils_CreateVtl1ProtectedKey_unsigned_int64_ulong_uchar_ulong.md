# VsmUtils::CreateVtl1ProtectedKey(unsigned __int64,ulong,uchar *,ulong)

- ea: `0x180076364`
- end: `0x180076438`
- name: `?CreateVtl1ProtectedKey@VsmUtils@@YAJ_KKPEAEK@Z`
- size: `212`
- prototype: `__int64 __fastcall(NCRYPT_KEY_HANDLE hKey, unsigned __int64, unsigned int, unsigned __int8 *, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001ea1c`
- `0x180048c48`

## callees

- `0x18000d62c`
- `0x1800159b4`
- `0x180076364`

## import_xrefs

- `ncrypt!NCryptFinalizeKey` at `0x180076410`
- `ncrypt!NCryptFinalizeKey` at `0x180076410`
- `ncrypt!NCryptSetProperty` at `0x180076387`
- `ncrypt!NCryptSetProperty` at `0x1800763f8`
- `ncrypt!NCryptSetProperty` at `0x180076387`
- `ncrypt!NCryptSetProperty` at `0x1800763f8`

## string_xrefs

- `0x18007639d`: `onecore\ds\security\trustlet\utils\vtl0\lib\vtl0tpmcommands.cpp`

## pseudocode

```c

```
