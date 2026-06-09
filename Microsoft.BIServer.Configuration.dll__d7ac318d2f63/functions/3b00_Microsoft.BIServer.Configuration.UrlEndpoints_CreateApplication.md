# Microsoft.BIServer.Configuration.UrlEndpoints::CreateApplication

- ea: `0x3b00`
- end: `0x3b2c`
- name: `Microsoft.BIServer.Configuration.UrlEndpoints::CreateApplication`
- size: `44`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x39e0`

## callees

- `0x3bb0`
- `0x3bd0`
- `0x3bf0`
- `0x3c10`
- `0x4790`
- `0x48c0`

## pseudocode

```c

```

## disassembly

```asm
0x3b00  ldarg.0
0x3b01  callvirt instance string Microsoft.BIServer.Configuration.UrlEndpointDefinition::get_Name()
0x3b06  ldarg.0
0x3b07  callvirt instance string Microsoft.BIServer.Configuration.UrlEndpointDefinition::get_VirtualDirectory()
0x3b0c  ldc.i4.1
0x3b0d  newarr   Microsoft.BIServer.Configuration.URL
0x3b12  dup
0x3b13  ldc.i4.0
0x3b14  ldarg.0
0x3b15  callvirt instance string Microsoft.BIServer.Configuration.UrlEndpointDefinition::get_UrlString()
0x3b1a  ldarg.0
0x3b1b  callvirt instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.AccountCredentials Microsoft.BIServer.Configuration.UrlEndpointDefinition::get_AccountCredentials()
0x3b20  call     class Microsoft.BIServer.Configuration.URL Microsoft.BIServer.Configuration.URL::Create(string urlString, class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.AccountCredentials accountCredentials)
0x3b25  stelem.ref
0x3b26  newobj   instance void Microsoft.BIServer.Configuration.Application::.ctor(string name, string virtualDirectory, class Microsoft.BIServer.Configuration.URL[] urls)
0x3b2b  ret
```
