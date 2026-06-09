# Microsoft.ReportingServices.Portal.WebHost.Services.Impl.WebAppServiceController::LogConfigurationSettings

- ea: `0x1380`
- end: `0x1425`
- name: `Microsoft.ReportingServices.Portal.WebHost.Services.Impl.WebAppServiceController::LogConfigurationSettings`
- size: `165`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x12d0`

## callees

- `0x1380`

## string_xrefs

- `0x1387`: `Working directory : {0}`

## pseudocode

```c

```

## disassembly

```asm
0x1380  ldarg.0
0x1381  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.WebHost.Services.Impl.WebAppServiceController::_logger
0x1386  ldc.i4.3
0x1387  ldstr    aWorkingDirecto// "Working directory : {0}"
0x138c  call     string [mscorlib]System.Environment::get_CurrentDirectory()
0x1391  call     string [mscorlib]System.String::Format(string, object)
0x1396  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x139b  ldarg.0
0x139c  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.WebHost.Services.Impl.WebAppServiceController::_logger
0x13a1  ldc.i4.3
0x13a2  ldstr    aReportServerUr// "Report Server url: {0}"
0x13a7  ldarg.1
0x13a8  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfiguration::get_ReportServerUrl()
0x13ad  call     string [mscorlib]System.String::Format(string, object)
0x13b2  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x13b7  ldarg.0
0x13b8  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.WebHost.Services.Impl.WebAppServiceController::_logger
0x13bd  ldc.i4.3
0x13be  ldstr    aReportServerWe// "Report Server Web App virtual root: {0}"
0x13c3  ldarg.1
0x13c4  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfiguration::get_ReportServerWebAppVirtualDirectory()
0x13c9  call     string [mscorlib]System.String::Format(string, object)
0x13ce  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x13d3  ldarg.1
0x13d4  callvirt instance string[] [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfiguration::get_RegisteredWebAppUrls()
0x13d9  stloc.0
0x13da  ldc.i4.0
0x13db  stloc.1
0x13dc  br.s     loc_13FD
0x13de  ldloc.0
0x13df  ldloc.1
0x13e0  ldelem.ref
0x13e1  stloc.2
0x13e2  ldarg.0
0x13e3  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.WebHost.Services.Impl.WebAppServiceController::_logger
0x13e8  ldc.i4.3
0x13e9  ldstr    aWebAppUrl0// "Web app url: {0}"
0x13ee  ldloc.2
0x13ef  call     string [mscorlib]System.String::Format(string, object)
0x13f4  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x13f9  ldloc.1
0x13fa  ldc.i4.1
0x13fb  add
0x13fc  stloc.1
0x13fd  ldloc.1
0x13fe  ldloc.0
0x13ff  ldlen
0x1400  conv.i4
0x1401  blt.s    loc_13DE
0x1403  ldarg.0
0x1404  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.WebHost.Services.Impl.WebAppServiceController::_logger
0x1409  ldc.i4.3
0x140a  ldstr    aAuthentication// "Authentication scheme(s): {0:F}"
0x140f  ldarg.1
0x1410  callvirt instance valuetype [System]System.Net.AuthenticationSchemes [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfiguration::get_AuthenticationSchemes()
0x1415  box      [System]System.Net.AuthenticationSchemes
0x141a  call     string [mscorlib]System.String::Format(string, object)
0x141f  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x1424  ret
```
