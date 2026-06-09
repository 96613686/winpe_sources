# OnlineKey::GetValue(ushort const *,PushButtonReset::RegValue * *)

- ea: `0x1800566e0`
- end: `0x1800568c1`
- name: `?GetValue@OnlineKey@@UEAAJPEBGPEAPEAVRegValue@PushButtonReset@@@Z`
- size: `481`
- prototype: `int(OnlineKey *__hidden this, const unsigned __int16 *, struct PushButtonReset::RegValue **)`
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
- `0x1800566e0`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x180056752`
- `ADVAPI32!RegGetValueW` at `0x1800567cb`
- `ADVAPI32!RegGetValueW` at `0x180056752`
- `ADVAPI32!RegGetValueW` at `0x1800567cb`

## string_xrefs

- `0x18005677f`: `Failed to read size of value [%s]`
- `0x1800567e9`: `Failed to read value [%s]`
- `0x180056855`: `Failed to create RegValue container for [%s]`

## pseudocode

```c

```
