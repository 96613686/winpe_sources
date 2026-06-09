# Windows::Globalization::Spelling::SpellerRegistration::ProcessSpellersFromKey(HKEY__ *,std::function<bool (std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)>)

- ea: `0x18006f958`
- end: `0x18006faed`
- name: `?ProcessSpellersFromKey@SpellerRegistration@Spelling@Globalization@Windows@@CA_NPEAUHKEY__@@V?$function@$$A6A_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z@std@@@Z`
- size: `405`
- prototype: `char __fastcall(HKEY hkey, __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180037c0c`

## callees

- `0x18001ee7c`
- `0x1800202e4`
- `0x180036bd4`
- `0x180061320`
- `0x18006f958`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18006f9cd`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18006f9cd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006fa1e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006fa1e`

## string_xrefs

- `0x18006fa10`: `CLSID`

## pseudocode

```c

```
