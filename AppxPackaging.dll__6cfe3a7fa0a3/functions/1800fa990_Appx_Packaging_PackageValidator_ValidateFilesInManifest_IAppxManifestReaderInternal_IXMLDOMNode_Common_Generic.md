# Appx::Packaging::PackageValidator::ValidateFilesInManifest(IAppxManifestReaderInternal *,IXMLDOMNode *,Common::GenericMap<ushort const *,ushort const *> const &,Appx::Packaging::Manifest::FileNameTable const *,ulong,bool)

- ea: `0x1800fa990`
- end: `0x1800fae75`
- name: `?ValidateFilesInManifest@PackageValidator@Packaging@Appx@@CAJPEAUIAppxManifestReaderInternal@@PEAUIXMLDOMNode@@AEBV?$GenericMap@PEBGPEBG@Common@@PEBUFileNameTable@Manifest@23@K_N@Z`
- size: `1253`
- prototype: `__int64(__int64, struct IXMLDOMNode *, struct _RTL_AVL_TABLE *, ...)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800f9dcc`

## callees

- `0x180005eb8`
- `0x1800133fc`
- `0x18004bd74`
- `0x1800538c8`
- `0x180074678`
- `0x180094a38`
- `0x1800992c4`
- `0x1800992d0`
- `0x1800ac590`
- `0x1800ac600`
- `0x1800f9aac`
- `0x1800f9c84`
- `0x1800fa990`
- `0x1800fb678`
- `0x1800fec2c`
- `0x180106010`

## import_xrefs

- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x1800faa07`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x1800faaff`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x1800faa07`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x1800faaff`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fad9a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fade7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fad9a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fade7`
- `OLEAUT32!__imp_SysStringLen` at `0x1800facc9`
- `OLEAUT32!__imp_SysStringLen` at `0x1800facc9`

## string_xrefs

- `0x1800fad32`: `Manifest validation error: Line %1!d!, Column %2!d!, Reason: The file name "%3" declared for element "%4" doesn't exist in the package.\n`
- `0x1800fad70`: `Manifest validation error: Line %1!d!, Column %2!d!, Reason: The folder name "%3" declared for element "%4" doesn't exist in the package.\n`
- `0x1800fae14`: `(GetXmlNodes(manifestRoot, fileXPaths[i].xpathToElement, &nodeList, &numNodes))`
- `0x1800fadd5`: `(GetXmlNodeText(node.Get(), fileXPaths[i].attributeName, &fileName))`

## pseudocode

```c

```
