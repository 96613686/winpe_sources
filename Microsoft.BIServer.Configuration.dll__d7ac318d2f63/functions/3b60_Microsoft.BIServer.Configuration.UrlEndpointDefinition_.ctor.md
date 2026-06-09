# Microsoft.BIServer.Configuration.UrlEndpointDefinition::.ctor

- ea: `0x3b60`
- end: `0x3b8c`
- name: `Microsoft.BIServer.Configuration.UrlEndpointDefinition::.ctor`
- size: `44`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x3850`

## callees

- `0x3ba0`
- `0x3bc0`
- `0x3be0`
- `0x3c00`
- `0x3c20`

## pseudocode

```c

```

## disassembly

```asm
0x3b60  ldarg.0
0x3b61  call     instance void [mscorlib]System.Object::.ctor()
0x3b66  ldarg.0
0x3b67  ldarg.1
0x3b68  call     instance void Microsoft.BIServer.Configuration.UrlEndpointDefinition::set_AccountCredentials(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.AccountCredentials value)
0x3b6d  ldarg.0
0x3b6e  ldarg.2
0x3b6f  call     instance void Microsoft.BIServer.Configuration.UrlEndpointDefinition::set_Name(string value)
0x3b74  ldarg.0
0x3b75  ldarg.3
0x3b76  call     instance void Microsoft.BIServer.Configuration.UrlEndpointDefinition::set_VirtualDirectory(string value)
0x3b7b  ldarg.0
0x3b7c  ldarg.s  4
0x3b7e  call     instance void Microsoft.BIServer.Configuration.UrlEndpointDefinition::set_UrlString(string value)
0x3b83  ldarg.0
0x3b84  ldarg.s  5
0x3b86  call     instance void Microsoft.BIServer.Configuration.UrlEndpointDefinition::set_UrlEndpointUsage(valuetype Microsoft.BIServer.Configuration.UrlEndpointUsage value)
0x3b8b  ret
```
