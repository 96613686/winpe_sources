# Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSource::OpenConnection

- ea: `0x1f6b90`
- end: `0x1f6c38`
- name: `Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSource::OpenConnection`
- size: `168`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x1f6860`
- `0x1f7c20`

## callees

- `0x113200`
- `0x1134b0`
- `0x114be0`
- `0x175de0`
- `0x1843f0`
- `0x184430`
- `0x1f6b90`
- `0x1f9200`
- `0x1f9270`
- `0x1f9310`
- `0x1fb210`
- `0x1fb430`

## string_xrefs

- `0x1f6c12`: `Opening a connection for DataSource: {0} took {1} ms.`

## pseudocode

```c

```

## disassembly

```asm
0x1f6b90  ldnull
0x1f6b91  stloc.0
0x1f6b92  ldarg.3
0x1f6b93  ldc.i4.3
0x1f6b94  callvirt instance void Microsoft.ReportingServices.OnDemandProcessing.DataProcessingMetrics::StartTimer(valuetype MetricType type)
0x1f6b99  ldnull
0x1f6b9a  stloc.1
0x1f6b9b  ldnull
0x1f6b9c  stloc.2
0x1f6b9d  ldarg.2
0x1f6b9e  callvirt instance class Microsoft.ReportingServices.ReportProcessing.IProcessingDataExtensionConnection Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::get_CreateAndSetupDataExtensionFunction()
0x1f6ba3  callvirt instance bool Microsoft.ReportingServices.ReportProcessing.IProcessingDataExtensionConnection::get_MustResolveSharedDataSources()
0x1f6ba8  brfalse.s loc_1F6BC3
0x1f6baa  ldarg.0
0x1f6bab  ldarg.2
0x1f6bac  ldloca.s 1
0x1f6bae  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.DataSource::ResolveConnectionString(class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext pc, [out] class Microsoft.ReportingServices.DataExtensions.DataSourceInfo& dataSourceInfo)
0x1f6bb3  stloc.2
0x1f6bb4  ldarg.2
0x1f6bb5  callvirt instance bool Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::get_UseVerboseExecutionLogging()
0x1f6bba  brfalse.s loc_1F6BC3
0x1f6bbc  ldarg.3
0x1f6bbd  ldloc.2
0x1f6bbe  callvirt instance void Microsoft.ReportingServices.OnDemandProcessing.DataProcessingMetrics::set_ResolvedConnectionString(string value)
0x1f6bc3  ldarg.2
0x1f6bc4  callvirt instance class Microsoft.ReportingServices.ReportProcessing.IProcessingDataExtensionConnection Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::get_CreateAndSetupDataExtensionFunction()
0x1f6bc9  ldarg.0
0x1f6bca  ldloc.2
0x1f6bcb  ldloc.1
0x1f6bcc  ldarg.1
0x1f6bcd  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.DataSet::get_Name()
0x1f6bd2  callvirt instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbConnection Microsoft.ReportingServices.ReportProcessing.IProcessingDataExtensionConnection::OpenDataSourceExtensionConnection(class Microsoft.ReportingServices.ReportProcessing.IProcessingDataSource dataSource, string connectionString, class Microsoft.ReportingServices.DataExtensions.DataSourceInfo dataSourceInfo, string datasetName)
0x1f6bd7  stloc.0
0x1f6bd8  leave.s  loc_1F6C36
0x1f6bda  pop
0x1f6bdb  rethrow
0x1f6bdd  stloc.3
0x1f6bde  ldloc.3
0x1f6bdf  call     bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Common.AsynchronousExceptionDetection::IsStoppingException(class [mscorlib]System.Exception)
0x1f6be4  brfalse.s loc_1F6BE8
0x1f6be6  rethrow
0x1f6be8  ldc.i4   0x99
0x1f6bed  ldloc.3
0x1f6bee  ldc.i4.1
0x1f6bef  newarr   [mscorlib]System.Object
0x1f6bf4  dup
0x1f6bf5  ldc.i4.0
0x1f6bf6  ldarg.0
0x1f6bf7  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.DataSource::get_Name()
0x1f6bfc  stelem.ref
0x1f6bfd  newobj   instance void Microsoft.ReportingServices.ReportProcessing.ReportProcessingException::.ctor(valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode code, class [mscorlib]System.Exception innerException, object[] arguments)
0x1f6c02  throw
0x1f6c03  ldarg.3
0x1f6c04  ldc.i4.3
0x1f6c05  callvirt instance int64 Microsoft.ReportingServices.OnDemandProcessing.DataProcessingMetrics::RecordTimerMeasurementWithUpdatedTotal(valuetype MetricType type)
0x1f6c0a  stloc.s  4
0x1f6c0c  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1f6c11  ldc.i4.4
0x1f6c12  ldstr    aOpeningAConnec// "Opening a connection for DataSource: {0"...
0x1f6c17  ldc.i4.2
0x1f6c18  newarr   [mscorlib]System.Object
0x1f6c1d  dup
0x1f6c1e  ldc.i4.0
0x1f6c1f  ldarg.0
0x1f6c20  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.DataSource::get_Name()
0x1f6c25  stelem.ref
0x1f6c26  dup
0x1f6c27  ldc.i4.1
0x1f6c28  ldloc.s  4
0x1f6c2a  box      [mscorlib]System.Int64
0x1f6c2f  stelem.ref
0x1f6c30  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x1f6c35  endfinally
0x1f6c36  ldloc.0
0x1f6c37  ret
```
