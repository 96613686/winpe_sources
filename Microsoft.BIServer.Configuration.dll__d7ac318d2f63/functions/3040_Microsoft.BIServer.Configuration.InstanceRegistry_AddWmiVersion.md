# Microsoft.BIServer.Configuration.InstanceRegistry::AddWmiVersion

- ea: `0x3040`
- end: `0x3063`
- name: `Microsoft.BIServer.Configuration.InstanceRegistry::AddWmiVersion`
- size: `35`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x2810`
- `0x30a0`

## pseudocode

```c

```

## disassembly

```asm
0x3040  ldarg.0
0x3041  ldfld    class Microsoft.BIServer.Configuration.IRegistryStore Microsoft.BIServer.Configuration.InstanceRegistry::_registryStore
0x3046  ldarg.0
0x3047  ldarg.0
0x3048  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath Microsoft.BIServer.Configuration.InstanceRegistry::_instancePath
0x304d  call     instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath Microsoft.BIServer.Configuration.InstanceRegistry::CurrentVersionPath(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath instancePath)
0x3052  call     string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath::op_Implicit(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath)
0x3057  ldstr    aCurrentversion// "CurrentVersion"
0x305c  ldarg.1
0x305d  callvirt instance void Microsoft.BIServer.Configuration.IRegistryStore::SetValue(string key, string name, string value)
0x3062  ret
```
