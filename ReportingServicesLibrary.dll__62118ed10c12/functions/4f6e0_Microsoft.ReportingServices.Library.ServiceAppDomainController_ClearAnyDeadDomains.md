# Microsoft.ReportingServices.Library.ServiceAppDomainController::ClearAnyDeadDomains

- ea: `0x4f6e0`
- end: `0x4f8fe`
- name: `Microsoft.ReportingServices.Library.ServiceAppDomainController::ClearAnyDeadDomains`
- size: `542`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x4f3b0`

## callees

- `0x4d340`
- `0x4d350`
- `0x4f6e0`
- `0x4f900`
- `0x4fae0`

## string_xrefs

- `0x4f778`: `Clearing dead AppDomain {0}: the DomainProxy has been disposed already in EndService`
- `0x4f7c1`: `Clearing dead AppDomain {0}: MaxTimedAppDomainUnload should be configured in order to force an unload herein`
- `0x4f8e2`: `ServiceAppDomainController::ClearAnyDeadDomains - Cleared dead AppDomains; Mark the WindowsService (worker) AppDomain as active.`

## pseudocode

```c

```

## disassembly

```asm
0x4f6e0  ldarg.0
0x4f6e1  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.ReportingServices.Library.ServiceAppDomainController::m_deadDomains
0x4f6e6  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x4f6eb  brtrue.s loc_4F6EE
0x4f6ed  ret
0x4f6ee  ldarg.0
0x4f6ef  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.ReportingServices.Library.ServiceAppDomainController::m_deadDomains
0x4f6f4  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x4f6f9  ldc.i4.1
0x4f6fa  sub
0x4f6fb  stloc.0
0x4f6fc  br       loc_4F8F6
0x4f701  ldarg.0
0x4f702  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.ReportingServices.Library.ServiceAppDomainController::m_deadDomains
0x4f707  ldloc.0
0x4f708  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x4f70d  castclass DeadDomain
0x4f712  stloc.1
0x4f713  ldloc.1
0x4f714  ldfld    class [mscorlib]System.AppDomain DeadDomain::ApplicationDomain
0x4f719  stloc.2
0x4f71a  ldloc.1
0x4f71b  ldfld    class Microsoft.ReportingServices.Library.IServiceAppDomain DeadDomain::WorkerDomainProxy
0x4f720  stloc.3
0x4f721  ldsfld   string [mscorlib]System.String::Empty
0x4f726  stloc.s  4
0x4f728  ldc.i4.m1
0x4f729  stloc.s  5
0x4f72b  ldloc.2
0x4f72c  brfalse.s loc_4F73E
0x4f72e  ldloc.2
0x4f72f  callvirt instance int32 [mscorlib]System.AppDomain::get_Id()
0x4f734  stloc.s  5
0x4f736  ldloc.2
0x4f737  callvirt instance string [mscorlib]System.AppDomain::get_FriendlyName()
0x4f73c  stloc.s  4
0x4f73e  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4f743  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x4f748  brfalse.s loc_4F792
0x4f74a  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4f74f  ldc.i4.3
0x4f750  ldstr    aClearingDeadAp// "Clearing dead AppDomain {0} ('{1}')"
0x4f755  ldc.i4.2
0x4f756  newarr   [mscorlib]System.Object
0x4f75b  dup
0x4f75c  ldc.i4.0
0x4f75d  ldloc.s  5
0x4f75f  box      [mscorlib]System.Int32
0x4f764  stelem.ref
0x4f765  dup
0x4f766  ldc.i4.1
0x4f767  ldloc.s  4
0x4f769  stelem.ref
0x4f76a  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x4f76f  ldloc.3
0x4f770  brtrue.s loc_4F792
0x4f772  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4f777  ldc.i4.3
0x4f778  ldstr    aClearingDeadAp_0// "Clearing dead AppDomain {0}: the Domain"...
0x4f77d  ldc.i4.1
0x4f77e  newarr   [mscorlib]System.Object
0x4f783  dup
0x4f784  ldc.i4.0
0x4f785  ldloc.s  5
0x4f787  box      [mscorlib]System.Int32
0x4f78c  stelem.ref
0x4f78d  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x4f792  ldc.i4.0
0x4f793  stloc.s  6
0x4f795  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x4f79a  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_MaxTimedAppDomainUnload()
0x4f79f  stloc.s  7
0x4f7a1  ldloc.s  7
0x4f7a3  ldsfld   valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::MinValue
0x4f7a8  call     bool [mscorlib]System.TimeSpan::op_Equality(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x4f7ad  brfalse.s loc_4F7DD
0x4f7af  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4f7b4  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x4f7b9  brfalse.s loc_4F7F9
0x4f7bb  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4f7c0  ldc.i4.3
0x4f7c1  ldstr    aClearingDeadAp_1// "Clearing dead AppDomain {0}: MaxTimedAp"...
0x4f7c6  ldc.i4.1
0x4f7c7  newarr   [mscorlib]System.Object
0x4f7cc  dup
0x4f7cd  ldc.i4.0
0x4f7ce  ldloc.s  5
0x4f7d0  box      [mscorlib]System.Int32
0x4f7d5  stelem.ref
0x4f7d6  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x4f7db  br.s     loc_4F7F9
0x4f7dd  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x4f7e2  ldloc.1
0x4f7e3  ldfld    valuetype [mscorlib]System.DateTime DeadDomain::TimeDied
0x4f7e8  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x4f7ed  ldloc.s  7
0x4f7ef  call     bool [mscorlib]System.TimeSpan::op_GreaterThan(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x4f7f4  brfalse.s loc_4F7F9
0x4f7f6  ldc.i4.1
0x4f7f7  stloc.s  6
0x4f7f9  ldc.i4.0
0x4f7fa  stloc.s  8
0x4f7fc  ldloc.3
0x4f7fd  brfalse.s loc_4F807
0x4f7ff  ldloc.3
0x4f800  callvirt instance bool Microsoft.ReportingServices.Library.IServiceAppDomain::get_StillProcessing()
0x4f805  stloc.s  8
0x4f807  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4f80c  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x4f811  brfalse.s loc_4F87D
0x4f813  ldloc.s  8
0x4f815  brfalse.s loc_4F85D
0x4f817  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4f81c  ldc.i4.3
0x4f81d  ldstr    aClearingDeadAp_2// "Clearing dead AppDomain {0}: the AppDom"...
0x4f822  ldc.i4.1
0x4f823  newarr   [mscorlib]System.Object
0x4f828  dup
0x4f829  ldc.i4.0
0x4f82a  ldloc.s  5
0x4f82c  box      [mscorlib]System.Int32
0x4f831  stelem.ref
0x4f832  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x4f837  ldloc.s  6
0x4f839  brtrue.s loc_4F87D
0x4f83b  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4f840  ldc.i4.3
0x4f841  ldstr    aClearingDeadAp_3// "Clearing dead AppDomain {0}: the AppDom"...
0x4f846  ldc.i4.1
0x4f847  newarr   [mscorlib]System.Object
0x4f84c  dup
0x4f84d  ldc.i4.0
0x4f84e  ldloc.s  5
0x4f850  box      [mscorlib]System.Int32
0x4f855  stelem.ref
0x4f856  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x4f85b  br.s     loc_4F87D
0x4f85d  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4f862  ldc.i4.3
0x4f863  ldstr    aClearingDeadAp_4// "Clearing dead AppDomain {0}: the AppDom"...
0x4f868  ldc.i4.1
0x4f869  newarr   [mscorlib]System.Object
0x4f86e  dup
0x4f86f  ldc.i4.0
0x4f870  ldloc.s  5
0x4f872  box      [mscorlib]System.Int32
0x4f877  stelem.ref
0x4f878  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x4f87d  ldloc.s  8
0x4f87f  ldc.i4.0
0x4f880  ceq
0x4f882  ldloc.s  6
0x4f884  or
0x4f885  brfalse.s loc_4F8D0
0x4f887  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4f88c  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x4f891  brfalse.s loc_4F8B3
0x4f893  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4f898  ldc.i4.3
0x4f899  ldstr    aClearingDeadAp_5// "Clearing dead AppDomain {0}: the AppDom"...
0x4f89e  ldc.i4.1
0x4f89f  newarr   [mscorlib]System.Object
0x4f8a4  dup
0x4f8a5  ldc.i4.0
0x4f8a6  ldloc.s  5
0x4f8a8  box      [mscorlib]System.Int32
0x4f8ad  stelem.ref
0x4f8ae  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x4f8b3  ldloc.3
0x4f8b4  brfalse.s loc_4F8BD
0x4f8b6  ldloc.3
0x4f8b7  ldc.i4.0
0x4f8b8  callvirt instance void Microsoft.ReportingServices.Library.IServiceAppDomain::EndService(valuetype [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals/ServiceStopMode stopMode)
0x4f8bd  ldloc.2
0x4f8be  ldc.i4.0
0x4f8bf  call     void Microsoft.ReportingServices.Library.ServiceAppDomainController::UnloadAppDomain(class [mscorlib]System.AppDomain domain, bool memoryRecycle)
0x4f8c4  ldarg.0
0x4f8c5  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.ReportingServices.Library.ServiceAppDomainController::m_deadDomains
0x4f8ca  ldloc.0
0x4f8cb  callvirt instance void [mscorlib]System.Collections.ArrayList::RemoveAt(int32)
0x4f8d0  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4f8d5  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x4f8da  brfalse.s loc_4F8EC
0x4f8dc  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4f8e1  ldc.i4.3
0x4f8e2  ldstr    aServiceappdoma_4// "ServiceAppDomainController::ClearAnyDea"...
0x4f8e7  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x4f8ec  ldarg.0
0x4f8ed  call     instance void Microsoft.ReportingServices.Library.ServiceAppDomainController::MarkProcessAsActive()
0x4f8f2  ldloc.0
0x4f8f3  ldc.i4.1
0x4f8f4  sub
0x4f8f5  stloc.0
0x4f8f6  ldloc.0
0x4f8f7  ldc.i4.0
0x4f8f8  bge      loc_4F701
0x4f8fd  ret
```
