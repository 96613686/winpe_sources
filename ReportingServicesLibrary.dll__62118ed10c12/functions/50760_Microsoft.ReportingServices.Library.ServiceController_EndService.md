# Microsoft.ReportingServices.Library.ServiceController::EndService

- ea: `0x50760`
- end: `0x508b6`
- name: `Microsoft.ReportingServices.Library.ServiceController::EndService`
- size: `342`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x4d460`

## callees

- `0x4d310`
- `0x4ffd0`
- `0x50760`

## string_xrefs

- `0x507ad`: `ServiceAppDomainController::EndService - the Windows Service start thread is still running; Wait for it to finish; Mark the WindowsService (worker) AppDomain as active.`
- `0x507f0`: `[ThreadAborted] Service is existing therefore ServiceStartThread is aborted after over 5 seconds of wait time.`
- `0x5085b`: `Service controller exiting.`
- `0x5087c`: `Error Stopping Service: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x50760  ldarg.0
0x50761  ldfld    valuetype CurrentRunningState Microsoft.ReportingServices.Library.ServiceController::m_serviceState
0x50766  brtrue.s loc_5076D
0x50768  leave    loc_508B5
0x5076d  ldarg.0
0x5076e  ldfld    class [mscorlib]System.Threading.Thread Microsoft.ReportingServices.Library.ServiceController::m_startThread
0x50773  brfalse  loc_50805
0x50778  ldarg.0
0x50779  ldfld    class [mscorlib]System.Threading.Thread Microsoft.ReportingServices.Library.ServiceController::m_startThread
0x5077e  callvirt instance valuetype [mscorlib]System.Threading.ThreadState [mscorlib]System.Threading.Thread::get_ThreadState()
0x50783  ldc.i4.s 0x10
0x50785  beq.s    loc_50805
0x50787  ldarg.0
0x50788  ldc.i4.1
0x50789  stfld    bool Microsoft.ReportingServices.Library.ServiceController::m_startThreadExitStarted
0x5078e  ldarg.0
0x5078f  ldfld    int32 Microsoft.ReportingServices.Library.ServiceController::m_startThreadWaitToAbortTimeout
0x50794  stloc.0
0x50795  ldc.i4.0
0x50796  stloc.1
0x50797  ldc.i4.0
0x50798  stloc.2
0x50799  br.s     loc_507DF
0x5079b  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x507a0  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x507a5  brfalse.s loc_507B7
0x507a7  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x507ac  ldc.i4.3
0x507ad  ldstr    aServiceappdoma_7// "ServiceAppDomainController::EndService "...
0x507b2  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x507b7  ldarg.0
0x507b8  ldfld    class Microsoft.ReportingServices.Library.IServiceAppDomainController Microsoft.ReportingServices.Library.ServiceController::m_appDomainController
0x507bd  callvirt instance void Microsoft.ReportingServices.Library.IServiceAppDomainController::MarkProcessAsActive()
0x507c2  ldloc.0
0x507c3  ldc.i4   0x1388
0x507c8  call     int32 [mscorlib]System.Math::Min(int32, int32)
0x507cd  stloc.1
0x507ce  ldloc.0
0x507cf  ldloc.1
0x507d0  sub
0x507d1  stloc.0
0x507d2  ldarg.0
0x507d3  ldfld    class [mscorlib]System.Threading.Thread Microsoft.ReportingServices.Library.ServiceController::m_startThread
0x507d8  ldloc.1
0x507d9  callvirt instance bool [mscorlib]System.Threading.Thread::Join(int32)
0x507de  stloc.2
0x507df  ldloc.2
0x507e0  brtrue.s loc_507E6
0x507e2  ldloc.0
0x507e3  ldc.i4.0
0x507e4  bgt.s    loc_5079B
0x507e6  ldloc.2
0x507e7  brtrue.s loc_50805
0x507e9  ldarg.0
0x507ea  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.ServiceController::m_tracer
0x507ef  ldc.i4.3
0x507f0  ldstr    aThreadabortedS// "[ThreadAborted] Service is existing the"...
0x507f5  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x507fa  ldarg.0
0x507fb  ldfld    class [mscorlib]System.Threading.Thread Microsoft.ReportingServices.Library.ServiceController::m_startThread
0x50800  callvirt instance void [mscorlib]System.Threading.Thread::Abort()
0x50805  ldarg.0
0x50806  ldfld    class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.DBPoll Microsoft.ReportingServices.Library.ServiceController::m_pollingService
0x5080b  brfalse.s loc_50819
0x5080d  ldarg.0
0x5080e  ldfld    class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.DBPoll Microsoft.ReportingServices.Library.ServiceController::m_pollingService
0x50813  ldarg.1
0x50814  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.DBPoll::StopPolling(valuetype [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals/ServiceStopMode)
0x50819  ldarg.1
0x5081a  ldc.i4.1
0x5081b  beq.s    loc_50839
0x5081d  ldarg.0
0x5081e  ldnull
0x5081f  stfld    class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.QueuePollWorker Microsoft.ReportingServices.Library.ServiceController::m_eventWorker
0x50824  ldarg.0
0x50825  ldnull
0x50826  stfld    class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.QueuePollWorker Microsoft.ReportingServices.Library.ServiceController::m_notificationWorker
0x5082b  ldarg.0
0x5082c  ldnull
0x5082d  stfld    class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.PollWorker Microsoft.ReportingServices.Library.ServiceController::m_scheduleWorker
0x50832  ldarg.0
0x50833  ldnull
0x50834  stfld    class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.PollWorker Microsoft.ReportingServices.Library.ServiceController::m_upgradeWorker
0x50839  call     void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory::ClearAllExtensions()
0x5083e  ldarg.0
0x5083f  call     instance void Microsoft.ReportingServices.Library.ServiceController::StopTimers()
0x50844  ldarg.0
0x50845  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.ServiceController::m_tracer
0x5084a  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x5084f  brfalse.s loc_50865
0x50851  ldarg.1
0x50852  brtrue.s loc_50865
0x50854  ldarg.0
0x50855  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.ServiceController::m_tracer
0x5085a  ldc.i4.3
0x5085b  ldstr    aServiceControl// "Service controller exiting."
0x50860  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x50865  leave.s  loc_508B5
0x50867  stloc.3
0x50868  ldarg.0
0x50869  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.ServiceController::m_tracer
0x5086e  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x50873  brfalse.s loc_50895
0x50875  ldarg.0
0x50876  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.ServiceController::m_tracer
0x5087b  ldc.i4.1
0x5087c  ldstr    aErrorStoppingS// "Error Stopping Service: {0}"
0x50881  ldc.i4.1
0x50882  newarr   [mscorlib]System.Object
0x50887  dup
0x50888  ldc.i4.0
0x50889  ldloc.3
0x5088a  callvirt instance string [mscorlib]System.Object::ToString()
0x5088f  stelem.ref
0x50890  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x50895  ldloc.3
0x50896  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException
0x5089b  brfalse.s loc_5089F
0x5089d  rethrow
0x5089f  ldloc.3
0x508a0  ldnull
0x508a1  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(class [mscorlib]System.Exception, string)
0x508a6  throw
0x508a7  ldarg.0
0x508a8  ldc.i4.0
0x508a9  stfld    bool Microsoft.ReportingServices.Library.ServiceController::m_startThreadExitStarted
0x508ae  ldarg.0
0x508af  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x508b4  endfinally
0x508b5  ret
```
