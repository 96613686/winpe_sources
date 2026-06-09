# System.Windows.Controls.DataGridTemplateColumn::RefreshCellContent

- ea: `0x15b9f0`
- end: `0x15ba4f`
- name: `System.Windows.Controls.DataGridTemplateColumn::RefreshCellContent`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x14fd60`
- `0x14fe50`
- `0x154200`
- `0x15b9f0`

## string_xrefs

- `0x15ba05`: `CellTemplate`
- `0x15ba13`: `CellTemplateSelector`
- `0x15ba24`: `CellEditingTemplate`
- `0x15ba32`: `CellEditingTemplateSelector`

## pseudocode

```c

```

## disassembly

```asm
0x15b9f0  ldarg.1
0x15b9f1  isinst   System.Windows.Controls.DataGridCell
0x15b9f6  stloc.0
0x15b9f7  ldloc.0
0x15b9f8  brfalse.s loc_15BA46
0x15b9fa  ldloc.0
0x15b9fb  callvirt instance bool System.Windows.Controls.DataGridCell::get_IsEditing()
0x15ba00  stloc.1
0x15ba01  ldloc.1
0x15ba02  brtrue.s loc_15BA20
0x15ba04  ldarg.2
0x15ba05  ldstr    aCelltemplate// "CellTemplate"
0x15ba0a  ldc.i4.4
0x15ba0b  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x15ba10  brfalse.s loc_15BA3F
0x15ba12  ldarg.2
0x15ba13  ldstr    aCelltemplatese// "CellTemplateSelector"
0x15ba18  ldc.i4.4
0x15ba19  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x15ba1e  brfalse.s loc_15BA3F
0x15ba20  ldloc.1
0x15ba21  brfalse.s loc_15BA46
0x15ba23  ldarg.2
0x15ba24  ldstr    aCelleditingtem// "CellEditingTemplate"
0x15ba29  ldc.i4.4
0x15ba2a  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x15ba2f  brfalse.s loc_15BA3F
0x15ba31  ldarg.2
0x15ba32  ldstr    aCelleditingtem_0// "CellEditingTemplateSelector"
0x15ba37  ldc.i4.4
0x15ba38  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x15ba3d  brtrue.s loc_15BA46
0x15ba3f  ldloc.0
0x15ba40  callvirt instance void System.Windows.Controls.DataGridCell::BuildVisualTree()
0x15ba45  ret
0x15ba46  ldarg.0
0x15ba47  ldarg.1
0x15ba48  ldarg.2
0x15ba49  call     instance void System.Windows.Controls.DataGridColumn::RefreshCellContent(class System.Windows.FrameworkElement element, string propertyName)
0x15ba4e  ret
```
