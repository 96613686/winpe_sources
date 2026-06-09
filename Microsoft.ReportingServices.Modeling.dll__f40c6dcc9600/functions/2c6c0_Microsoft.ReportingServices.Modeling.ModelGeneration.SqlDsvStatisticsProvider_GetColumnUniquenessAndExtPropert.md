# Microsoft.ReportingServices.Modeling.ModelGeneration.SqlDsvStatisticsProvider::GetColumnUniquenessAndExtProperties

- ea: `0x2c6c0`
- end: `0x2c907`
- name: `Microsoft.ReportingServices.Modeling.ModelGeneration.SqlDsvStatisticsProvider::GetColumnUniquenessAndExtProperties`
- size: `583`
- prototype: ``
- caller_count: `1`
- callee_count: `28`
- tags: `service_task, broker_com_uri`

## callers

- `0x2c100`

## callees

- `0xd990`
- `0xdf80`
- `0xdfa0`
- `0xdff0`
- `0xe020`
- `0xe060`
- `0xe390`
- `0xe3a0`
- `0xe3c0`
- `0xe410`
- `0xe460`
- `0xe4a0`
- `0xe4d0`
- `0xe4e0`
- `0xe520`
- `0xe530`
- `0xe540`
- `0xe550`
- `0x278b0`
- `0x2c2a0`
- `0x2c2e0`
- `0x2c310`
- `0x2c6c0`
- `0x2c910`
- `0x2caf0`
- `0x2d3b0`
- `0x2d510`
- `0x3a500`

## pseudocode

```c

```

## disassembly

```asm
0x2c6c0  ldnull
0x2c6c1  stloc.0
0x2c6c2  ldc.i4.0
0x2c6c3  stloc.1
0x2c6c4  ldc.i4.0
0x2c6c5  stloc.2
0x2c6c6  br       loc_2C8E8
0x2c6cb  ldarg.0
0x2c6cc  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Modeling.DsvTable> Microsoft.ReportingServices.Modeling.ModelGeneration.SqlDsvStatisticsProvider::m_tables
0x2c6d1  ldloc.2
0x2c6d2  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Modeling.DsvTable>::get_Item(!!T0)
0x2c6d7  stloc.3
0x2c6d8  ldarg.0
0x2c6d9  call     string Microsoft.ReportingServices.Modeling.ModelGeneration.SR::get_SqlDsvStatisticsProvider_CalculatingUniqueness()
0x2c6de  ldloc.3
0x2c6df  callvirt instance string Microsoft.ReportingServices.Modeling.DsvItem::get_Name()
0x2c6e4  ldloc.2
0x2c6e5  ldc.i4.1
0x2c6e6  add
0x2c6e7  ldarg.0
0x2c6e8  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Modeling.DsvTable> Microsoft.ReportingServices.Modeling.ModelGeneration.SqlDsvStatisticsProvider::m_tables
0x2c6ed  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Modeling.DsvTable>::get_Count()
0x2c6f2  call     instance void Microsoft.ReportingServices.Modeling.ModelGeneration.SqlDsvStatisticsProvider::RaiseProgress(string step, string objectName, int32 progress, int32 total)
0x2c6f7  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Modeling.DsvColumn>::.ctor()
0x2c6fc  stloc.s  4
0x2c6fe  ldloc.3
0x2c6ff  callvirt instance class Microsoft.ReportingServices.Modeling.DsvColumnCollection Microsoft.ReportingServices.Modeling.DsvTable::get_Columns()
0x2c704  ldarg.0
0x2c705  ldfld    class Microsoft.ReportingServices.Modeling.ModelGeneration.IDsvItemFilter Microsoft.ReportingServices.Modeling.ModelGeneration.SqlDsvStatisticsProvider::m_filter
0x2c70a  dup
0x2c70b  ldvirtftn instance bool Microsoft.ReportingServices.Modeling.ModelGeneration.IDsvItemFilter::Evaluate(class Microsoft.ReportingServices.Modeling.DsvItem dsvItem)
0x2c711  newobj   instance void class [mscorlib]System.Predicate`1<class Microsoft.ReportingServices.Modeling.DsvColumn>::.ctor(object, native int)
0x2c716  call     T0x2B00010B
0x2c71b  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.ReportingServices.Modeling.DsvColumn>::GetEnumerator()
0x2c720  stloc.s  5
0x2c722  br       loc_2C87C
0x2c727  ldloc.s  5
0x2c729  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.ReportingServices.Modeling.DsvColumn>::get_Current()
0x2c72e  stloc.s  6
0x2c730  ldloc.s  6
0x2c732  callvirt instance class [mscorlib]System.Type Microsoft.ReportingServices.Modeling.DsvColumn::get_DataType()
0x2c737  ldtoken  [mscorlib]System.String
0x2c73c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2c741  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2c746  brtrue.s loc_2C760
0x2c748  ldloc.s  6
0x2c74a  callvirt instance class [mscorlib]System.Type Microsoft.ReportingServices.Modeling.DsvColumn::get_DataType()
0x2c74f  ldtoken  unsigned int8[]
0x2c754  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2c759  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2c75e  brfalse.s loc_2C7A5
0x2c760  ldarg.0
0x2c761  ldloc.s  6
0x2c763  callvirt instance bool Microsoft.ReportingServices.Modeling.ModelGeneration.SqlDsvStatisticsProvider::IsBlob(class Microsoft.ReportingServices.Modeling.DsvColumn column)
0x2c768  brfalse.s loc_2C779
0x2c76a  ldloc.s  6
0x2c76c  ldc.i4.1
0x2c76d  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x2c772  callvirt instance void Microsoft.ReportingServices.Modeling.DsvColumn::set_IsBlob(valuetype [mscorlib]System.Nullable`1<bool> value)
0x2c777  br.s     loc_2C7A5
0x2c779  ldloc.s  6
0x2c77b  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> Microsoft.ReportingServices.Modeling.DsvColumn::get_IsBlob()
0x2c780  stloc.s  7
0x2c782  ldloca.s 7
0x2c784  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x2c789  brfalse.s loc_2C7A5
0x2c78b  ldloca.s 7
0x2c78d  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x2c792  brfalse.s loc_2C7A5
0x2c794  ldloc.s  6
0x2c796  ldloca.s 8
0x2c798  initobj  valuetype [mscorlib]System.Nullable`1<bool>
0x2c79e  ldloc.s  8
0x2c7a0  callvirt instance void Microsoft.ReportingServices.Modeling.DsvColumn::set_IsBlob(valuetype [mscorlib]System.Nullable`1<bool> value)
0x2c7a5  ldloc.s  6
0x2c7a7  callvirt instance bool Microsoft.ReportingServices.Modeling.DsvColumn::get_IsLogical()
0x2c7ac  brtrue.s loc_2C7F3
0x2c7ae  ldloc.3
0x2c7af  callvirt instance bool Microsoft.ReportingServices.Modeling.DsvTable::get_IsLogical()
0x2c7b4  brtrue.s loc_2C7F3
0x2c7b6  ldloc.s  6
0x2c7b8  callvirt instance string Microsoft.ReportingServices.Modeling.DsvColumn::get_DbDataType()
0x2c7bd  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2c7c2  brfalse.s loc_2C7F3
0x2c7c4  ldloc.1
0x2c7c5  brtrue.s loc_2C7D0
0x2c7c7  ldarg.0
0x2c7c8  callvirt instance class IGetColumnDbTypeName Microsoft.ReportingServices.Modeling.ModelGeneration.SqlDsvStatisticsProvider::GetColumnDbTypeNameDictionary()
0x2c7cd  stloc.0
0x2c7ce  ldc.i4.1
0x2c7cf  stloc.1
0x2c7d0  ldloc.0
0x2c7d1  brfalse.s loc_2C7F3
0x2c7d3  ldloc.s  6
0x2c7d5  ldloc.0
0x2c7d6  ldloc.3
0x2c7d7  callvirt instance string Microsoft.ReportingServices.Modeling.DsvTable::get_DbSchemaName()
0x2c7dc  ldloc.3
0x2c7dd  callvirt instance string Microsoft.ReportingServices.Modeling.DsvTable::get_DbTableName()
0x2c7e2  ldloc.s  6
0x2c7e4  callvirt instance string Microsoft.ReportingServices.Modeling.DsvColumn::get_DbColumnName()
0x2c7e9  callvirt instance string IGetColumnDbTypeName::GetColumnDbTypeName(string tableSchema, string tableName, string columnDbName)
0x2c7ee  callvirt instance void Microsoft.ReportingServices.Modeling.DsvColumn::set_DbDataType(string value)
0x2c7f3  ldloc.s  6
0x2c7f5  callvirt instance valuetype [mscorlib]System.Nullable`1<int64> Microsoft.ReportingServices.Modeling.DsvColumn::get_UniqueValueCount()
0x2c7fa  stloc.s  9
0x2c7fc  ldloca.s 9
0x2c7fe  call     instance bool valuetype [mscorlib]System.Nullable`1<int64>::get_HasValue()
0x2c803  brfalse.s loc_2C81F
0x2c805  ldloc.s  6
0x2c807  callvirt instance valuetype [mscorlib]System.Nullable`1<int32> Microsoft.ReportingServices.Modeling.DsvColumn::get_UniqueValuePercent()
0x2c80c  stloc.s  0xA
0x2c80e  ldloca.s 0xA
0x2c810  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x2c815  brfalse.s loc_2C81F
0x2c817  ldarg.0
0x2c818  ldfld    bool Microsoft.ReportingServices.Modeling.ModelGeneration.SqlDsvStatisticsProvider::m_overwrite
0x2c81d  brfalse.s loc_2C87C
0x2c81f  ldloc.s  6
0x2c821  callvirt instance bool Microsoft.ReportingServices.Modeling.DsvColumn::get_Unique()
0x2c826  brtrue.s loc_2C832
0x2c828  ldarg.0
0x2c829  ldloc.s  6
0x2c82b  callvirt instance string Microsoft.ReportingServices.Modeling.ModelGeneration.SqlDsvStatisticsProvider::WrapForCountExpression(class Microsoft.ReportingServices.Modeling.DsvColumn column)
0x2c830  brtrue.s loc_2C84F
0x2c832  ldloc.s  6
0x2c834  ldc.i4.s 0x64
0x2c836  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x2c83b  callvirt instance void Microsoft.ReportingServices.Modeling.DsvColumn::set_UniqueValuePercent(valuetype [mscorlib]System.Nullable`1<int32> value)
0x2c840  ldloc.s  6
0x2c842  ldloc.3
0x2c843  callvirt instance valuetype [mscorlib]System.Nullable`1<int64> Microsoft.ReportingServices.Modeling.DsvTable::get_RowCount()
0x2c848  callvirt instance void Microsoft.ReportingServices.Modeling.DsvColumn::set_UniqueValueCount(valuetype [mscorlib]System.Nullable`1<int64> value)
0x2c84d  br.s     loc_2C87C
0x2c84f  ldarg.0
0x2c850  ldfld    class Microsoft.ReportingServices.Common.Bag`1<class Microsoft.ReportingServices.Modeling.DsvColumn> Microsoft.ReportingServices.Modeling.ModelGeneration.SqlDsvStatisticsProvider::m_indexedColumns
0x2c855  ldloc.s  6
0x2c857  callvirt instance bool class Microsoft.ReportingServices.Common.Bag`1<class Microsoft.ReportingServices.Modeling.DsvColumn>::Contains(var<u1>)
0x2c85c  brfalse.s loc_2C873
0x2c85e  ldarg.0
0x2c85f  ldloc.3
0x2c860  ldc.i4.1
0x2c861  newarr   Microsoft.ReportingServices.Modeling.DsvColumn
0x2c866  dup
0x2c867  ldc.i4.0
0x2c868  ldloc.s  6
0x2c86a  stelem.ref
0x2c86b  ldc.i4.0
0x2c86c  call     instance void Microsoft.ReportingServices.Modeling.ModelGeneration.SqlDsvStatisticsProvider::GetColumnUniquenessCore(class Microsoft.ReportingServices.Modeling.DsvTable table, class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.Modeling.DsvColumn> columns, bool allowSampling)
0x2c871  br.s     loc_2C87C
0x2c873  ldloc.s  4
0x2c875  ldloc.s  6
0x2c877  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Modeling.DsvColumn>::Add(var<u1>)
0x2c87c  ldloc.s  5
0x2c87e  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2c883  brtrue   loc_2C727
0x2c888  leave.s  loc_2C896
0x2c88a  ldloc.s  5
0x2c88c  brfalse.s loc_2C895
0x2c88e  ldloc.s  5
0x2c890  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2c895  endfinally
0x2c896  ldloc.s  4
0x2c898  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Modeling.DsvColumn>::get_Count()
0x2c89d  ldc.i4.0
0x2c89e  ble.s    loc_2C8DD
0x2c8a0  ldc.i4.0
0x2c8a1  stloc.s  0xB
0x2c8a3  br.s     loc_2C8D2
0x2c8a5  ldloc.s  4
0x2c8a7  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Modeling.DsvColumn>::get_Count()
0x2c8ac  ldloc.s  0xB
0x2c8ae  sub
0x2c8af  ldc.i4.s 0xF
0x2c8b1  call     int32 [mscorlib]System.Math::Min(int32, int32)
0x2c8b6  stloc.s  0xC
0x2c8b8  ldarg.0
0x2c8b9  ldloc.3
0x2c8ba  ldloc.s  4
0x2c8bc  ldloc.s  0xB
0x2c8be  ldloc.s  0xC
0x2c8c0  callvirt instance class [mscorlib]System.Collections.Generic.List`1<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Modeling.DsvColumn>::GetRange(!!T0, int32)
0x2c8c5  ldc.i4.1
0x2c8c6  call     instance void Microsoft.ReportingServices.Modeling.ModelGeneration.SqlDsvStatisticsProvider::GetColumnUniquenessCore(class Microsoft.ReportingServices.Modeling.DsvTable table, class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.Modeling.DsvColumn> columns, bool allowSampling)
0x2c8cb  ldloc.s  0xB
0x2c8cd  ldc.i4.s 0xF
0x2c8cf  add
0x2c8d0  stloc.s  0xB
0x2c8d2  ldloc.s  0xB
0x2c8d4  ldloc.s  4
0x2c8d6  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Modeling.DsvColumn>::get_Count()
0x2c8db  blt.s    loc_2C8A5
0x2c8dd  ldarg.0
0x2c8de  ldloc.3
0x2c8df  call     instance void Microsoft.ReportingServices.Modeling.ModelGeneration.SqlDsvStatisticsProvider::GetColumnGroupUniqueness(class Microsoft.ReportingServices.Modeling.DsvTable table)
0x2c8e4  ldloc.2
0x2c8e5  ldc.i4.1
0x2c8e6  add
0x2c8e7  stloc.2
0x2c8e8  ldloc.2
0x2c8e9  ldarg.0
0x2c8ea  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Modeling.DsvTable> Microsoft.ReportingServices.Modeling.ModelGeneration.SqlDsvStatisticsProvider::m_tables
0x2c8ef  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Modeling.DsvTable>::get_Count()
0x2c8f4  bge.s    loc_2C906
0x2c8f6  ldarg.0
0x2c8f7  ldfld    class Microsoft.ReportingServices.Modeling.ModelGeneration.ICancelEvent Microsoft.ReportingServices.Modeling.ModelGeneration.SqlDsvStatisticsProvider::m_cancelEvent
0x2c8fc  callvirt instance bool Microsoft.ReportingServices.Modeling.ModelGeneration.ICancelEvent::get_CancelRequested()
0x2c901  brfalse  loc_2C6CB
0x2c906  ret
```
