# OfflineKey::GetValue(ushort const *,PushButtonReset::RegValue * *)

- ea: `0x180057580`
- end: `0x180057761`
- name: `?GetValue@OfflineKey@@UEAAJPEBGPEAPEAVRegValue@PushButtonReset@@@Z`
- size: `481`
- prototype: `int(OfflineKey *__hidden this, const unsigned __int16 *, struct PushButtonReset::RegValue **)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x18000509c`
- `0x180005cc0`
- `0x18000d740`
- `0x180037344`
- `0x180037b70`
- `0x180038778`
- `0x180057580`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x1800575f2`
- `ADVAPI32!RegGetValueW` at `0x18005766b`
- `ADVAPI32!RegGetValueW` at `0x1800575f2`
- `ADVAPI32!RegGetValueW` at `0x18005766b`

## string_xrefs

- `0x18005761f`: `Failed to read size of value [%s]`
- `0x180057689`: `Failed to read value [%s]`
- `0x1800576f5`: `Failed to create RegValue container for [%s]`

## pseudocode

```c

```
