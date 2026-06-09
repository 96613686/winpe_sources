# NgcUtils::GetNCryptBinaryBlob(unsigned __int64,ushort const *,uchar * *,ulong *)

- ea: `0x180073d64`
- end: `0x180073e61`
- name: `?GetNCryptBinaryBlob@NgcUtils@@YAJ_KPEBGPEAPEAEPEAK@Z`
- size: `253`
- prototype: `__int64 __fastcall(NCRYPT_HANDLE hObject, unsigned __int64, const unsigned __int16 *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180072218`

## callees

- `0x18000d62c`
- `0x1800721d0`
- `0x180073d64`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180073e42`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180073e42`
- `ncrypt!NCryptGetProperty` at `0x180073da1`
- `ncrypt!NCryptGetProperty` at `0x180073e15`
- `ncrypt!NCryptGetProperty` at `0x180073da1`
- `ncrypt!NCryptGetProperty` at `0x180073e15`

## string_xrefs

- `0x180073db7`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`
- `0x180073e26`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`

## pseudocode

```c

```
