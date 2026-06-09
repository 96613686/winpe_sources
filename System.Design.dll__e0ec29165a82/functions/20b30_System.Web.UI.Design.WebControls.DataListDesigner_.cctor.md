# System.Web.UI.Design.WebControls.DataListDesigner::.cctor

- ea: `0x20b30`
- end: `0x20b9e`
- name: `System.Web.UI.Design.WebControls.DataListDesigner::.cctor`
- size: `110`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## string_xrefs

- `0x20b67`: `ItemTemplate`
- `0x20b7f`: `EditItemTemplate`
- `0x20b4c`: `HeaderTemplate`
- `0x20b54`: `FooterTemplate`
- `0x20b6f`: `AlternatingItemTemplate`
- `0x20b77`: `SelectedItemTemplate`
- `0x20b92`: `SeparatorTemplate`

## pseudocode

```c

```

## disassembly

```asm
0x20b30  ldstr    aDatalistdesign// "DATALISTDESIGNER"
0x20b35  ldstr    aEnableDatalist// "Enable DataList designer general purpos"...
0x20b3a  newobj   instance void [System]System.Diagnostics.TraceSwitch::.ctor(string, string)
0x20b3f  stsfld   class [System]System.Diagnostics.TraceSwitch System.Web.UI.Design.WebControls.DataListDesigner::DataListDesignerSwitch
0x20b44  ldc.i4.2
0x20b45  newarr   [mscorlib]System.String
0x20b4a  dup
0x20b4b  ldc.i4.0
0x20b4c  ldstr    aHeadertemplate// "HeaderTemplate"
0x20b51  stelem.ref
0x20b52  dup
0x20b53  ldc.i4.1
0x20b54  ldstr    aFootertemplate// "FooterTemplate"
0x20b59  stelem.ref
0x20b5a  stsfld   string[] System.Web.UI.Design.WebControls.DataListDesigner::HeaderFooterTemplateNames
0x20b5f  ldc.i4.4
0x20b60  newarr   [mscorlib]System.String
0x20b65  dup
0x20b66  ldc.i4.0
0x20b67  ldstr    aItemtemplate// "ItemTemplate"
0x20b6c  stelem.ref
0x20b6d  dup
0x20b6e  ldc.i4.1
0x20b6f  ldstr    aAlternatingite_0// "AlternatingItemTemplate"
0x20b74  stelem.ref
0x20b75  dup
0x20b76  ldc.i4.2
0x20b77  ldstr    aSelecteditemte// "SelectedItemTemplate"
0x20b7c  stelem.ref
0x20b7d  dup
0x20b7e  ldc.i4.3
0x20b7f  ldstr    aEdititemtempla// "EditItemTemplate"
0x20b84  stelem.ref
0x20b85  stsfld   string[] System.Web.UI.Design.WebControls.DataListDesigner::ItemTemplateNames
0x20b8a  ldc.i4.1
0x20b8b  newarr   [mscorlib]System.String
0x20b90  dup
0x20b91  ldc.i4.0
0x20b92  ldstr    aSeparatortempl// "SeparatorTemplate"
0x20b97  stelem.ref
0x20b98  stsfld   string[] System.Web.UI.Design.WebControls.DataListDesigner::SeparatorTemplateNames
0x20b9d  ret
```
