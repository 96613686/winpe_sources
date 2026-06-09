# Microsoft.ReportingServices.Modeling.ColumnBinding::CheckBinding

- ea: `0xc510`
- end: `0xc647`
- name: `Microsoft.ReportingServices.Modeling.ColumnBinding::CheckBinding`
- size: `311`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callers

- `0xfc40`
- `0x111a0`

## callees

- `0xbce0`
- `0xbd10`
- `0xbd30`
- `0xbd70`
- `0xbda0`
- `0xbe90`
- `0xc410`
- `0xc510`
- `0xc650`
- `0xd990`
- `0xe510`
- `0x24ae0`
- `0x24b20`
- `0x24b40`
- `0x24b60`
- `0x25a90`
- `0x25b70`

## pseudocode

```c

```

## disassembly

```asm
0xc510  ldarg.3
0xc511  ldnull
0xc512  stind.ref
0xc513  ldarg.s  4
0xc515  ldc.i4.8
0xc516  stind.i1
0xc517  ldarg.0
0xc518  call     instance bool Microsoft.ReportingServices.Modeling.Binding::CheckBinding()
0xc51d  brtrue.s loc_C521
0xc51f  ldc.i4.0
0xc520  ret
0xc521  ldarg.2
0xc522  brfalse.s loc_C573
0xc524  ldarg.0
0xc525  ldfld    string Microsoft.ReportingServices.Modeling.ColumnBinding::m_tableName
0xc52a  callvirt instance int32 [mscorlib]System.String::get_Length()
0xc52f  brtrue.s loc_C546
0xc531  ldarg.1
0xc532  ldc.i4.s 0x35
0xc534  ldarg.1
0xc535  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0xc53a  call     string Microsoft.ReportingServices.Modeling.SRErrors::MissingColumnTableName(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName)
0xc53f  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0xc544  ldc.i4.0
0xc545  ret
0xc546  ldarg.0
0xc547  callvirt instance class Microsoft.ReportingServices.Modeling.DsvTable Microsoft.ReportingServices.Modeling.Binding::GetTable()
0xc54c  brtrue.s loc_C5B3
0xc54e  ldarg.1
0xc54f  ldc.i4.s 0x33
0xc551  ldstr    aColumn// "Column"
0xc556  ldarg.1
0xc557  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0xc55c  ldarg.0
0xc55d  ldfld    string Microsoft.ReportingServices.Modeling.ColumnBinding::m_tableName
0xc562  call     valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.Binding::GetTableDescriptor(string tableName)
0xc567  call     string Microsoft.ReportingServices.Modeling.SRErrors::InvalidBinding(string propertyName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor dsvItemTypeAndName)
0xc56c  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0xc571  ldc.i4.0
0xc572  ret
0xc573  ldarg.0
0xc574  call     instance class Microsoft.ReportingServices.Modeling.DsvTable Microsoft.ReportingServices.Modeling.Binding::GetParentTable()
0xc579  stloc.0
0xc57a  ldarg.0
0xc57b  callvirt instance class Microsoft.ReportingServices.Modeling.DsvTable Microsoft.ReportingServices.Modeling.Binding::GetTable()
0xc580  stloc.1
0xc581  ldloc.0
0xc582  brtrue.s loc_C586
0xc584  ldc.i4.0
0xc585  ret
0xc586  ldloc.1
0xc587  ldloc.0
0xc588  beq.s    loc_C5B3
0xc58a  ldarg.1
0xc58b  ldc.i4.s 0x36
0xc58d  ldarg.1
0xc58e  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0xc593  ldarg.0
0xc594  ldfld    string Microsoft.ReportingServices.Modeling.ColumnBinding::m_tableName
0xc599  call     valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.Binding::GetTableDescriptor(string tableName)
0xc59e  ldloc.0
0xc59f  callvirt instance string Microsoft.ReportingServices.Modeling.DsvItem::get_Name()
0xc5a4  call     valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.Binding::GetTableDescriptor(string tableName)
0xc5a9  call     string Microsoft.ReportingServices.Modeling.SRErrors::InvalidColumnTableName(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor columnTableTypeAndName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor entityTableTypeAndName)
0xc5ae  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0xc5b3  ldarg.3
0xc5b4  ldarg.0
0xc5b5  call     instance class Microsoft.ReportingServices.Modeling.DsvColumn Microsoft.ReportingServices.Modeling.ColumnBinding::GetColumn()
0xc5ba  stind.ref
0xc5bb  ldarg.3
0xc5bc  ldind.ref
0xc5bd  brtrue.s loc_C5DF
0xc5bf  ldarg.1
0xc5c0  ldc.i4.s 0x33
0xc5c2  ldstr    aColumn// "Column"
0xc5c7  ldarg.1
0xc5c8  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0xc5cd  ldarg.0
0xc5ce  call     instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ColumnBinding::GetColumnDescriptor()
0xc5d3  call     string Microsoft.ReportingServices.Modeling.SRErrors::InvalidBinding(string propertyName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor dsvItemTypeAndName)
0xc5d8  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0xc5dd  ldc.i4.0
0xc5de  ret
0xc5df  ldarg.2
0xc5e0  brtrue.s loc_C602
0xc5e2  ldc.i4.1
0xc5e3  newarr   Microsoft.ReportingServices.Modeling.DsvColumn
0xc5e8  dup
0xc5e9  ldc.i4.0
0xc5ea  ldarg.3
0xc5eb  ldind.ref
0xc5ec  stelem.ref
0xc5ed  ldarg.0
0xc5ee  call     instance class Microsoft.ReportingServices.Modeling.Binding Microsoft.ReportingServices.Modeling.Binding::GetParentBinding()
0xc5f3  ldarg.1
0xc5f4  ldstr    aColumn// "Column"
0xc5f9  call     bool Microsoft.ReportingServices.Modeling.Binding::CheckColumns(class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.Modeling.DsvColumn> columns, class Microsoft.ReportingServices.Modeling.Binding parentBinding, class Microsoft.ReportingServices.Modeling.CompilationContext ctx, string propertyName)
0xc5fe  brtrue.s loc_C602
0xc600  ldc.i4.0
0xc601  ret
0xc602  ldarg.3
0xc603  ldind.ref
0xc604  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.DataType> Microsoft.ReportingServices.Modeling.DsvColumn::get_ModelingDataType()
0xc609  stloc.2
0xc60a  ldloca.s 2
0xc60c  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.DataType>::get_HasValue()
0xc611  brtrue.s loc_C633
0xc613  ldarg.1
0xc614  ldc.i4.s 0x37
0xc616  ldstr    aColumn// "Column"
0xc61b  ldarg.1
0xc61c  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0xc621  ldarg.0
0xc622  call     instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ColumnBinding::GetColumnDescriptor()
0xc627  call     string Microsoft.ReportingServices.Modeling.SRErrors::InvalidColumnDataType(string propertyName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor columnTypeAndName)
0xc62c  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0xc631  ldc.i4.0
0xc632  ret
0xc633  ldarg.s  4
0xc635  ldarg.3
0xc636  ldind.ref
0xc637  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.DataType> Microsoft.ReportingServices.Modeling.DsvColumn::get_ModelingDataType()
0xc63c  stloc.2
0xc63d  ldloca.s 2
0xc63f  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.DataType>::get_Value()
0xc644  stind.i1
0xc645  ldc.i4.1
0xc646  ret
```
