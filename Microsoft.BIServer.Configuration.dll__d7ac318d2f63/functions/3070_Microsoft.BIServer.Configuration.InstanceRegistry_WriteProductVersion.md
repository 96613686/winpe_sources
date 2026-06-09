# Microsoft.BIServer.Configuration.InstanceRegistry::WriteProductVersion

- ea: `0x3070`
- end: `0x3093`
- name: `Microsoft.BIServer.Configuration.InstanceRegistry::WriteProductVersion`
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
0x3070  ldarg.0
0x3071  ldfld    class Microsoft.BIServer.Configuration.IRegistryStore Microsoft.BIServer.Configuration.InstanceRegistry::_registryStore
0x3076  ldarg.0
0x3077  ldarg.0
0x3078  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath Microsoft.BIServer.Configuration.InstanceRegistry::_instancePath
0x307d  call     instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath Microsoft.BIServer.Configuration.InstanceRegistry::CurrentVersionPath(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath instancePath)
0x3082  call     string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath::op_Implicit(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath)
0x3087  ldstr    aProductversion// "ProductVersion"
0x308c  ldarg.1
0x308d  callvirt instance void Microsoft.BIServer.Configuration.IRegistryStore::SetValue(string key, string name, string value)
0x3092  ret
```
