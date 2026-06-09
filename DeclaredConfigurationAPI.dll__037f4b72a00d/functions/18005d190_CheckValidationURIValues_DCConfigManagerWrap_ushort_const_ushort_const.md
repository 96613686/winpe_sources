# CheckValidationURIValues(DCConfigManagerWrap *,ushort const *,ushort const *)

- ea: `0x18005d190`
- end: `0x18005d449`
- name: `?CheckValidationURIValues@@YAJPEAVDCConfigManagerWrap@@PEBG1@Z`
- size: `697`
- prototype: `__int64 __fastcall(struct DCConfigManagerWrap *this, const unsigned __int16 *, wchar_t *Str)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005c05c`

## callees

- `0x18000b9e0`
- `0x180011fe0`
- `0x18001438c`
- `0x180016a54`
- `0x180016da8`
- `0x180016f58`
- `0x180018ac0`
- `0x18001dea8`
- `0x18004e3d8`
- `0x180051e0c`
- `0x180053ef0`
- `0x18005d190`
- `0x18009a2e4`
- `0x1800f5c8c`
- `0x1800f9d70`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18005d3df`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18005d3df`
- `OLEAUT32!__imp_VariantInit` at `0x18005d208`
- `OLEAUT32!__imp_VariantInit` at `0x18005d208`
- `OLEAUT32!__imp_VariantClear` at `0x18005d22f`
- `OLEAUT32!__imp_VariantClear` at `0x18005d405`
- `OLEAUT32!__imp_VariantClear` at `0x18005d22f`
- `OLEAUT32!__imp_VariantClear` at `0x18005d405`

## string_xrefs

- `0x18005d1e2`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18005d322`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18005d260`: `CheckValidationURIValues`
- `0x18005d2f0`: `CheckValidationURIValues`
- `0x18005d2b6`: `URI: :%s, expected value type:%d or %d, actual value type: %d`

## pseudocode

```c

```
