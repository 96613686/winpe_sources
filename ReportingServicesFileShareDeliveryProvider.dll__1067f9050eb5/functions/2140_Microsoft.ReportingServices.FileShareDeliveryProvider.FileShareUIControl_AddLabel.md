# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::AddLabel

- ea: `0x2140`
- end: `0x2164`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::AddLabel`
- size: `36`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x28d0`

## callees

- `0x21b0`

## pseudocode

```c

```

## disassembly

```asm
0x2140  newobj   instance void [System.Web]System.Web.UI.WebControls.Label::.ctor()
0x2145  stloc.0
0x2146  ldloc.0
0x2147  ldarg.1
0x2148  call     string [System.Web]System.Web.HttpUtility::HtmlEncode(string)
0x214d  callvirt instance void [System.Web]System.Web.UI.WebControls.Label::set_Text(string)
0x2152  ldarg.0
0x2153  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableCell Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::get_CurrentCell()
0x2158  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x215d  ldloc.0
0x215e  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x2163  ret
```
