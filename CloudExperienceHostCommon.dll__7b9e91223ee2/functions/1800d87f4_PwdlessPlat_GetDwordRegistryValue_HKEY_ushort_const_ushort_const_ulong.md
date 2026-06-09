# PwdlessPlat::GetDwordRegistryValue(HKEY__ *,ushort const *,ushort const *,ulong *)

- ea: `0x1800d87f4`
- end: `0x1800d888e`
- name: `?GetDwordRegistryValue@PwdlessPlat@@YAJPEAUHKEY__@@PEBG1PEAK@Z`
- size: `154`
- prototype: `__int64 __fastcall(PwdlessPlat *__hidden this, HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800d8894`

## callees

- `0x1800153f8`
- `0x1800d87f4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800d883c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800d883c`

## string_xrefs

- `0x1800d8863`: `onecore\ds\security\pwdless\customization\lib\pwdlessplatimagecustomizations.cpp`

## pseudocode

```c

```
