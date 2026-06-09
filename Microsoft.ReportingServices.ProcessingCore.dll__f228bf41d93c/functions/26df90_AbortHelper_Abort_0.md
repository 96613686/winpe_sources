# AbortHelper::Abort_0

- ea: `0x26df90`
- end: `0x26e07c`
- name: `AbortHelper::Abort_0`
- size: `236`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x26df80`
- `0x26e160`

## callees

- `0x23fb60`
- `0x26df90`
- `0x26e0c0`
- `0x26e110`

## string_xrefs

- `0x26dfaa`: `Some other thread is aborting processing.`
- `0x26dfd1`: `Some other thread has already aborted processing.`

## pseudocode

```c

```

## disassembly

```asm
0x26df90  ldarg.0
0x26df91  call     bool [mscorlib]System.Threading.Monitor::TryEnter(object)
0x26df96  brtrue.s loc_26DFB6
0x26df98  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x26df9d  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x26dfa2  brfalse.s loc_26DFB4
0x26dfa4  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x26dfa9  ldc.i4.3
0x26dfaa  ldstr    aSomeOtherThrea// "Some other thread is aborting processin"...
0x26dfaf  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x26dfb4  ldc.i4.0
0x26dfb5  ret
0x26dfb6  ldarg.0
0x26dfb7  ldarg.1
0x26dfb8  call     instance valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ProcessingStatus AbortHelper::GetStatus(int32 uniqueName)
0x26dfbd  brfalse.s loc_26DFE3
0x26dfbf  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x26dfc4  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x26dfc9  brfalse.s loc_26DFDB
0x26dfcb  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x26dfd0  ldc.i4.3
0x26dfd1  ldstr    aSomeOtherThrea_0// "Some other thread has already aborted p"...
0x26dfd6  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x26dfdb  ldarg.0
0x26dfdc  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x26dfe1  ldc.i4.0
0x26dfe2  ret
0x26dfe3  ldc.i4.0
0x26dfe4  stloc.0
0x26dfe5  ldarg.0
0x26dfe6  ldarg.1
0x26dfe7  ldarg.2
0x26dfe8  call     instance void AbortHelper::SetStatus(int32 uniqueName, valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ProcessingStatus newStatus)
0x26dfed  ldarg.0
0x26dfee  ldfld    class [mscorlib]System.EventHandler AbortHelper::ProcessingAbortEvent
0x26dff3  brfalse.s loc_26E055
0x26dff5  ldarg.0
0x26dff6  ldfld    class [mscorlib]System.EventHandler AbortHelper::ProcessingAbortEvent
0x26dffb  ldarg.0
0x26dffc  ldarg.1
0x26dffd  newobj   instance void ProcessingAbortEventArgs::.ctor(int32 reportUniqueName)
0x26e002  callvirt instance void [mscorlib]System.EventHandler::Invoke(object, class [mscorlib]System.EventArgs)
0x26e007  ldc.i4.1
0x26e008  stloc.0
0x26e009  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x26e00e  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x26e013  brfalse.s loc_26E025
0x26e015  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x26e01a  ldc.i4.4
0x26e01b  ldstr    aAbortCallbackS// "Abort callback successful."
0x26e020  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x26e025  leave.s  loc_26E07A
0x26e027  stloc.1
0x26e028  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x26e02d  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x26e032  brfalse.s loc_26E053
0x26e034  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x26e039  ldc.i4.1
0x26e03a  ldstr    aExceptionInAbo// "Exception in abort callback. Details: {"...
0x26e03f  ldc.i4.1
0x26e040  newarr   [mscorlib]System.Object
0x26e045  dup
0x26e046  ldc.i4.0
0x26e047  ldloc.1
0x26e048  callvirt instance string [mscorlib]System.Object::ToString()
0x26e04d  stelem.ref
0x26e04e  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x26e053  leave.s  loc_26E07A
0x26e055  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x26e05a  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x26e05f  brfalse.s loc_26E071
0x26e061  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x26e066  ldc.i4.4
0x26e067  ldstr    aNoAbortCallbac// "No abort callback."
0x26e06c  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x26e071  leave.s  loc_26E07A
0x26e073  ldarg.0
0x26e074  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x26e079  endfinally
0x26e07a  ldloc.0
0x26e07b  ret
```
