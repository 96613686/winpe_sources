# Microsoft.ReportingServices.OnDemandProcessing.RuntimeAtomicDataSource::ProcessConcurrent

- ea: `0x1f6cb0`
- end: `0x1f6ddd`
- name: `Microsoft.ReportingServices.OnDemandProcessing.RuntimeAtomicDataSource::ProcessConcurrent`
- size: `301`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x1f4970`

## callees

- `0x113200`
- `0x1f2480`
- `0x1f6260`
- `0x1f6270`
- `0x1f6cb0`
- `0x1f6de0`
- `0x1f8e90`
- `0x1fb200`
- `0x1fb7f0`
- `0x1fb8b0`

## string_xrefs

- `0x1f6cc2`: `Thread has started processing data source '{0}'`
- `0x1f6dad`: `Processing of data source '{0}' completed.`

## pseudocode

```c

```

## disassembly

```asm
0x1f6cb0  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1f6cb5  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x1f6cba  brfalse.s loc_1F6CE0
0x1f6cbc  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1f6cc1  ldc.i4.4
0x1f6cc2  ldstr    aThreadHasStart_0// "Thread has started processing data sour"...
0x1f6cc7  ldc.i4.1
0x1f6cc8  newarr   [mscorlib]System.Object
0x1f6ccd  dup
0x1f6cce  ldc.i4.0
0x1f6ccf  ldarg.0
0x1f6cd0  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.DataSource Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSource::get_DataSourceDefinition()
0x1f6cd5  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.DataSource::get_Name()
0x1f6cda  stelem.ref
0x1f6cdb  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x1f6ce0  ldarg.0
0x1f6ce1  ldc.i4.0
0x1f6ce2  call     instance void Microsoft.ReportingServices.OnDemandProcessing.RuntimeAtomicDataSource::Process(bool fromOdp)
0x1f6ce7  leave    loc_1F6DDC
0x1f6cec  pop
0x1f6ced  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1f6cf2  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceWarning()
0x1f6cf7  brfalse.s loc_1F6D1D
0x1f6cf9  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1f6cfe  ldc.i4.2
0x1f6cff  ldstr    aDataSource0Rep// "Data source '{0}': Report processing ha"...
0x1f6d04  ldc.i4.1
0x1f6d05  newarr   [mscorlib]System.Object
0x1f6d0a  dup
0x1f6d0b  ldc.i4.0
0x1f6d0c  ldarg.0
0x1f6d0d  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.DataSource Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSource::get_DataSourceDefinition()
0x1f6d12  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.DataSource::get_Name()
0x1f6d17  stelem.ref
0x1f6d18  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x1f6d1d  ldarg.0
0x1f6d1e  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSource::m_odpContext
0x1f6d23  callvirt instance bool Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::get_StreamingMode()
0x1f6d28  brfalse.s loc_1F6D2C
0x1f6d2a  rethrow
0x1f6d2c  leave    loc_1F6DDC
0x1f6d31  stloc.0
0x1f6d32  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1f6d37  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x1f6d3c  brfalse.s loc_1F6D6B
0x1f6d3e  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1f6d43  ldc.i4.1
0x1f6d44  ldstr    aAnExceptionHas_1// "An exception has occurred in data sourc"...
0x1f6d49  ldc.i4.2
0x1f6d4a  newarr   [mscorlib]System.Object
0x1f6d4f  dup
0x1f6d50  ldc.i4.0
0x1f6d51  ldarg.0
0x1f6d52  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.DataSource Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSource::get_DataSourceDefinition()
0x1f6d57  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.DataSource::get_Name()
0x1f6d5c  stelem.ref
0x1f6d5d  dup
0x1f6d5e  ldc.i4.1
0x1f6d5f  ldloc.0
0x1f6d60  callvirt instance string [mscorlib]System.Object::ToString()
0x1f6d65  stelem.ref
0x1f6d66  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x1f6d6b  ldarg.0
0x1f6d6c  call     instance class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSource::get_OdpContext()
0x1f6d71  callvirt instance class Microsoft.ReportingServices.OnDemandProcessing.AbortHelper Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::get_AbortInfo()
0x1f6d76  brfalse.s loc_1F6D97
0x1f6d78  ldarg.0
0x1f6d79  call     instance class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSource::get_OdpContext()
0x1f6d7e  callvirt instance class Microsoft.ReportingServices.OnDemandProcessing.AbortHelper Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::get_AbortInfo()
0x1f6d83  ldloc.0
0x1f6d84  ldarg.0
0x1f6d85  call     instance class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSource::get_OdpContext()
0x1f6d8a  callvirt instance string Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::get_ProcessingAbortItemUniqueIdentifier()
0x1f6d8f  callvirt instance bool Microsoft.ReportingServices.OnDemandProcessing.AbortHelper::SetError(class [mscorlib]System.Exception e, string uniqueName)
0x1f6d94  pop
0x1f6d95  br.s     loc_1F6D99
0x1f6d97  rethrow
0x1f6d99  leave.s  loc_1F6DDC
0x1f6d9b  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1f6da0  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x1f6da5  brfalse.s loc_1F6DCB
0x1f6da7  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1f6dac  ldc.i4.4
0x1f6dad  ldstr    aProcessingOfDa_0// "Processing of data source '{0}' complet"...
0x1f6db2  ldc.i4.1
0x1f6db3  newarr   [mscorlib]System.Object
0x1f6db8  dup
0x1f6db9  ldc.i4.0
0x1f6dba  ldarg.0
0x1f6dbb  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.DataSource Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSource::get_DataSourceDefinition()
0x1f6dc0  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.DataSource::get_Name()
0x1f6dc5  stelem.ref
0x1f6dc6  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x1f6dcb  ldarg.1
0x1f6dcc  isinst   Microsoft.ReportingServices.OnDemandProcessing.ThreadSet
0x1f6dd1  stloc.1
0x1f6dd2  ldloc.1
0x1f6dd3  brfalse.s loc_1F6DDB
0x1f6dd5  ldloc.1
0x1f6dd6  callvirt instance void Microsoft.ReportingServices.OnDemandProcessing.ThreadSet::ThreadCompleted()
0x1f6ddb  endfinally
0x1f6ddc  ret
```
