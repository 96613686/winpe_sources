# Microsoft.ReportingServices.Portal.Services.SoapProxy.SoapRS2010Proxy::CreateRsConnection

- ea: `0xb1d0`
- end: `0xb1fc`
- name: `Microsoft.ReportingServices.Portal.Services.SoapProxy.SoapRS2010Proxy::CreateRsConnection`
- size: `44`
- prototype: ``
- caller_count: `36`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xb200`
- `0xb260`
- `0xb2a0`
- `0xb2e0`
- `0xb3a0`
- `0xb3e0`
- `0xb430`
- `0xb470`
- `0xb4d0`
- `0xb510`
- `0xb570`
- `0xb5b0`
- `0xb620`
- `0xb690`
- `0xb6d0`
- `0xb710`
- `0xb770`
- `0xb7d0`
- `0xb810`
- `0xb850`
- `0xb8a0`
- `0xb8e0`
- `0xb920`
- `0xb960`
- `0xb9a0`
- `0xb9e0`
- `0xba30`
- `0xba80`
- `0xbac0`
- `0xbb10`
- `0xbb60`
- `0xbba0`
- `0xbbe0`
- `0xbc30`
- `0xbc80`
- `0xbce0`

## callees

- `0xbde0`

## pseudocode

```c

```

## disassembly

```asm
0xb1d0  ldarg.0
0xb1d1  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager Microsoft.ReportingServices.Portal.Services.SoapProxy.SoapRS2010Proxy::portalConfigurationManager
0xb1d6  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfiguration [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager::get_Current()
0xb1db  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfiguration::get_ReportServerUrl()
0xb1e0  ldarg.0
0xb1e1  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager Microsoft.ReportingServices.Portal.Services.SoapProxy.SoapRS2010Proxy::portalConfigurationManager
0xb1e6  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfiguration [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager::get_Current()
0xb1eb  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfiguration::get_ReportServerHostName()
0xb1f0  ldarg.1
0xb1f1  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Principal.IPrincipal::get_Identity()
0xb1f6  newobj   instance void Microsoft.ReportingServices.Portal.Services.SoapProxy.SoapRsManagementConnection::.ctor(string reportServerUrl, string reportServerHostName, class [mscorlib]System.Security.Principal.IIdentity userContext)
0xb1fb  ret
```
