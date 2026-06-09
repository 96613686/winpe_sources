# Microsoft.ReportingServices.Modeling.ModelGeneration.SqlDsvStatisticsProvider::GetColumnWidthsCore

- ea: `0x2cde0`
- end: `0x2d0da`
- name: `Microsoft.ReportingServices.Modeling.ModelGeneration.SqlDsvStatisticsProvider::GetColumnWidthsCore`
- size: `762`
- prototype: ``
- caller_count: `1`
- callee_count: `30`
- tags: `service_task, broker_com_uri`

## callers

- `0x2cc80`

## callees

- `0x97d0`
- `0xe060`
- `0xe510`
- `0xe590`
- `0xe5b0`
- `0xe5d0`
- `0xe5f0`
- `0xe610`
- `0xe630`
- `0x2c300`
- `0x2c380`
- `0x2c390`
- `0x2c3a0`
- `0x2c3b0`
- `0x2c3c0`
- `0x2c3d0`
- `0x2c3e0`
- `0x2c3f0`
- `0x2c400`
- `0x2c410`
- `0x2c420`
- `0x2c430`
- `0x2cad0`
- `0x2cde0`
- `0x2d0e0`
- `0x2d210`
- `0x2d250`
- `0x3a3a0`
- `0x3a440`
- `0x3a460`

## pseudocode

```c

```

## disassembly

```asm
0x2cde0  ldarg.1
0x2cde1  brtrue.s loc_2CDEE
0x2cde3  ldstr    aTableIsNull// "table is null"
0x2cde8  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x2cded  throw
0x2cdee  ldarg.2
0x2cdef  brfalse.s loc_2CDF9
0x2cdf1  ldarg.2
0x2cdf2  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.ReportingServices.Modeling.DsvColumn>::get_Count()
0x2cdf7  brtrue.s loc_2CE04
0x2cdf9  ldstr    aColumnsIsNullE// "columns is null/empty"
0x2cdfe  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x2ce03  throw
0x2ce04  ldarg.2
0x2ce05  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.ReportingServices.Modeling.DsvColumn>::get_Count()
0x2ce0a  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor(int32)
0x2ce0f  stloc.0
0x2ce10  ldarg.2
0x2ce11  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.ReportingServices.Modeling.DsvColumn>::get_Count()
0x2ce16  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.ReportingServices.Modeling.DsvColumn, int32>::.ctor(int32)
0x2ce1b  stloc.1
0x2ce1c  ldarg.2
0x2ce1d  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.ReportingServices.Modeling.DsvColumn>::GetEnumerator()
0x2ce22  stloc.3
0x2ce23  br       loc_2CF43
0x2ce28  ldloc.3
0x2ce29  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.ReportingServices.Modeling.DsvColumn>::get_Current()
0x2ce2e  stloc.s  4
0x2ce30  ldloc.1
0x2ce31  ldloc.s  4
0x2ce33  ldloc.0
0x2ce34  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x2ce39  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.ReportingServices.Modeling.DsvColumn, int32>::Add(var<u1>, !!T0)
0x2ce3e  ldloc.s  4
0x2ce40  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.DataType> Microsoft.ReportingServices.Modeling.DsvColumn::get_ModelingDataType()
0x2ce45  stloc.s  6
0x2ce47  ldloca.s 6
0x2ce49  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.DataType>::get_Value()
0x2ce4e  stloc.s  5
0x2ce50  ldloc.s  5
0x2ce52  switch   loc_2CE6C, loc_2CE9B, loc_2CEC7, loc_2CEC7
0x2ce67  br       loc_2CF1D
0x2ce6c  ldloc.0
0x2ce6d  ldarg.0
0x2ce6e  ldloc.s  4
0x2ce70  callvirt instance string Microsoft.ReportingServices.Modeling.ModelGeneration.SqlDsvStatisticsProvider::GetSqlForStringAvgWidthExpression(class Microsoft.ReportingServices.Modeling.DsvColumn column)
0x2ce75  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x2ce7a  ldloc.0
0x2ce7b  ldarg.0
0x2ce7c  ldloc.s  4
0x2ce7e  callvirt instance string Microsoft.ReportingServices.Modeling.ModelGeneration.SqlDsvStatisticsProvider::GetSqlForStringStDevWidthExpression(class Microsoft.ReportingServices.Modeling.DsvColumn column)
0x2ce83  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x2ce88  ldloc.0
0x2ce89  ldarg.0
0x2ce8a  ldloc.s  4
0x2ce8c  callvirt instance string Microsoft.ReportingServices.Modeling.ModelGeneration.SqlDsvStatisticsProvider::GetSqlForStringMaxWidthExpression(class Microsoft.ReportingServices.Modeling.DsvColumn column)
0x2ce91  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x2ce96  br       loc_2CF43
0x2ce9b  ldloc.0
0x2ce9c  ldarg.0
0x2ce9d  ldloc.s  4
0x2ce9f  callvirt instance string Microsoft.ReportingServices.Modeling.ModelGeneration.SqlDsvStatisticsProvider::GetSqlForIntAvgWidthExpression(class Microsoft.ReportingServices.Modeling.DsvColumn column)
0x2cea4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x2cea9  ldloc.0
0x2ceaa  ldarg.0
0x2ceab  ldloc.s  4
0x2cead  callvirt instance string Microsoft.ReportingServices.Modeling.ModelGeneration.SqlDsvStatisticsProvider::GetSqlForIntStDevWidthExpression(class Microsoft.ReportingServices.Modeling.DsvColumn column)
0x2ceb2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x2ceb7  ldloc.0
0x2ceb8  ldarg.0
0x2ceb9  ldloc.s  4
0x2cebb  callvirt instance string Microsoft.ReportingServices.Modeling.ModelGeneration.SqlDsvStatisticsProvider::GetSqlForIntMaxWidthExpression(class Microsoft.ReportingServices.Modeling.DsvColumn column)
0x2cec0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x2cec5  br.s     loc_2CF43
0x2cec7  ldloc.0
0x2cec8  ldarg.0
0x2cec9  ldloc.s  4
0x2cecb  callvirt instance string Microsoft.ReportingServices.Modeling.ModelGeneration.SqlDsvStatisticsProvider::GetSqlForRealAvgWidthExpression(class Microsoft.ReportingServices.Modeling.DsvColumn column)
0x2ced0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x2ced5  ldloc.0
0x2ced6  ldarg.0
0x2ced7  ldloc.s  4
0x2ced9  callvirt instance string Microsoft.ReportingServices.Modeling.ModelGeneration.SqlDsvStatisticsProvider::GetSqlForRealStDevWidthExpression(class Microsoft.ReportingServices.Modeling.DsvColumn column)
0x2cede  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x2cee3  ldloc.0
0x2cee4  ldarg.0
0x2cee5  ldloc.s  4
0x2cee7  callvirt instance string Microsoft.ReportingServices.Modeling.ModelGeneration.SqlDsvStatisticsProvider::GetSqlForRealMaxWidthExpression(class Microsoft.ReportingServices.Modeling.DsvColumn column)
0x2ceec  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x2cef1  ldloc.0
0x2cef2  ldarg.0
0x2cef3  ldloc.s  4
0x2cef5  callvirt instance string Microsoft.ReportingServices.Modeling.ModelGeneration.SqlDsvStatisticsProvider::GetSqlForRealAvgScaleExpression(class Microsoft.ReportingServices.Modeling.DsvColumn column)
0x2cefa  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x2ceff  ldloc.0
0x2cf00  ldarg.0
0x2cf01  ldloc.s  4
0x2cf03  callvirt instance string Microsoft.ReportingServices.Modeling.ModelGeneration.SqlDsvStatisticsProvider::GetSqlForRealStDevScaleExpression(class Microsoft.ReportingServices.Modeling.DsvColumn column)
0x2cf08  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x2cf0d  ldloc.0
0x2cf0e  ldarg.0
0x2cf0f  ldloc.s  4
0x2cf11  callvirt instance string Microsoft.ReportingServices.Modeling.ModelGeneration.SqlDsvStatisticsProvider::GetSqlForRealMaxScaleExpression(class Microsoft.ReportingServices.Modeling.DsvColumn column)
0x2cf16  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x2cf1b  br.s     loc_2CF43
0x2cf1d  ldstr    aUnexpectedColu// "Unexpected column DataType in GetColumn"...
0x2cf22  ldloc.s  4
0x2cf24  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.DataType> Microsoft.ReportingServices.Modeling.DsvColumn::get_ModelingDataType()
0x2cf29  stloc.s  6
0x2cf2b  ldloca.s 6
0x2cf2d  constrained. valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.DataType>
0x2cf33  callvirt instance string [mscorlib]System.Object::ToString()
0x2cf38  call     string [mscorlib]System.String::Concat(string, string)
0x2cf3d  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x2cf42  throw
0x2cf43  ldloc.3
0x2cf44  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2cf49  brtrue   loc_2CE28
0x2cf4e  leave.s  loc_2CF5A
0x2cf50  ldloc.3
0x2cf51  brfalse.s loc_2CF59
0x2cf53  ldloc.3
0x2cf54  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2cf59  endfinally
0x2cf5a  ldarg.0
0x2cf5b  ldarg.1
0x2cf5c  call     instance string Microsoft.ReportingServices.Modeling.ModelGeneration.SqlDsvStatisticsProvider::GetSqlForTableSourceExpression(class Microsoft.ReportingServices.Modeling.DsvTable table)
0x2cf61  stloc.2
0x2cf62  ldarg.1
0x2cf63  callvirt instance valuetype [mscorlib]System.Nullable`1<int64> Microsoft.ReportingServices.Modeling.DsvTable::get_RowCount()
0x2cf68  stloc.s  7
0x2cf6a  ldc.i4   0x186A0
0x2cf6f  conv.i8
0x2cf70  stloc.s  8
0x2cf72  ldloca.s 7
0x2cf74  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int64>::GetValueOrDefault()
0x2cf79  ldloc.s  8
0x2cf7b  cgt
0x2cf7d  ldloca.s 7
0x2cf7f  call     instance bool valuetype [mscorlib]System.Nullable`1<int64>::get_HasValue()
0x2cf84  and
0x2cf85  ldarg.3
0x2cf86  and
0x2cf87  brfalse.s loc_2CFAC
0x2cf89  ldarg.0
0x2cf8a  ldarg.1
0x2cf8b  callvirt instance valuetype [mscorlib]System.Nullable`1<int64> Microsoft.ReportingServices.Modeling.DsvTable::get_RowCount()
0x2cf90  stloc.s  7
0x2cf92  ldloca.s 7
0x2cf94  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int64>::get_Value()
0x2cf99  ldc.i4   0x186A0
0x2cf9e  conv.i8
0x2cf9f  ldloc.2
0x2cfa0  ldarg.1
0x2cfa1  call     bool Microsoft.ReportingServices.Modeling.ModelGeneration.SqlDsvStatisticsProvider::IsPhysicalTable(class Microsoft.ReportingServices.Modeling.DsvTable table)
0x2cfa6  callvirt instance string Microsoft.ReportingServices.Modeling.ModelGeneration.SqlDsvStatisticsProvider::GetSqlForSelectSampledTableSource(int64 actualRowCount, int64 targetRowCount, string tableSource, bool isTable)
0x2cfab  stloc.2
0x2cfac  ldarg.0
0x2cfad  ldarg.0
0x2cfae  ldloc.0
0x2cfaf  ldloc.2
0x2cfb0  call     instance string Microsoft.ReportingServices.Modeling.ModelGeneration.SqlDsvStatisticsProvider::GetSqlForSelect(class [mscorlib]System.Collections.Generic.IList`1<string> selectExpressions, string tableSource)
0x2cfb5  call     instance class SchemaReader Microsoft.ReportingServices.Modeling.ModelGeneration.SqlDsvStatisticsProvider::ExecuteQuery(string commandText)
0x2cfba  stloc.s  9
0x2cfbc  ldloc.s  9
0x2cfbe  callvirt instance bool SchemaReader::Read()
0x2cfc3  brfalse  loc_2D0C2
0x2cfc8  ldloc.1
0x2cfc9  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.ReportingServices.Modeling.DsvColumn, int32>::GetEnumerator()
0x2cfce  stloc.s  0xA
0x2cfd0  br       loc_2D0A6
0x2cfd5  ldloca.s 0xA
0x2cfd7  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<class Microsoft.ReportingServices.Modeling.DsvColumn, int32>::get_Current()
0x2cfdc  stloc.s  0xB
0x2cfde  ldloca.s 0xB
0x2cfe0  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.ReportingServices.Modeling.DsvColumn, int32>::get_Key()
0x2cfe5  stloc.s  0xC
0x2cfe7  ldloc.s  0xC
0x2cfe9  ldloc.s  9
0x2cfeb  ldloca.s 0xB
0x2cfed  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.ReportingServices.Modeling.DsvColumn, int32>::get_Value()
0x2cff2  callvirt instance float32 SchemaReader::GetSingle(int32 index)
0x2cff7  newobj   instance void valuetype [mscorlib]System.Nullable`1<float32>::.ctor(var<u1>)
0x2cffc  callvirt instance void Microsoft.ReportingServices.Modeling.DsvColumn::set_AvgWidth(valuetype [mscorlib]System.Nullable`1<float32> value)
0x2d001  ldloc.s  0xC
0x2d003  ldloc.s  9
0x2d005  ldloca.s 0xB
0x2d007  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.ReportingServices.Modeling.DsvColumn, int32>::get_Value()
0x2d00c  ldc.i4.1
0x2d00d  add
0x2d00e  callvirt instance float32 SchemaReader::GetSingle(int32 index)
0x2d013  newobj   instance void valuetype [mscorlib]System.Nullable`1<float32>::.ctor(var<u1>)
0x2d018  callvirt instance void Microsoft.ReportingServices.Modeling.DsvColumn::set_StDevWidth(valuetype [mscorlib]System.Nullable`1<float32> value)
0x2d01d  ldloc.s  0xC
0x2d01f  ldloc.s  9
0x2d021  ldloca.s 0xB
0x2d023  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.ReportingServices.Modeling.DsvColumn, int32>::get_Value()
0x2d028  ldc.i4.2
0x2d029  add
0x2d02a  callvirt instance int32 SchemaReader::GetInt32(int32 index)
0x2d02f  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x2d034  callvirt instance void Microsoft.ReportingServices.Modeling.DsvColumn::set_MaxWidth(valuetype [mscorlib]System.Nullable`1<int32> value)
0x2d039  ldloc.s  0xC
0x2d03b  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.DataType> Microsoft.ReportingServices.Modeling.DsvColumn::get_ModelingDataType()
0x2d040  stloc.s  6
0x2d042  ldloca.s 6
0x2d044  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.DataType>::get_Value()
0x2d049  stloc.s  5
0x2d04b  ldloc.s  5
0x2d04d  ldc.i4.2
0x2d04e  sub
0x2d04f  ldc.i4.1
0x2d050  bgt.un.s loc_2D0A6
0x2d052  ldloc.s  0xC
0x2d054  ldloc.s  9
0x2d056  ldloca.s 0xB
0x2d058  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.ReportingServices.Modeling.DsvColumn, int32>::get_Value()
0x2d05d  ldc.i4.3
0x2d05e  add
0x2d05f  callvirt instance float32 SchemaReader::GetSingle(int32 index)
0x2d064  newobj   instance void valuetype [mscorlib]System.Nullable`1<float32>::.ctor(var<u1>)
0x2d069  callvirt instance void Microsoft.ReportingServices.Modeling.DsvColumn::set_AvgScale(valuetype [mscorlib]System.Nullable`1<float32> value)
0x2d06e  ldloc.s  0xC
0x2d070  ldloc.s  9
0x2d072  ldloca.s 0xB
0x2d074  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.ReportingServices.Modeling.DsvColumn, int32>::get_Value()
0x2d079  ldc.i4.4
0x2d07a  add
0x2d07b  callvirt instance float32 SchemaReader::GetSingle(int32 index)
0x2d080  newobj   instance void valuetype [mscorlib]System.Nullable`1<float32>::.ctor(var<u1>)
0x2d085  callvirt instance void Microsoft.ReportingServices.Modeling.DsvColumn::set_StDevScale(valuetype [mscorlib]System.Nullable`1<float32> value)
0x2d08a  ldloc.s  0xC
0x2d08c  ldloc.s  9
0x2d08e  ldloca.s 0xB
0x2d090  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.ReportingServices.Modeling.DsvColumn, int32>::get_Value()
0x2d095  ldc.i4.5
0x2d096  add
0x2d097  callvirt instance int32 SchemaReader::GetInt32(int32 index)
0x2d09c  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x2d0a1  callvirt instance void Microsoft.ReportingServices.Modeling.DsvColumn::set_MaxScale(valuetype [mscorlib]System.Nullable`1<int32> value)
0x2d0a6  ldloca.s 0xA
0x2d0a8  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<class Microsoft.ReportingServices.Modeling.DsvColumn, int32>::MoveNext()
0x2d0ad  brtrue   loc_2CFD5
0x2d0b2  leave.s  loc_2D0D9
0x2d0b4  ldloca.s 0xA
0x2d0b6  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<class Microsoft.ReportingServices.Modeling.DsvColumn, int32>
0x2d0bc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2d0c1  endfinally
0x2d0c2  ldstr    aUnexpectedEndO_0// "Unexpected end of data for column width"...
0x2d0c7  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x2d0cc  throw
0x2d0cd  ldloc.s  9
0x2d0cf  brfalse.s loc_2D0D8
0x2d0d1  ldloc.s  9
0x2d0d3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2d0d8  endfinally
0x2d0d9  ret
```
