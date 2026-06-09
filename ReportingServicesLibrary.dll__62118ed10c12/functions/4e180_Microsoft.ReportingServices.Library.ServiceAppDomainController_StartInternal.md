# Microsoft.ReportingServices.Library.ServiceAppDomainController::StartInternal

- ea: `0x4e180`
- end: `0x4e410`
- name: `Microsoft.ReportingServices.Library.ServiceAppDomainController::StartInternal`
- size: `656`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x4e0d0`
- `0x4e180`
- `0x4e7b0`
- `0x4ea60`
- `0x4ecf0`
- `0x4ef20`
- `0x4fb70`
- `0x508c0`

## string_xrefs

- `0x4e1a0`: `rsConfigFilePath`
- `0x4e1eb`: `Error initializing configuration from the database: `
- `0x4e2f9`: `Either another process {0} instance is already running or another application with the RPC endpoint {1} is running.`

## pseudocode

```c

```

## disassembly

```asm
0x4e180  ldarg.0
0x4e181  call     instance string Microsoft.ReportingServices.Library.ServiceAppDomainController::get_EntryAssembly()
0x4e186  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0x4e18b  stsfld   string Microsoft.ReportingServices.Library.ServiceAppDomainController::m_serviceExeLocation
0x4e190  ldarg.0
0x4e191  call     instance string Microsoft.ReportingServices.Library.ServiceAppDomainController::get_EntryAssembly()
0x4e196  stsfld   string Microsoft.ReportingServices.Library.ServiceAppDomainController::m_fullServiceExePath
0x4e19b  ldsfld   class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig::Current
0x4e1a0  ldstr    aRsconfigfilepa// "rsConfigFilePath"
0x4e1a5  ldsfld   string [mscorlib]System.String::Empty
0x4e1aa  callvirt instance string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig::GetOrDefault(string, string)
0x4e1af  newobj   instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::.ctor(string)
0x4e1b4  stloc.0
0x4e1b5  ldloc.0
0x4e1b6  ldc.i4.0
0x4e1b7  call     void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::InitConfiguration(class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfigurationManager, valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication)
0x4e1bc  ldarg.0
0x4e1bd  call     instance void Microsoft.ReportingServices.Library.ServiceAppDomainController::ConfigureConcurrencyLimit()
0x4e1c2  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x4e1c7  callvirt instance bool [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_ConnectionStringSet()
0x4e1cc  brfalse.s loc_4E203
0x4e1ce  call     void Microsoft.ReportingServices.Library.ServiceController::EnsureConfigurationFromDB()
0x4e1d3  leave.s  loc_4E203
0x4e1d5  stloc.s  4
0x4e1d7  ldarg.0
0x4e1d8  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.ServiceAppDomainController::m_tracer
0x4e1dd  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x4e1e2  brfalse.s loc_4E201
0x4e1e4  ldarg.0
0x4e1e5  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.ServiceAppDomainController::m_tracer
0x4e1ea  ldc.i4.1
0x4e1eb  ldstr    aErrorInitializ// "Error initializing configuration from t"...
0x4e1f0  ldloc.s  4
0x4e1f2  callvirt instance string [mscorlib]System.Object::ToString()
0x4e1f7  call     string [mscorlib]System.String::Concat(string, string)
0x4e1fc  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x4e201  leave.s  loc_4E203
0x4e203  ldc.i4.1
0x4e204  call     void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::InitServer(bool)
0x4e209  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x4e20e  callvirt instance class [mscorlib]System.AppDomainManager [mscorlib]System.AppDomain::get_DomainManager()
0x4e213  isinst   [mscorlib]System.IServiceProvider
0x4e218  stloc.1
0x4e219  ldloc.1
0x4e21a  brfalse.s loc_4E262
0x4e21c  ldarg.0
0x4e21d  ldloc.1
0x4e21e  ldtoken  [System]System.ComponentModel.Design.IServiceContainer
0x4e223  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4e228  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x4e22d  castclass [System]System.ComponentModel.Design.IServiceContainer
0x4e232  stfld    class [System]System.ComponentModel.Design.IServiceContainer Microsoft.ReportingServices.Library.ServiceAppDomainController::m_serviceContainer
0x4e237  ldarg.0
0x4e238  ldfld    class [System]System.ComponentModel.Design.IServiceContainer Microsoft.ReportingServices.Library.ServiceAppDomainController::m_serviceContainer
0x4e23d  ldtoken  [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfigurationManager
0x4e242  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4e247  callvirt instance void [System]System.ComponentModel.Design.IServiceContainer::RemoveService(class [mscorlib]System.Type)
0x4e24c  ldarg.0
0x4e24d  ldfld    class [System]System.ComponentModel.Design.IServiceContainer Microsoft.ReportingServices.Library.ServiceAppDomainController::m_serviceContainer
0x4e252  ldtoken  [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfigurationManager
0x4e257  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4e25c  ldloc.0
0x4e25d  callvirt instance void [System]System.ComponentModel.Design.IServiceContainer::AddService(class [mscorlib]System.Type, object)
0x4e262  ldarg.0
0x4e263  ldc.i4.1
0x4e264  call     instance void Microsoft.ReportingServices.Library.ServiceAppDomainController::StartServiceInNewAppDomain(bool firstTime)
0x4e269  ldarg.0
0x4e26a  call     instance void Microsoft.ReportingServices.Library.ServiceAppDomainController::ApplyNativeConfiguration()
0x4e26f  ldarg.0
0x4e270  ldarg.0
0x4e271  ldftn    instance void Microsoft.ReportingServices.Library.ServiceAppDomainController::ServiceMaintenance()
0x4e277  newobj   instance void [mscorlib]System.Threading.ThreadStart::.ctor(object, native int)
0x4e27c  newobj   instance void [mscorlib]System.Threading.Thread::.ctor(class [mscorlib]System.Threading.ThreadStart)
0x4e281  stfld    class [mscorlib]System.Threading.Thread Microsoft.ReportingServices.Library.ServiceAppDomainController::m_maintenance
0x4e286  ldarg.0
0x4e287  ldfld    class [mscorlib]System.Threading.Thread Microsoft.ReportingServices.Library.ServiceAppDomainController::m_maintenance
0x4e28c  callvirt instance void [mscorlib]System.Threading.Thread::Start()
0x4e291  ldarg.0
0x4e292  call     instance void Microsoft.ReportingServices.Library.ServiceAppDomainController::StartProcessMonitoring()
0x4e297  ldc.i4   0x6CC
0x4e29c  stloc.2
0x4e29d  call     class [System]System.Diagnostics.Process [System]System.Diagnostics.Process::GetCurrentProcess()
0x4e2a2  callvirt instance valuetype [mscorlib]System.DateTime [System]System.Diagnostics.Process::get_StartTime()
0x4e2a7  stloc.s  5
0x4e2a9  ldloca.s 5
0x4e2ab  ldc.i4.0
0x4e2ac  ldc.i4.0
0x4e2ad  call     int32 Microsoft.ReportingServices.Library.ServiceAppDomainController::get_ServiceStartupTimeout()
0x4e2b2  ldc.i4.5
0x4e2b3  sub
0x4e2b4  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x4e2b9  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::Add(valuetype [mscorlib]System.TimeSpan)
0x4e2be  stloc.3
0x4e2bf  br.s     loc_4E31F
0x4e2c1  ldloc.2
0x4e2c2  ldarg.0
0x4e2c3  ldfld    int32 Microsoft.ReportingServices.Library.ServiceAppDomainController::m_startRPCServerResult
0x4e2c8  bne.un.s loc_4E315
0x4e2ca  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_AppDomainManagerTracer()
0x4e2cf  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x4e2d4  brfalse.s loc_4E315
0x4e2d6  call     class [System]System.Diagnostics.Process [System]System.Diagnostics.Process::GetCurrentProcess()
0x4e2db  callvirt instance string [System]System.Diagnostics.Process::get_ProcessName()
0x4e2e0  stloc.s  6
0x4e2e2  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x4e2e7  callvirt instance string [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_InstanceID()
0x4e2ec  call     string [ReportingServicesNativeClient]RSRemoteRpcClient.Utilities::RPCEndpointFromInstanceID(string)
0x4e2f1  stloc.s  7
0x4e2f3  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_AppDomainManagerTracer()
0x4e2f8  ldc.i4.1
0x4e2f9  ldstr    aEitherAnotherP// "Either another process {0} instance is "...
0x4e2fe  ldc.i4.2
0x4e2ff  newarr   [mscorlib]System.Object
0x4e304  dup
0x4e305  ldc.i4.0
0x4e306  ldloc.s  6
0x4e308  stelem.ref
0x4e309  dup
0x4e30a  ldc.i4.1
0x4e30b  ldloc.s  7
0x4e30d  stelem.ref
0x4e30e  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x4e313  br.s     loc_4E334
0x4e315  ldc.i4   0x3E8
0x4e31a  call     void [mscorlib]System.Threading.Thread::Sleep(int32)
0x4e31f  ldarg.0
0x4e320  ldfld    bool Microsoft.ReportingServices.Library.ServiceAppDomainController::m_isRPCServerStarted
0x4e325  brtrue.s loc_4E334
0x4e327  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x4e32c  ldloc.3
0x4e32d  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x4e332  brtrue.s loc_4E2C1
0x4e334  ldarg.0
0x4e335  ldfld    bool Microsoft.ReportingServices.Library.ServiceAppDomainController::m_isRPCServerStarted
0x4e33a  brtrue.s loc_4E34F
0x4e33c  ldarg.0
0x4e33d  ldfld    int32 Microsoft.ReportingServices.Library.ServiceAppDomainController::m_startRPCServerResult
0x4e342  brfalse.s loc_4E34F
0x4e344  ldstr    aRpcServerFaile// "RPC Server failed to start."
0x4e349  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0x4e34e  throw
0x4e34f  leave    loc_4E40F
0x4e354  stloc.s  8
0x4e356  ldarg.0
0x4e357  ldc.i4.0
0x4e358  stfld    bool Microsoft.ReportingServices.Library.ServiceAppDomainController::m_continue
0x4e35d  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::get_Current()
0x4e362  ldc.i4   0x8C
0x4e367  ldc.i4.2
0x4e368  newarr   [mscorlib]System.Object
0x4e36d  dup
0x4e36e  ldc.i4.0
0x4e36f  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x4e374  callvirt instance string [mscorlib]System.AppDomain::get_FriendlyName()
0x4e379  stelem.ref
0x4e37a  dup
0x4e37b  ldc.i4.1
0x4e37c  ldloc.s  8
0x4e37e  callvirt instance string [mscorlib]System.Exception::get_Message()
0x4e383  stelem.ref
0x4e384  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::WriteError(valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Event, object[])
0x4e389  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4e38e  ldstr    aAppdomain01Fai// "Appdomain:{0} {1} failed to initialize."...
0x4e393  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x4e398  callvirt instance int32 [mscorlib]System.AppDomain::get_Id()
0x4e39d  box      [mscorlib]System.Int32
0x4e3a2  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x4e3a7  callvirt instance string [mscorlib]System.AppDomain::get_FriendlyName()
0x4e3ac  ldloc.s  8
0x4e3ae  callvirt instance string [mscorlib]System.Object::ToString()
0x4e3b3  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object, object)
0x4e3b8  stloc.s  9
0x4e3ba  ldloc.s  9
0x4e3bc  call     void [mscorlib]System.Console::WriteLine(string)
0x4e3c1  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_AppDomainManagerTracer()
0x4e3c6  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x4e3cb  brfalse.s loc_4E3DA
0x4e3cd  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_AppDomainManagerTracer()
0x4e3d2  ldc.i4.1
0x4e3d3  ldloc.s  9
0x4e3d5  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x4e3da  ldarg.1
0x4e3db  isinst   [mscorlib]System.Threading.Thread
0x4e3e0  callvirt instance bool [mscorlib]System.Threading.Thread::get_IsAlive()
0x4e3e5  brtrue.s loc_4E40D
0x4e3e7  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_AppDomainManagerTracer()
0x4e3ec  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x4e3f1  brfalse.s loc_4E403
0x4e3f3  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_AppDomainManagerTracer()
0x4e3f8  ldc.i4.3
0x4e3f9  ldstr    aTerminatingThe// "Terminating the process because the def"...
0x4e3fe  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x4e403  call     class [System]System.Diagnostics.Process [System]System.Diagnostics.Process::GetCurrentProcess()
0x4e408  callvirt instance void [System]System.Diagnostics.Process::Kill()
0x4e40d  leave.s  loc_4E40F
0x4e40f  ret
```
