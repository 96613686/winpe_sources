# Microsoft.BIServer.Configuration.InstanceRegistry::GetInstanceInstallationDirectory

- ea: `0x3260`
- end: `0x329d`
- name: `Microsoft.BIServer.Configuration.InstanceRegistry::GetInstanceInstallationDirectory`
- size: `61`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x2830`
- `0x3260`

## string_xrefs

- `0x327b`: `InstallRootDirectory`

## pseudocode

```c

```

## disassembly

```asm
0x3260  ldarg.0
0x3261  ldfld    class Microsoft.BIServer.Configuration.IRegistryStore Microsoft.BIServer.Configuration.InstanceRegistry::_registryStore
0x3266  ldarg.0
0x3267  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath Microsoft.BIServer.Configuration.InstanceRegistry::_instancePath
0x326c  ldstr    aSetup// "Setup"
0x3271  call     class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath::op_Addition(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath, string)
0x3276  call     string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath::op_Implicit(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath)
0x327b  ldstr    aInstallrootdir// "InstallRootDirectory"
0x3280  callvirt instance string Microsoft.BIServer.Configuration.IRegistryStore::GetValue(string key, string name)
0x3285  stloc.0
0x3286  ldloc.0
0x3287  brfalse.s loc_329B
0x3289  ldloc.0
0x328a  ldarg.0
0x328b  ldfld    class Microsoft.BIServer.Configuration.InstanceId Microsoft.BIServer.Configuration.InstanceRegistry::_instanceId
0x3290  callvirt instance string [mscorlib]System.Object::ToString()
0x3295  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x329a  ret
0x329b  ldnull
0x329c  ret
```
