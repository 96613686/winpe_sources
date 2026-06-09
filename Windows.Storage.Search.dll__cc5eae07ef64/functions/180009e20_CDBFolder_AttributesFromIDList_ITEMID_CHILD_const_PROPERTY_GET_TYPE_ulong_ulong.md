# CDBFolder::_AttributesFromIDList(_ITEMID_CHILD const *,PROPERTY_GET_TYPE,ulong,ulong *)

- ea: `0x180009e20`
- end: `0x18000a181`
- name: `?_AttributesFromIDList@CDBFolder@@AEAAJPEFBU_ITEMID_CHILD@@W4PROPERTY_GET_TYPE@@KPEAK@Z`
- size: `865`
- prototype: `int __high(const struct _ITEMID_CHILD *, enum PROPERTY_GET_TYPE, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180007c70`

## callees

- `0x180009e20`
- `0x18000a350`
- `0x18000a730`
- `0x18000b650`
- `0x1800ea010`

## import_xrefs

- `SHCORE!__imp_SHGetObjectCompatFlags` at `0x18000a164`
- `SHCORE!__imp_SHGetObjectCompatFlags` at `0x18000a164`
- `Windows.Storage!ILFindLastID` at `0x180009ec8`
- `Windows.Storage!ILFindLastID` at `0x180009f0e`
- `Windows.Storage!ILFindLastID` at `0x180009ec8`
- `Windows.Storage!ILFindLastID` at `0x180009f0e`
- `Windows.Storage!ILFree` at `0x18000a0ba`
- `Windows.Storage!ILFree` at `0x18000a0ba`
- `Windows.Storage!SHBindToFolderIDListParentEx` at `0x18000a04b`
- `Windows.Storage!SHBindToFolderIDListParentEx` at `0x18000a04b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180009eab`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000a0cb`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180009eab`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000a0cb`
- `PROPSYS!PropVariantToUInt32WithDefault` at `0x180009e9d`
- `PROPSYS!PropVariantToUInt32WithDefault` at `0x180009e9d`
- `PROPSYS!PropVariantToInt32WithDefault` at `0x18000a133`
- `PROPSYS!PropVariantToInt32WithDefault` at `0x18000a133`

## pseudocode

```c

```
