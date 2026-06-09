# Appx::Packaging::PackageValidator::ValidateComposedFilesInManifest(IAppxManifestReaderInternal *,IXMLDOMNode *,Common::GenericMap<ushort const *,ushort const *> const &,Appx::Packaging::Manifest::ComposedFileNameTable const *,ulong,bool)

- ea: `0x1800fa138`
- end: `0x1800fa52f`
- name: `?ValidateComposedFilesInManifest@PackageValidator@Packaging@Appx@@CAJPEAUIAppxManifestReaderInternal@@PEAUIXMLDOMNode@@AEBV?$GenericMap@PEBGPEBG@Common@@PEBUComposedFileNameTable@Manifest@23@K_N@Z`
- size: `1015`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800f9dcc`

## callees

- `0x180005eb8`
- `0x18004bd74`
- `0x1800538c8`
- `0x180092c64`
- `0x180094a38`
- `0x1800992c4`
- `0x1800f9aac`
- `0x1800f9c84`
- `0x1800fa138`
- `0x1800fec2c`
- `0x180106010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800fa249`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fa3c9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fa3f4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fa46b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fa4c9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fa249`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fa3c9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fa3f4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fa46b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fa4c9`
- `OLEAUT32!__imp_SysStringLen` at `0x1800fa339`
- `OLEAUT32!__imp_SysStringLen` at `0x1800fa339`

## string_xrefs

- `0x1800fa3aa`: `Manifest validation error: Line %1!d!, Column %2!d!, Reason: The file name "%3" declared for element "%4" doesn't exist in the package.\n`
- `0x1800fa4f6`: `(GetXmlNodes(manifestRoot, composedFileXPaths[i].xpathFolderElement, &folderNodeList, &numFolderNodes))`
- `0x1800fa459`: `(GetXmlNodeText(fileNode.Get(), composedFileXPaths[i].attributeFileName, &fileName))`
- `0x1800fa498`: `(GetXmlNodes(folderNode.Get(), composedFileXPaths[i].xpathFileElement, &fileNodeList, &numFileNodes))`
- `0x1800fa4b7`: `(GetXmlNodeText(folderNode.Get(), composedFileXPaths[i].attributeFolderName, &folderValue))`
- `0x1800fa438`: `(StringHelper::CombinePath(folderValue, fileName, &fullFileName))`

## pseudocode

```c

```
