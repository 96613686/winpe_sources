# Microsoft.ReportingServices.Portal.WebHost.Services.Impl.WebAppServiceController::System.IDisposable.Dispose

- ea: `0x1450`
- end: `0x1468`
- name: `Microsoft.ReportingServices.Portal.WebHost.Services.Impl.WebAppServiceController::System.IDisposable.Dispose`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x1450  ldarg.0
0x1451  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager Microsoft.ReportingServices.Portal.WebHost.Services.Impl.WebAppServiceController::_portalConfigurationManager
0x1456  ldarg.0
0x1457  ldftn    instance void Microsoft.ReportingServices.Portal.WebHost.Services.Impl.WebAppServiceController::OnCurrentPortalConfigurationChanged(object sender, class [mscorlib]System.EventArgs eventArgs)
0x145d  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x1462  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager::remove_CurrentConfigurationChanged(class [mscorlib]System.EventHandler)
0x1467  ret
```
