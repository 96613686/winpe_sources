# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::AddNewRow

- ea: `0x2070`
- end: `0x209a`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::AddNewRow`
- size: `42`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x28d0`
- `0x3390`

## callees

- `0x2070`

## pseudocode

```c

```

## disassembly

```asm
0x2070  ldarg.0
0x2071  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlTable Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::m_currentTable
0x2076  brtrue.s loc_207A
0x2078  ldnull
0x2079  ret
0x207a  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableRow::.ctor()
0x207f  stloc.0
0x2080  ldarg.0
0x2081  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlTable Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::m_currentTable
0x2086  callvirt instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableRowCollection [System.Web]System.Web.UI.HtmlControls.HtmlTable::get_Rows()
0x208b  ldloc.0
0x208c  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableRowCollection::Add(class [System.Web]System.Web.UI.HtmlControls.HtmlTableRow)
0x2091  ldarg.0
0x2092  ldloc.0
0x2093  stfld    class [System.Web]System.Web.UI.HtmlControls.HtmlTableRow Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::m_currentRow
0x2098  ldloc.0
0x2099  ret
```
