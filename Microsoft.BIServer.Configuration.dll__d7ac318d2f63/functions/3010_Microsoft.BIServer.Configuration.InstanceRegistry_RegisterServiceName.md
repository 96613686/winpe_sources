# Microsoft.BIServer.Configuration.InstanceRegistry::RegisterServiceName

- ea: `0x3010`
- end: `0x3037`
- name: `Microsoft.BIServer.Configuration.InstanceRegistry::RegisterServiceName`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x2810`

## string_xrefs

- `0x302b`: `ServiceName`

## pseudocode

```c

```

## disassembly

```asm
0x3010  ldarg.0
0x3011  ldfld    class Microsoft.BIServer.Configuration.IRegistryStore Microsoft.BIServer.Configuration.InstanceRegistry::_registryStore
0x3016  ldarg.0
0x3017  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath Microsoft.BIServer.Configuration.InstanceRegistry::_instancePath
0x301c  ldstr    aSetup// "Setup"
0x3021  call     class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath::op_Addition(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath, string)
0x3026  call     string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath::op_Implicit(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath)
0x302b  ldstr    aServicename// "ServiceName"
0x3030  ldarg.1
0x3031  callvirt instance void Microsoft.BIServer.Configuration.IRegistryStore::SetValue(string key, string name, string value)
0x3036  ret
```
