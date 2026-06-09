# Microsoft.Reporting.WebForms.ReportViewerStyle::set_LinkActiveHoverColor

- ea: `0x16f90`
- end: `0x16fa7`
- name: `Microsoft.Reporting.WebForms.ReportViewerStyle::set_LinkActiveHoverColor`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x16f96`: `LinkActiveHoverColor`

## pseudocode

```c

```

## disassembly

```asm
0x16f90  ldarg.0
0x16f91  call     instance class [System.Web]System.Web.UI.StateBag [System.Web]System.Web.UI.WebControls.Style::get_ViewState()
0x16f96  ldstr    aLinkactivehove// "LinkActiveHoverColor"
0x16f9b  ldarg.1
0x16f9c  box      [System.Drawing]System.Drawing.Color
0x16fa1  callvirt instance void [System.Web]System.Web.UI.StateBag::set_Item(string, object)
0x16fa6  ret
```
