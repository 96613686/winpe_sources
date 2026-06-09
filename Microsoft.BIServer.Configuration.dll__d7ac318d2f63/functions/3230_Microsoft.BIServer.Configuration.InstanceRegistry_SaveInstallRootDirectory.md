# Microsoft.BIServer.Configuration.InstanceRegistry::SaveInstallRootDirectory

- ea: `0x3230`
- end: `0x3257`
- name: `Microsoft.BIServer.Configuration.InstanceRegistry::SaveInstallRootDirectory`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x2810`

## string_xrefs

- `0x324b`: `InstallRootDirectory`

## pseudocode

```c

```

## disassembly

```asm
0x3230  ldarg.0
0x3231  ldfld    class Microsoft.BIServer.Configuration.IRegistryStore Microsoft.BIServer.Configuration.InstanceRegistry::_registryStore
0x3236  ldarg.0
0x3237  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath Microsoft.BIServer.Configuration.InstanceRegistry::_instancePath
0x323c  ldstr    aSetup// "Setup"
0x3241  call     class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath::op_Addition(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath, string)
0x3246  call     string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath::op_Implicit(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath)
0x324b  ldstr    aInstallrootdir// "InstallRootDirectory"
0x3250  ldarg.1
0x3251  callvirt instance void Microsoft.BIServer.Configuration.IRegistryStore::SetValue(string key, string name, string value)
0x3256  ret
```
