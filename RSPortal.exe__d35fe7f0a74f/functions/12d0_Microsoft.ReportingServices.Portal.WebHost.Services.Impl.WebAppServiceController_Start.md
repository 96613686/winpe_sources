# Microsoft.ReportingServices.Portal.WebHost.Services.Impl.WebAppServiceController::Start

- ea: `0x12d0`
- end: `0x137e`
- name: `Microsoft.ReportingServices.Portal.WebHost.Services.Impl.WebAppServiceController::Start`
- size: `174`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x4d0`
- `0x1290`

## callees

- `0x9b0`
- `0x12c0`
- `0x12d0`
- `0x1380`

## string_xrefs

- `0x12e9`: `Web Application already started`
- `0x1362`: `ReportingServiesWebApp is not configured - not listening on any URLs`
- `0x1373`: `Ensure the database instance hosting the catalog is running, and URLs are configured via RSConfig tool.`

## pseudocode

```c

```

## disassembly

```asm
0x12d0  ldarg.0
0x12d1  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.WebHost.Services.Impl.WebAppServiceController::_logger
0x12d6  ldc.i4.3
0x12d7  ldstr    aStartingReport// "Starting ReportServerWebApp"
0x12dc  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x12e1  ldarg.0
0x12e2  call     instance bool Microsoft.ReportingServices.Portal.WebHost.Services.Impl.WebAppServiceController::get_IsRunning()
0x12e7  brfalse.s loc_12F4
0x12e9  ldstr    aWebApplication// "Web Application already started"
0x12ee  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x12f3  throw
0x12f4  ldarg.0
0x12f5  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager Microsoft.ReportingServices.Portal.WebHost.Services.Impl.WebAppServiceController::_portalConfigurationManager
0x12fa  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfiguration [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager::get_Current()
0x12ff  stloc.0
0x1300  ldloc.0
0x1301  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfiguration::get_AppConfigured()
0x1306  brfalse.s loc_135B
0x1308  ldarg.0
0x1309  ldloc.0
0x130a  call     instance void Microsoft.ReportingServices.Portal.WebHost.Services.Impl.WebAppServiceController::LogConfigurationSettings(class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfiguration portalConfiguration)
0x130f  newobj   instance void [Microsoft.Owin.Hosting]Microsoft.Owin.Hosting.StartOptions::.ctor()
0x1314  stloc.1
0x1315  ldloc.0
0x1316  callvirt instance string[] [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfiguration::get_RegisteredWebAppUrls()
0x131b  stloc.2
0x131c  ldc.i4.0
0x131d  stloc.3
0x131e  br.s     loc_1336
0x1320  ldloc.2
0x1321  ldloc.3
0x1322  ldelem.ref
0x1323  stloc.s  4
0x1325  ldloc.1
0x1326  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<string> [Microsoft.Owin.Hosting]Microsoft.Owin.Hosting.StartOptions::get_Urls()
0x132b  ldloc.s  4
0x132d  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x1332  ldloc.3
0x1333  ldc.i4.1
0x1334  add
0x1335  stloc.3
0x1336  ldloc.3
0x1337  ldloc.2
0x1338  ldlen
0x1339  conv.i4
0x133a  blt.s    loc_1320
0x133c  ldarg.0
0x133d  ldarg.0
0x133e  ldfld    class Microsoft.ReportingServices.Portal.WebHost.Services.IWebAppWrapper Microsoft.ReportingServices.Portal.WebHost.Services.Impl.WebAppServiceController::_webApp
0x1343  ldloc.1
0x1344  ldarg.0
0x1345  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager Microsoft.ReportingServices.Portal.WebHost.Services.Impl.WebAppServiceController::_portalConfigurationManager
0x134a  ldarg.0
0x134b  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.WebHost.Services.Impl.WebAppServiceController::_logger
0x1350  callvirt instance class [mscorlib]System.IDisposable Microsoft.ReportingServices.Portal.WebHost.Services.IWebAppWrapper::Start(class [Microsoft.Owin.Hosting]Microsoft.Owin.Hosting.StartOptions options, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager rsConfigManager, class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger logger)
0x1355  stfld    class [mscorlib]System.IDisposable Microsoft.ReportingServices.Portal.WebHost.Services.Impl.WebAppServiceController::_webAppDisposable
0x135a  ret
0x135b  ldarg.0
0x135c  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.WebHost.Services.Impl.WebAppServiceController::_logger
0x1361  ldc.i4.3
0x1362  ldstr    aReportingservi// "ReportingServiesWebApp is not configure"...
0x1367  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x136c  ldarg.0
0x136d  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.WebHost.Services.Impl.WebAppServiceController::_logger
0x1372  ldc.i4.3
0x1373  ldstr    aEnsureTheDatab// "Ensure the database instance hosting th"...
0x1378  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x137d  ret
```
