# Microsoft.ReportingServices.OnDemandProcessing.RuntimeQueryExecutor::ExecuteConcurrent

- ea: `0x1f89c0`
- end: `0x1f8add`
- name: `Microsoft.ReportingServices.OnDemandProcessing.RuntimeQueryExecutor::ExecuteConcurrent`
- size: `285`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1f30a0`

## callees

- `0x114be0`
- `0x1f2480`
- `0x1f89c0`
- `0x1f8ae0`
- `0x1f8e90`
- `0x1fb7f0`
- `0x1fb8b0`

## string_xrefs

- `0x1f8aad`: `Processing of data set '{0}' completed.`
- `0x1f89d2`: `Thread has started query execution for data set '{0}'`

## pseudocode

```c

```

## disassembly

```asm
0x1f89c0  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1f89c5  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x1f89ca  brfalse.s loc_1F89F0
0x1f89cc  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1f89d1  ldc.i4.4
0x1f89d2  ldstr    aThreadHasStart_1// "Thread has started query execution for "...
0x1f89d7  ldc.i4.1
0x1f89d8  newarr   [mscorlib]System.Object
0x1f89dd  dup
0x1f89de  ldc.i4.0
0x1f89df  ldarg.0
0x1f89e0  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.DataSet Microsoft.ReportingServices.OnDemandProcessing.RuntimeLiveQueryExecutor::m_dataSet
0x1f89e5  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.DataSet::get_Name()
0x1f89ea  stelem.ref
0x1f89eb  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x1f89f0  ldarg.0
0x1f89f1  call     instance void Microsoft.ReportingServices.OnDemandProcessing.RuntimeQueryExecutor::Execute()
0x1f89f6  leave    loc_1F8ADC
0x1f89fb  pop
0x1f89fc  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1f8a01  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceWarning()
0x1f8a06  brfalse.s loc_1F8A2C
0x1f8a08  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1f8a0d  ldc.i4.2
0x1f8a0e  ldstr    aDataSet0QueryE// "Data set '{0}': query execution has bee"...
0x1f8a13  ldc.i4.1
0x1f8a14  newarr   [mscorlib]System.Object
0x1f8a19  dup
0x1f8a1a  ldc.i4.0
0x1f8a1b  ldarg.0
0x1f8a1c  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.DataSet Microsoft.ReportingServices.OnDemandProcessing.RuntimeLiveQueryExecutor::m_dataSet
0x1f8a21  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.DataSet::get_Name()
0x1f8a26  stelem.ref
0x1f8a27  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x1f8a2c  leave    loc_1F8ADC
0x1f8a31  stloc.0
0x1f8a32  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1f8a37  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x1f8a3c  brfalse.s loc_1F8A6B
0x1f8a3e  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1f8a43  ldc.i4.1
0x1f8a44  ldstr    aAnExceptionHas_0// "An exception has occurred in data set '"...
0x1f8a49  ldc.i4.2
0x1f8a4a  newarr   [mscorlib]System.Object
0x1f8a4f  dup
0x1f8a50  ldc.i4.0
0x1f8a51  ldarg.0
0x1f8a52  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.DataSet Microsoft.ReportingServices.OnDemandProcessing.RuntimeLiveQueryExecutor::m_dataSet
0x1f8a57  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.DataSet::get_Name()
0x1f8a5c  stelem.ref
0x1f8a5d  dup
0x1f8a5e  ldc.i4.1
0x1f8a5f  ldloc.0
0x1f8a60  callvirt instance string [mscorlib]System.Object::ToString()
0x1f8a65  stelem.ref
0x1f8a66  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x1f8a6b  ldarg.0
0x1f8a6c  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.OnDemandProcessing.RuntimeLiveQueryExecutor::m_odpContext
0x1f8a71  callvirt instance class Microsoft.ReportingServices.OnDemandProcessing.AbortHelper Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::get_AbortInfo()
0x1f8a76  brfalse.s loc_1F8A97
0x1f8a78  ldarg.0
0x1f8a79  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.OnDemandProcessing.RuntimeLiveQueryExecutor::m_odpContext
0x1f8a7e  callvirt instance class Microsoft.ReportingServices.OnDemandProcessing.AbortHelper Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::get_AbortInfo()
0x1f8a83  ldloc.0
0x1f8a84  ldarg.0
0x1f8a85  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.OnDemandProcessing.RuntimeLiveQueryExecutor::m_odpContext
0x1f8a8a  callvirt instance string Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::get_ProcessingAbortItemUniqueIdentifier()
0x1f8a8f  callvirt instance bool Microsoft.ReportingServices.OnDemandProcessing.AbortHelper::SetError(class [mscorlib]System.Exception e, string uniqueName)
0x1f8a94  pop
0x1f8a95  br.s     loc_1F8A99
0x1f8a97  rethrow
0x1f8a99  leave.s  loc_1F8ADC
0x1f8a9b  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1f8aa0  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x1f8aa5  brfalse.s loc_1F8ACB
0x1f8aa7  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1f8aac  ldc.i4.4
0x1f8aad  ldstr    aProcessingOfDa// "Processing of data set '{0}' completed."
0x1f8ab2  ldc.i4.1
0x1f8ab3  newarr   [mscorlib]System.Object
0x1f8ab8  dup
0x1f8ab9  ldc.i4.0
0x1f8aba  ldarg.0
0x1f8abb  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.DataSet Microsoft.ReportingServices.OnDemandProcessing.RuntimeLiveQueryExecutor::m_dataSet
0x1f8ac0  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.DataSet::get_Name()
0x1f8ac5  stelem.ref
0x1f8ac6  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x1f8acb  ldarg.1
0x1f8acc  isinst   Microsoft.ReportingServices.OnDemandProcessing.ThreadSet
0x1f8ad1  stloc.1
0x1f8ad2  ldloc.1
0x1f8ad3  brfalse.s loc_1F8ADB
0x1f8ad5  ldloc.1
0x1f8ad6  callvirt instance void Microsoft.ReportingServices.OnDemandProcessing.ThreadSet::ThreadCompleted()
0x1f8adb  endfinally
0x1f8adc  ret
```
