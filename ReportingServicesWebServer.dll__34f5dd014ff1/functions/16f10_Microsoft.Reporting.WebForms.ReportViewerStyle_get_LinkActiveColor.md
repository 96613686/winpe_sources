# Microsoft.Reporting.WebForms.ReportViewerStyle::get_LinkActiveColor

- ea: `0x16f10`
- end: `0x16f31`
- name: `Microsoft.Reporting.WebForms.ReportViewerStyle::get_LinkActiveColor`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x16f10`

## string_xrefs

- `0x16f16`: `LinkActiveColor`

## pseudocode

```c

```

## disassembly

```asm
0x16f10  ldarg.0
0x16f11  call     instance class [System.Web]System.Web.UI.StateBag [System.Web]System.Web.UI.WebControls.Style::get_ViewState()
0x16f16  ldstr    aLinkactivecolo// "LinkActiveColor"
0x16f1b  callvirt instance object [System.Web]System.Web.UI.StateBag::get_Item(string)
0x16f20  stloc.0
0x16f21  ldloc.0
0x16f22  brtrue.s loc_16F2A
0x16f24  ldsfld   valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.Color::Empty
0x16f29  ret
0x16f2a  ldloc.0
0x16f2b  unbox.any [System.Drawing]System.Drawing.Color
0x16f30  ret
```
