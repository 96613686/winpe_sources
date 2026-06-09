# Microsoft.SharePoint.Spx.WebSite.ApplicationPages.ServiceHandler::get_CustomColorsXsdUrlRelative

- ea: `0xb10`
- end: `0xb25`
- name: `Microsoft.SharePoint.Spx.WebSite.ApplicationPages.ServiceHandler::get_CustomColorsXsdUrlRelative`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0xb50`

## string_xrefs

- `0xb1a`: `/wh/editor/CustomColorXMLVerify.xsd`

## pseudocode

```c

```

## disassembly

```asm
0xb10  ldstr    asc_20240// "/"
0xb15  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::get_ContextLayoutsFolder()
0xb1a  ldstr    aWhEditorCustom// "/wh/editor/CustomColorXMLVerify.xsd"
0xb1f  call     string [mscorlib]System.String::Concat(string, string, string)
0xb24  ret
```
