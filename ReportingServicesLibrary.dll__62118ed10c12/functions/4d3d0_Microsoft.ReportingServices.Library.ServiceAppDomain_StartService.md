# Microsoft.ReportingServices.Library.ServiceAppDomain::StartService

- ea: `0x4d3d0`
- end: `0x4d457`
- name: `Microsoft.ReportingServices.Library.ServiceAppDomain::StartService`
- size: `135`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xbc20`
- `0x4d3d0`
- `0x4fc30`
- `0x4fc80`
- `0x4fc90`
- `0x4fcb0`
- `0x508c0`

## string_xrefs

- `0x4d3d5`: `rsConfigFilePath`
- `0x4d417`: `Error initializing configuration from the database: `

## pseudocode

```c

```

## disassembly

```asm
0x4d3d0  ldsfld   class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig::Current
0x4d3d5  ldstr    aRsconfigfilepa// "rsConfigFilePath"
0x4d3da  ldsfld   string [mscorlib]System.String::Empty
0x4d3df  callvirt instance string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig::GetOrDefault(string, string)
0x4d3e4  newobj   instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::.ctor(string)
0x4d3e9  ldc.i4.0
0x4d3ea  call     void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::InitConfiguration(class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfigurationManager, valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication)
0x4d3ef  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x4d3f4  callvirt instance bool [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_ConnectionStringSet()
0x4d3f9  brfalse.s loc_4D42E
0x4d3fb  call     void Microsoft.ReportingServices.Library.ServiceController::EnsureConfigurationFromDB()
0x4d400  leave.s  loc_4D42E
0x4d402  stloc.0
0x4d403  ldarg.0
0x4d404  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.ServiceAppDomain::m_tracer
0x4d409  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x4d40e  brfalse.s loc_4D42C
0x4d410  ldarg.0
0x4d411  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.ServiceAppDomain::m_tracer
0x4d416  ldc.i4.1
0x4d417  ldstr    aErrorInitializ// "Error initializing configuration from t"...
0x4d41c  ldloc.0
0x4d41d  callvirt instance string [mscorlib]System.Object::ToString()
0x4d422  call     string [mscorlib]System.String::Concat(string, string)
0x4d427  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x4d42c  leave.s  loc_4D42E
0x4d42e  ldarg.2
0x4d42f  call     void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::InitServer(bool)
0x4d434  call     class Microsoft.ReportingServices.Library.ServiceController Microsoft.ReportingServices.Library.ServiceController::get_Current()
0x4d439  brtrue.s loc_4D446
0x4d43b  ldarg.1
0x4d43c  newobj   instance void Microsoft.ReportingServices.Library.ServiceController::.ctor(class Microsoft.ReportingServices.Library.IServiceAppDomainController appDomainController)
0x4d441  call     void Microsoft.ReportingServices.Library.ServiceController::set_Current(class Microsoft.ReportingServices.Library.ServiceController value)
0x4d446  call     void Microsoft.ReportingServices.Library.ExecutionLog::Init()
0x4d44b  call     class Microsoft.ReportingServices.Library.ServiceController Microsoft.ReportingServices.Library.ServiceController::get_Current()
0x4d450  ldarg.2
0x4d451  callvirt instance void Microsoft.ReportingServices.Library.ServiceController::StartService(bool firstStart)
0x4d456  ret
```
