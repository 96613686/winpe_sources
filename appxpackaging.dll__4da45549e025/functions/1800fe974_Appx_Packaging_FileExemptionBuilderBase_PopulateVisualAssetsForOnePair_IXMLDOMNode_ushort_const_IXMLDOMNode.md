# Appx::Packaging::FileExemptionBuilderBase::PopulateVisualAssetsForOnePair(IXMLDOMNode *,ushort const *,IXMLDOMNode *)

- ea: `0x1800fe974`
- end: `0x1800febf5`
- name: `?PopulateVisualAssetsForOnePair@FileExemptionBuilderBase@Packaging@Appx@@AEAAJPEAUIXMLDOMNode@@PEBG0@Z`
- size: `641`
- prototype: `__int64 __fastcall(Appx::Packaging::FileExemptionBuilderBase *__hidden this, struct IXMLDOMNode *, const unsigned __int16 *, struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800fd708`

## callees

- `0x180005eb8`
- `0x1800133fc`
- `0x180094280`
- `0x1800944f0`
- `0x180094a38`
- `0x180094a70`
- `0x1800fe974`
- `0x180106010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800fe9bb`
- `OLEAUT32!__imp_SysAllocString` at `0x1800fe9bb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fead9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800feb09`
- `OLEAUT32!__imp_SysFreeString` at `0x1800feb41`
- `OLEAUT32!__imp_SysFreeString` at `0x1800feb9b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800febca`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fead9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800feb09`
- `OLEAUT32!__imp_SysFreeString` at `0x1800feb41`
- `OLEAUT32!__imp_SysFreeString` at `0x1800feb9b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800febca`

## string_xrefs

- `0x1800feb79`: `manifestRootNode->selectNodes(query, &list)`
- `0x1800feb1e`: `AddExemptedFilePathIfNotExists(packageName, resourcePath)`
- `0x1800feac1`: `PopulateVisualAssetsByResolving(resourcePath, packageName, resourcesPriDumpNode)`
- `0x1800feb27`: `currentNode->get_text(&manifestResourceReference)`

## pseudocode

```c

```
