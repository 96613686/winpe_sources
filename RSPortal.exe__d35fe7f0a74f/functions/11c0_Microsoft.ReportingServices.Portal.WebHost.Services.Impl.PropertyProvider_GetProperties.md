# Microsoft.ReportingServices.Portal.WebHost.Services.Impl.PropertyProvider::GetProperties

- ea: `0x11c0`
- end: `0x11ef`
- name: `Microsoft.ReportingServices.Portal.WebHost.Services.Impl.PropertyProvider::GetProperties`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x11c0`

## pseudocode

```c

```

## disassembly

```asm
0x11c0  ldarg.0
0x11c1  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager Microsoft.ReportingServices.Portal.WebHost.Services.Impl.PropertyProvider::_portalConfigManager
0x11c6  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfiguration [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager::get_Current()
0x11cb  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IOAuthConfiguration [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfiguration::get_OAuthConfiguration()
0x11d0  brfalse.s loc_11E9
0x11d2  ldarg.0
0x11d3  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager Microsoft.ReportingServices.Portal.WebHost.Services.Impl.PropertyProvider::_portalConfigManager
0x11d8  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfiguration [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager::get_Current()
0x11dd  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IOAuthConfiguration [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfiguration::get_OAuthConfiguration()
0x11e2  ldarg.1
0x11e3  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IOAuthConfiguration::GetProperties(class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x11e8  ret
0x11e9  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x11ee  ret
```
