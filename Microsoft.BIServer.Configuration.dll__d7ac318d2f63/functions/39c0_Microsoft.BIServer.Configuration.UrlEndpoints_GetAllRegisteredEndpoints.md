# Microsoft.BIServer.Configuration.UrlEndpoints::GetAllRegisteredEndpoints

- ea: `0x39c0`
- end: `0x39de`
- name: `Microsoft.BIServer.Configuration.UrlEndpoints::GetAllRegisteredEndpoints`
- size: `30`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x3750`
- `0x39e0`
- `0x3aa0`

## pseudocode

```c

```

## disassembly

```asm
0x39c0  ldarg.0
0x39c1  ldarg.1
0x39c2  call     class Microsoft.BIServer.Configuration.UrlApplications Microsoft.BIServer.Configuration.UrlEndpoints::GetDefaultUrlApplications(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.AccountCredentials accountCredentials, class Microsoft.BIServer.Configuration.InstanceId instanceId)
0x39c7  dup
0x39c8  ldarg.2
0x39c9  callvirt instance void Microsoft.BIServer.Configuration.UrlApplications::Add(class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.BIServer.Configuration.Application> apps)
0x39ce  dup
0x39cf  ldarg.0
0x39d0  ldarg.1
0x39d1  ldarg.2
0x39d2  ldc.i4.0
0x39d3  call     class [mscorlib]System.Collections.Generic.List`1<class Microsoft.BIServer.Configuration.Application> Microsoft.BIServer.Configuration.UrlEndpoints::GetEndpointsBasedOnPortalEndpoint(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.AccountCredentials accountCredentials, class Microsoft.BIServer.Configuration.InstanceId instanceId, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.BIServer.Configuration.Application> appsFromConfig, valuetype Microsoft.BIServer.Configuration.UrlEndpointUsage usageFilter)
0x39d8  callvirt instance void Microsoft.BIServer.Configuration.UrlApplications::Add(class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.BIServer.Configuration.Application> apps)
0x39dd  ret
```
