# RuntimeDataSourceNode::ProcessConcurrent

- ea: `0x2589f0`
- end: `0x258b63`
- name: `RuntimeDataSourceNode::ProcessConcurrent`
- size: `371`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x2040f0`
- `0x257a20`
- `0x257c70`

## callees

- `0x197200`
- `0x23fbe0`
- `0x240890`
- `0x2409b0`
- `0x240b40`
- `0x2589f0`
- `0x258b70`
- `0x26e160`

## string_xrefs

- `0x258a21`: `Thread has started processing data source '{0}'`
- `0x258b25`: `Processing of data source '{0}' completed.`

## pseudocode

```c

```

## disassembly

```asm
0x2589f0  ldnull
0x2589f1  stloc.0
0x2589f2  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x2589f7  ldarg.0
0x2589f8  ldfld    class Microsoft.ReportingServices.ReportProcessing.DataSource RuntimeDataSourceNode::m_dataSource
0x2589fd  callvirt instance string Microsoft.ReportingServices.ReportProcessing.DataSource::get_Name()
0x258a02  ldnull
0x258a03  cgt.un
0x258a05  ldstr    aTheNameOfAData_0// "The name of a data source cannot be nul"...
0x258a0a  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x258a0f  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x258a14  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x258a19  brfalse.s loc_258A3F
0x258a1b  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x258a20  ldc.i4.4
0x258a21  ldstr    aThreadHasStart_0// "Thread has started processing data sour"...
0x258a26  ldc.i4.1
0x258a27  newarr   [mscorlib]System.Object
0x258a2c  dup
0x258a2d  ldc.i4.0
0x258a2e  ldarg.0
0x258a2f  ldfld    class Microsoft.ReportingServices.ReportProcessing.DataSource RuntimeDataSourceNode::m_dataSource
0x258a34  callvirt instance string Microsoft.ReportingServices.ReportProcessing.DataSource::get_Name()
0x258a39  stelem.ref
0x258a3a  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x258a3f  ldarg.0
0x258a40  ldfld    class ProcessingContext RuntimeDataSourceNode::m_processingContext
0x258a45  callvirt instance class [mscorlib]System.Globalization.CultureInfo ProcessingContext::get_ThreadCulture()
0x258a4a  brfalse.s loc_258A6C
0x258a4c  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x258a51  callvirt instance class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Threading.Thread::get_CurrentCulture()
0x258a56  stloc.0
0x258a57  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x258a5c  ldarg.0
0x258a5d  ldfld    class ProcessingContext RuntimeDataSourceNode::m_processingContext
0x258a62  callvirt instance class [mscorlib]System.Globalization.CultureInfo ProcessingContext::get_ThreadCulture()
0x258a67  callvirt instance void [mscorlib]System.Threading.Thread::set_CurrentCulture(class [mscorlib]System.Globalization.CultureInfo)
0x258a6c  ldarg.0
0x258a6d  callvirt instance void RuntimeDataSourceNode::Process()
0x258a72  leave    loc_258B62
0x258a77  pop
0x258a78  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x258a7d  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceWarning()
0x258a82  brfalse.s loc_258AA8
0x258a84  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x258a89  ldc.i4.2
0x258a8a  ldstr    aDataSource0Rep// "Data source '{0}': Report processing ha"...
0x258a8f  ldc.i4.1
0x258a90  newarr   [mscorlib]System.Object
0x258a95  dup
0x258a96  ldc.i4.0
0x258a97  ldarg.0
0x258a98  ldfld    class Microsoft.ReportingServices.ReportProcessing.DataSource RuntimeDataSourceNode::m_dataSource
0x258a9d  callvirt instance string Microsoft.ReportingServices.ReportProcessing.DataSource::get_Name()
0x258aa2  stelem.ref
0x258aa3  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x258aa8  leave    loc_258B62
0x258aad  stloc.1
0x258aae  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x258ab3  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x258ab8  brfalse.s loc_258AE7
0x258aba  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x258abf  ldc.i4.1
0x258ac0  ldstr    aAnExceptionHas_1// "An exception has occurred in data sourc"...
0x258ac5  ldc.i4.2
0x258ac6  newarr   [mscorlib]System.Object
0x258acb  dup
0x258acc  ldc.i4.0
0x258acd  ldarg.0
0x258ace  ldfld    class Microsoft.ReportingServices.ReportProcessing.DataSource RuntimeDataSourceNode::m_dataSource
0x258ad3  callvirt instance string Microsoft.ReportingServices.ReportProcessing.DataSource::get_Name()
0x258ad8  stelem.ref
0x258ad9  dup
0x258ada  ldc.i4.1
0x258adb  ldloc.1
0x258adc  callvirt instance string [mscorlib]System.Object::ToString()
0x258ae1  stelem.ref
0x258ae2  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x258ae7  ldarg.0
0x258ae8  ldfld    class ProcessingContext RuntimeDataSourceNode::m_processingContext
0x258aed  callvirt instance class AbortHelper ProcessingContext::get_AbortInfo()
0x258af2  brfalse.s loc_258B11
0x258af4  ldarg.0
0x258af5  ldfld    class ProcessingContext RuntimeDataSourceNode::m_processingContext
0x258afa  callvirt instance class AbortHelper ProcessingContext::get_AbortInfo()
0x258aff  ldarg.0
0x258b00  ldfld    class ProcessingContext RuntimeDataSourceNode::m_processingContext
0x258b05  callvirt instance int32 ProcessingContext::get_DataSetUniqueName()
0x258b0a  ldloc.1
0x258b0b  callvirt instance bool AbortHelper::SetError(int32 reportUniqueName, class [mscorlib]System.Exception e)
0x258b10  pop
0x258b11  leave.s  loc_258B62
0x258b13  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x258b18  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x258b1d  brfalse.s loc_258B43
0x258b1f  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x258b24  ldc.i4.4
0x258b25  ldstr    aProcessingOfDa_0// "Processing of data source '{0}' complet"...
0x258b2a  ldc.i4.1
0x258b2b  newarr   [mscorlib]System.Object
0x258b30  dup
0x258b31  ldc.i4.0
0x258b32  ldarg.0
0x258b33  ldfld    class Microsoft.ReportingServices.ReportProcessing.DataSource RuntimeDataSourceNode::m_dataSource
0x258b38  callvirt instance string Microsoft.ReportingServices.ReportProcessing.DataSource::get_Name()
0x258b3d  stelem.ref
0x258b3e  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x258b43  ldloc.0
0x258b44  brfalse.s loc_258B51
0x258b46  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x258b4b  ldloc.0
0x258b4c  callvirt instance void [mscorlib]System.Threading.Thread::set_CurrentCulture(class [mscorlib]System.Globalization.CultureInfo)
0x258b51  ldarg.1
0x258b52  isinst   ThreadSet
0x258b57  stloc.2
0x258b58  ldloc.2
0x258b59  brfalse.s loc_258B61
0x258b5b  ldloc.2
0x258b5c  callvirt instance void ThreadSet::ThreadCompleted()
0x258b61  endfinally
0x258b62  ret
```
