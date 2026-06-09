# Microsoft.ReportingServices.OnDemandProcessing.RuntimeAtomicDataSet::ProcessConcurrent

- ea: `0x1f4b10`
- end: `0x1f4c5a`
- name: `Microsoft.ReportingServices.OnDemandProcessing.RuntimeAtomicDataSet::ProcessConcurrent`
- size: `330`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1f6e20`
- `0x1f6e80`

## callees

- `0x114be0`
- `0x1f2480`
- `0x1f4b10`
- `0x1f4c70`
- `0x1f8e90`
- `0x1fb200`
- `0x1fb7f0`
- `0x1fb8b0`

## string_xrefs

- `0x1f4b3f`: `Thread has started processing data set '{0}'`
- `0x1f4c2a`: `Processing of data set '{0}' completed.`

## pseudocode

```c

```

## disassembly

```asm
0x1f4b10  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1f4b15  ldarg.0
0x1f4b16  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.DataSet Microsoft.ReportingServices.OnDemandProcessing.RuntimeLiveQueryExecutor::m_dataSet
0x1f4b1b  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.DataSet::get_Name()
0x1f4b20  ldnull
0x1f4b21  cgt.un
0x1f4b23  ldstr    aTheNameOfAData// "The name of a data set cannot be null."
0x1f4b28  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x1f4b2d  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1f4b32  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x1f4b37  brfalse.s loc_1F4B5D
0x1f4b39  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1f4b3e  ldc.i4.4
0x1f4b3f  ldstr    aThreadHasStart// "Thread has started processing data set "...
0x1f4b44  ldc.i4.1
0x1f4b45  newarr   [mscorlib]System.Object
0x1f4b4a  dup
0x1f4b4b  ldc.i4.0
0x1f4b4c  ldarg.0
0x1f4b4d  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.DataSet Microsoft.ReportingServices.OnDemandProcessing.RuntimeLiveQueryExecutor::m_dataSet
0x1f4b52  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.DataSet::get_Name()
0x1f4b57  stelem.ref
0x1f4b58  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x1f4b5d  ldarg.0
0x1f4b5e  ldnull
0x1f4b5f  call     instance void Microsoft.ReportingServices.OnDemandProcessing.RuntimeAtomicDataSet::Process(class Microsoft.ReportingServices.OnDemandProcessing.ExecutedQuery existingQuery)
0x1f4b64  leave    loc_1F4C59
0x1f4b69  pop
0x1f4b6a  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1f4b6f  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceWarning()
0x1f4b74  brfalse.s loc_1F4B9A
0x1f4b76  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1f4b7b  ldc.i4.2
0x1f4b7c  ldstr    aDataSet0Report// "Data set '{0}': Report processing has b"...
0x1f4b81  ldc.i4.1
0x1f4b82  newarr   [mscorlib]System.Object
0x1f4b87  dup
0x1f4b88  ldc.i4.0
0x1f4b89  ldarg.0
0x1f4b8a  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.DataSet Microsoft.ReportingServices.OnDemandProcessing.RuntimeLiveQueryExecutor::m_dataSet
0x1f4b8f  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.DataSet::get_Name()
0x1f4b94  stelem.ref
0x1f4b95  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x1f4b9a  ldarg.0
0x1f4b9b  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.OnDemandProcessing.RuntimeLiveQueryExecutor::m_odpContext
0x1f4ba0  callvirt instance bool Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::get_StreamingMode()
0x1f4ba5  brfalse.s loc_1F4BA9
0x1f4ba7  rethrow
0x1f4ba9  leave    loc_1F4C59
0x1f4bae  stloc.0
0x1f4baf  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1f4bb4  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x1f4bb9  brfalse.s loc_1F4BE8
0x1f4bbb  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1f4bc0  ldc.i4.1
0x1f4bc1  ldstr    aAnExceptionHas_0// "An exception has occurred in data set '"...
0x1f4bc6  ldc.i4.2
0x1f4bc7  newarr   [mscorlib]System.Object
0x1f4bcc  dup
0x1f4bcd  ldc.i4.0
0x1f4bce  ldarg.0
0x1f4bcf  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.DataSet Microsoft.ReportingServices.OnDemandProcessing.RuntimeLiveQueryExecutor::m_dataSet
0x1f4bd4  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.DataSet::get_Name()
0x1f4bd9  stelem.ref
0x1f4bda  dup
0x1f4bdb  ldc.i4.1
0x1f4bdc  ldloc.0
0x1f4bdd  callvirt instance string [mscorlib]System.Object::ToString()
0x1f4be2  stelem.ref
0x1f4be3  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x1f4be8  ldarg.0
0x1f4be9  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.OnDemandProcessing.RuntimeLiveQueryExecutor::m_odpContext
0x1f4bee  callvirt instance class Microsoft.ReportingServices.OnDemandProcessing.AbortHelper Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::get_AbortInfo()
0x1f4bf3  brfalse.s loc_1F4C14
0x1f4bf5  ldarg.0
0x1f4bf6  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.OnDemandProcessing.RuntimeLiveQueryExecutor::m_odpContext
0x1f4bfb  callvirt instance class Microsoft.ReportingServices.OnDemandProcessing.AbortHelper Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::get_AbortInfo()
0x1f4c00  ldloc.0
0x1f4c01  ldarg.0
0x1f4c02  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.OnDemandProcessing.RuntimeLiveQueryExecutor::m_odpContext
0x1f4c07  callvirt instance string Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::get_ProcessingAbortItemUniqueIdentifier()
0x1f4c0c  callvirt instance bool Microsoft.ReportingServices.OnDemandProcessing.AbortHelper::SetError(class [mscorlib]System.Exception e, string uniqueName)
0x1f4c11  pop
0x1f4c12  br.s     loc_1F4C16
0x1f4c14  rethrow
0x1f4c16  leave.s  loc_1F4C59
0x1f4c18  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1f4c1d  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x1f4c22  brfalse.s loc_1F4C48
0x1f4c24  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1f4c29  ldc.i4.4
0x1f4c2a  ldstr    aProcessingOfDa// "Processing of data set '{0}' completed."
0x1f4c2f  ldc.i4.1
0x1f4c30  newarr   [mscorlib]System.Object
0x1f4c35  dup
0x1f4c36  ldc.i4.0
0x1f4c37  ldarg.0
0x1f4c38  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.DataSet Microsoft.ReportingServices.OnDemandProcessing.RuntimeLiveQueryExecutor::m_dataSet
0x1f4c3d  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.DataSet::get_Name()
0x1f4c42  stelem.ref
0x1f4c43  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x1f4c48  ldarg.1
0x1f4c49  isinst   Microsoft.ReportingServices.OnDemandProcessing.ThreadSet
0x1f4c4e  stloc.1
0x1f4c4f  ldloc.1
0x1f4c50  brfalse.s loc_1F4C58
0x1f4c52  ldloc.1
0x1f4c53  callvirt instance void Microsoft.ReportingServices.OnDemandProcessing.ThreadSet::ThreadCompleted()
0x1f4c58  endfinally
0x1f4c59  ret
```
