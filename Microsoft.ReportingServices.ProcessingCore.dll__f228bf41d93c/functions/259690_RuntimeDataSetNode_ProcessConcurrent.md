# RuntimeDataSetNode::ProcessConcurrent

- ea: `0x259690`
- end: `0x259867`
- name: `RuntimeDataSetNode::ProcessConcurrent`
- size: `471`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x258c00`

## callees

- `0xbe730`
- `0x197800`
- `0x197880`
- `0x197a00`
- `0x197a10`
- `0x197f80`
- `0x23fbe0`
- `0x240890`
- `0x2409b0`
- `0x240b10`
- `0x240b30`
- `0x240b40`
- `0x259690`
- `0x259a20`
- `0x26e160`

## string_xrefs

- `0x2596c1`: `Thread has started processing data set '{0}'`
- `0x259829`: `Processing of data set '{0}' completed.`

## pseudocode

```c

```

## disassembly

```asm
0x259690  ldnull
0x259691  stloc.0
0x259692  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x259697  ldarg.0
0x259698  ldfld    class Microsoft.ReportingServices.ReportProcessing.DataSet RuntimeDataSetNode::m_dataSet
0x25969d  callvirt instance string Microsoft.ReportingServices.ReportProcessing.DataSet::get_Name()
0x2596a2  ldnull
0x2596a3  cgt.un
0x2596a5  ldstr    aTheNameOfAData// "The name of a data set cannot be null."
0x2596aa  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x2596af  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x2596b4  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x2596b9  brfalse.s loc_2596DF
0x2596bb  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x2596c0  ldc.i4.4
0x2596c1  ldstr    aThreadHasStart// "Thread has started processing data set "...
0x2596c6  ldc.i4.1
0x2596c7  newarr   [mscorlib]System.Object
0x2596cc  dup
0x2596cd  ldc.i4.0
0x2596ce  ldarg.0
0x2596cf  ldfld    class Microsoft.ReportingServices.ReportProcessing.DataSet RuntimeDataSetNode::m_dataSet
0x2596d4  callvirt instance string Microsoft.ReportingServices.ReportProcessing.DataSet::get_Name()
0x2596d9  stelem.ref
0x2596da  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x2596df  ldarg.0
0x2596e0  ldfld    class ProcessingContext RuntimeDataSetNode::m_processingContext
0x2596e5  callvirt instance class [mscorlib]System.Globalization.CultureInfo ProcessingContext::get_ThreadCulture()
0x2596ea  brfalse.s loc_25970C
0x2596ec  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x2596f1  callvirt instance class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Threading.Thread::get_CurrentCulture()
0x2596f6  stloc.0
0x2596f7  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x2596fc  ldarg.0
0x2596fd  ldfld    class ProcessingContext RuntimeDataSetNode::m_processingContext
0x259702  callvirt instance class [mscorlib]System.Globalization.CultureInfo ProcessingContext::get_ThreadCulture()
0x259707  callvirt instance void [mscorlib]System.Threading.Thread::set_CurrentCulture(class [mscorlib]System.Globalization.CultureInfo)
0x25970c  ldsfld   unsigned int32 Microsoft.ReportingServices.ReportPublishing.DataSetValidator::LOCALE_SYSTEM_DEFAULT
0x259711  ldarg.0
0x259712  ldfld    class Microsoft.ReportingServices.ReportProcessing.DataSet RuntimeDataSetNode::m_dataSet
0x259717  callvirt instance unsigned int32 Microsoft.ReportingServices.ReportProcessing.DataSet::get_LCID()
0x25971c  bne.un.s loc_259739
0x25971e  ldarg.0
0x25971f  ldfld    class Microsoft.ReportingServices.ReportProcessing.DataSet RuntimeDataSetNode::m_dataSet
0x259724  ldarg.0
0x259725  ldfld    class Microsoft.ReportingServices.ReportProcessing.DataSet RuntimeDataSetNode::m_dataSet
0x25972a  callvirt instance string Microsoft.ReportingServices.ReportProcessing.DataSet::get_Collation()
0x25972f  call     unsigned int32 Microsoft.ReportingServices.ReportPublishing.DataSetValidator::LCIDfromRDLCollation(string collation)
0x259734  callvirt instance void Microsoft.ReportingServices.ReportProcessing.DataSet::set_LCID(unsigned int32 value)
0x259739  ldarg.0
0x25973a  ldfld    class ProcessingContext RuntimeDataSetNode::m_processingContext
0x25973f  ldarg.0
0x259740  ldfld    class Microsoft.ReportingServices.ReportProcessing.DataSet RuntimeDataSetNode::m_dataSet
0x259745  callvirt instance unsigned int32 Microsoft.ReportingServices.ReportProcessing.DataSet::get_LCID()
0x25974a  ldc.i4.0
0x25974b  newobj   instance void [mscorlib]System.Globalization.CultureInfo::.ctor(int32, bool)
0x259750  callvirt instance class [mscorlib]System.Globalization.CompareInfo [mscorlib]System.Globalization.CultureInfo::get_CompareInfo()
0x259755  callvirt instance void ProcessingContext::set_CompareInfo(class [mscorlib]System.Globalization.CompareInfo value)
0x25975a  ldarg.0
0x25975b  ldfld    class ProcessingContext RuntimeDataSetNode::m_processingContext
0x259760  ldarg.0
0x259761  ldfld    class Microsoft.ReportingServices.ReportProcessing.DataSet RuntimeDataSetNode::m_dataSet
0x259766  callvirt instance valuetype [mscorlib]System.Globalization.CompareOptions Microsoft.ReportingServices.ReportProcessing.DataSet::GetCLRCompareOptions()
0x25976b  callvirt instance void ProcessingContext::set_ClrCompareOptions(valuetype [mscorlib]System.Globalization.CompareOptions value)
0x259770  ldarg.0
0x259771  callvirt instance void RuntimeDataSetNode::Process()
0x259776  leave    loc_259866
0x25977b  pop
0x25977c  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x259781  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceWarning()
0x259786  brfalse.s loc_2597AC
0x259788  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x25978d  ldc.i4.2
0x25978e  ldstr    aDataSet0Report// "Data set '{0}': Report processing has b"...
0x259793  ldc.i4.1
0x259794  newarr   [mscorlib]System.Object
0x259799  dup
0x25979a  ldc.i4.0
0x25979b  ldarg.0
0x25979c  ldfld    class Microsoft.ReportingServices.ReportProcessing.DataSet RuntimeDataSetNode::m_dataSet
0x2597a1  callvirt instance string Microsoft.ReportingServices.ReportProcessing.DataSet::get_Name()
0x2597a6  stelem.ref
0x2597a7  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x2597ac  leave    loc_259866
0x2597b1  stloc.1
0x2597b2  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x2597b7  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x2597bc  brfalse.s loc_2597EB
0x2597be  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x2597c3  ldc.i4.1
0x2597c4  ldstr    aAnExceptionHas_1// "An exception has occurred in data sourc"...
0x2597c9  ldc.i4.2
0x2597ca  newarr   [mscorlib]System.Object
0x2597cf  dup
0x2597d0  ldc.i4.0
0x2597d1  ldarg.0
0x2597d2  ldfld    class Microsoft.ReportingServices.ReportProcessing.DataSet RuntimeDataSetNode::m_dataSet
0x2597d7  callvirt instance string Microsoft.ReportingServices.ReportProcessing.DataSet::get_Name()
0x2597dc  stelem.ref
0x2597dd  dup
0x2597de  ldc.i4.1
0x2597df  ldloc.1
0x2597e0  callvirt instance string [mscorlib]System.Object::ToString()
0x2597e5  stelem.ref
0x2597e6  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x2597eb  ldarg.0
0x2597ec  ldfld    class ProcessingContext RuntimeDataSetNode::m_processingContext
0x2597f1  callvirt instance class AbortHelper ProcessingContext::get_AbortInfo()
0x2597f6  brfalse.s loc_259815
0x2597f8  ldarg.0
0x2597f9  ldfld    class ProcessingContext RuntimeDataSetNode::m_processingContext
0x2597fe  callvirt instance class AbortHelper ProcessingContext::get_AbortInfo()
0x259803  ldarg.0
0x259804  ldfld    class ProcessingContext RuntimeDataSetNode::m_processingContext
0x259809  callvirt instance int32 ProcessingContext::get_DataSetUniqueName()
0x25980e  ldloc.1
0x25980f  callvirt instance bool AbortHelper::SetError(int32 reportUniqueName, class [mscorlib]System.Exception e)
0x259814  pop
0x259815  leave.s  loc_259866
0x259817  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x25981c  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x259821  brfalse.s loc_259847
0x259823  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x259828  ldc.i4.4
0x259829  ldstr    aProcessingOfDa// "Processing of data set '{0}' completed."
0x25982e  ldc.i4.1
0x25982f  newarr   [mscorlib]System.Object
0x259834  dup
0x259835  ldc.i4.0
0x259836  ldarg.0
0x259837  ldfld    class Microsoft.ReportingServices.ReportProcessing.DataSet RuntimeDataSetNode::m_dataSet
0x25983c  callvirt instance string Microsoft.ReportingServices.ReportProcessing.DataSet::get_Name()
0x259841  stelem.ref
0x259842  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x259847  ldloc.0
0x259848  brfalse.s loc_259855
0x25984a  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x25984f  ldloc.0
0x259850  callvirt instance void [mscorlib]System.Threading.Thread::set_CurrentCulture(class [mscorlib]System.Globalization.CultureInfo)
0x259855  ldarg.1
0x259856  isinst   ThreadSet
0x25985b  stloc.2
0x25985c  ldloc.2
0x25985d  brfalse.s loc_259865
0x25985f  ldloc.2
0x259860  callvirt instance void ThreadSet::ThreadCompleted()
0x259865  endfinally
0x259866  ret
```
