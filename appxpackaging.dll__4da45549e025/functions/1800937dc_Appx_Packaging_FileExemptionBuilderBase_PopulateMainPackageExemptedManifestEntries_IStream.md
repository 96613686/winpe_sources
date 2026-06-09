# Appx::Packaging::FileExemptionBuilderBase::PopulateMainPackageExemptedManifestEntries(IStream *)

- ea: `0x1800937dc`
- end: `0x180093b97`
- name: `?PopulateMainPackageExemptedManifestEntries@FileExemptionBuilderBase@Packaging@Appx@@AEAAJPEAUIStream@@@Z`
- size: `955`
- prototype: `__int64 __fastcall(Appx::Packaging::FileExemptionBuilderBase *__hidden this, struct IStream *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x1800fe690`

## callees

- `0x1800059f0`
- `0x180005eb8`
- `0x1800133fc`
- `0x18004f810`
- `0x180083668`
- `0x1800937dc`
- `0x180094a38`
- `0x180094a70`
- `0x1800992c4`
- `0x1800992d0`
- `0x1800f8f6c`
- `0x1800fe050`
- `0x180106010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800938ba`
- `OLEAUT32!__imp_SysAllocString` at `0x1800938ba`
- `OLEAUT32!__imp_SysFreeString` at `0x1800939f2`
- `OLEAUT32!__imp_SysFreeString` at `0x180093a20`
- `OLEAUT32!__imp_SysFreeString` at `0x180093a5c`
- `OLEAUT32!__imp_SysFreeString` at `0x180093a7d`
- `OLEAUT32!__imp_SysFreeString` at `0x180093ad9`
- `OLEAUT32!__imp_SysFreeString` at `0x180093b33`
- `OLEAUT32!__imp_SysFreeString` at `0x180093b62`
- `OLEAUT32!__imp_SysFreeString` at `0x1800939f2`
- `OLEAUT32!__imp_SysFreeString` at `0x180093a20`
- `OLEAUT32!__imp_SysFreeString` at `0x180093a5c`
- `OLEAUT32!__imp_SysFreeString` at `0x180093a7d`
- `OLEAUT32!__imp_SysFreeString` at `0x180093ad9`
- `OLEAUT32!__imp_SysFreeString` at `0x180093b33`
- `OLEAUT32!__imp_SysFreeString` at `0x180093b62`

## string_xrefs

- `0x180093a38`: `m_mainPackageExemptedManifestEntries->Add(exemptedManifestEntryValue.GetChars())`
- `0x180093a93`: `exemptedManifestEntryValue.SetValueFromString(manifestResourceReference.Value())`
- `0x180093885`: `InitializeManifestReaderDom(manifestStream, &manifestRootNode)`
- `0x180093b11`: `manifestRootNode->selectNodes(query, &list)`
- `0x180093abf`: `currentNode->get_text(&manifestResourceReference)`
- `0x180093ab6`: `StringHelper::FindStringInList( *m_mainPackageExemptedManifestEntries, manifestResourceReference.Value(), &foundExemptedEntry)`
- `0x18009384d`: `(m_mainPackageExemptedManifestEntries) == NULL`

## pseudocode

```c

```
