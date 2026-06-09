# Microsoft.Reporting.WebForms.ReportViewerStyle::set_LinkActiveColor

- ea: `0x16f40`
- end: `0x16f57`
- name: `Microsoft.Reporting.WebForms.ReportViewerStyle::set_LinkActiveColor`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x16f46`: `LinkActiveColor`

## pseudocode

```c

```

## disassembly

```asm
0x16f40  ldarg.0
0x16f41  call     instance class [System.Web]System.Web.UI.StateBag [System.Web]System.Web.UI.WebControls.Style::get_ViewState()
0x16f46  ldstr    aLinkactivecolo// "LinkActiveColor"
0x16f4b  ldarg.1
0x16f4c  box      [System.Drawing]System.Drawing.Color
0x16f51  callvirt instance void [System.Web]System.Web.UI.StateBag::set_Item(string, object)
0x16f56  ret
```
