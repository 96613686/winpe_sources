# GetNamedAttributeValue(IXMLDOMNode *,ushort *,ushort * *)

- ea: `0x1800651b0`
- end: `0x1800654bd`
- name: `?GetNamedAttributeValue@@YAJPEAUIXMLDOMNode@@PEAGPEAPEAG@Z`
- size: `781`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `10`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180062b0c`
- `0x1800635a0`
- `0x180064124`
- `0x180065cc4`
- `0x180065f98`
- `0x18006c524`
- `0x18006d1b4`
- `0x18006d548`
- `0x18006d7bc`
- `0x18006d9b4`

## callees

- `0x1800054c4`
- `0x180005524`
- `0x18000b1d8`
- `0x18000ec54`
- `0x18000ec94`
- `0x18000ece0`
- `0x1800651b0`
- `0x1800a3010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800651e5`
- `OLEAUT32!__imp_VariantInit` at `0x1800651e5`
- `OLEAUT32!__imp_VariantClear` at `0x180065494`
- `OLEAUT32!__imp_VariantClear` at `0x180065494`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18006542f`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18006542f`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18006543b`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18006543b`

## string_xrefs

- `0x180065244`: `IXMLDOMNode::get_attributes failed`
- `0x18006531f`: `IXMLDOMNamedNodeMap::getNamedItem failed`
- `0x180065482`: `CComvariant::CopyTo failed`

## pseudocode

```c

```
