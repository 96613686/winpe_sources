# Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSource::OpenInitialConnectionAndTransaction

- ea: `0x1f6860`
- end: `0x1f6aef`
- name: `Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSource::OpenInitialConnectionAndTransaction`
- size: `655`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callers

- `0x1f6390`

## callees

- `0x113200`
- `0x113220`
- `0x121d20`
- `0x1f6620`
- `0x1f6860`
- `0x1f6af0`
- `0x1f6b90`
- `0x1f7b60`
- `0x1fb620`
- `0x1fb650`
- `0x23fa20`
- `0x23fa30`
- `0x23fa70`
- `0x23faa0`
- `0x23fb30`
- `0x23fb40`

## string_xrefs

- `0x1f6949`: `Data source '{0}': Created a connection.`

## pseudocode

```c

```

## disassembly

```asm
0x1f6860  ldarg.0
0x1f6861  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.DataSource Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSource::m_dataSource
0x1f6866  callvirt instance bool Microsoft.ReportingServices.ReportIntermediateFormat.DataSource::get_Transaction()
0x1f686b  brfalse.s loc_1F68AC
0x1f686d  ldarg.0
0x1f686e  ldfld    bool Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSource::m_mergeTran
0x1f6873  brfalse.s loc_1F68AC
0x1f6875  ldarg.0
0x1f6876  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSource::m_odpContext
0x1f687b  callvirt instance class DataSourceInfoHashtable Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::get_GlobalDataSourceInfo()
0x1f6880  ldarg.0
0x1f6881  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.DataSource Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSource::m_dataSource
0x1f6886  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.DataSource::get_Name()
0x1f688b  callvirt instance class DataSourceInfo DataSourceInfoHashtable::get_Item(string dataSourceName)
0x1f6890  stloc.1
0x1f6891  ldloc.1
0x1f6892  brfalse.s loc_1F68AC
0x1f6894  ldarg.0
0x1f6895  ldloc.1
0x1f6896  callvirt instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbConnection DataSourceInfo::get_Connection()
0x1f689b  stfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbConnection Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSource::m_connection
0x1f68a0  ldarg.0
0x1f68a1  ldloc.1
0x1f68a2  callvirt instance class TransactionInfo DataSourceInfo::get_TransactionInfo()
0x1f68a7  stfld    class TransactionInfo Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSource::m_transaction
0x1f68ac  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1f68b1  ldc.i4.4
0x1f68b2  ldstr    aDataSource0Tra// "Data source '{0}': Transaction = {1}, M"...
0x1f68b7  ldc.i4.4
0x1f68b8  newarr   [mscorlib]System.Object
0x1f68bd  dup
0x1f68be  ldc.i4.0
0x1f68bf  ldarg.0
0x1f68c0  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.DataSource Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSource::m_dataSource
0x1f68c5  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.DataSource::get_Name()
0x1f68ca  stelem.ref
0x1f68cb  dup
0x1f68cc  ldc.i4.1
0x1f68cd  ldarg.0
0x1f68ce  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.DataSource Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSource::m_dataSource
0x1f68d3  callvirt instance bool Microsoft.ReportingServices.ReportIntermediateFormat.DataSource::get_Transaction()
0x1f68d8  box      [mscorlib]System.Boolean
0x1f68dd  stelem.ref
0x1f68de  dup
0x1f68df  ldc.i4.2
0x1f68e0  ldarg.0
0x1f68e1  ldfld    bool Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSource::m_mergeTran
0x1f68e6  box      [mscorlib]System.Boolean
0x1f68eb  stelem.ref
0x1f68ec  dup
0x1f68ed  ldc.i4.3
0x1f68ee  ldarg.0
0x1f68ef  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSet> Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSource::m_runtimeDataSets
0x1f68f4  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSet>::get_Count()
0x1f68f9  box      [mscorlib]System.Int32
0x1f68fe  stelem.ref
0x1f68ff  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x1f6904  ldarg.0
0x1f6905  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbConnection Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSource::m_connection
0x1f690a  brtrue.s loc_1F6967
0x1f690c  ldarg.0
0x1f690d  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSet> Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSource::m_runtimeDataSets
0x1f6912  ldc.i4.0
0x1f6913  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSet>::get_Item(!!T0)
0x1f6918  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.DataSet Microsoft.ReportingServices.OnDemandProcessing.RuntimeLiveQueryExecutor::get_DataSet()
0x1f691d  stloc.2
0x1f691e  ldarg.0
0x1f691f  ldarg.0
0x1f6920  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.DataSource Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSource::m_dataSource
0x1f6925  ldloc.2
0x1f6926  ldarg.0
0x1f6927  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSource::m_odpContext
0x1f692c  ldarg.0
0x1f692d  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.DataProcessingMetrics Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSource::m_executionMetrics
0x1f6932  call     class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbConnection Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSource::OpenConnection(class Microsoft.ReportingServices.ReportIntermediateFormat.DataSource dataSourceObj, class Microsoft.ReportingServices.ReportIntermediateFormat.DataSet dataSetObj, class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext pc, class Microsoft.ReportingServices.OnDemandProcessing.DataProcessingMetrics metrics)
0x1f6937  stfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbConnection Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSource::m_connection
0x1f693c  ldarg.0
0x1f693d  ldc.i4.1
0x1f693e  stfld    bool Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSource::m_needToCloseConnection
0x1f6943  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1f6948  ldc.i4.4
0x1f6949  ldstr    aDataSource0Cre// "Data source '{0}': Created a connection"...
0x1f694e  ldc.i4.1
0x1f694f  newarr   [mscorlib]System.Object
0x1f6954  dup
0x1f6955  ldc.i4.0
0x1f6956  ldarg.0
0x1f6957  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.DataSource Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSource::m_dataSource
0x1f695c  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.DataSource::get_Name()
0x1f6961  stelem.ref
0x1f6962  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x1f6967  ldc.i4.0
0x1f6968  stloc.0
0x1f6969  ldarg.0
0x1f696a  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.DataSource Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSource::m_dataSource
0x1f696f  callvirt instance bool Microsoft.ReportingServices.ReportIntermediateFormat.DataSource::get_Transaction()
0x1f6974  brfalse  loc_1F6A2D
0x1f6979  ldarg.0
0x1f697a  ldfld    class TransactionInfo Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSource::m_transaction
0x1f697f  brtrue.s loc_1F69C6
0x1f6981  ldarg.0
0x1f6982  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbConnection Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSource::m_connection
0x1f6987  callvirt instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbTransaction [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbConnection::BeginTransaction()
0x1f698c  stloc.s  4
0x1f698e  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1f6993  ldc.i4.4
0x1f6994  ldstr    aDataSource0Beg// "Data source '{0}': Begun a transaction."
0x1f6999  ldc.i4.1
0x1f699a  newarr   [mscorlib]System.Object
0x1f699f  dup
0x1f69a0  ldc.i4.0
0x1f69a1  ldarg.0
0x1f69a2  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.DataSource Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSource::m_dataSource
0x1f69a7  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.DataSource::get_Name()
0x1f69ac  stelem.ref
0x1f69ad  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x1f69b2  ldarg.0
0x1f69b3  ldloc.s  4
0x1f69b5  newobj   instance void TransactionInfo::.ctor(class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbTransaction transaction)
0x1f69ba  stfld    class TransactionInfo Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSource::m_transaction
0x1f69bf  ldarg.0
0x1f69c0  ldc.i4.1
0x1f69c1  stfld    bool Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSource::m_isTransactionOwner
0x1f69c6  ldarg.0
0x1f69c7  ldfld    class TransactionInfo Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSource::m_transaction
0x1f69cc  callvirt instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbTransaction TransactionInfo::get_Transaction()
0x1f69d1  isinst   [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbTransactionExtension
0x1f69d6  stloc.3
0x1f69d7  ldloc.3
0x1f69d8  brfalse.s loc_1F69E2
0x1f69da  ldloc.3
0x1f69db  callvirt instance bool [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbTransactionExtension::get_AllowMultiConnection()
0x1f69e0  br.s     loc_1F69E3
0x1f69e2  ldc.i4.0
0x1f69e3  stloc.0
0x1f69e4  ldarg.0
0x1f69e5  ldarg.0
0x1f69e6  ldfld    bool Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSource::m_useConcurrentDataSetProcessing
0x1f69eb  ldloc.0
0x1f69ec  and
0x1f69ed  stfld    bool Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSource::m_useConcurrentDataSetProcessing
0x1f69f2  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1f69f7  ldc.i4.4
0x1f69f8  ldstr    aDataSource0Tra_0// "Data source '{0}': TransactionCanSpanCo"...
0x1f69fd  ldc.i4.3
0x1f69fe  newarr   [mscorlib]System.Object
0x1f6a03  dup
0x1f6a04  ldc.i4.0
0x1f6a05  ldarg.0
0x1f6a06  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.DataSource Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSource::m_dataSource
0x1f6a0b  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.DataSource::get_Name()
0x1f6a10  stelem.ref
0x1f6a11  dup
0x1f6a12  ldc.i4.1
0x1f6a13  ldloc.0
0x1f6a14  box      [mscorlib]System.Boolean
0x1f6a19  stelem.ref
0x1f6a1a  dup
0x1f6a1b  ldc.i4.2
0x1f6a1c  ldarg.0
0x1f6a1d  ldfld    bool Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSource::m_useConcurrentDataSetProcessing
0x1f6a22  box      [mscorlib]System.Boolean
0x1f6a27  stelem.ref
0x1f6a28  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x1f6a2d  ldarg.0
0x1f6a2e  ldarg.0
0x1f6a2f  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbConnection Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSource::m_connection
0x1f6a34  call     instance void Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSource::MergeAutoCollationSettings(class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbConnection connection)
0x1f6a39  ldarg.0
0x1f6a3a  ldfld    bool Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSource::m_isTransactionOwner
0x1f6a3f  brfalse  loc_1F6AEE
0x1f6a44  ldarg.0
0x1f6a45  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Report Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSource::m_report
0x1f6a4a  callvirt instance bool Microsoft.ReportingServices.ReportIntermediateFormat.Report::get_SubReportMergeTransactions()
0x1f6a4f  brfalse  loc_1F6AEE
0x1f6a54  ldarg.0
0x1f6a55  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSource::m_odpContext
0x1f6a5a  callvirt instance bool Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::get_ProcessReportParameters()
0x1f6a5f  brtrue   loc_1F6AEE
0x1f6a64  ldloc.0
0x1f6a65  brfalse.s loc_1F6A73
0x1f6a67  ldnull
0x1f6a68  stloc.s  5
0x1f6a6a  ldarg.0
0x1f6a6b  ldc.i4.0
0x1f6a6c  stfld    bool Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSource::m_isGlobalConnection
0x1f6a71  br.s     loc_1F6A82
0x1f6a73  ldarg.0
0x1f6a74  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbConnection Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSource::m_connection
0x1f6a79  stloc.s  5
0x1f6a7b  ldarg.0
0x1f6a7c  ldc.i4.1
0x1f6a7d  stfld    bool Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSource::m_isGlobalConnection
0x1f6a82  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1f6a87  ldc.i4.4
0x1f6a88  ldstr    aDataSource0Sto// "Data source '{0}': Storing trans+conn i"...
0x1f6a8d  ldc.i4.2
0x1f6a8e  newarr   [mscorlib]System.Object
0x1f6a93  dup
0x1f6a94  ldc.i4.0
0x1f6a95  ldarg.0
0x1f6a96  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.DataSource Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSource::m_dataSource
0x1f6a9b  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.DataSource::get_Name()
0x1f6aa0  stelem.ref
0x1f6aa1  dup
0x1f6aa2  ldc.i4.1
0x1f6aa3  ldarg.0
0x1f6aa4  ldfld    bool Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSource::m_needToCloseConnection
0x1f6aa9  box      [mscorlib]System.Boolean
0x1f6aae  stelem.ref
0x1f6aaf  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x1f6ab4  ldarg.0
0x1f6ab5  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.DataSource Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSource::m_dataSource
0x1f6aba  ldarg.0
0x1f6abb  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSource::m_odpContext
0x1f6ac0  call     class Microsoft.ReportingServices.DataExtensions.DataSourceInfo Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSource::GetDataSourceInfo(class Microsoft.ReportingServices.ReportIntermediateFormat.DataSource dataSource, class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext processingContext)
0x1f6ac5  stloc.s  6
0x1f6ac7  ldarg.0
0x1f6ac8  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSource::m_odpContext
0x1f6acd  callvirt instance class DataSourceInfoHashtable Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::get_GlobalDataSourceInfo()
0x1f6ad2  ldarg.0
0x1f6ad3  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.DataSource Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSource::m_dataSource
0x1f6ad8  ldloc.s  5
0x1f6ada  ldarg.0
0x1f6adb  ldfld    class TransactionInfo Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSource::m_transaction
0x1f6ae0  ldloc.s  6
0x1f6ae2  callvirt instance void DataSourceInfoHashtable::Add(class Microsoft.ReportingServices.ReportProcessing.IProcessingDataSource procDataSource, class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbConnection connection, class TransactionInfo transInfo, class Microsoft.ReportingServices.DataExtensions.DataSourceInfo dataExtDataSourceInfo)
0x1f6ae7  ldarg.0
0x1f6ae8  ldc.i4.1
0x1f6ae9  stfld    bool Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSource::m_isGlobalTransaction
0x1f6aee  ret
```
