# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::AddNewCell

- ea: `0x20a0`
- end: `0x20da`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::AddNewCell`
- size: `58`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x20e0`
- `0x28d0`
- `0x3390`

## callees

- `0x20a0`

## pseudocode

```c

```

## disassembly

```asm
0x20a0  ldarg.0
0x20a1  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlTableRow Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::m_currentRow
0x20a6  brtrue.s loc_20AA
0x20a8  ldnull
0x20a9  ret
0x20aa  ldstr    aTd// "td"
0x20af  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableCell::.ctor(string)
0x20b4  stloc.0
0x20b5  ldloc.0
0x20b6  ldstr    aTop// "top"
0x20bb  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableCell::set_VAlign(string)
0x20c0  ldarg.0
0x20c1  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlTableRow Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::m_currentRow
0x20c6  callvirt instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableCellCollection [System.Web]System.Web.UI.HtmlControls.HtmlTableRow::get_Cells()
0x20cb  ldloc.0
0x20cc  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableCellCollection::Add(class [System.Web]System.Web.UI.HtmlControls.HtmlTableCell)
0x20d1  ldarg.0
0x20d2  ldloc.0
0x20d3  stfld    class [System.Web]System.Web.UI.HtmlControls.HtmlTableCell Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::m_currentCell
0x20d8  ldloc.0
0x20d9  ret
```
