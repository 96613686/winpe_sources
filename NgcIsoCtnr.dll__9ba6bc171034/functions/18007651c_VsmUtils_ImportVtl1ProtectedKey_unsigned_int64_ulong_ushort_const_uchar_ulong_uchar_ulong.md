# VsmUtils::ImportVtl1ProtectedKey(unsigned __int64,ulong,ushort const *,uchar *,ulong,uchar *,ulong)

- ea: `0x18007651c`
- end: `0x180076649`
- name: `?ImportVtl1ProtectedKey@VsmUtils@@YAJ_KKPEBGPEAEK2K@Z`
- size: `301`
- prototype: `__int64 __usercall@<rax>(NCRYPT_KEY_HANDLE hKey@<rcx>, unsigned __int64@<rdx>, unsigned int@<r8d>, const unsigned __int16 *@<r9>, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180024820`

## callees

- `0x18000d62c`
- `0x18007651c`

## import_xrefs

- `ncrypt!NCryptFinalizeKey` at `0x180076613`
- `ncrypt!NCryptFinalizeKey` at `0x180076613`
- `ncrypt!NCryptSetProperty` at `0x180076548`
- `ncrypt!NCryptSetProperty` at `0x180076590`
- `ncrypt!NCryptSetProperty` at `0x1800765c0`
- `ncrypt!NCryptSetProperty` at `0x1800765f8`
- `ncrypt!NCryptSetProperty` at `0x180076548`
- `ncrypt!NCryptSetProperty` at `0x180076590`
- `ncrypt!NCryptSetProperty` at `0x1800765c0`
- `ncrypt!NCryptSetProperty` at `0x1800765f8`

## string_xrefs

- `0x18007655e`: `onecore\ds\security\trustlet\utils\vtl0\lib\vtl0tpmcommands.cpp`
- `0x180076624`: `onecore\ds\security\trustlet\utils\vtl0\lib\vtl0tpmcommands.cpp`

## pseudocode

```c

```
