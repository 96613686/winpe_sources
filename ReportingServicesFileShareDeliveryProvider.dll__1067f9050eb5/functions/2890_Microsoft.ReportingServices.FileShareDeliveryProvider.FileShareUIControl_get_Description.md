# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::get_Description

- ea: `0x2890`
- end: `0x28ac`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::get_Description`
- size: `28`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x3bf0`

## pseudocode

```c

```

## disassembly

```asm
0x2890  ldarg.0
0x2891  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_txtPath
0x2896  callvirt instance string [System.Web]System.Web.UI.WebControls.TextBox::get_Text()
0x289b  ldarg.0
0x289c  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_txtFileName
0x28a1  callvirt instance string [System.Web]System.Web.UI.WebControls.TextBox::get_Text()
0x28a6  call     string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::SubDescription(string path, string fileName)
0x28ab  ret
```
