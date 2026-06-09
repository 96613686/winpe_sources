# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::PushNewTable

- ea: `0x1f60`
- end: `0x1fb7`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::PushNewTable`
- size: `87`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x28d0`
- `0x3390`

## callees

- `0x1f60`
- `0x1fc0`
- `0x2190`
- `0x21b0`

## pseudocode

```c

```

## disassembly

```asm
0x1f60  ldarg.0
0x1f61  ldfld    class [mscorlib]System.Collections.Stack Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::m_cellStack
0x1f66  ldarg.0
0x1f67  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableCell Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::get_CurrentCell()
0x1f6c  callvirt instance void [mscorlib]System.Collections.Stack::Push(object)
0x1f71  ldarg.0
0x1f72  ldfld    class [mscorlib]System.Collections.Stack Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::m_rowStack
0x1f77  ldarg.0
0x1f78  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableRow Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::get_CurrentRow()
0x1f7d  callvirt instance void [mscorlib]System.Collections.Stack::Push(object)
0x1f82  ldarg.0
0x1f83  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlTable Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::CreateTable()
0x1f88  stloc.0
0x1f89  ldarg.0
0x1f8a  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlTableCell Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::m_currentCell
0x1f8f  brfalse.s loc_1FA2
0x1f91  ldarg.0
0x1f92  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlTableCell Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::m_currentCell
0x1f97  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x1f9c  ldloc.0
0x1f9d  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x1fa2  ldarg.0
0x1fa3  ldfld    class [mscorlib]System.Collections.Stack Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::m_tableStack
0x1fa8  ldloc.0
0x1fa9  callvirt instance void [mscorlib]System.Collections.Stack::Push(object)
0x1fae  ldarg.0
0x1faf  ldloc.0
0x1fb0  stfld    class [System.Web]System.Web.UI.HtmlControls.HtmlTable Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::m_currentTable
0x1fb5  ldloc.0
0x1fb6  ret
```
