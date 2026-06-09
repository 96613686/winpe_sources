# Microsoft.ReportingServices.OnDemandProcessing.AbortHelper::Abort_0

- ea: `0x1f24f0`
- end: `0x1f25b1`
- name: `Microsoft.ReportingServices.OnDemandProcessing.AbortHelper::Abort_0`
- size: `193`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1f2400`
- `0x1f2480`

## callees

- `0x1f2410`
- `0x1f2420`
- `0x1f24f0`
- `0x1f2970`

## string_xrefs

- `0x1f250d`: `Some other thread is aborting processing.`
- `0x1f2529`: `Some other thread has already aborted processing.`

## pseudocode

```c

```

## disassembly

```asm
0x1f24f0  ldarg.0
0x1f24f1  ldfld    bool Microsoft.ReportingServices.OnDemandProcessing.AbortHelper::m_requireEventHandler
0x1f24f6  ldc.i4.0
0x1f24f7  ceq
0x1f24f9  stloc.0
0x1f24fa  ldarg.0
0x1f24fb  ldfld    object Microsoft.ReportingServices.OnDemandProcessing.AbortHelper::m_syncRoot
0x1f2500  call     bool [mscorlib]System.Threading.Monitor::TryEnter(object)
0x1f2505  brtrue.s loc_1F2519
0x1f2507  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1f250c  ldc.i4.3
0x1f250d  ldstr    aSomeOtherThrea// "Some other thread is aborting processin"...
0x1f2512  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x1f2517  ldloc.0
0x1f2518  ret
0x1f2519  nop
0x1f251a  ldarg.0
0x1f251b  ldarg.2
0x1f251c  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ProcessingStatus Microsoft.ReportingServices.OnDemandProcessing.AbortHelper::GetStatus(string uniqueName)
0x1f2521  brfalse.s loc_1F2537
0x1f2523  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1f2528  ldc.i4.3
0x1f2529  ldstr    aSomeOtherThrea_0// "Some other thread has already aborted p"...
0x1f252e  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x1f2533  ldloc.0
0x1f2534  stloc.1
0x1f2535  leave.s  loc_1F25AF
0x1f2537  ldarg.0
0x1f2538  ldarg.1
0x1f2539  ldarg.2
0x1f253a  callvirt instance void Microsoft.ReportingServices.OnDemandProcessing.AbortHelper::SetStatus(valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ProcessingStatus newStatus, string uniqueName)
0x1f253f  ldarg.0
0x1f2540  ldfld    class [mscorlib]System.EventHandler Microsoft.ReportingServices.OnDemandProcessing.AbortHelper::ProcessingAbortEvent
0x1f2545  brfalse.s loc_1F258F
0x1f2547  ldarg.0
0x1f2548  ldfld    class [mscorlib]System.EventHandler Microsoft.ReportingServices.OnDemandProcessing.AbortHelper::ProcessingAbortEvent
0x1f254d  ldarg.0
0x1f254e  ldarg.2
0x1f254f  newobj   instance void Microsoft.ReportingServices.OnDemandProcessing.ProcessingAbortEventArgs::.ctor(string uniqueName)
0x1f2554  callvirt instance void [mscorlib]System.EventHandler::Invoke(object, class [mscorlib]System.EventArgs)
0x1f2559  ldc.i4.1
0x1f255a  stloc.0
0x1f255b  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1f2560  ldc.i4.4
0x1f2561  ldstr    aAbortCallbackS// "Abort callback successful."
0x1f2566  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x1f256b  leave.s  loc_1F25AD
0x1f256d  stloc.2
0x1f256e  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1f2573  ldc.i4.1
0x1f2574  ldstr    aExceptionInAbo// "Exception in abort callback. Details: {"...
0x1f2579  ldc.i4.1
0x1f257a  newarr   [mscorlib]System.Object
0x1f257f  dup
0x1f2580  ldc.i4.0
0x1f2581  ldloc.2
0x1f2582  callvirt instance string [mscorlib]System.Object::ToString()
0x1f2587  stelem.ref
0x1f2588  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x1f258d  leave.s  loc_1F25AD
0x1f258f  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1f2594  ldc.i4.4
0x1f2595  ldstr    aNoAbortCallbac// "No abort callback."
0x1f259a  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x1f259f  leave.s  loc_1F25AD
0x1f25a1  ldarg.0
0x1f25a2  ldfld    object Microsoft.ReportingServices.OnDemandProcessing.AbortHelper::m_syncRoot
0x1f25a7  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x1f25ac  endfinally
0x1f25ad  ldloc.0
0x1f25ae  ret
0x1f25af  ldloc.1
0x1f25b0  ret
```
