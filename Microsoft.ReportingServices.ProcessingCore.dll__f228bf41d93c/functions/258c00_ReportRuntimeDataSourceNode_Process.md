# ReportRuntimeDataSourceNode::Process

- ea: `0x258c00`
- end: `0x259456`
- name: `ReportRuntimeDataSourceNode::Process`
- size: `2134`
- prototype: ``
- caller_count: `0`
- callee_count: `46`
- tags: `broker_com_uri`

## callees

- `0x175de0`
- `0x1767c0`
- `0x1843f0`
- `0x184410`
- `0x18f700`
- `0x195b60`
- `0x195f30`
- `0x197200`
- `0x197220`
- `0x197240`
- `0x1972e0`
- `0x197420`
- `0x197960`
- `0x197eb0`
- `0x1d08a0`
- `0x1d22e0`
- `0x23fa20`
- `0x23fa30`
- `0x23fa70`
- `0x23faa0`
- `0x23fb30`
- `0x23fb40`
- `0x23fb90`
- `0x23fc30`
- `0x240710`
- `0x240730`
- `0x240770`
- `0x2408d0`
- `0x240910`
- `0x240950`
- `0x2409d0`
- `0x2409e0`
- `0x240bc0`
- `0x240be0`
- `0x240c30`
- `0x258c00`
- `0x259460`
- `0x259510`
- `0x259590`
- `0x2595a0`
- `0x2595b0`
- `0x259670`
- `0x259690`
- `0x25a800`
- `0x25b4f0`
- `0x25b6c0`

## string_xrefs

- `0x259282`: `Data source '{0}': Committing transaction.`
- `0x259194`: `Data source '{0}': Processing of all data sets completed.`
- `0x258e66`: `Data source '{0}': Created a connection.`

## pseudocode

```c

```

## disassembly

```asm
0x258c00  ldarg.0
0x258c01  ldfld    class Microsoft.ReportingServices.ReportProcessing.DataSource RuntimeDataSourceNode::m_dataSource
0x258c06  callvirt instance class Microsoft.ReportingServices.ReportProcessing.DataSetList Microsoft.ReportingServices.ReportProcessing.DataSource::get_DataSets()
0x258c0b  brfalse.s loc_258C20
0x258c0d  ldc.i4.0
0x258c0e  ldarg.0
0x258c0f  ldfld    class Microsoft.ReportingServices.ReportProcessing.DataSource RuntimeDataSourceNode::m_dataSource
0x258c14  callvirt instance class Microsoft.ReportingServices.ReportProcessing.DataSetList Microsoft.ReportingServices.ReportProcessing.DataSource::get_DataSets()
0x258c19  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x258c1e  blt.s    loc_258C21
0x258c20  ret
0x258c21  ldnull
0x258c22  stloc.0
0x258c23  ldnull
0x258c24  stloc.1
0x258c25  ldc.i4.0
0x258c26  stloc.2
0x258c27  ldc.i4.1
0x258c28  stloc.3
0x258c29  ldnull
0x258c2a  stloc.s  4
0x258c2c  ldc.i4.0
0x258c2d  stloc.s  5
0x258c2f  ldc.i4.0
0x258c30  stloc.s  6
0x258c32  ldarg.0
0x258c33  ldfld    class ProcessingContext RuntimeDataSourceNode::m_processingContext
0x258c38  callvirt instance bool ProcessingContext::get_ProcessReportParameters()
0x258c3d  brfalse.s loc_258C7D
0x258c3f  ldarg.0
0x258c40  ldfld    class RuntimeDataSetNodeList RuntimeDataSourceNode::m_runtimeDataSetNodes
0x258c45  ldarg.0
0x258c46  ldfld    class Microsoft.ReportingServices.ReportProcessing.Report RuntimeDataSourceNode::m_report
0x258c4b  ldarg.0
0x258c4c  ldfld    class Microsoft.ReportingServices.ReportProcessing.DataSource RuntimeDataSourceNode::m_dataSource
0x258c51  callvirt instance class Microsoft.ReportingServices.ReportProcessing.DataSetList Microsoft.ReportingServices.ReportProcessing.DataSource::get_DataSets()
0x258c56  ldarg.0
0x258c57  ldfld    int32 RuntimeDataSourceNode::m_dataSetIndex
0x258c5c  callvirt instance class Microsoft.ReportingServices.ReportProcessing.DataSet Microsoft.ReportingServices.ReportProcessing.DataSetList::get_Item(int32 index)
0x258c61  ldarg.0
0x258c62  ldfld    class ProcessingContext RuntimeDataSourceNode::m_processingContext
0x258c67  ldarg.0
0x258c68  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.LegacyReportParameterDataSetCache ReportRuntimeDataSourceNode::m_cache
0x258c6d  newobj   instance void RuntimeReportParametersDataSetNode::.ctor(class Microsoft.ReportingServices.ReportProcessing.Report report, class Microsoft.ReportingServices.ReportProcessing.DataSet dataSet, class ProcessingContext processingContext, class Microsoft.ReportingServices.OnDemandProcessing.LegacyReportParameterDataSetCache aCache)
0x258c72  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x258c77  pop
0x258c78  br       loc_258CFD
0x258c7d  ldarg.0
0x258c7e  ldfld    class Microsoft.ReportingServices.ReportProcessing.DataSource RuntimeDataSourceNode::m_dataSource
0x258c83  callvirt instance class Microsoft.ReportingServices.ReportProcessing.DataSetList Microsoft.ReportingServices.ReportProcessing.DataSource::get_DataSets()
0x258c88  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x258c8d  stloc.3
0x258c8e  ldc.i4.0
0x258c8f  stloc.s  7
0x258c91  br.s     loc_258CF8
0x258c93  ldarg.0
0x258c94  ldfld    class Microsoft.ReportingServices.ReportProcessing.DataSource RuntimeDataSourceNode::m_dataSource
0x258c99  callvirt instance class Microsoft.ReportingServices.ReportProcessing.DataSetList Microsoft.ReportingServices.ReportProcessing.DataSource::get_DataSets()
0x258c9e  ldloc.s  7
0x258ca0  callvirt instance class Microsoft.ReportingServices.ReportProcessing.DataSet Microsoft.ReportingServices.ReportProcessing.DataSetList::get_Item(int32 index)
0x258ca5  stloc.s  4
0x258ca7  ldloc.s  4
0x258ca9  callvirt instance bool Microsoft.ReportingServices.ReportProcessing.DataSet::get_UsedOnlyInParameters()
0x258cae  brtrue.s loc_258CF2
0x258cb0  ldarg.0
0x258cb1  ldfld    bool ReportRuntimeDataSourceNode::m_prefetchDataOnly
0x258cb6  brfalse.s loc_258CCF
0x258cb8  ldarg.0
0x258cb9  ldfld    class Microsoft.ReportingServices.ReportProcessing.Report RuntimeDataSourceNode::m_report
0x258cbe  ldloc.s  4
0x258cc0  ldarg.0
0x258cc1  ldfld    class ProcessingContext RuntimeDataSourceNode::m_processingContext
0x258cc6  newobj   instance void RuntimePrefetchDataSetNode::.ctor(class Microsoft.ReportingServices.ReportProcessing.Report report, class Microsoft.ReportingServices.ReportProcessing.DataSet dataSet, class ProcessingContext processingContext)
0x258ccb  stloc.s  8
0x258ccd  br.s     loc_258CE4
0x258ccf  ldarg.0
0x258cd0  ldfld    class Microsoft.ReportingServices.ReportProcessing.Report RuntimeDataSourceNode::m_report
0x258cd5  ldloc.s  4
0x258cd7  ldarg.0
0x258cd8  ldfld    class ProcessingContext RuntimeDataSourceNode::m_processingContext
0x258cdd  newobj   instance void RuntimeReportDataSetNode::.ctor(class Microsoft.ReportingServices.ReportProcessing.Report report, class Microsoft.ReportingServices.ReportProcessing.DataSet dataSet, class ProcessingContext processingContext)
0x258ce2  stloc.s  8
0x258ce4  ldarg.0
0x258ce5  ldfld    class RuntimeDataSetNodeList RuntimeDataSourceNode::m_runtimeDataSetNodes
0x258cea  ldloc.s  8
0x258cec  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x258cf1  pop
0x258cf2  ldloc.s  7
0x258cf4  ldc.i4.1
0x258cf5  add
0x258cf6  stloc.s  7
0x258cf8  ldloc.s  7
0x258cfa  ldloc.3
0x258cfb  blt.s    loc_258C93
0x258cfd  ldarg.0
0x258cfe  ldfld    class RuntimeDataSetNodeList RuntimeDataSourceNode::m_runtimeDataSetNodes
0x258d03  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x258d08  stloc.3
0x258d09  ldc.i4.0
0x258d0a  ldloc.3
0x258d0b  blt.s    loc_258D15
0x258d0d  ldarg.0
0x258d0e  ldc.i4.0
0x258d0f  stfld    bool RuntimeDataSourceNode::m_noRows
0x258d14  ret
0x258d15  ldarg.0
0x258d16  ldc.i4.1
0x258d17  stfld    bool RuntimeDataSourceNode::m_canAbort
0x258d1c  ldarg.0
0x258d1d  ldfld    class ProcessingContext RuntimeDataSourceNode::m_processingContext
0x258d22  callvirt instance void ProcessingContext::CheckAndThrowIfAborted()
0x258d27  ldloc.3
0x258d28  ldc.i4.1
0x258d29  ble.s    loc_258D58
0x258d2b  ldarg.0
0x258d2c  ldfld    class ProcessingContext RuntimeDataSourceNode::m_processingContext
0x258d31  callvirt instance bool ProcessingContext::get_UserSortFilterProcessing()
0x258d36  brfalse.s loc_258D55
0x258d38  ldarg.0
0x258d39  ldfld    class ProcessingContext RuntimeDataSourceNode::m_processingContext
0x258d3e  callvirt instance unsigned int32 ProcessingContext::get_SubReportLevel()
0x258d43  brfalse.s loc_258D55
0x258d45  ldarg.0
0x258d46  ldfld    class Microsoft.ReportingServices.ReportProcessing.Report RuntimeDataSourceNode::m_report
0x258d4b  callvirt instance bool Microsoft.ReportingServices.ReportProcessing.Report::get_HasUserSortFilter()
0x258d50  ldc.i4.0
0x258d51  ceq
0x258d53  br.s     loc_258D59
0x258d55  ldc.i4.1
0x258d56  br.s     loc_258D59
0x258d58  ldc.i4.0
0x258d59  stloc.s  9
0x258d5b  ldarg.0
0x258d5c  ldfld    class ProcessingContext RuntimeDataSourceNode::m_processingContext
0x258d61  callvirt instance bool ProcessingContext::get_SnapshotProcessing()
0x258d66  brtrue   loc_258F44
0x258d6b  ldarg.0
0x258d6c  ldfld    class ProcessingContext RuntimeDataSourceNode::m_processingContext
0x258d71  callvirt instance bool ProcessingContext::get_ProcessWithCachedData()
0x258d76  brtrue   loc_258F44
0x258d7b  ldarg.0
0x258d7c  ldfld    class Microsoft.ReportingServices.ReportProcessing.DataSource RuntimeDataSourceNode::m_dataSource
0x258d81  callvirt instance bool Microsoft.ReportingServices.ReportProcessing.DataSource::get_Transaction()
0x258d86  brfalse.s loc_258DC1
0x258d88  ldarg.0
0x258d89  ldfld    bool ReportRuntimeDataSourceNode::m_mergeTran
0x258d8e  brfalse.s loc_258DC1
0x258d90  ldarg.0
0x258d91  ldfld    class ProcessingContext RuntimeDataSourceNode::m_processingContext
0x258d96  callvirt instance class DataSourceInfoHashtable ProcessingContext::get_GlobalDataSourceInfo()
0x258d9b  ldarg.0
0x258d9c  ldfld    class Microsoft.ReportingServices.ReportProcessing.DataSource RuntimeDataSourceNode::m_dataSource
0x258da1  callvirt instance string Microsoft.ReportingServices.ReportProcessing.DataSource::get_Name()
0x258da6  callvirt instance class DataSourceInfo DataSourceInfoHashtable::get_Item(string dataSourceName)
0x258dab  stloc.s  0xE
0x258dad  ldloc.s  0xE
0x258daf  brfalse.s loc_258DC1
0x258db1  ldloc.s  0xE
0x258db3  callvirt instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbConnection DataSourceInfo::get_Connection()
0x258db8  stloc.0
0x258db9  ldloc.s  0xE
0x258dbb  callvirt instance class TransactionInfo DataSourceInfo::get_TransactionInfo()
0x258dc0  stloc.1
0x258dc1  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x258dc6  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x258dcb  brfalse.s loc_258E1B
0x258dcd  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x258dd2  ldc.i4.4
0x258dd3  ldstr    aDataSource0Tra// "Data source '{0}': Transaction = {1}, M"...
0x258dd8  ldc.i4.4
0x258dd9  newarr   [mscorlib]System.Object
0x258dde  dup
0x258ddf  ldc.i4.0
0x258de0  ldarg.0
0x258de1  ldfld    class Microsoft.ReportingServices.ReportProcessing.DataSource RuntimeDataSourceNode::m_dataSource
0x258de6  callvirt instance string Microsoft.ReportingServices.ReportProcessing.DataSource::get_Name()
0x258deb  stelem.ref
0x258dec  dup
0x258ded  ldc.i4.1
0x258dee  ldarg.0
0x258def  ldfld    class Microsoft.ReportingServices.ReportProcessing.DataSource RuntimeDataSourceNode::m_dataSource
0x258df4  callvirt instance bool Microsoft.ReportingServices.ReportProcessing.DataSource::get_Transaction()
0x258df9  box      [mscorlib]System.Boolean
0x258dfe  stelem.ref
0x258dff  dup
0x258e00  ldc.i4.2
0x258e01  ldarg.0
0x258e02  ldfld    bool ReportRuntimeDataSourceNode::m_mergeTran
0x258e07  box      [mscorlib]System.Boolean
0x258e0c  stelem.ref
0x258e0d  dup
0x258e0e  ldc.i4.3
0x258e0f  ldloc.3
0x258e10  box      [mscorlib]System.Int32
0x258e15  stelem.ref
0x258e16  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x258e1b  ldloc.0
0x258e1c  brtrue.s loc_258E86
0x258e1e  ldarg.0
0x258e1f  ldfld    class ProcessingContext RuntimeDataSourceNode::m_processingContext
0x258e24  castclass ReportProcessingContext
0x258e29  stloc.s  0xF
0x258e2b  ldarg.0
0x258e2c  ldfld    class Microsoft.ReportingServices.ReportProcessing.DataSource RuntimeDataSourceNode::m_dataSource
0x258e31  ldloc.s  0xF
0x258e33  ldloca.s 0x10
0x258e35  callvirt instance string Microsoft.ReportingServices.ReportProcessing.DataSource::ResolveConnectionString(class ReportProcessingContext pc, [out] class Microsoft.ReportingServices.DataExtensions.DataSourceInfo& dataSourceInfo)
0x258e3a  stloc.s  0x11
0x258e3c  ldloc.s  0xF
0x258e3e  callvirt instance class Microsoft.ReportingServices.ReportProcessing.IProcessingDataExtensionConnection ProcessingContext::get_DataExtensionConnection()
0x258e43  ldarg.0
0x258e44  ldfld    class Microsoft.ReportingServices.ReportProcessing.DataSource RuntimeDataSourceNode::m_dataSource
0x258e49  ldloc.s  0x11
0x258e4b  ldloc.s  0x10
0x258e4d  ldnull
0x258e4e  callvirt instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbConnection Microsoft.ReportingServices.ReportProcessing.IProcessingDataExtensionConnection::OpenDataSourceExtensionConnection(class Microsoft.ReportingServices.ReportProcessing.IProcessingDataSource dataSource, string connectionString, class Microsoft.ReportingServices.DataExtensions.DataSourceInfo dataSourceInfo, string datasetName)
0x258e53  stloc.0
0x258e54  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x258e59  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x258e5e  brfalse.s loc_258E84
0x258e60  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x258e65  ldc.i4.4
0x258e66  ldstr    aDataSource0Cre// "Data source '{0}': Created a connection"...
0x258e6b  ldc.i4.1
0x258e6c  newarr   [mscorlib]System.Object
0x258e71  dup
0x258e72  ldc.i4.0
0x258e73  ldarg.0
0x258e74  ldfld    class Microsoft.ReportingServices.ReportProcessing.DataSource RuntimeDataSourceNode::m_dataSource
0x258e79  callvirt instance string Microsoft.ReportingServices.ReportProcessing.DataSource::get_Name()
0x258e7e  stelem.ref
0x258e7f  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x258e84  ldc.i4.1
0x258e85  stloc.2
0x258e86  ldarg.0
0x258e87  ldfld    class Microsoft.ReportingServices.ReportProcessing.DataSource RuntimeDataSourceNode::m_dataSource
0x258e8c  callvirt instance bool Microsoft.ReportingServices.ReportProcessing.DataSource::get_Transaction()
0x258e91  brfalse  loc_258F44
0x258e96  ldloc.1
0x258e97  brtrue.s loc_258EDC
0x258e99  ldloc.0
0x258e9a  callvirt instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbTransaction [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbConnection::BeginTransaction()
0x258e9f  stloc.s  0x13
0x258ea1  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x258ea6  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x258eab  brfalse.s loc_258ED1
0x258ead  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x258eb2  ldc.i4.4
0x258eb3  ldstr    aDataSource0Beg// "Data source '{0}': Begun a transaction."
0x258eb8  ldc.i4.1
0x258eb9  newarr   [mscorlib]System.Object
0x258ebe  dup
0x258ebf  ldc.i4.0
0x258ec0  ldarg.0
0x258ec1  ldfld    class Microsoft.ReportingServices.ReportProcessing.DataSource RuntimeDataSourceNode::m_dataSource
0x258ec6  callvirt instance string Microsoft.ReportingServices.ReportProcessing.DataSource::get_Name()
0x258ecb  stelem.ref
0x258ecc  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x258ed1  ldloc.s  0x13
0x258ed3  newobj   instance void TransactionInfo::.ctor(class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbTransaction transaction)
0x258ed8  stloc.1
0x258ed9  ldc.i4.1
0x258eda  stloc.s  5
0x258edc  ldloc.1
0x258edd  callvirt instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbTransaction TransactionInfo::get_Transaction()
0x258ee2  isinst   [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbTransactionExtension
0x258ee7  stloc.s  0x12
0x258ee9  ldloc.s  0x12
0x258eeb  brfalse.s loc_258EF6
0x258eed  ldloc.s  0x12
0x258eef  callvirt instance bool [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbTransactionExtension::get_AllowMultiConnection()
0x258ef4  br.s     loc_258EF7
0x258ef6  ldc.i4.0
0x258ef7  stloc.s  6
0x258ef9  ldloc.s  9
0x258efb  ldloc.s  6
0x258efd  and
0x258efe  stloc.s  9
0x258f00  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x258f05  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x258f0a  brfalse.s loc_258F44
0x258f0c  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x258f11  ldc.i4.4
0x258f12  ldstr    aDataSource0Tra_0// "Data source '{0}': TransactionCanSpanCo"...
0x258f17  ldc.i4.3
0x258f18  newarr   [mscorlib]System.Object
0x258f1d  dup
0x258f1e  ldc.i4.0
0x258f1f  ldarg.0
0x258f20  ldfld    class Microsoft.ReportingServices.ReportProcessing.DataSource RuntimeDataSourceNode::m_dataSource
0x258f25  callvirt instance string Microsoft.ReportingServices.ReportProcessing.DataSource::get_Name()
0x258f2a  stelem.ref
0x258f2b  dup
0x258f2c  ldc.i4.1
0x258f2d  ldloc.s  6
0x258f2f  box      [mscorlib]System.Boolean
0x258f34  stelem.ref
0x258f35  dup
0x258f36  ldc.i4.2
0x258f37  ldloc.s  9
  ... truncated ...
```
