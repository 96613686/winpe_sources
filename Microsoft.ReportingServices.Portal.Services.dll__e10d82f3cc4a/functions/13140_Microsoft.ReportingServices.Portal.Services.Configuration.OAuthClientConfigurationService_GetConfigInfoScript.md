# Microsoft.ReportingServices.Portal.Services.Configuration.OAuthClientConfigurationService::GetConfigInfoScript

- ea: `0x13140`
- end: `0x131ac`
- name: `Microsoft.ReportingServices.Portal.Services.Configuration.OAuthClientConfigurationService::GetConfigInfoScript`
- size: `108`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x13140`
- `0x131d0`

## string_xrefs

- `0x1316c`: `var __oAuthConfigData__ = `

## pseudocode

```c

```

## disassembly

```asm
0x13140  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x13145  stloc.0
0x13146  ldarg.0
0x13147  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager Microsoft.ReportingServices.Portal.Services.Configuration.OAuthClientConfigurationService::_portalConfigurationManager
0x1314c  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfiguration [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager::get_Current()
0x13151  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IOAuthConfiguration [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfiguration::get_OAuthConfiguration()
0x13156  stloc.1
0x13157  ldloc.0
0x13158  ldstr    aUseStrict// "'use strict';"
0x1315d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x13162  pop
0x13163  ldarg.0
0x13164  call     instance bool Microsoft.ReportingServices.Portal.Services.Configuration.OAuthClientConfigurationService::IsOAuthRequired()
0x13169  brfalse.s loc_131A5
0x1316b  ldloc.0
0x1316c  ldstr    aVarOauthconfig// "var __oAuthConfigData__ = "
0x13171  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x13176  pop
0x13177  ldloc.0
0x13178  ldloc.1
0x13179  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IOAuthConfiguration::get_TokenUrl()
0x1317e  ldloc.1
0x1317f  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IOAuthConfiguration::get_ClientId()
0x13184  ldloc.1
0x13185  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IOAuthConfiguration::get_TenantId()
0x1318a  newobj   instance void class <>f__AnonymousType0`3<string, string, string>::.ctor(var<u1>, !!T0, var<u1>)
0x1318f  ldc.i4.1
0x13190  call     string [Newtonsoft.Json]Newtonsoft.Json.JsonConvert::SerializeObject(object, valuetype [Newtonsoft.Json]Newtonsoft.Json.Formatting)
0x13195  ldstr    asc_28720// ";"
0x1319a  call     string [mscorlib]System.String::Concat(string, string)
0x1319f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x131a4  pop
0x131a5  ldloc.0
0x131a6  callvirt instance string [mscorlib]System.Object::ToString()
0x131ab  ret
```
