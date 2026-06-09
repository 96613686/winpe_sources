# Microsoft.BIServer.Configuration.UrlEndpoints::GetDeveloperApplicationsForConfig

- ea: `0x3ac0`
- end: `0x3ad2`
- name: `Microsoft.BIServer.Configuration.UrlEndpoints::GetDeveloperApplicationsForConfig`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x3930`
- `0x3960`

## pseudocode

```c

```

## disassembly

```asm
0x3ac0  ldc.i4.s 0x42
0x3ac2  ldarg.1
0x3ac3  call     valuetype Microsoft.BIServer.Configuration.UrlEndpointUsage Microsoft.BIServer.Configuration.UrlEndpoints::GetProductUsage(class Microsoft.BIServer.Configuration.InstanceId instanceId)
0x3ac8  or
0x3ac9  stloc.0
0x3aca  ldarg.0
0x3acb  ldloc.0
0x3acc  call     class Microsoft.BIServer.Configuration.UrlApplications Microsoft.BIServer.Configuration.UrlEndpoints::GetApplicationsForUsage(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.AccountCredentials accountCredentials, valuetype Microsoft.BIServer.Configuration.UrlEndpointUsage targetUsage)
0x3ad1  ret
```
