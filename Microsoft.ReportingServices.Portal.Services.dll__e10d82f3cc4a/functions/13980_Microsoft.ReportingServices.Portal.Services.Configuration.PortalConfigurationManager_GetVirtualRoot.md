# Microsoft.ReportingServices.Portal.Services.Configuration.PortalConfigurationManager::GetVirtualRoot

- ea: `0x13980`
- end: `0x139ae`
- name: `Microsoft.ReportingServices.Portal.Services.Configuration.PortalConfigurationManager::GetVirtualRoot`
- size: `46`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x13640`

## callees

- `0x13900`
- `0x13980`

## string_xrefs

- `0x13983`: `urlConfig`
- `0x13988`: `Did you forget to set your 'ReportServerPath' in the app.config?`

## pseudocode

```c

```

## disassembly

```asm
0x13980  ldarg.1
0x13981  brtrue.s loc_13993
0x13983  ldstr    aUrlconfig// "urlConfig"
0x13988  ldstr    aDidYouForgetTo// "Did you forget to set your 'ReportServe"...
0x1398d  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string, string)
0x13992  throw
0x13993  ldarg.1
0x13994  call     bool Microsoft.ReportingServices.Portal.Services.Configuration.PortalConfigurationManager::IsRSWebAppConfigured(class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication, valuetype [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.UrlConfiguration> urlConfig)
0x13999  brfalse.s loc_139A8
0x1399b  ldarg.1
0x1399c  ldarg.0
0x1399d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication, valuetype [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.UrlConfiguration>::get_Item(void)
0x139a2  ldfld    string [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.UrlConfiguration::VirtualRoot
0x139a7  ret
0x139a8  ldsfld   string [mscorlib]System.String::Empty
0x139ad  ret
```
