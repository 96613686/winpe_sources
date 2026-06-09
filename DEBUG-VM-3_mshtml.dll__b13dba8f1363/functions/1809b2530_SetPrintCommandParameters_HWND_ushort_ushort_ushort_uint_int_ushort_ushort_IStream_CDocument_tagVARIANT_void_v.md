# SetPrintCommandParameters(HWND__ *,ushort *,ushort *,ushort *,uint,int,ushort *,ushort *,IStream *,CDocument *,tagVARIANT *,void *,void *,ushort *,ushort *,ushort *,PRINTTYPE,ushort *)

- ea: `0x1809b2530`
- end: `0x1809b2dc0`
- name: `?SetPrintCommandParameters@@YAPEAUIUnknown@@PEAUHWND__@@PEAG11IH11PEAUIStream@@PEAVCDocument@@PEAUtagVARIANT@@PEAX5111W4PRINTTYPE@@1@Z`
- size: `2192`
- prototype: `struct IUnknown *__high(HWND, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned int, int, unsigned __int16 *, unsigned __int16 *, struct IStream *, struct CDocument *, struct tagVARIANT *, void *, void *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, enum PRINTTYPE, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1806d3d68`
- `0x1809b1478`
- `0x1809b21e0`
- `0x1809b31f0`

## callees

- `0x1800d904c`
- `0x18030035c`
- `0x18043c328`
- `0x1809b038c`
- `0x1809b10a0`
- `0x1809b2530`
- `0x180a0d45c`
- `0x181075704`
- `0x1810d1010`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1809b2ba1`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1809b2ba1`
- `OLEAUT32!__imp_SysAllocString` at `0x1809b25fd`
- `OLEAUT32!__imp_SysAllocString` at `0x1809b2823`
- `OLEAUT32!__imp_SysAllocString` at `0x1809b286f`
- `OLEAUT32!__imp_SysAllocString` at `0x1809b28bf`
- `OLEAUT32!__imp_SysAllocString` at `0x1809b290f`
- `OLEAUT32!__imp_SysAllocString` at `0x1809b295f`
- `OLEAUT32!__imp_SysAllocString` at `0x1809b2b0d`
- `OLEAUT32!__imp_SysAllocString` at `0x1809b2ced`
- `OLEAUT32!__imp_SysAllocString` at `0x1809b25fd`
- `OLEAUT32!__imp_SysAllocString` at `0x1809b2823`
- `OLEAUT32!__imp_SysAllocString` at `0x1809b286f`
- `OLEAUT32!__imp_SysAllocString` at `0x1809b28bf`
- `OLEAUT32!__imp_SysAllocString` at `0x1809b290f`
- `OLEAUT32!__imp_SysAllocString` at `0x1809b295f`
- `OLEAUT32!__imp_SysAllocString` at `0x1809b2b0d`
- `OLEAUT32!__imp_SysAllocString` at `0x1809b2ced`
- `OLEAUT32!__imp_VariantInit` at `0x1809b2af0`
- `OLEAUT32!__imp_VariantInit` at `0x1809b2af0`
- `OLEAUT32!__imp_VariantClear` at `0x1809b260d`
- `OLEAUT32!__imp_VariantClear` at `0x1809b2647`
- `OLEAUT32!__imp_VariantClear` at `0x1809b268e`
- `OLEAUT32!__imp_VariantClear` at `0x1809b2786`
- `OLEAUT32!__imp_VariantClear` at `0x1809b27cf`
- `OLEAUT32!__imp_VariantClear` at `0x1809b2815`
- `OLEAUT32!__imp_VariantClear` at `0x1809b2861`
- `OLEAUT32!__imp_VariantClear` at `0x1809b28ad`
- `OLEAUT32!__imp_VariantClear` at `0x1809b28fd`
- `OLEAUT32!__imp_VariantClear` at `0x1809b294d`
- `OLEAUT32!__imp_VariantClear` at `0x1809b299d`
- `OLEAUT32!__imp_VariantClear` at `0x1809b29f8`
- `OLEAUT32!__imp_VariantClear` at `0x1809b2b4b`
- `OLEAUT32!__imp_VariantClear` at `0x1809b2b96`
- `OLEAUT32!__imp_VariantClear` at `0x1809b2bf3`
- `OLEAUT32!__imp_VariantClear` at `0x1809b2c84`
- `OLEAUT32!__imp_VariantClear` at `0x1809b2cd2`
- `OLEAUT32!__imp_VariantClear` at `0x1809b2d2b`
- `OLEAUT32!__imp_VariantClear` at `0x1809b2d84`
- `OLEAUT32!__imp_VariantClear` at `0x1809b2da3`
- `OLEAUT32!__imp_VariantClear` at `0x1809b260d`
- `OLEAUT32!__imp_VariantClear` at `0x1809b2647`
- `OLEAUT32!__imp_VariantClear` at `0x1809b268e`
- `OLEAUT32!__imp_VariantClear` at `0x1809b2786`
- `OLEAUT32!__imp_VariantClear` at `0x1809b27cf`
- `OLEAUT32!__imp_VariantClear` at `0x1809b2815`
- `OLEAUT32!__imp_VariantClear` at `0x1809b2861`
- `OLEAUT32!__imp_VariantClear` at `0x1809b28ad`
- `OLEAUT32!__imp_VariantClear` at `0x1809b28fd`
- `OLEAUT32!__imp_VariantClear` at `0x1809b294d`
- `OLEAUT32!__imp_VariantClear` at `0x1809b299d`
- `OLEAUT32!__imp_VariantClear` at `0x1809b29f8`
- `OLEAUT32!__imp_VariantClear` at `0x1809b2b4b`
- `OLEAUT32!__imp_VariantClear` at `0x1809b2b96`
- `OLEAUT32!__imp_VariantClear` at `0x1809b2bf3`
- `OLEAUT32!__imp_VariantClear` at `0x1809b2c84`
- `OLEAUT32!__imp_VariantClear` at `0x1809b2cd2`
- `OLEAUT32!__imp_VariantClear` at `0x1809b2d2b`
- `OLEAUT32!__imp_VariantClear` at `0x1809b2d84`
- `OLEAUT32!__imp_VariantClear` at `0x1809b2da3`

## string_xrefs

- `0x1809b261f`: `__IE_TemplateUrl`
- `0x1809b2a0d`: `__IE_TemporaryFiles`
- `0x1809b2d00`: `__IE_SerializeCommandListOutfile`

## pseudocode

```c

```
