# Microsoft.ReportingServices.Library.ServiceAppDomainController::ServiceMaintenanceInternal

- ea: `0x4f3b0`
- end: `0x4f590`
- name: `Microsoft.ReportingServices.Library.ServiceAppDomainController::ServiceMaintenanceInternal`
- size: `480`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x4efb0`

## callees

- `0x4df60`
- `0x4ecf0`
- `0x4efe0`
- `0x4f040`
- `0x4f0e0`
- `0x4f150`
- `0x4f190`
- `0x4f240`
- `0x4f3b0`
- `0x4f6e0`
- `0x4f900`
- `0x8b380`

## string_xrefs

- `0x4f475`: `ServiceAppDomainController::ServiceMaintenanceInternal - Mark the WindowsService (worker) AppDomain as active.`
- `0x4f4c4`: `ServiceMaintenanceInternal: caught an exception: {0}`
- `0x4f518`: `ServiceMaintenanceInternal: Exiting process for the following exception: {0}`
- `0x4f54f`: `ServiceMaintenanceInternal: Restarting maintenance thread for the following exception: {0}.`

## pseudocode

```c

```

## disassembly

```asm
0x4f3b0  ldloca.s 0
0x4f3b2  initobj  Recycle
0x4f3b8  ldloca.s 0
0x4f3ba  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x4f3bf  stfld    valuetype [mscorlib]System.DateTime Recycle::lastRecycle
0x4f3c4  ldloca.s 0
0x4f3c6  ldc.i4.0
0x4f3c7  stfld    int32 Recycle::memoryExceedingLimitCount
0x4f3cc  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4f3d1  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x4f3d6  brfalse.s loc_4F3FC
0x4f3d8  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4f3dd  ldc.i4.3
0x4f3de  ldstr    aTotalPhysicalM// "Total Physical memory: {0}"
0x4f3e3  ldc.i4.1
0x4f3e4  newarr   [mscorlib]System.Object
0x4f3e9  dup
0x4f3ea  ldc.i4.0
0x4f3eb  ldarg.0
0x4f3ec  ldfld    unsigned int64 Microsoft.ReportingServices.Library.ServiceAppDomainController::m_totalPhysicalMemory
0x4f3f1  box      [mscorlib]System.UInt64
0x4f3f6  stelem.ref
0x4f3f7  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x4f3fc  ldloca.s 0
0x4f3fe  call     instance void Recycle::Reset()
0x4f403  ldarg.0
0x4f404  call     instance class Microsoft.ReportingServices.Library.IServiceAppDomain Microsoft.ReportingServices.Library.ServiceAppDomainController::get_WorkerDomainProxy()
0x4f409  brtrue.s loc_4F41E
0x4f40b  ldarg.0
0x4f40c  ldc.i4.0
0x4f40d  call     instance void Microsoft.ReportingServices.Library.ServiceAppDomainController::StartServiceInNewAppDomain(bool firstTime)
0x4f412  ldloca.s 0
0x4f414  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x4f419  stfld    valuetype [mscorlib]System.DateTime Recycle::lastRecycle
0x4f41e  ldarg.0
0x4f41f  ldloca.s 0
0x4f421  call     instance void Microsoft.ReportingServices.Library.ServiceAppDomainController::CheckForScheduledRecycle(valuetype Recycle& recycle)
0x4f426  ldarg.0
0x4f427  ldloca.s 0
0x4f429  call     instance void Microsoft.ReportingServices.Library.ServiceAppDomainController::CheckForExceedingMemoryRecycle(valuetype Recycle& recycle)
0x4f42e  ldarg.0
0x4f42f  ldloca.s 0
0x4f431  call     instance void Microsoft.ReportingServices.Library.ServiceAppDomainController::CheckForServiceNotWorkingRecycle(valuetype Recycle& recycle)
0x4f436  ldarg.0
0x4f437  ldloca.s 0
0x4f439  call     instance void Microsoft.ReportingServices.Library.ServiceAppDomainController::CheckForConfigChangedRecycle(valuetype Recycle& recycle)
0x4f43e  ldloc.0
0x4f43f  ldfld    bool Recycle::cycleWebAppDomains
0x4f444  brfalse.s loc_4F44D
0x4f446  ldarg.0
0x4f447  ldloc.0
0x4f448  call     instance void Microsoft.ReportingServices.Library.ServiceAppDomainController::CycleWebAppDomains(valuetype Recycle recycle)
0x4f44d  ldloc.0
0x4f44e  ldfld    bool Recycle::cycleWindowsServiceAppDomain
0x4f453  brfalse.s loc_4F45D
0x4f455  ldarg.0
0x4f456  ldloca.s 0
0x4f458  call     instance void Microsoft.ReportingServices.Library.ServiceAppDomainController::CycleWindowsServiceAppDomain(valuetype Recycle& recycle)
0x4f45d  ldarg.0
0x4f45e  call     instance void Microsoft.ReportingServices.Library.ServiceAppDomainController::ClearAnyDeadDomains()
0x4f463  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4f468  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x4f46d  brfalse.s loc_4F47F
0x4f46f  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4f474  ldc.i4.4
0x4f475  ldstr    aServiceappdoma_2// "ServiceAppDomainController::ServiceMain"...
0x4f47a  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x4f47f  ldarg.0
0x4f480  call     instance void Microsoft.ReportingServices.Library.ServiceAppDomainController::MarkProcessAsActive()
0x4f485  leave    loc_4F56A
0x4f48a  stloc.1
0x4f48b  ldloc.1
0x4f48c  ldsfld   class [mscorlib]System.Predicate`1<class [mscorlib]System.Exception> <>c::<>9__59_0
0x4f491  dup
0x4f492  brtrue.s loc_4F4AB
0x4f494  pop
0x4f495  ldsfld   class <>c <>c::<>9
0x4f49a  ldftn    instance bool <>c::<ServiceMaintenanceInternal>b__59_0(class [mscorlib]System.Exception ex)
0x4f4a0  newobj   instance void class [mscorlib]System.Predicate`1<class [mscorlib]System.Exception>::.ctor(object, native int)
0x4f4a5  dup
0x4f4a6  stsfld   class [mscorlib]System.Predicate`1<class [mscorlib]System.Exception> <>c::<>9__59_0
0x4f4ab  call     bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Exceptions.ExceptionUtils::ContainsException(class [mscorlib]System.Exception, class [mscorlib]System.Predicate`1<class [mscorlib]System.Exception>)
0x4f4b0  brfalse.s loc_4F4F7
0x4f4b2  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4f4b7  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x4f4bc  brfalse.s loc_4F4DD
0x4f4be  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4f4c3  ldc.i4.3
0x4f4c4  ldstr    aServicemainten// "ServiceMaintenanceInternal: caught an e"...
0x4f4c9  ldc.i4.1
0x4f4ca  newarr   [mscorlib]System.Object
0x4f4cf  dup
0x4f4d0  ldc.i4.0
0x4f4d1  ldloc.1
0x4f4d2  callvirt instance string [mscorlib]System.Exception::get_Message()
0x4f4d7  stelem.ref
0x4f4d8  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x4f4dd  ldloc.1
0x4f4de  isinst   [mscorlib]System.Threading.ThreadAbortException
0x4f4e3  brfalse.s loc_4F4EA
0x4f4e5  call     void [mscorlib]System.Threading.Thread::ResetAbort()
0x4f4ea  ldarg.0
0x4f4eb  ldfld    bool Microsoft.ReportingServices.Library.ServiceAppDomainController::m_continue
0x4f4f0  brtrue.s loc_4F53D
0x4f4f2  leave    loc_4F58F
0x4f4f7  ldloc.1
0x4f4f8  call     bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Exceptions.ExceptionUtils::IsStoppingException(class [mscorlib]System.Exception)
0x4f4fd  brfalse.s loc_4F53D
0x4f4ff  ldarg.0
0x4f500  ldc.i4.0
0x4f501  stfld    bool Microsoft.ReportingServices.Library.ServiceAppDomainController::m_continue
0x4f506  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4f50b  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x4f510  brfalse.s loc_4F531
0x4f512  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4f517  ldc.i4.1
0x4f518  ldstr    aServicemainten_0// "ServiceMaintenanceInternal: Exiting pro"...
0x4f51d  ldc.i4.1
0x4f51e  newarr   [mscorlib]System.Object
0x4f523  dup
0x4f524  ldc.i4.0
0x4f525  ldloc.1
0x4f526  callvirt instance string [mscorlib]System.Object::ToString()
0x4f52b  stelem.ref
0x4f52c  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x4f531  call     class [System]System.Diagnostics.Process [System]System.Diagnostics.Process::GetCurrentProcess()
0x4f536  callvirt instance void [System]System.Diagnostics.Process::Kill()
0x4f53b  leave.s  loc_4F58F
0x4f53d  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4f542  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x4f547  brfalse.s loc_4F568
0x4f549  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4f54e  ldc.i4.1
0x4f54f  ldstr    aServicemainten_1// "ServiceMaintenanceInternal: Restarting "...
0x4f554  ldc.i4.1
0x4f555  newarr   [mscorlib]System.Object
0x4f55a  dup
0x4f55b  ldc.i4.0
0x4f55c  ldloc.1
0x4f55d  callvirt instance string [mscorlib]System.Object::ToString()
0x4f562  stelem.ref
0x4f563  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x4f568  leave.s  loc_4F56A
0x4f56a  ldloc.0
0x4f56b  ldfld    bool Recycle::cycleWindowsServiceAppDomain
0x4f570  brtrue.s loc_4F584
0x4f572  ldarg.0
0x4f573  ldfld    class [mscorlib]System.Threading.AutoResetEvent Microsoft.ReportingServices.Library.ServiceAppDomainController::m_resetEvent
0x4f578  ldc.i4   0x3E8
0x4f57d  ldc.i4.0
0x4f57e  callvirt instance bool [mscorlib]System.Threading.WaitHandle::WaitOne(int32, bool)
0x4f583  pop
0x4f584  ldarg.0
0x4f585  ldfld    bool Microsoft.ReportingServices.Library.ServiceAppDomainController::m_continue
0x4f58a  brtrue   loc_4F3FC
0x4f58f  ret
```
