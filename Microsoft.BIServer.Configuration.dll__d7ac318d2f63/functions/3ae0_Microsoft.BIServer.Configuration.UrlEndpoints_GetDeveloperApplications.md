# Microsoft.BIServer.Configuration.UrlEndpoints::GetDeveloperApplications

- ea: `0x3ae0`
- end: `0x3af1`
- name: `Microsoft.BIServer.Configuration.UrlEndpoints::GetDeveloperApplications`
- size: `17`
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
0x3ae0  ldc.i4.2
0x3ae1  ldarg.1
0x3ae2  call     valuetype Microsoft.BIServer.Configuration.UrlEndpointUsage Microsoft.BIServer.Configuration.UrlEndpoints::GetProductUsage(class Microsoft.BIServer.Configuration.InstanceId instanceId)
0x3ae7  or
0x3ae8  stloc.0
0x3ae9  ldarg.0
0x3aea  ldloc.0
0x3aeb  call     class Microsoft.BIServer.Configuration.UrlApplications Microsoft.BIServer.Configuration.UrlEndpoints::GetApplicationsForUsage(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.AccountCredentials accountCredentials, valuetype Microsoft.BIServer.Configuration.UrlEndpointUsage targetUsage)
0x3af0  ret
```
