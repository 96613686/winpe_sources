# Microsoft.ReportingServices.Portal.WebHost.Program::Main

- ea: `0x4d0`
- end: `0x566`
- name: `Microsoft.ReportingServices.Portal.WebHost.Program::Main`
- size: `150`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x4d0`
- `0x670`
- `0x1230`
- `0x12d0`
- `0x1430`
- `0x1580`

## pseudocode

```c

```

## disassembly

```asm
0x4d0  .entrypoint
0x4d5  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Args::PauseIfDebugSwitch()
0x4da  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x4df  callvirt instance string [mscorlib]System.AppDomain::get_BaseDirectory()
0x4e4  call     void [mscorlib]System.Environment::set_CurrentDirectory(string)
0x4e9  ldstr    aRsportal// "RSPortal"
0x4ee  ldc.i4.4
0x4ef  call     class [mscorlib]System.IDisposable [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Create(string, valuetype [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger/Level)
0x4f4  stloc.0
0x4f5  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::InitializeInHostedProcess()
0x4fa  newobj   instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.DefaultTraceLogger::.ctor()
0x4ff  stloc.1
0x500  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x505  ldnull
0x506  ldftn    void Microsoft.ReportingServices.Portal.WebHost.Program::UnhandledExceptionEventHandler(object sender, class [mscorlib]System.UnhandledExceptionEventArgs args)
0x50c  newobj   instance void [mscorlib]System.UnhandledExceptionEventHandler::.ctor(object, native int)
0x511  callvirt instance void [mscorlib]System.AppDomain::add_UnhandledException(class [mscorlib]System.UnhandledExceptionEventHandler)
0x516  ldloc.1
0x517  newobj   instance void [Microsoft.ReportingServices.Portal.Services]Microsoft.ReportingServices.Portal.Services.Configuration.RsConfigProvider::.ctor(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger)
0x51c  ldloc.1
0x51d  newobj   instance void [Microsoft.ReportingServices.Portal.Services]Microsoft.ReportingServices.Portal.Services.Configuration.PortalConfigurationManager::.ctor(class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IRsConfigProvider, class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger)
0x522  stloc.2
0x523  newobj   instance void Microsoft.ReportingServices.Portal.WebHost.Services.Impl.WebAppWrapper::.ctor()
0x528  ldloc.2
0x529  ldloc.1
0x52a  newobj   instance void Microsoft.ReportingServices.Portal.WebHost.Services.Impl.WebAppServiceController::.ctor(class Microsoft.ReportingServices.Portal.WebHost.Services.IWebAppWrapper webApp, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager portalConfigurationManager, class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger logger)
0x52f  ldc.i4.0
0x530  newobj   instance void [mscorlib]System.Threading.ManualResetEvent::.ctor(bool)
0x535  stloc.3
0x536  ldloc.1
0x537  newobj   instance void Microsoft.ReportingServices.Portal.WebHost.AlternateLoggerTracer::.ctor(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger logWrapper)
0x53c  call     void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::SetTrace(class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.IRSTraceInternal)
0x541  ldc.i4.1
0x542  call     void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::InitServer(bool)
0x547  dup
0x548  callvirt instance void Microsoft.ReportingServices.Portal.WebHost.Services.Impl.WebAppServiceController::Start()
0x54d  ldloc.3
0x54e  callvirt instance bool [mscorlib]System.Threading.WaitHandle::WaitOne()
0x553  pop
0x554  callvirt instance void Microsoft.ReportingServices.Portal.WebHost.Services.Impl.WebAppServiceController::Stop()
0x559  leave.s  loc_565
0x55b  ldloc.0
0x55c  brfalse.s loc_564
0x55e  ldloc.0
0x55f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x564  endfinally
0x565  ret
```
