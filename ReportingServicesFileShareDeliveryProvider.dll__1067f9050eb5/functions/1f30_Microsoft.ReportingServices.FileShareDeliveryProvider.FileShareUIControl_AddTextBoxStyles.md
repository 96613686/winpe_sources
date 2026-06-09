# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::AddTextBoxStyles

- ea: `0x1f30`
- end: `0x1f5b`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::AddTextBoxStyles`
- size: `43`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x28d0`

## pseudocode

```c

```

## disassembly

```asm
0x1f30  ldarg.0
0x1f31  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.WebControls.WebControl::get_Style()
0x1f36  ldstr    aFontFamily// "font-family"
0x1f3b  ldstr    aVerdanaSansSer// "Verdana, Sans-Serif"
0x1f40  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::Add(string, string)
0x1f45  ldarg.0
0x1f46  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.WebControls.WebControl::get_Style()
0x1f4b  ldstr    aFontSize// "font-size"
0x1f50  ldstr    aXSmall// "x-small"
0x1f55  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::Add(string, string)
0x1f5a  ret
```
