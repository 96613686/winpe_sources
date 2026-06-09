# Microsoft.BIServer.Configuration.UrlEndpoints::GetDefaultUrlApplications

- ea: `0x3aa0`
- end: `0x3ab1`
- name: `Microsoft.BIServer.Configuration.UrlEndpoints::GetDefaultUrlApplications`
- size: `17`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x39c0`

## callees

- `0x3930`
- `0x3960`

## pseudocode

```c

```

## disassembly

```asm
0x3aa0  ldarg.1
0x3aa1  call     valuetype Microsoft.BIServer.Configuration.UrlEndpointUsage Microsoft.BIServer.Configuration.UrlEndpoints::GetProductUsage(class Microsoft.BIServer.Configuration.InstanceId instanceId)
0x3aa6  ldc.i4.1
0x3aa7  or
0x3aa8  stloc.0
0x3aa9  ldarg.0
0x3aaa  ldloc.0
0x3aab  call     class Microsoft.BIServer.Configuration.UrlApplications Microsoft.BIServer.Configuration.UrlEndpoints::GetApplicationsForUsage(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.AccountCredentials accountCredentials, valuetype Microsoft.BIServer.Configuration.UrlEndpointUsage targetUsage)
0x3ab0  ret
```
