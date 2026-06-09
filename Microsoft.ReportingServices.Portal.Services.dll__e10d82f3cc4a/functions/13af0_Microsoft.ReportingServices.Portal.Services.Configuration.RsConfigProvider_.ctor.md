# Microsoft.ReportingServices.Portal.Services.Configuration.RsConfigProvider::.ctor

- ea: `0x13af0`
- end: `0x13b4a`
- name: `Microsoft.ReportingServices.Portal.Services.Configuration.RsConfigProvider::.ctor`
- size: `90`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x13af0`

## string_xrefs

- `0x13b18`: `ReportServerPath`
- `0x13b2d`: `rsreportserver.config`

## pseudocode

```c

```

## disassembly

```asm
0x13af0  ldarg.0
0x13af1  call     instance void [mscorlib]System.Object::.ctor()
0x13af6  ldarg.1
0x13af7  brtrue.s loc_13B04
0x13af9  ldstr    aLogger// "logger"
0x13afe  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x13b03  throw
0x13b04  ldarg.0
0x13b05  ldarg.1
0x13b06  stfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.Services.Configuration.RsConfigProvider::_logger
0x13b0b  ldc.i4.1
0x13b0c  stsfld   bool [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Sku::IgnoreExpirationCheck
0x13b11  ldc.i4.3
0x13b12  stloc.0
0x13b13  call     class [System]System.Collections.Specialized.NameValueCollection [System.Configuration]System.Configuration.ConfigurationManager::get_AppSettings()
0x13b18  ldstr    aReportserverpa// "ReportServerPath"
0x13b1d  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x13b22  dup
0x13b23  brtrue.s loc_13B2B
0x13b25  pop
0x13b26  ldstr    aReportserver// "..\\ReportServer\\"
0x13b2b  stloc.1
0x13b2c  ldarg.0
0x13b2d  ldstr    aRsreportserver// "rsreportserver.config"
0x13b32  ldloc.1
0x13b33  newobj   instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfigurationFileWatcherManager::.ctor(string, string)
0x13b38  stfld    class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager Microsoft.ReportingServices.Portal.Services.Configuration.RsConfigProvider::_configFileManager
0x13b3d  ldarg.0
0x13b3e  ldfld    class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager Microsoft.ReportingServices.Portal.Services.Configuration.RsConfigProvider::_configFileManager
0x13b43  ldloc.0
0x13b44  call     void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::InitConfiguration(class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfigurationManager, valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication)
0x13b49  ret
```
