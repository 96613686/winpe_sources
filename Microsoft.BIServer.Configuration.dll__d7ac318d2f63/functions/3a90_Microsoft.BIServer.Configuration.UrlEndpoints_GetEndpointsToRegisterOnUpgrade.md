# Microsoft.BIServer.Configuration.UrlEndpoints::GetEndpointsToRegisterOnUpgrade

- ea: `0x3a90`
- end: `0x3a9e`
- name: `Microsoft.BIServer.Configuration.UrlEndpoints::GetEndpointsToRegisterOnUpgrade`
- size: `14`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x3990`

## callees

- `0x39e0`

## pseudocode

```c

```

## disassembly

```asm
0x3a90  ldarg.0
0x3a91  ldarg.1
0x3a92  ldarg.2
0x3a93  ldc.i4   0x80
0x3a98  call     class [mscorlib]System.Collections.Generic.List`1<class Microsoft.BIServer.Configuration.Application> Microsoft.BIServer.Configuration.UrlEndpoints::GetEndpointsBasedOnPortalEndpoint(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.AccountCredentials accountCredentials, class Microsoft.BIServer.Configuration.InstanceId instanceId, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.BIServer.Configuration.Application> appsFromConfig, valuetype Microsoft.BIServer.Configuration.UrlEndpointUsage usageFilter)
0x3a9d  ret
```
