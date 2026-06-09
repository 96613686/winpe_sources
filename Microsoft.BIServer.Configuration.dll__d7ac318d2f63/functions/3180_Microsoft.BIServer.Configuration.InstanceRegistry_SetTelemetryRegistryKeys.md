# Microsoft.BIServer.Configuration.InstanceRegistry::SetTelemetryRegistryKeys

- ea: `0x3180`
- end: `0x31af`
- name: `Microsoft.BIServer.Configuration.InstanceRegistry::SetTelemetryRegistryKeys`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x2820`
- `0x3180`

## pseudocode

```c

```

## disassembly

```asm
0x3180  ldarg.1
0x3181  brtrue.s loc_3186
0x3183  ldc.i4.0
0x3184  br.s     loc_3187
0x3186  ldc.i4.1
0x3187  stloc.0
0x3188  ldarg.0
0x3189  ldfld    class Microsoft.BIServer.Configuration.IRegistryStore Microsoft.BIServer.Configuration.InstanceRegistry::_registryStore
0x318e  ldarg.0
0x318f  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath Microsoft.BIServer.Configuration.InstanceRegistry::_instancePath
0x3194  ldstr    aCpe// "CPE"
0x3199  call     class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath::op_Addition(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath, string)
0x319e  call     string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath::op_Implicit(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath)
0x31a3  ldstr    aCustomerfeedba// "CustomerFeedback"
0x31a8  ldloc.0
0x31a9  callvirt instance void Microsoft.BIServer.Configuration.IRegistryStore::SetValue(string key, string name, int32 value)
0x31ae  ret
```
