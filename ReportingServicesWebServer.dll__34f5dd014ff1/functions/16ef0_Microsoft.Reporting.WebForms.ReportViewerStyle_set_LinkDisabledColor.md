# Microsoft.Reporting.WebForms.ReportViewerStyle::set_LinkDisabledColor

- ea: `0x16ef0`
- end: `0x16f07`
- name: `Microsoft.Reporting.WebForms.ReportViewerStyle::set_LinkDisabledColor`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x16ef6`: `LinkDisabledColor`

## pseudocode

```c

```

## disassembly

```asm
0x16ef0  ldarg.0
0x16ef1  call     instance class [System.Web]System.Web.UI.StateBag [System.Web]System.Web.UI.WebControls.Style::get_ViewState()
0x16ef6  ldstr    aLinkdisabledco// "LinkDisabledColor"
0x16efb  ldarg.1
0x16efc  box      [System.Drawing]System.Drawing.Color
0x16f01  callvirt instance void [System.Web]System.Web.UI.StateBag::set_Item(string, object)
0x16f06  ret
```
