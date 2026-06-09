# PwdlessPlat::GetDwordRegistryValue(HKEY__ *,ushort const *,ushort const *,ulong *)

- ea: `0x180029330`
- end: `0x1800293d1`
- name: `?GetDwordRegistryValue@PwdlessPlat@@YAJPEAUHKEY__@@PEBG1PEAK@Z`
- size: `161`
- prototype: `__int64 __fastcall(PwdlessPlat *__hidden this, HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180077250`

## callees

- `0x180023278`
- `0x180029330`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180029378`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180029378`

## string_xrefs

- `0x1800293a5`: `onecore\ds\security\pwdless\customization\lib\pwdlessplatimagecustomizations.cpp`

## pseudocode

```c

```
