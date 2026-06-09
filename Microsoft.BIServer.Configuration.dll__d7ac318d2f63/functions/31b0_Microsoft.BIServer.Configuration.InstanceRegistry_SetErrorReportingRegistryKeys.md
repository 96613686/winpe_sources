# Microsoft.BIServer.Configuration.InstanceRegistry::SetErrorReportingRegistryKeys

- ea: `0x31b0`
- end: `0x31df`
- name: `Microsoft.BIServer.Configuration.InstanceRegistry::SetErrorReportingRegistryKeys`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x2820`
- `0x31b0`

## pseudocode

```c

```

## disassembly

```asm
0x31b0  ldarg.1
0x31b1  brtrue.s loc_31B6
0x31b3  ldc.i4.0
0x31b4  br.s     loc_31B7
0x31b6  ldc.i4.1
0x31b7  stloc.0
0x31b8  ldarg.0
0x31b9  ldfld    class Microsoft.BIServer.Configuration.IRegistryStore Microsoft.BIServer.Configuration.InstanceRegistry::_registryStore
0x31be  ldarg.0
0x31bf  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath Microsoft.BIServer.Configuration.InstanceRegistry::_instancePath
0x31c4  ldstr    aCpe// "CPE"
0x31c9  call     class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath::op_Addition(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath, string)
0x31ce  call     string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath::op_Implicit(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath)
0x31d3  ldstr    aEnableerrorrep// "EnableErrorReporting"
0x31d8  ldloc.0
0x31d9  callvirt instance void Microsoft.BIServer.Configuration.IRegistryStore::SetValue(string key, string name, int32 value)
0x31de  ret
```
