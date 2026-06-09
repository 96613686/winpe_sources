# Microsoft.Reporting.WebForms.ReportViewerStyle::get_LinkDisabledColor

- ea: `0x16ec0`
- end: `0x16ee1`
- name: `Microsoft.Reporting.WebForms.ReportViewerStyle::get_LinkDisabledColor`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x16ec0`

## string_xrefs

- `0x16ec6`: `LinkDisabledColor`

## pseudocode

```c

```

## disassembly

```asm
0x16ec0  ldarg.0
0x16ec1  call     instance class [System.Web]System.Web.UI.StateBag [System.Web]System.Web.UI.WebControls.Style::get_ViewState()
0x16ec6  ldstr    aLinkdisabledco// "LinkDisabledColor"
0x16ecb  callvirt instance object [System.Web]System.Web.UI.StateBag::get_Item(string)
0x16ed0  stloc.0
0x16ed1  ldloc.0
0x16ed2  brtrue.s loc_16EDA
0x16ed4  ldsfld   valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.Color::Empty
0x16ed9  ret
0x16eda  ldloc.0
0x16edb  unbox.any [System.Drawing]System.Drawing.Color
0x16ee0  ret
```
