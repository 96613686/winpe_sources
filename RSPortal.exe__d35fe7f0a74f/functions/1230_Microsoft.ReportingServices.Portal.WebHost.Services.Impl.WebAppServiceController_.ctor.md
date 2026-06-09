# Microsoft.ReportingServices.Portal.WebHost.Services.Impl.WebAppServiceController::.ctor

- ea: `0x1230`
- end: `0x128d`
- name: `Microsoft.ReportingServices.Portal.WebHost.Services.Impl.WebAppServiceController::.ctor`
- size: `93`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x4d0`

## callees

- `0x1230`

## string_xrefs

- `0x1247`: `portalConfigurationManager`

## pseudocode

```c

```

## disassembly

```asm
0x1230  ldarg.0
0x1231  call     instance void [mscorlib]System.Object::.ctor()
0x1236  ldarg.1
0x1237  brtrue.s loc_1244
0x1239  ldstr    aWebapp// "webApp"
0x123e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1243  throw
0x1244  ldarg.2
0x1245  brtrue.s loc_1252
0x1247  ldstr    aPortalconfigur// "portalConfigurationManager"
0x124c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1251  throw
0x1252  ldarg.3
0x1253  brtrue.s loc_1260
0x1255  ldstr    aLogger// "logger"
0x125a  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x125f  throw
0x1260  ldarg.0
0x1261  ldarg.1
0x1262  stfld    class Microsoft.ReportingServices.Portal.WebHost.Services.IWebAppWrapper Microsoft.ReportingServices.Portal.WebHost.Services.Impl.WebAppServiceController::_webApp
0x1267  ldarg.0
0x1268  ldarg.2
0x1269  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager Microsoft.ReportingServices.Portal.WebHost.Services.Impl.WebAppServiceController::_portalConfigurationManager
0x126e  ldarg.0
0x126f  ldarg.3
0x1270  stfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.WebHost.Services.Impl.WebAppServiceController::_logger
0x1275  ldarg.0
0x1276  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager Microsoft.ReportingServices.Portal.WebHost.Services.Impl.WebAppServiceController::_portalConfigurationManager
0x127b  ldarg.0
0x127c  ldftn    instance void Microsoft.ReportingServices.Portal.WebHost.Services.Impl.WebAppServiceController::OnCurrentPortalConfigurationChanged(object sender, class [mscorlib]System.EventArgs eventArgs)
0x1282  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x1287  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager::add_CurrentConfigurationChanged(class [mscorlib]System.EventHandler)
0x128c  ret
```
