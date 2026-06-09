# Microsoft.ReportingServices.Library.ServiceAppDomainController::StartServiceInNewAppDomain

- ea: `0x4ecf0`
- end: `0x4ee92`
- name: `Microsoft.ReportingServices.Library.ServiceAppDomainController::StartServiceInNewAppDomain`
- size: `418`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x4e180`
- `0x4f240`
- `0x4f3b0`

## callees

- `0x4d330`
- `0x4d360`
- `0x4df60`
- `0x4ecf0`
- `0x4eea0`

## string_xrefs

- `0x4ee22`: `Service failed to start. Error: {0}`
- `0x4ee7d`: `Exiting process because windows service failed to start.`

## pseudocode

```c

```

## disassembly

```asm
0x4ecf0  ldarg.0
0x4ecf1  ldfld    class [mscorlib]System.AppDomain Microsoft.ReportingServices.Library.ServiceAppDomainController::m_workerAppDomain
0x4ecf6  brtrue   loc_4EDE9
0x4ecfb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4ed00  ldstr    a01_5// "{0}_{1}"
0x4ed05  ldc.i4.1
0x4ed06  box      [ReportingServicesAppDomainManager]Microsoft.ReportingServices.HostingInterfaces.RsAppDomainType
0x4ed0b  ldarg.0
0x4ed0c  ldarg.0
0x4ed0d  ldfld    int64 Microsoft.ReportingServices.Library.ServiceAppDomainController::m_serviceAppDomainInstanceCounter
0x4ed12  stloc.2
0x4ed13  ldloc.2
0x4ed14  ldc.i4.1
0x4ed15  conv.i8
0x4ed16  add
0x4ed17  stfld    int64 Microsoft.ReportingServices.Library.ServiceAppDomainController::m_serviceAppDomainInstanceCounter
0x4ed1c  ldloc.2
0x4ed1d  box      [mscorlib]System.Int64
0x4ed22  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object)
0x4ed27  stloc.1
0x4ed28  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x4ed2d  stloc.3
0x4ed2e  newobj   instance void [mscorlib]System.AppDomainSetup::.ctor()
0x4ed33  stloc.s  4
0x4ed35  ldloc.s  4
0x4ed37  ldloc.3
0x4ed38  callvirt instance class [mscorlib]System.AppDomainSetup [mscorlib]System.AppDomain::get_SetupInformation()
0x4ed3d  callvirt instance string [mscorlib]System.AppDomainSetup::get_ApplicationBase()
0x4ed42  callvirt instance void [mscorlib]System.AppDomainSetup::set_ApplicationBase(string)
0x4ed47  ldloc.s  4
0x4ed49  ldc.i4.3
0x4ed4a  callvirt instance void [mscorlib]System.AppDomainSetup::set_LoaderOptimization(valuetype [mscorlib]System.LoaderOptimization)
0x4ed4f  ldarg.0
0x4ed50  ldloc.1
0x4ed51  ldarg.0
0x4ed52  call     instance class [mscorlib]System.Security.Policy.Evidence Microsoft.ReportingServices.Library.ServiceAppDomainController::GetDefaultDomainIdentity()
0x4ed57  ldloc.s  4
0x4ed59  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::CreateDomain(string, class [mscorlib]System.Security.Policy.Evidence, class [mscorlib]System.AppDomainSetup)
0x4ed5e  stfld    class [mscorlib]System.AppDomain Microsoft.ReportingServices.Library.ServiceAppDomainController::m_workerAppDomain
0x4ed63  leave    loc_4EDE9
0x4ed68  stloc.s  5
0x4ed6a  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::get_Current()
0x4ed6f  ldc.i4   0x8B
0x4ed74  ldc.i4.2
0x4ed75  newarr   [mscorlib]System.Object
0x4ed7a  dup
0x4ed7b  ldc.i4.0
0x4ed7c  ldloc.1
0x4ed7d  stelem.ref
0x4ed7e  dup
0x4ed7f  ldc.i4.1
0x4ed80  ldloc.s  5
0x4ed82  callvirt instance string [mscorlib]System.Object::ToString()
0x4ed87  stelem.ref
0x4ed88  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::WriteError(valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Event, object[])
0x4ed8d  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_AppDomainManagerTracer()
0x4ed92  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x4ed97  brfalse.s loc_4EDBD
0x4ed99  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_AppDomainManagerTracer()
0x4ed9e  ldc.i4.1
0x4ed9f  ldstr    aAppdomain0Fail// "AppDomain {0} failed to start. Error: {"...
0x4eda4  ldc.i4.2
0x4eda5  newarr   [mscorlib]System.Object
0x4edaa  dup
0x4edab  ldc.i4.0
0x4edac  ldloc.1
0x4edad  stelem.ref
0x4edae  dup
0x4edaf  ldc.i4.1
0x4edb0  ldloc.s  5
0x4edb2  callvirt instance string [mscorlib]System.Object::ToString()
0x4edb7  stelem.ref
0x4edb8  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x4edbd  ldloc.s  5
0x4edbf  ldsfld   class [mscorlib]System.Predicate`1<class [mscorlib]System.Exception> <>c::<>9__46_0
0x4edc4  dup
0x4edc5  brtrue.s loc_4EDDE
0x4edc7  pop
0x4edc8  ldsfld   class <>c <>c::<>9
0x4edcd  ldftn    instance bool <>c::<StartServiceInNewAppDomain>b__46_0(class [mscorlib]System.Exception ex)
0x4edd3  newobj   instance void class [mscorlib]System.Predicate`1<class [mscorlib]System.Exception>::.ctor(object, native int)
0x4edd8  dup
0x4edd9  stsfld   class [mscorlib]System.Predicate`1<class [mscorlib]System.Exception> <>c::<>9__46_0
0x4edde  call     bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Exceptions.ExceptionUtils::ContainsException(class [mscorlib]System.Exception, class [mscorlib]System.Predicate`1<class [mscorlib]System.Exception>)
0x4ede3  brfalse.s loc_4EDE7
0x4ede5  rethrow
0x4ede7  leave.s  loc_4EDE9
0x4ede9  ldc.i4.0
0x4edea  stloc.0
0x4edeb  ldarg.0
0x4edec  call     instance class Microsoft.ReportingServices.Library.IServiceAppDomain Microsoft.ReportingServices.Library.ServiceAppDomainController::get_WorkerDomainProxy()
0x4edf1  brfalse.s loc_4EE0C
0x4edf3  ldarg.0
0x4edf4  call     instance class Microsoft.ReportingServices.Library.IServiceAppDomain Microsoft.ReportingServices.Library.ServiceAppDomainController::get_WorkerDomainProxy()
0x4edf9  ldarg.0
0x4edfa  ldarg.1
0x4edfb  callvirt instance void Microsoft.ReportingServices.Library.IServiceAppDomain::StartService(class Microsoft.ReportingServices.Library.IServiceAppDomainController controller, bool firstStart)
0x4ee00  ldarg.0
0x4ee01  call     instance class Microsoft.ReportingServices.Library.IServiceAppDomain Microsoft.ReportingServices.Library.ServiceAppDomainController::get_WorkerDomainProxy()
0x4ee06  callvirt instance bool Microsoft.ReportingServices.Library.IServiceAppDomain::get_IsServiceStarted()
0x4ee0b  stloc.0
0x4ee0c  leave.s  loc_4EE68
0x4ee0e  stloc.s  6
0x4ee10  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_AppDomainManagerTracer()
0x4ee15  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x4ee1a  brfalse.s loc_4EE3C
0x4ee1c  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_AppDomainManagerTracer()
0x4ee21  ldc.i4.1
0x4ee22  ldstr    aServiceFailedT// "Service failed to start. Error: {0}"
0x4ee27  ldc.i4.1
0x4ee28  newarr   [mscorlib]System.Object
0x4ee2d  dup
0x4ee2e  ldc.i4.0
0x4ee2f  ldloc.s  6
0x4ee31  callvirt instance string [mscorlib]System.Object::ToString()
0x4ee36  stelem.ref
0x4ee37  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x4ee3c  ldloc.s  6
0x4ee3e  ldsfld   class [mscorlib]System.Predicate`1<class [mscorlib]System.Exception> <>c::<>9__46_1
0x4ee43  dup
0x4ee44  brtrue.s loc_4EE5D
0x4ee46  pop
0x4ee47  ldsfld   class <>c <>c::<>9
0x4ee4c  ldftn    instance bool <>c::<StartServiceInNewAppDomain>b__46_1(class [mscorlib]System.Exception ex)
0x4ee52  newobj   instance void class [mscorlib]System.Predicate`1<class [mscorlib]System.Exception>::.ctor(object, native int)
0x4ee57  dup
0x4ee58  stsfld   class [mscorlib]System.Predicate`1<class [mscorlib]System.Exception> <>c::<>9__46_1
0x4ee5d  call     bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Exceptions.ExceptionUtils::ContainsException(class [mscorlib]System.Exception, class [mscorlib]System.Predicate`1<class [mscorlib]System.Exception>)
0x4ee62  brfalse.s loc_4EE66
0x4ee64  rethrow
0x4ee66  leave.s  loc_4EE68
0x4ee68  ldloc.0
0x4ee69  brtrue.s loc_4EE91
0x4ee6b  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_AppDomainManagerTracer()
0x4ee70  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x4ee75  brfalse.s loc_4EE87
0x4ee77  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_AppDomainManagerTracer()
0x4ee7c  ldc.i4.1
0x4ee7d  ldstr    aExitingProcess// "Exiting process because windows service"...
0x4ee82  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x4ee87  call     class [System]System.Diagnostics.Process [System]System.Diagnostics.Process::GetCurrentProcess()
0x4ee8c  callvirt instance void [System]System.Diagnostics.Process::Kill()
0x4ee91  ret
```
