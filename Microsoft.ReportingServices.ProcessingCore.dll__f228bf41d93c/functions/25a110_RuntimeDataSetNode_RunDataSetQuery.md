# RuntimeDataSetNode::RunDataSetQuery

- ea: `0x25a110`
- end: `0x25a7d8`
- name: `RuntimeDataSetNode::RunDataSetQuery`
- size: `1736`
- prototype: ``
- caller_count: `3`
- callee_count: `40`
- tags: ``

## callers

- `0x25ae70`
- `0x25b5a0`
- `0x25b6e0`

## callees

- `0x175de0`
- `0x175e50`
- `0x1843f0`
- `0x18ee10`
- `0x18f110`
- `0x1903a0`
- `0x1940d0`
- `0x197200`
- `0x197420`
- `0x197800`
- `0x197820`
- `0x197840`
- `0x197980`
- `0x197a60`
- `0x197d90`
- `0x198420`
- `0x198440`
- `0x198460`
- `0x198480`
- `0x1984b0`
- `0x1984c0`
- `0x1984d0`
- `0x198720`
- `0x198740`
- `0x198950`
- `0x198970`
- `0x1c5800`
- `0x1c5930`
- `0x1d07c0`
- `0x1d0c20`
- `0x1d0c40`
- `0x23faa0`
- `0x240610`
- `0x2408f0`
- `0x240910`
- `0x240bc0`
- `0x240be0`
- `0x240c30`
- `0x25a110`
- `0x25b8f0`

## string_xrefs

- `0x25a685`: `The source data reader is null. Cannot read results.`

## pseudocode

```c

```

## disassembly

```asm
0x25a110  ldc.i4.0
0x25a111  stloc.0
0x25a112  ldc.i4.0
0x25a113  stloc.1
0x25a114  ldarg.0
0x25a115  ldfld    class Microsoft.ReportingServices.ReportProcessing.DataSet RuntimeDataSetNode::m_dataSet
0x25a11a  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ReportQuery Microsoft.ReportingServices.ReportProcessing.DataSet::get_Query()
0x25a11f  brtrue.s loc_25A123
0x25a121  ldloc.0
0x25a122  ret
0x25a123  ldarg.0
0x25a124  ldfld    class Microsoft.ReportingServices.ReportProcessing.DataSet RuntimeDataSetNode::m_dataSet
0x25a129  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ReportQuery Microsoft.ReportingServices.ReportProcessing.DataSet::get_Query()
0x25a12e  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ParameterValueList Microsoft.ReportingServices.ReportProcessing.ReportQuery::get_Parameters()
0x25a133  stloc.2
0x25a134  ldloc.2
0x25a135  brfalse.s loc_25A13F
0x25a137  ldloc.2
0x25a138  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x25a13d  br.s     loc_25A140
0x25a13f  ldc.i4.0
0x25a140  newarr   [mscorlib]System.Object
0x25a145  stloc.3
0x25a146  ldc.i4.0
0x25a147  stloc.s  7
0x25a149  br.s     loc_25A1AA
0x25a14b  ldloc.2
0x25a14c  ldloc.s  7
0x25a14e  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ParameterValue Microsoft.ReportingServices.ReportProcessing.ParameterValueList::get_Item(int32 index)
0x25a153  stloc.s  8
0x25a155  ldarg.0
0x25a156  ldfld    class ProcessingContext RuntimeDataSetNode::m_processingContext
0x25a15b  callvirt instance void ProcessingContext::CheckAndThrowIfAborted()
0x25a160  ldloc.3
0x25a161  ldloc.s  7
0x25a163  ldarg.0
0x25a164  ldfld    class ProcessingContext RuntimeDataSetNode::m_processingContext
0x25a169  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ReportRuntime ProcessingContext::get_ReportRuntime()
0x25a16e  ldloc.s  8
0x25a170  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ExpressionInfo Microsoft.ReportingServices.ReportProcessing.ParameterValue::get_Value()
0x25a175  ldarg.0
0x25a176  ldfld    class Microsoft.ReportingServices.ReportProcessing.DataSet RuntimeDataSetNode::m_dataSet
0x25a17b  callvirt instance class [Microsoft.ReportingServices.ProcessingObjectModel]Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataSetExprHost Microsoft.ReportingServices.ReportProcessing.DataSet::get_ExprHost()
0x25a180  brtrue.s loc_25A185
0x25a182  ldnull
0x25a183  br.s     loc_25A195
0x25a185  ldarg.0
0x25a186  ldfld    class Microsoft.ReportingServices.ReportProcessing.DataSet RuntimeDataSetNode::m_dataSet
0x25a18b  callvirt instance class [Microsoft.ReportingServices.ProcessingObjectModel]Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataSetExprHost Microsoft.ReportingServices.ReportProcessing.DataSet::get_ExprHost()
0x25a190  ldfld    class [Microsoft.ReportingServices.ProcessingObjectModel]Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.IndexedExprHost [Microsoft.ReportingServices.ProcessingObjectModel]Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataSetExprHost::QueryParametersHost
0x25a195  ldc.i4.s 0x17
0x25a197  ldloc.s  8
0x25a199  callvirt instance string Microsoft.ReportingServices.ReportProcessing.ParameterValue::get_Name()
0x25a19e  callvirt instance object Microsoft.ReportingServices.ReportProcessing.ReportRuntime::EvaluateQueryParamValue(class Microsoft.ReportingServices.ReportProcessing.ExpressionInfo paramValue, class [Microsoft.ReportingServices.ProcessingObjectModel]Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.IndexedExprHost queryParamsExprHost, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName)
0x25a1a3  stelem.ref
0x25a1a4  ldloc.s  7
0x25a1a6  ldc.i4.1
0x25a1a7  add
0x25a1a8  stloc.s  7
0x25a1aa  ldloc.s  7
0x25a1ac  ldloc.3
0x25a1ad  ldlen
0x25a1ae  conv.i4
0x25a1af  blt.s    loc_25A14B
0x25a1b1  ldarg.0
0x25a1b2  ldfld    class ProcessingContext RuntimeDataSetNode::m_processingContext
0x25a1b7  callvirt instance void ProcessingContext::CheckAndThrowIfAborted()
0x25a1bc  ldnull
0x25a1bd  stloc.s  4
0x25a1bf  ldarg.0
0x25a1c0  ldfld    class ProcessingContext RuntimeDataSetNode::m_processingContext
0x25a1c5  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IJobContext ProcessingContext::get_JobContext()
0x25a1ca  brfalse.s loc_25A1DA
0x25a1cc  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Timer::.ctor()
0x25a1d1  stloc.s  4
0x25a1d3  ldloc.s  4
0x25a1d5  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Timer::StartTimer()
0x25a1da  ldnull
0x25a1db  stloc.s  5
0x25a1dd  ldnull
0x25a1de  stloc.s  6
0x25a1e0  ldarg.0
0x25a1e1  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbConnection RuntimeDataSetNode::m_dataSourceConnection
0x25a1e6  brtrue.s loc_25A223
0x25a1e8  ldarg.0
0x25a1e9  ldfld    class ProcessingContext RuntimeDataSetNode::m_processingContext
0x25a1ee  castclass ReportProcessingContext
0x25a1f3  stloc.s  0xA
0x25a1f5  ldarg.0
0x25a1f6  ldfld    class Microsoft.ReportingServices.ReportProcessing.DataSource RuntimeDataSetNode::m_dataSource
0x25a1fb  ldloc.s  0xA
0x25a1fd  ldloca.s 0xB
0x25a1ff  callvirt instance string Microsoft.ReportingServices.ReportProcessing.DataSource::ResolveConnectionString(class ReportProcessingContext pc, [out] class Microsoft.ReportingServices.DataExtensions.DataSourceInfo& dataSourceInfo)
0x25a204  stloc.s  0xC
0x25a206  ldarg.0
0x25a207  ldloc.s  0xA
0x25a209  callvirt instance class Microsoft.ReportingServices.ReportProcessing.IProcessingDataExtensionConnection ProcessingContext::get_DataExtensionConnection()
0x25a20e  ldarg.0
0x25a20f  ldfld    class Microsoft.ReportingServices.ReportProcessing.DataSource RuntimeDataSetNode::m_dataSource
0x25a214  ldloc.s  0xC
0x25a216  ldloc.s  0xB
0x25a218  ldnull
0x25a219  callvirt instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbConnection Microsoft.ReportingServices.ReportProcessing.IProcessingDataExtensionConnection::OpenDataSourceExtensionConnection(class Microsoft.ReportingServices.ReportProcessing.IProcessingDataSource dataSource, string connectionString, class Microsoft.ReportingServices.DataExtensions.DataSourceInfo dataSourceInfo, string datasetName)
0x25a21e  stfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbConnection RuntimeDataSetNode::m_dataSourceConnection
0x25a223  nop
0x25a224  ldarg.0
0x25a225  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbConnection RuntimeDataSetNode::m_dataSourceConnection
0x25a22a  callvirt instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbCommand [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbConnection::CreateCommand()
0x25a22f  stloc.s  6
0x25a231  leave.s  loc_25A256
0x25a233  stloc.s  0xD
0x25a235  ldc.i4   0xA2
0x25a23a  ldloc.s  0xD
0x25a23c  ldc.i4.1
0x25a23d  newarr   [mscorlib]System.Object
0x25a242  dup
0x25a243  ldc.i4.0
0x25a244  ldarg.0
0x25a245  ldfld    class Microsoft.ReportingServices.ReportProcessing.DataSource RuntimeDataSetNode::m_dataSource
0x25a24a  callvirt instance string Microsoft.ReportingServices.ReportProcessing.DataSource::get_Name()
0x25a24f  stelem.ref
0x25a250  newobj   instance void Microsoft.ReportingServices.ReportProcessing.ReportProcessingException::.ctor(valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode code, class [mscorlib]System.Exception innerException, object[] arguments)
0x25a255  throw
0x25a256  ldc.i4.0
0x25a257  stloc.s  0xE
0x25a259  br       loc_25A404
0x25a25e  nop
0x25a25f  ldloc.s  6
0x25a261  callvirt instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDataParameter [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbCommand::CreateParameter()
0x25a266  stloc.s  0xF
0x25a268  leave.s  loc_25A28D
0x25a26a  stloc.s  0x12
0x25a26c  ldc.i4   0xA3
0x25a271  ldloc.s  0x12
0x25a273  ldc.i4.1
0x25a274  newarr   [mscorlib]System.Object
0x25a279  dup
0x25a27a  ldc.i4.0
0x25a27b  ldarg.0
0x25a27c  ldfld    class Microsoft.ReportingServices.ReportProcessing.DataSet RuntimeDataSetNode::m_dataSet
0x25a281  callvirt instance string Microsoft.ReportingServices.ReportProcessing.DataSet::get_Name()
0x25a286  stelem.ref
0x25a287  newobj   instance void Microsoft.ReportingServices.ReportProcessing.ReportProcessingException::.ctor(valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode code, class [mscorlib]System.Exception innerException, object[] arguments)
0x25a28c  throw
0x25a28d  ldloc.s  0xF
0x25a28f  ldloc.2
0x25a290  ldloc.s  0xE
0x25a292  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ParameterValue Microsoft.ReportingServices.ReportProcessing.ParameterValueList::get_Item(int32 index)
0x25a297  callvirt instance string Microsoft.ReportingServices.ReportProcessing.ParameterValue::get_Name()
0x25a29c  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDataParameter::set_ParameterName(string)
0x25a2a1  ldloc.s  0xF
0x25a2a3  isinst   [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDataMultiValueParameter
0x25a2a8  brfalse.s loc_25A2B8
0x25a2aa  ldloc.3
0x25a2ab  ldloc.s  0xE
0x25a2ad  ldelem.ref
0x25a2ae  isinst   [mscorlib]System.Collections.ICollection
0x25a2b3  ldnull
0x25a2b4  cgt.un
0x25a2b6  br.s     loc_25A2B9
0x25a2b8  ldc.i4.0
0x25a2b9  stloc.s  0x10
0x25a2bb  ldloc.3
0x25a2bc  ldloc.s  0xE
0x25a2be  ldelem.ref
0x25a2bf  stloc.s  0x11
0x25a2c1  ldloc.s  0x11
0x25a2c3  brtrue.s loc_25A2CC
0x25a2c5  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x25a2ca  stloc.s  0x11
0x25a2cc  ldloc.s  0xF
0x25a2ce  isinst   [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDataMultiValueParameter
0x25a2d3  brtrue.s loc_25A30A
0x25a2d5  ldloc.3
0x25a2d6  ldloc.s  0xE
0x25a2d8  ldelem.ref
0x25a2d9  isinst   [mscorlib]System.Collections.ICollection
0x25a2de  brfalse.s loc_25A30A
0x25a2e0  ldc.i4   0xA4
0x25a2e5  ldnull
0x25a2e6  ldc.i4.2
0x25a2e7  newarr   [mscorlib]System.Object
0x25a2ec  dup
0x25a2ed  ldc.i4.0
0x25a2ee  ldarg.0
0x25a2ef  ldfld    class Microsoft.ReportingServices.ReportProcessing.DataSet RuntimeDataSetNode::m_dataSet
0x25a2f4  callvirt instance string Microsoft.ReportingServices.ReportProcessing.DataSet::get_Name()
0x25a2f9  stelem.ref
0x25a2fa  dup
0x25a2fb  ldc.i4.1
0x25a2fc  ldloc.s  0xF
0x25a2fe  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDataParameter::get_ParameterName()
0x25a303  stelem.ref
0x25a304  newobj   instance void Microsoft.ReportingServices.ReportProcessing.ReportProcessingException::.ctor(valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode code, class [mscorlib]System.Exception innerException, object[] arguments)
0x25a309  throw
0x25a30a  ldloc.s  0x10
0x25a30c  brfalse  loc_25A39A
0x25a311  ldloc.s  0x11
0x25a313  castclass [mscorlib]System.Collections.ICollection
0x25a318  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x25a31d  stloc.s  0x13
0x25a31f  ldc.i4.1
0x25a320  ldloc.s  0x13
0x25a322  bne.un.s loc_25A372
0x25a324  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x25a329  ldloc.s  0x11
0x25a32b  isinst   object[]
0x25a330  ldnull
0x25a331  cgt.un
0x25a333  ldstr    aParamvalueIsOb// "(paramValue is object[])"
0x25a338  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x25a33d  ldloc.s  0xF
0x25a33f  ldloc.s  0x11
0x25a341  isinst   object[]
0x25a346  ldc.i4.0
0x25a347  ldelem.ref
0x25a348  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDataParameter::set_Value(object)
0x25a34d  leave.s  loc_25A3C9
0x25a34f  stloc.s  0x14
0x25a351  ldc.i4   0xA5
0x25a356  ldloc.s  0x14
0x25a358  ldc.i4.1
0x25a359  newarr   [mscorlib]System.Object
0x25a35e  dup
0x25a35f  ldc.i4.0
0x25a360  ldarg.0
0x25a361  ldfld    class Microsoft.ReportingServices.ReportProcessing.DataSource RuntimeDataSetNode::m_dataSource
0x25a366  callvirt instance string Microsoft.ReportingServices.ReportProcessing.DataSource::get_Name()
0x25a36b  stelem.ref
0x25a36c  newobj   instance void Microsoft.ReportingServices.ReportProcessing.ReportProcessingException::.ctor(valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode code, class [mscorlib]System.Exception innerException, object[] arguments)
0x25a371  throw
0x25a372  ldloc.s  0x13
0x25a374  newarr   [mscorlib]System.Object
0x25a379  stloc.s  0x15
0x25a37b  ldloc.s  0x11
0x25a37d  castclass [mscorlib]System.Collections.ICollection
0x25a382  ldloc.s  0x15
0x25a384  ldc.i4.0
0x25a385  callvirt instance void [mscorlib]System.Collections.ICollection::CopyTo(class [mscorlib]System.Array, int32)
0x25a38a  ldloc.s  0xF
0x25a38c  castclass [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDataMultiValueParameter
0x25a391  ldloc.s  0x15
0x25a393  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDataMultiValueParameter::set_Values(object[])
0x25a398  br.s     loc_25A3C9
0x25a39a  nop
0x25a39b  ldloc.s  0xF
0x25a39d  ldloc.s  0x11
0x25a39f  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDataParameter::set_Value(object)
0x25a3a4  leave.s  loc_25A3C9
0x25a3a6  stloc.s  0x16
0x25a3a8  ldc.i4   0xA5
0x25a3ad  ldloc.s  0x16
0x25a3af  ldc.i4.1
0x25a3b0  newarr   [mscorlib]System.Object
0x25a3b5  dup
0x25a3b6  ldc.i4.0
0x25a3b7  ldarg.0
0x25a3b8  ldfld    class Microsoft.ReportingServices.ReportProcessing.DataSource RuntimeDataSetNode::m_dataSource
0x25a3bd  callvirt instance string Microsoft.ReportingServices.ReportProcessing.DataSource::get_Name()
0x25a3c2  stelem.ref
0x25a3c3  newobj   instance void Microsoft.ReportingServices.ReportProcessing.ReportProcessingException::.ctor(valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode code, class [mscorlib]System.Exception innerException, object[] arguments)
0x25a3c8  throw
0x25a3c9  nop
0x25a3ca  ldloc.s  6
0x25a3cc  callvirt instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDataParameterCollection [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbCommand::get_Parameters()
0x25a3d1  ldloc.s  0xF
0x25a3d3  callvirt instance int32 [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDataParameterCollection::Add(class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDataParameter)
0x25a3d8  pop
0x25a3d9  leave.s  loc_25A3FE
0x25a3db  stloc.s  0x17
0x25a3dd  ldc.i4   0xA5
0x25a3e2  ldloc.s  0x17
0x25a3e4  ldc.i4.1
0x25a3e5  newarr   [mscorlib]System.Object
0x25a3ea  dup
0x25a3eb  ldc.i4.0
0x25a3ec  ldarg.0
0x25a3ed  ldfld    class Microsoft.ReportingServices.ReportProcessing.DataSource RuntimeDataSetNode::m_dataSource
0x25a3f2  callvirt instance string Microsoft.ReportingServices.ReportProcessing.DataSource::get_Name()
0x25a3f7  stelem.ref
0x25a3f8  newobj   instance void Microsoft.ReportingServices.ReportProcessing.ReportProcessingException::.ctor(valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode code, class [mscorlib]System.Exception innerException, object[] arguments)
0x25a3fd  throw
0x25a3fe  ldloc.s  0xE
0x25a400  ldc.i4.1
0x25a401  add
0x25a402  stloc.s  0xE
0x25a404  ldloc.s  0xE
0x25a406  ldloc.3
0x25a407  ldlen
0x25a408  conv.i4
0x25a409  blt      loc_25A25E
0x25a40e  ldarg.0
0x25a40f  ldfld    class ProcessingContext RuntimeDataSetNode::m_processingContext
0x25a414  callvirt instance void ProcessingContext::CheckAndThrowIfAborted()
0x25a419  ldarg.0
0x25a41a  ldfld    class Microsoft.ReportingServices.ReportProcessing.DataSet RuntimeDataSetNode::m_dataSet
0x25a41f  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ReportQuery Microsoft.ReportingServices.ReportProcessing.DataSet::get_Query()
0x25a424  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ExpressionInfo Microsoft.ReportingServices.ReportProcessing.ReportQuery::get_CommandText()
0x25a429  brfalse.s loc_25A48D
0x25a42b  ldarg.0
  ... truncated ...
```
