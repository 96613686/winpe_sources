# Microsoft.ReportingServices.Library.ServiceAppDomainController::CycleWindowsServiceAppDomain

- ea: `0x4f240`
- end: `0x4f3b0`
- name: `Microsoft.ReportingServices.Library.ServiceAppDomainController::CycleWindowsServiceAppDomain`
- size: `368`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x4f3b0`

## callees

- `0x4df60`
- `0x4dfb0`
- `0x4ecf0`
- `0x4f240`
- `0x4f590`
- `0x4f600`
- `0x4f900`
- `0x4fa40`
- `0x8b3b0`

## string_xrefs

- `0x4f25d`: `Recycling the WindowsService AppDomain from the default domain. Max allowed unload time = {0} sec`
- `0x4f300`: `ServiceAppDomainController::CycleWindowsServiceAppDomain - Memory pressure detected; Mark the WindowsService (worker) AppDomain as active.`

## pseudocode

```c

```

## disassembly

```asm
0x4f240  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x4f245  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_MaxAppDomainUnloadTime()
0x4f24a  stloc.0
0x4f24b  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4f250  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x4f255  brfalse.s loc_4F27C
0x4f257  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4f25c  ldc.i4.3
0x4f25d  ldstr    aRecyclingTheWi// "Recycling the WindowsService AppDomain "...
0x4f262  ldc.i4.1
0x4f263  newarr   [mscorlib]System.Object
0x4f268  dup
0x4f269  ldc.i4.0
0x4f26a  ldloca.s 0
0x4f26c  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x4f271  box      [mscorlib]System.Double
0x4f276  stelem.ref
0x4f277  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x4f27c  nop
0x4f27d  ldarg.0
0x4f27e  ldc.i4.1
0x4f27f  call     instance void Microsoft.ReportingServices.Library.ServiceAppDomainController::InternalStop(valuetype AppDomainStopMode stopMode)
0x4f284  leave.s  loc_4F2CB
0x4f286  newobj   instance void DeadDomain::.ctor()
0x4f28b  stloc.1
0x4f28c  ldloc.1
0x4f28d  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x4f292  stfld    valuetype [mscorlib]System.DateTime DeadDomain::TimeDied
0x4f297  ldloc.1
0x4f298  ldarg.0
0x4f299  ldfld    class [mscorlib]System.AppDomain Microsoft.ReportingServices.Library.ServiceAppDomainController::m_workerAppDomain
0x4f29e  stfld    class [mscorlib]System.AppDomain DeadDomain::ApplicationDomain
0x4f2a3  ldloc.1
0x4f2a4  ldarg.0
0x4f2a5  call     instance class Microsoft.ReportingServices.Library.IServiceAppDomain Microsoft.ReportingServices.Library.ServiceAppDomainController::get_WorkerDomainProxy()
0x4f2aa  stfld    class Microsoft.ReportingServices.Library.IServiceAppDomain DeadDomain::WorkerDomainProxy
0x4f2af  ldarg.0
0x4f2b0  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.ReportingServices.Library.ServiceAppDomainController::m_deadDomains
0x4f2b5  ldloc.1
0x4f2b6  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x4f2bb  pop
0x4f2bc  ldarg.0
0x4f2bd  ldnull
0x4f2be  stfld    class [mscorlib]System.AppDomain Microsoft.ReportingServices.Library.ServiceAppDomainController::m_workerAppDomain
0x4f2c3  ldarg.0
0x4f2c4  ldnull
0x4f2c5  call     instance void Microsoft.ReportingServices.Library.ServiceAppDomainController::set_WorkerDomainProxy(class Microsoft.ReportingServices.Library.IServiceAppDomain value)
0x4f2ca  endfinally
0x4f2cb  ldarg.1
0x4f2cc  ldfld    bool Recycle::ensureWindowsAppDomainUnload
0x4f2d1  brfalse  loc_4F38E
0x4f2d6  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x4f2db  stloc.2
0x4f2dc  ldarg.1
0x4f2dd  ldfld    bool Recycle::memoryRecycle
0x4f2e2  brfalse  loc_4F382
0x4f2e7  ldc.i4.0
0x4f2e8  stloc.3
0x4f2e9  br       loc_4F377
0x4f2ee  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4f2f3  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x4f2f8  brfalse.s loc_4F30A
0x4f2fa  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4f2ff  ldc.i4.3
0x4f300  ldstr    aServiceappdoma_1// "ServiceAppDomainController::CycleWindow"...
0x4f305  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x4f30a  ldarg.0
0x4f30b  call     instance void Microsoft.ReportingServices.Library.ServiceAppDomainController::MarkProcessAsActive()
0x4f310  ldloc.0
0x4f311  ldsfld   valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::MinValue
0x4f316  call     bool [mscorlib]System.TimeSpan::op_Inequality(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x4f31b  brfalse.s loc_4F34E
0x4f31d  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x4f322  ldloc.2
0x4f323  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x4f328  ldloc.0
0x4f329  call     bool [mscorlib]System.TimeSpan::op_GreaterThan(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x4f32e  brfalse.s loc_4F34E
0x4f330  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4f335  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x4f33a  brfalse.s loc_4F382
0x4f33c  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4f341  ldc.i4.3
0x4f342  ldstr    aForcingUnloadO// "Forcing unload of domains due to max un"...
0x4f347  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x4f34c  br.s     loc_4F382
0x4f34e  ldarg.0
0x4f34f  ldfld    class [mscorlib]System.Threading.AutoResetEvent Microsoft.ReportingServices.Library.ServiceAppDomainController::m_resetEvent
0x4f354  ldc.i4   0x3E8
0x4f359  ldc.i4.0
0x4f35a  callvirt instance bool [mscorlib]System.Threading.WaitHandle::WaitOne(int32, bool)
0x4f35f  pop
0x4f360  ldloc.3
0x4f361  ldc.i4.s 0x1E
0x4f363  rem
0x4f364  ldc.i4.0
0x4f365  ceq
0x4f367  stloc.s  4
0x4f369  ldarg.0
0x4f36a  ldloc.s  4
0x4f36c  call     instance bool Microsoft.ReportingServices.Library.ServiceAppDomainController::AreAnyDeadDomainsWorking(bool traceProgress)
0x4f371  brfalse.s loc_4F382
0x4f373  ldloc.3
0x4f374  ldc.i4.1
0x4f375  add
0x4f376  stloc.3
0x4f377  ldarg.0
0x4f378  ldfld    bool Microsoft.ReportingServices.Library.ServiceAppDomainController::m_continue
0x4f37d  brtrue   loc_4F2EE
0x4f382  ldarg.0
0x4f383  ldarg.1
0x4f384  ldfld    bool Recycle::memoryRecycle
0x4f389  call     instance void Microsoft.ReportingServices.Library.ServiceAppDomainController::UnloadAllDeadDomains(bool memoryRecycle)
0x4f38e  ldarg.0
0x4f38f  ldfld    bool Microsoft.ReportingServices.Library.ServiceAppDomainController::m_continue
0x4f394  brfalse.s loc_4F3AF
0x4f396  ldarg.0
0x4f397  ldc.i4.0
0x4f398  stfld    int32 Microsoft.ReportingServices.Library.ServiceAppDomainController::m_configChanged
0x4f39d  ldarg.0
0x4f39e  ldc.i4.0
0x4f39f  call     instance void Microsoft.ReportingServices.Library.ServiceAppDomainController::StartServiceInNewAppDomain(bool firstTime)
0x4f3a4  ldarg.1
0x4f3a5  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x4f3aa  stfld    valuetype [mscorlib]System.DateTime Recycle::lastRecycle
0x4f3af  ret
```
