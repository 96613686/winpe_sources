# Appx::Packaging::PackageValidator::ValidateFileTypeAssociationsExtension(IAppxManifestReaderInternal *,IXMLDOMNode *)

- ea: `0x1800fa538`
- end: `0x1800fa987`
- name: `?ValidateFileTypeAssociationsExtension@PackageValidator@Packaging@Appx@@CAJPEAUIAppxManifestReaderInternal@@PEAUIXMLDOMNode@@@Z`
- size: `1103`
- prototype: `static int(struct IAppxManifestReaderInternal *, struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x1800f9dcc`

## callees

- `0x180005eb8`
- `0x1800446d0`
- `0x180094a38`
- `0x1800f9aac`
- `0x1800f9c84`
- `0x1800fa538`
- `0x1800fec2c`
- `0x180106010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800fa8b9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fa8ca`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fa900`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fa911`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fa8b9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fa8ca`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fa900`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fa911`

## string_xrefs

- `0x1800fa704`: `*[local-name()='Applications']/*[local-name()='Application']/*[local-name()='Extensions']/*[local-name()='Extension']/*[local-name()='FileTypeAssociation']/*[local-name()='SupportedFileTypes']/*[local-name()='FileType']`
- `0x1800fa894`: `Manifest validation error: Line %1!d!, Column %2!d!, Reason: Applications can't register for a file type association with the "%3" content type.\n`
- `0x1800fa7f1`: `Manifest validation error: Line %1!d!, Column %2!d!, Reason: Applications can't register for the "%3" file type association.\n`
- `0x1800fa8ed`: `(GetXmlNodeText(node.Get(), Manifest::AttributeNameWithoutPrefix::ContentType, &contentType))`
- `0x1800fa719`: `(GetXmlNodes(manifestRoot, AssociationsXPath, &nodeList, &numNodes))`

## pseudocode

```c

```
