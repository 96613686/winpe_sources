# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::PopTable

- ea: `0x2000`
- end: `0x2064`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::PopTable`
- size: `100`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x28d0`
- `0x3390`

## callees

- `0x2000`

## pseudocode

```c

```

## disassembly

```asm
0x2000  ldarg.0
0x2001  ldfld    class [mscorlib]System.Collections.Stack Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::m_tableStack
0x2006  callvirt instance object [mscorlib]System.Collections.Stack::Pop()
0x200b  castclass [System.Web]System.Web.UI.HtmlControls.HtmlTable
0x2010  ldarg.0
0x2011  ldarg.0
0x2012  ldfld    class [mscorlib]System.Collections.Stack Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::m_tableStack
0x2017  callvirt instance int32 [mscorlib]System.Collections.Stack::get_Count()
0x201c  ldc.i4.0
0x201d  bgt.s    loc_2022
0x201f  ldnull
0x2020  br.s     loc_2032
0x2022  ldarg.0
0x2023  ldfld    class [mscorlib]System.Collections.Stack Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::m_tableStack
0x2028  callvirt instance object [mscorlib]System.Collections.Stack::Peek()
0x202d  castclass [System.Web]System.Web.UI.HtmlControls.HtmlTable
0x2032  stfld    class [System.Web]System.Web.UI.HtmlControls.HtmlTable Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::m_currentTable
0x2037  ldarg.0
0x2038  ldarg.0
0x2039  ldfld    class [mscorlib]System.Collections.Stack Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::m_rowStack
0x203e  callvirt instance object [mscorlib]System.Collections.Stack::Pop()
0x2043  castclass [System.Web]System.Web.UI.HtmlControls.HtmlTableRow
0x2048  stfld    class [System.Web]System.Web.UI.HtmlControls.HtmlTableRow Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::m_currentRow
0x204d  ldarg.0
0x204e  ldarg.0
0x204f  ldfld    class [mscorlib]System.Collections.Stack Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::m_cellStack
0x2054  callvirt instance object [mscorlib]System.Collections.Stack::Pop()
0x2059  castclass [System.Web]System.Web.UI.HtmlControls.HtmlTableCell
0x205e  stfld    class [System.Web]System.Web.UI.HtmlControls.HtmlTableCell Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::m_currentCell
0x2063  ret
```
