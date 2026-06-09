# Microsoft.BIServer.Configuration.UrlEndpoints::GetEndpointsToRegister

- ea: `0x3990`
- end: `0x39b4`
- name: `Microsoft.BIServer.Configuration.UrlEndpoints::GetEndpointsToRegister`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x3750`
- `0x3930`
- `0x3960`
- `0x3980`
- `0x3a90`

## pseudocode

```c

```

## disassembly

```asm
0x3990  ldarg.2
0x3991  call     valuetype Microsoft.BIServer.Configuration.UrlEndpointUsage Microsoft.BIServer.Configuration.UrlEndpoints::GetProductUsage(class Microsoft.BIServer.Configuration.InstanceId instanceId)
0x3996  ldarg.0
0x3997  call     valuetype Microsoft.BIServer.Configuration.UrlEndpointUsage Microsoft.BIServer.Configuration.UrlEndpoints::GetProductModeUsage(bool isDeveloperMode)
0x399c  or
0x399d  stloc.0
0x399e  ldarg.1
0x399f  ldloc.0
0x39a0  call     class Microsoft.BIServer.Configuration.UrlApplications Microsoft.BIServer.Configuration.UrlEndpoints::GetApplicationsForUsage(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.AccountCredentials accountCredentials, valuetype Microsoft.BIServer.Configuration.UrlEndpointUsage targetUsage)
0x39a5  dup
0x39a6  ldarg.1
0x39a7  ldarg.2
0x39a8  ldarg.3
0x39a9  call     class [mscorlib]System.Collections.Generic.List`1<class Microsoft.BIServer.Configuration.Application> Microsoft.BIServer.Configuration.UrlEndpoints::GetEndpointsToRegisterOnUpgrade(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.AccountCredentials accountCredentials, class Microsoft.BIServer.Configuration.InstanceId instanceId, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.BIServer.Configuration.Application> appsFromConfig)
0x39ae  callvirt instance void Microsoft.BIServer.Configuration.UrlApplications::Add(class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.BIServer.Configuration.Application> apps)
0x39b3  ret
```
