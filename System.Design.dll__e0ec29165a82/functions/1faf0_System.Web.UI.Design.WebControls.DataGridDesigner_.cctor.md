# System.Web.UI.Design.WebControls.DataGridDesigner::.cctor

- ea: `0x1faf0`
- end: `0x1fb30`
- name: `System.Web.UI.Design.WebControls.DataGridDesigner::.cctor`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## string_xrefs

- `0x1fb0c`: `ItemTemplate`
- `0x1fb14`: `EditItemTemplate`
- `0x1fb1c`: `HeaderTemplate`
- `0x1fb24`: `FooterTemplate`

## pseudocode

```c

```

## disassembly

```asm
0x1faf0  ldstr    aDatagriddesign// "DATAGRIDDESIGNER"
0x1faf5  ldstr    aEnableDatagrid// "Enable DataGrid designer general purpos"...
0x1fafa  newobj   instance void [System]System.Diagnostics.TraceSwitch::.ctor(string, string)
0x1faff  stsfld   class [System]System.Diagnostics.TraceSwitch System.Web.UI.Design.WebControls.DataGridDesigner::DataGridDesignerSwitch
0x1fb04  ldc.i4.4
0x1fb05  newarr   [mscorlib]System.String
0x1fb0a  dup
0x1fb0b  ldc.i4.0
0x1fb0c  ldstr    aItemtemplate// "ItemTemplate"
0x1fb11  stelem.ref
0x1fb12  dup
0x1fb13  ldc.i4.1
0x1fb14  ldstr    aEdititemtempla// "EditItemTemplate"
0x1fb19  stelem.ref
0x1fb1a  dup
0x1fb1b  ldc.i4.2
0x1fb1c  ldstr    aHeadertemplate// "HeaderTemplate"
0x1fb21  stelem.ref
0x1fb22  dup
0x1fb23  ldc.i4.3
0x1fb24  ldstr    aFootertemplate// "FooterTemplate"
0x1fb29  stelem.ref
0x1fb2a  stsfld   string[] System.Web.UI.Design.WebControls.DataGridDesigner::ColumnTemplateNames
0x1fb2f  ret
```
