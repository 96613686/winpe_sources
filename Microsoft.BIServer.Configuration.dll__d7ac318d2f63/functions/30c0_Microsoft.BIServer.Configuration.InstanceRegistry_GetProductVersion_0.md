# Microsoft.BIServer.Configuration.InstanceRegistry::GetProductVersion_0

- ea: `0x30c0`
- end: `0x30e1`
- name: `Microsoft.BIServer.Configuration.InstanceRegistry::GetProductVersion_0`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x30b0`

## callees

- `0x2830`

## pseudocode

```c

```

## disassembly

```asm
0x30c0  ldarg.0
0x30c1  ldfld    class Microsoft.BIServer.Configuration.IRegistryStore Microsoft.BIServer.Configuration.InstanceRegistry::_registryStore
0x30c6  ldarg.1
0x30c7  ldstr    aMssqlserverCur// "MSSQLServer\\CurrentVersion"
0x30cc  call     class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath::op_Addition(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath, string)
0x30d1  call     string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath::op_Implicit(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath)
0x30d6  ldstr    aProductversion// "ProductVersion"
0x30db  callvirt instance string Microsoft.BIServer.Configuration.IRegistryStore::GetValue(string key, string name)
0x30e0  ret
```
