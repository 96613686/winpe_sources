# Microsoft.ReportingServices.Library.ServiceController::ServiceStartThread

- ea: `0x502c0`
- end: `0x50588`
- name: `Microsoft.ReportingServices.Library.ServiceController::ServiceStartThread`
- size: `712`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0xf070`
- `0x4d300`
- `0x4fd30`
- `0x50080`
- `0x502c0`
- `0x505d0`
- `0x506e0`
- `0x508c0`

## string_xrefs

- `0x5033a`: `ServiceStartThread: Exiting for the following exception: {0}`
- `0x50370`: `ServiceStartThread: Exiting for the following exception: {0}`
- `0x503bb`: `ServiceStartThread: Exception caught while starting service. Error: {0}`
- `0x503db`: `ServiceStartThread: Attempting to start service again...`

## pseudocode

```c

```

## disassembly

```asm
0x502c0  ldc.i4.0
0x502c1  stloc.0
0x502c2  ldc.i4.0
0x502c3  stloc.1
0x502c4  ldc.i4.0
0x502c5  stloc.2
0x502c6  ldnull
0x502c7  stloc.3
0x502c8  ldc.i4.0
0x502c9  stloc.0
0x502ca  ldnull
0x502cb  stloc.s  4
0x502cd  newobj   instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::.ctor()
0x502d2  stloc.s  4
0x502d4  ldloc.s  4
0x502d6  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::WillDisconnectStorage()
0x502db  ldloc.s  4
0x502dd  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::VerifyConnectionAndDbVersion()
0x502e2  ldloc.s  4
0x502e4  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::EnsureDBCmptLevel()
0x502e9  call     void Microsoft.ReportingServices.Library.ServiceController::EnsureConfigurationFromDB()
0x502ee  ldloc.2
0x502ef  brtrue.s loc_502F9
0x502f1  ldarg.0
0x502f2  call     instance void Microsoft.ReportingServices.Library.ServiceController::SetAppDomainPolicy()
0x502f7  ldc.i4.1
0x502f8  stloc.2
0x502f9  ldarg.0
0x502fa  call     instance void Microsoft.ReportingServices.Library.ServiceController::StartDatabaseVersionCheckTimer()
0x502ff  ldarg.0
0x50300  call     instance void Microsoft.ReportingServices.Library.ServiceController::PreparePollingMaintenance()
0x50305  ldarg.0
0x50306  call     instance void Microsoft.ReportingServices.Library.ServiceController::StartAllWorkers()
0x5030b  ldnull
0x5030c  stloc.3
0x5030d  leave    loc_50421
0x50312  stloc.s  5
0x50314  ldloc.s  5
0x50316  call     bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Exceptions.ExceptionUtils::IsStoppingException(class [mscorlib]System.Exception)
0x5031b  brfalse.s loc_50392
0x5031d  ldloc.s  5
0x5031f  isinst   [mscorlib]System.Threading.ThreadAbortException
0x50324  brfalse.s loc_5035C
0x50326  ldarg.0
0x50327  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.ServiceController::m_tracer
0x5032c  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x50331  brfalse.s loc_50354
0x50333  ldarg.0
0x50334  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.ServiceController::m_tracer
0x50339  ldc.i4.3
0x5033a  ldstr    aServicestartth// "ServiceStartThread: Exiting for the fol"...
0x5033f  ldc.i4.1
0x50340  newarr   [mscorlib]System.Object
0x50345  dup
0x50346  ldc.i4.0
0x50347  ldloc.s  5
0x50349  callvirt instance string [mscorlib]System.Exception::get_Message()
0x5034e  stelem.ref
0x5034f  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x50354  ldloc.s  5
0x50356  stloc.3
0x50357  leave    loc_50587
0x5035c  ldarg.0
0x5035d  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.ServiceController::m_tracer
0x50362  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x50367  brfalse.s loc_5038A
0x50369  ldarg.0
0x5036a  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.ServiceController::m_tracer
0x5036f  ldc.i4.1
0x50370  ldstr    aServicestartth// "ServiceStartThread: Exiting for the fol"...
0x50375  ldc.i4.1
0x50376  newarr   [mscorlib]System.Object
0x5037b  dup
0x5037c  ldc.i4.0
0x5037d  ldloc.s  5
0x5037f  callvirt instance string [mscorlib]System.Object::ToString()
0x50384  stelem.ref
0x50385  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x5038a  ldloc.s  5
0x5038c  stloc.3
0x5038d  leave    loc_50587
0x50392  ldloc.3
0x50393  brfalse.s loc_503A9
0x50395  ldloc.s  5
0x50397  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x5039c  ldloc.3
0x5039d  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x503a2  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x503a7  brfalse.s loc_503FC
0x503a9  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.Global::m_Tracer
0x503ae  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x503b3  brfalse.s loc_503E5
0x503b5  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.Global::m_Tracer
0x503ba  ldc.i4.1
0x503bb  ldstr    aServicestartth_0// "ServiceStartThread: Exception caught wh"...
0x503c0  ldc.i4.1
0x503c1  newarr   [mscorlib]System.Object
0x503c6  dup
0x503c7  ldc.i4.0
0x503c8  ldloc.s  5
0x503ca  callvirt instance string [mscorlib]System.Object::ToString()
0x503cf  stelem.ref
0x503d0  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x503d5  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.Global::m_Tracer
0x503da  ldc.i4.1
0x503db  ldstr    aServicestartth_1// "ServiceStartThread: Attempting to start"...
0x503e0  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x503e5  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.Global::m_Tracer
0x503ea  ldc.i4.1
0x503eb  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::set_BufferOutput(bool)
0x503f0  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.Global::m_Tracer
0x503f5  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::WriteBuffer()
0x503fa  br.s     loc_50406
0x503fc  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.Global::m_Tracer
0x50401  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::ClearBuffer()
0x50406  ldloc.s  5
0x50408  stloc.3
0x50409  ldarg.0
0x5040a  ldfld    bool Microsoft.ReportingServices.Library.ServiceController::m_startThreadExitStarted
0x5040f  ldc.i4.0
0x50410  ceq
0x50412  stloc.0
0x50413  leave.s  loc_50421
0x50415  ldloc.s  4
0x50417  brfalse.s loc_50420
0x50419  ldloc.s  4
0x5041b  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::DisconnectStorage()
0x50420  endfinally
0x50421  ldloc.1
0x50422  brtrue.s loc_5043E
0x50424  ldarg.0
0x50425  ldfld    bool Microsoft.ReportingServices.Library.ServiceController::m_startThreadExitStarted
0x5042a  brtrue.s loc_5043E
0x5042c  ldarg.0
0x5042d  ldfld    class Microsoft.ReportingServices.Library.IServiceAppDomainController Microsoft.ReportingServices.Library.ServiceController::m_appDomainController
0x50432  ldarg.1
0x50433  unbox.any [mscorlib]System.Boolean
0x50438  callvirt instance bool Microsoft.ReportingServices.Library.IServiceAppDomainController::StartRPCServer(bool firstTime)
0x5043d  stloc.1
0x5043e  ldloc.0
0x5043f  brfalse.s loc_50453
0x50441  ldarg.0
0x50442  ldfld    class [mscorlib]System.Threading.AutoResetEvent Microsoft.ReportingServices.Library.ServiceController::m_serviceResetEvent
0x50447  ldc.i4   0x1388
0x5044c  ldc.i4.0
0x5044d  callvirt instance bool [mscorlib]System.Threading.WaitHandle::WaitOne(int32, bool)
0x50452  pop
0x50453  ldloc.0
0x50454  brtrue   loc_502C8
0x50459  leave    loc_50587
0x5045e  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.Global::m_Tracer
0x50463  ldc.i4.0
0x50464  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::set_BufferOutput(bool)
0x50469  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.Global::m_Tracer
0x5046e  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::WriteBuffer()
0x50473  ldstr    asc_90EAC// ""
0x50478  stloc.s  6
0x5047a  ldloc.3
0x5047b  ldnull
0x5047c  ceq
0x5047e  ldloc.1
0x5047f  and
0x50480  brfalse.s loc_504D9
0x50482  call     void Microsoft.ReportingServices.Library.Global::SetInitialized()
0x50487  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5048c  ldstr    aAppdomain01Ini// "Appdomain:{0} {1} initialized."
0x50491  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x50496  callvirt instance int32 [mscorlib]System.AppDomain::get_Id()
0x5049b  box      [mscorlib]System.Int32
0x504a0  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x504a5  callvirt instance string [mscorlib]System.AppDomain::get_FriendlyName()
0x504aa  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object)
0x504af  stloc.s  6
0x504b1  ldloc.s  6
0x504b3  call     void [mscorlib]System.Console::WriteLine(string)
0x504b8  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_AppDomainManagerTracer()
0x504bd  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x504c2  brfalse  loc_5057F
0x504c7  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_AppDomainManagerTracer()
0x504cc  ldc.i4.3
0x504cd  ldloc.s  6
0x504cf  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x504d4  br       loc_5057F
0x504d9  ldarg.0
0x504da  ldfld    bool Microsoft.ReportingServices.Library.ServiceController::m_startThreadExitStarted
0x504df  brtrue   loc_5057F
0x504e4  ldstr    asc_90EAC// ""
0x504e9  stloc.s  7
0x504eb  ldloc.3
0x504ec  brfalse.s loc_504F8
0x504ee  ldloc.3
0x504ef  callvirt instance string [mscorlib]System.Object::ToString()
0x504f4  stloc.s  7
0x504f6  br.s     loc_5050C
0x504f8  ldloc.1
0x504f9  brtrue.s loc_5050C
0x504fb  ldc.i4   0x6B8
0x50500  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor(int32)
0x50505  callvirt instance string [mscorlib]System.Exception::get_Message()
0x5050a  stloc.s  7
0x5050c  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::get_Current()
0x50511  ldc.i4   0x8C
0x50516  ldc.i4.2
0x50517  newarr   [mscorlib]System.Object
0x5051c  dup
0x5051d  ldc.i4.0
0x5051e  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x50523  callvirt instance string [mscorlib]System.AppDomain::get_FriendlyName()
0x50528  stelem.ref
0x50529  dup
0x5052a  ldc.i4.1
0x5052b  ldloc.s  7
0x5052d  stelem.ref
0x5052e  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::WriteError(valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Event, object[])
0x50533  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x50538  ldstr    aAppdomain01Fai// "Appdomain:{0} {1} failed to initialize."...
0x5053d  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x50542  callvirt instance int32 [mscorlib]System.AppDomain::get_Id()
0x50547  box      [mscorlib]System.Int32
0x5054c  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x50551  callvirt instance string [mscorlib]System.AppDomain::get_FriendlyName()
0x50556  ldloc.s  7
0x50558  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object, object)
0x5055d  stloc.s  6
0x5055f  ldloc.s  6
0x50561  call     void [mscorlib]System.Console::WriteLine(string)
0x50566  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_AppDomainManagerTracer()
0x5056b  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x50570  brfalse.s loc_5057F
0x50572  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_AppDomainManagerTracer()
0x50577  ldc.i4.1
0x50578  ldloc.s  6
0x5057a  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x5057f  ldarg.0
0x50580  ldc.i4.1
0x50581  stfld    bool Microsoft.ReportingServices.Library.ServiceController::m_serviceStartThreadExited
0x50586  endfinally
0x50587  ret
```
