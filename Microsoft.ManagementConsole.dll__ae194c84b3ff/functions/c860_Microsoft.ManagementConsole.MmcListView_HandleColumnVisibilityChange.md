# Microsoft.ManagementConsole.MmcListView::HandleColumnVisibilityChange

- ea: `0xc860`
- end: `0xc945`
- name: `Microsoft.ManagementConsole.MmcListView::HandleColumnVisibilityChange`
- size: `229`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0xc480`

## callees

- `0x9790`
- `0xb320`
- `0xc1b0`
- `0xc860`
- `0xcb40`
- `0xcef0`

## string_xrefs

- `0xc886`: `Column id {0} in View {1} not found. May have been deleted.`
- `0xc8f5`: `Column id {0} in View {1} not found. May have been deleted.`

## pseudocode

```c

```

## disassembly

```asm
0xc860  ldarg.1
0xc861  stloc.s  4
0xc863  ldc.i4.0
0xc864  stloc.s  5
0xc866  br.s     loc_C8C7
0xc868  ldloc.s  4
0xc86a  ldloc.s  5
0xc86c  ldelem.i4
0xc86d  stloc.0
0xc86e  ldarg.0
0xc86f  call     instance class Microsoft.ManagementConsole.MmcListViewColumnCollection Microsoft.ManagementConsole.MmcListView::get_Columns()
0xc874  ldloc.0
0xc875  callvirt instance class Microsoft.ManagementConsole.MmcListViewColumn Microsoft.ManagementConsole.MmcListViewColumnCollection::GetColumn(int32 id)
0xc87a  stloc.1
0xc87b  ldloc.1
0xc87c  brtrue.s loc_C8B5
0xc87e  call     class [System]System.Diagnostics.TraceSource [MMCFxCommon]Microsoft.ManagementConsole.TraceSources::get_ExecutiveSource()
0xc883  ldc.i4.4
0xc884  ldc.i4.s 0xC
0xc886  ldstr    aColumnId0InVie// "Column id {0} in View {1} not found. Ma"...
0xc88b  ldc.i4.2
0xc88c  newarr   [mscorlib]System.Object
0xc891  stloc.s  6
0xc893  ldloc.s  6
0xc895  ldc.i4.0
0xc896  ldloc.0
0xc897  box      [mscorlib]System.Int32
0xc89c  stelem.ref
0xc89d  ldloc.s  6
0xc89f  ldc.i4.1
0xc8a0  ldarg.0
0xc8a1  call     instance int32 Microsoft.ManagementConsole.View::get_ViewInstanceId()
0xc8a6  box      [mscorlib]System.Int32
0xc8ab  stelem.ref
0xc8ac  ldloc.s  6
0xc8ae  callvirt instance void [System]System.Diagnostics.TraceSource::TraceEvent(valuetype [System]System.Diagnostics.TraceEventType, int32, string, object[])
0xc8b3  br.s     loc_C8C1
0xc8b5  ldloc.1
0xc8b6  callvirt instance class [MMCFxCommon]Microsoft.ManagementConsole.Internal.ColumnData Microsoft.ManagementConsole.MmcListViewColumn::get_Data()
0xc8bb  ldc.i4.1
0xc8bc  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.ColumnData::set_Visible(bool)
0xc8c1  ldloc.s  5
0xc8c3  ldc.i4.1
0xc8c4  add
0xc8c5  stloc.s  5
0xc8c7  ldloc.s  5
0xc8c9  ldloc.s  4
0xc8cb  ldlen
0xc8cc  conv.i4
0xc8cd  blt.s    loc_C868
0xc8cf  ldarg.2
0xc8d0  stloc.s  7
0xc8d2  ldc.i4.0
0xc8d3  stloc.s  8
0xc8d5  br.s     loc_C936
0xc8d7  ldloc.s  7
0xc8d9  ldloc.s  8
0xc8db  ldelem.i4
0xc8dc  stloc.2
0xc8dd  ldarg.0
0xc8de  call     instance class Microsoft.ManagementConsole.MmcListViewColumnCollection Microsoft.ManagementConsole.MmcListView::get_Columns()
0xc8e3  ldloc.2
0xc8e4  callvirt instance class Microsoft.ManagementConsole.MmcListViewColumn Microsoft.ManagementConsole.MmcListViewColumnCollection::GetColumn(int32 id)
0xc8e9  stloc.3
0xc8ea  ldloc.3
0xc8eb  brtrue.s loc_C924
0xc8ed  call     class [System]System.Diagnostics.TraceSource [MMCFxCommon]Microsoft.ManagementConsole.TraceSources::get_ExecutiveSource()
0xc8f2  ldc.i4.4
0xc8f3  ldc.i4.s 0xC
0xc8f5  ldstr    aColumnId0InVie// "Column id {0} in View {1} not found. Ma"...
0xc8fa  ldc.i4.2
0xc8fb  newarr   [mscorlib]System.Object
0xc900  stloc.s  9
0xc902  ldloc.s  9
0xc904  ldc.i4.0
0xc905  ldloc.2
0xc906  box      [mscorlib]System.Int32
0xc90b  stelem.ref
0xc90c  ldloc.s  9
0xc90e  ldc.i4.1
0xc90f  ldarg.0
0xc910  call     instance int32 Microsoft.ManagementConsole.View::get_ViewInstanceId()
0xc915  box      [mscorlib]System.Int32
0xc91a  stelem.ref
0xc91b  ldloc.s  9
0xc91d  callvirt instance void [System]System.Diagnostics.TraceSource::TraceEvent(valuetype [System]System.Diagnostics.TraceEventType, int32, string, object[])
0xc922  br.s     loc_C930
0xc924  ldloc.3
0xc925  callvirt instance class [MMCFxCommon]Microsoft.ManagementConsole.Internal.ColumnData Microsoft.ManagementConsole.MmcListViewColumn::get_Data()
0xc92a  ldc.i4.0
0xc92b  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.ColumnData::set_Visible(bool)
0xc930  ldloc.s  8
0xc932  ldc.i4.1
0xc933  add
0xc934  stloc.s  8
0xc936  ldloc.s  8
0xc938  ldloc.s  7
0xc93a  ldlen
0xc93b  conv.i4
0xc93c  blt.s    loc_C8D7
0xc93e  ldarg.0
0xc93f  callvirt instance void Microsoft.ManagementConsole.MmcListView::OnColumnVisibilityChanged()
0xc944  ret
```
