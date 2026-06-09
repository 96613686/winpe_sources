# Microsoft.ReportingServices.OnDemandProcessing.RuntimeLiveQueryExecutor::ExecuteReader

- ea: `0x1f7de0`
- end: `0x1f7f2c`
- name: `Microsoft.ReportingServices.OnDemandProcessing.RuntimeLiveQueryExecutor::ExecuteReader`
- size: `332`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x1f7c20`

## callees

- `0x1340`
- `0x114be0`
- `0x175de0`
- `0x175e50`
- `0x176250`
- `0x176280`
- `0x1f3240`
- `0x1f3280`
- `0x1f7de0`
- `0x1f7f30`
- `0x1f9200`
- `0x1f9230`
- `0x1fb9e0`

## string_xrefs

- `0x1f7f01`: `The source data reader is null. Cannot read results.`

## pseudocode

```c

```

## disassembly

```asm
0x1f7de0  ldnull
0x1f7de1  stloc.0
0x1f7de2  ldarg.1
0x1f7de3  brfalse.s loc_1F7DF1
0x1f7de5  ldarg.1
0x1f7de6  ldarg.0
0x1f7de7  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbCommand Microsoft.ReportingServices.OnDemandProcessing.RuntimeLiveQueryExecutor::m_commandWrappedForCancel
0x1f7dec  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IJobContext::AddCommand(class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbCommand)
0x1f7df1  ldarg.0
0x1f7df2  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.DataProcessingMetrics Microsoft.ReportingServices.OnDemandProcessing.RuntimeLiveQueryExecutor::m_executionMetrics
0x1f7df7  ldc.i4.0
0x1f7df8  callvirt instance void Microsoft.ReportingServices.OnDemandProcessing.DataProcessingMetrics::StartTimer(valuetype MetricType type)
0x1f7dfd  ldarg.0
0x1f7dfe  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbCommand Microsoft.ReportingServices.OnDemandProcessing.RuntimeLiveQueryExecutor::m_command
0x1f7e03  ldc.i4.1
0x1f7e04  callvirt instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDataReader [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbCommand::ExecuteReader(valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.CommandBehavior)
0x1f7e09  stloc.0
0x1f7e0a  leave    loc_1F7EEC
0x1f7e0f  stloc.1
0x1f7e10  ldarg.0
0x1f7e11  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.OnDemandProcessing.RuntimeLiveQueryExecutor::m_odpContext
0x1f7e16  callvirt instance valuetype Mode Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::get_ContextMode()
0x1f7e1b  ldc.i4.1
0x1f7e1c  bne.un   loc_1F7EAE
0x1f7e21  ldc.i4.0
0x1f7e22  stloc.2
0x1f7e23  ldarg.2
0x1f7e24  brfalse.s loc_1F7E31
0x1f7e26  ldarg.2
0x1f7e27  ldloc.1
0x1f7e28  ldloca.s 2
0x1f7e2a  callvirt instance bool Microsoft.ReportingServices.OnDemandProcessing.DataSourceErrorInspector::TryInterpretProviderErrorCode(class [mscorlib]System.Exception e, [out] valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode& errorCode)
0x1f7e2f  br.s     loc_1F7E32
0x1f7e31  ldc.i4.0
0x1f7e32  stloc.3
0x1f7e33  ldarg.0
0x1f7e34  ldloc.1
0x1f7e35  ldarg.3
0x1f7e36  ldloc.3
0x1f7e37  brtrue.s loc_1F7E45
0x1f7e39  ldloca.s 4
0x1f7e3b  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode>
0x1f7e41  ldloc.s  4
0x1f7e43  br.s     loc_1F7E4B
0x1f7e45  ldloc.2
0x1f7e46  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode>::.ctor(var<u1>)
0x1f7e4b  call     instance void Microsoft.ReportingServices.OnDemandProcessing.RuntimeLiveQueryExecutor::TraceExecuteReaderFailed(class [mscorlib]System.Exception e, string commandText, valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode> specificErrorCode)
0x1f7e50  ldloc.3
0x1f7e51  brfalse.s loc_1F7E82
0x1f7e53  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x1f7e58  call     string RPRes::get_rsErrorExecutingCommand()
0x1f7e5d  ldarg.0
0x1f7e5e  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.DataSet Microsoft.ReportingServices.OnDemandProcessing.RuntimeLiveQueryExecutor::m_dataSet
0x1f7e63  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.DataSet::get_Name()
0x1f7e68  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x1f7e6d  stloc.s  5
0x1f7e6f  ldloc.2
0x1f7e70  ldloc.1
0x1f7e71  ldc.i4.1
0x1f7e72  newarr   [mscorlib]System.Object
0x1f7e77  dup
0x1f7e78  ldc.i4.0
0x1f7e79  ldloc.s  5
0x1f7e7b  stelem.ref
0x1f7e7c  newobj   instance void Microsoft.ReportingServices.ReportProcessing.ReportProcessingQueryException::.ctor(valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode errorCode, class [mscorlib]System.Exception innerException, object[] arguments)
0x1f7e81  throw
0x1f7e82  ldarg.2
0x1f7e83  brfalse.s loc_1F7EAE
0x1f7e85  ldarg.2
0x1f7e86  ldloc.1
0x1f7e87  callvirt instance bool Microsoft.ReportingServices.OnDemandProcessing.DataSourceErrorInspector::IsOnPremiseServiceException(class [mscorlib]System.Exception e)
0x1f7e8c  brfalse.s loc_1F7EAE
0x1f7e8e  ldc.i4   0xAA
0x1f7e93  ldloc.1
0x1f7e94  ldc.i4.1
0x1f7e95  newarr   [mscorlib]System.Object
0x1f7e9a  dup
0x1f7e9b  ldc.i4.0
0x1f7e9c  ldarg.0
0x1f7e9d  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.DataSet Microsoft.ReportingServices.OnDemandProcessing.RuntimeLiveQueryExecutor::m_dataSet
0x1f7ea2  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.DataSet::get_Name()
0x1f7ea7  stelem.ref
0x1f7ea8  newobj   instance void Microsoft.ReportingServices.ReportProcessing.ReportProcessingQueryOnPremiseServiceException::.ctor(valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode errorCode, class [mscorlib]System.Exception innerException, object[] arguments)
0x1f7ead  throw
0x1f7eae  ldc.i4   0xAA
0x1f7eb3  ldloc.1
0x1f7eb4  ldc.i4.1
0x1f7eb5  newarr   [mscorlib]System.Object
0x1f7eba  dup
0x1f7ebb  ldc.i4.0
0x1f7ebc  ldarg.0
0x1f7ebd  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.DataSet Microsoft.ReportingServices.OnDemandProcessing.RuntimeLiveQueryExecutor::m_dataSet
0x1f7ec2  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.DataSet::get_Name()
0x1f7ec7  stelem.ref
0x1f7ec8  newobj   instance void Microsoft.ReportingServices.ReportProcessing.ReportProcessingException::.ctor(valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode code, class [mscorlib]System.Exception innerException, object[] arguments)
0x1f7ecd  throw
0x1f7ece  ldarg.0
0x1f7ecf  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.DataProcessingMetrics Microsoft.ReportingServices.OnDemandProcessing.RuntimeLiveQueryExecutor::m_executionMetrics
0x1f7ed4  ldc.i4.0
0x1f7ed5  callvirt instance int64 Microsoft.ReportingServices.OnDemandProcessing.DataProcessingMetrics::RecordTimerMeasurement(valuetype MetricType type)
0x1f7eda  pop
0x1f7edb  endfinally
0x1f7edc  ldarg.1
0x1f7edd  brfalse.s loc_1F7EEB
0x1f7edf  ldarg.1
0x1f7ee0  ldarg.0
0x1f7ee1  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbCommand Microsoft.ReportingServices.OnDemandProcessing.RuntimeLiveQueryExecutor::m_commandWrappedForCancel
0x1f7ee6  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IJobContext::RemoveCommand(class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbCommand)
0x1f7eeb  endfinally
0x1f7eec  ldloc.0
0x1f7eed  brtrue.s loc_1F7F2A
0x1f7eef  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1f7ef4  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x1f7ef9  brfalse.s loc_1F7F0B
0x1f7efb  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1f7f00  ldc.i4.1
0x1f7f01  ldstr    aTheSourceDataR// "The source data reader is null. Cannot "...
0x1f7f06  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x1f7f0b  ldc.i4   0xAB
0x1f7f10  ldc.i4.1
0x1f7f11  newarr   [mscorlib]System.Object
0x1f7f16  dup
0x1f7f17  ldc.i4.0
0x1f7f18  ldarg.0
0x1f7f19  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.DataSet Microsoft.ReportingServices.OnDemandProcessing.RuntimeLiveQueryExecutor::m_dataSet
0x1f7f1e  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.DataSet::get_Name()
0x1f7f23  stelem.ref
0x1f7f24  newobj   instance void Microsoft.ReportingServices.ReportProcessing.ReportProcessingException::.ctor(valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode code, object[] arguments)
0x1f7f29  throw
0x1f7f2a  ldloc.0
0x1f7f2b  ret
```
