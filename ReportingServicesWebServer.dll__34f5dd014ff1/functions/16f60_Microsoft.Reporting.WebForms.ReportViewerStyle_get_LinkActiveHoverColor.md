# Microsoft.Reporting.WebForms.ReportViewerStyle::get_LinkActiveHoverColor

- ea: `0x16f60`
- end: `0x16f81`
- name: `Microsoft.Reporting.WebForms.ReportViewerStyle::get_LinkActiveHoverColor`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x16f60`

## string_xrefs

- `0x16f66`: `LinkActiveHoverColor`

## pseudocode

```c

```

## disassembly

```asm
0x16f60  ldarg.0
0x16f61  call     instance class [System.Web]System.Web.UI.StateBag [System.Web]System.Web.UI.WebControls.Style::get_ViewState()
0x16f66  ldstr    aLinkactivehove// "LinkActiveHoverColor"
0x16f6b  callvirt instance object [System.Web]System.Web.UI.StateBag::get_Item(string)
0x16f70  stloc.0
0x16f71  ldloc.0
0x16f72  brtrue.s loc_16F7A
0x16f74  ldsfld   valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.Color::Empty
0x16f79  ret
0x16f7a  ldloc.0
0x16f7b  unbox.any [System.Drawing]System.Drawing.Color
0x16f80  ret
```
