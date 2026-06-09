# Microsoft.ReportingServices.Portal.Services.Configuration.PortalConfigurationManager::.ctor

- ea: `0x13590`
- end: `0x135d8`
- name: `Microsoft.ReportingServices.Portal.Services.Configuration.PortalConfigurationManager::.ctor`
- size: `72`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x13590`

## string_xrefs

- `0x13599`: `configProvider`

## pseudocode

```c

```

## disassembly

```asm
0x13590  ldarg.0
0x13591  call     instance void [mscorlib]System.Object::.ctor()
0x13596  ldarg.1
0x13597  brtrue.s loc_135A4
0x13599  ldstr    aConfigprovider// "configProvider"
0x1359e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x135a3  throw
0x135a4  ldarg.2
0x135a5  brtrue.s loc_135B2
0x135a7  ldstr    aLogger// "logger"
0x135ac  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x135b1  throw
0x135b2  ldarg.0
0x135b3  ldarg.1
0x135b4  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IRsConfigProvider Microsoft.ReportingServices.Portal.Services.Configuration.PortalConfigurationManager::_configProvider
0x135b9  ldarg.0
0x135ba  ldarg.2
0x135bb  stfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.Services.Configuration.PortalConfigurationManager::_logger
0x135c0  ldarg.0
0x135c1  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IRsConfigProvider Microsoft.ReportingServices.Portal.Services.Configuration.PortalConfigurationManager::_configProvider
0x135c6  ldarg.0
0x135c7  ldftn    instance void Microsoft.ReportingServices.Portal.Services.Configuration.PortalConfigurationManager::OnConfigurationChanged(object sender, class [mscorlib]System.EventArgs e)
0x135cd  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x135d2  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IRsConfigProvider::add_ConfigurationChanged(class [mscorlib]System.EventHandler)
0x135d7  ret
```
