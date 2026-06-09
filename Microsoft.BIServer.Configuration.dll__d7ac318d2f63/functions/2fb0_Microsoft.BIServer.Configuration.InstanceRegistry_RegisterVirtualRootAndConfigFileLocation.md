# Microsoft.BIServer.Configuration.InstanceRegistry::RegisterVirtualRootAndConfigFileLocation

- ea: `0x2fb0`
- end: `0x3006`
- name: `Microsoft.BIServer.Configuration.InstanceRegistry::RegisterVirtualRootAndConfigFileLocation`
- size: `86`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x2810`

## string_xrefs

- `0x2ff5`: `RsConfigFilePath`

## pseudocode

```c

```

## disassembly

```asm
0x2fb0  ldarg.0
0x2fb1  ldfld    class Microsoft.BIServer.Configuration.IRegistryStore Microsoft.BIServer.Configuration.InstanceRegistry::_registryStore
0x2fb6  ldarg.0
0x2fb7  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath Microsoft.BIServer.Configuration.InstanceRegistry::_instancePath
0x2fbc  ldstr    aSetup// "Setup"
0x2fc1  call     class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath::op_Addition(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath, string)
0x2fc6  call     string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath::op_Implicit(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath)
0x2fcb  ldstr    aRsvirtualroots// "RSVirtualRootServer"
0x2fd0  ldstr    aReportserver// "ReportServer"
0x2fd5  callvirt instance void Microsoft.BIServer.Configuration.IRegistryStore::SetValue(string key, string name, string value)
0x2fda  ldarg.0
0x2fdb  ldfld    class Microsoft.BIServer.Configuration.IRegistryStore Microsoft.BIServer.Configuration.InstanceRegistry::_registryStore
0x2fe0  ldarg.0
0x2fe1  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath Microsoft.BIServer.Configuration.InstanceRegistry::_instancePath
0x2fe6  ldstr    aSetup// "Setup"
0x2feb  call     class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath::op_Addition(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath, string)
0x2ff0  call     string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath::op_Implicit(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath)
0x2ff5  ldstr    aRsconfigfilepa_0// "RsConfigFilePath"
0x2ffa  ldarg.1
0x2ffb  call     string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath::op_Implicit(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath)
0x3000  callvirt instance void Microsoft.BIServer.Configuration.IRegistryStore::SetValue(string key, string name, string value)
0x3005  ret
```
