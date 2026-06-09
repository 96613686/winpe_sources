# Microsoft.ReportingServices.Diagnostics.MapTileServerConfigurationPropertyBag::Add

- ea: `0x1ed0`
- end: `0x1ef5`
- name: `Microsoft.ReportingServices.Diagnostics.MapTileServerConfigurationPropertyBag::Add`
- size: `37`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1b70`

## callees

- `0x17f0`
- `0x1820`
- `0x1ed0`

## pseudocode

```c

```

## disassembly

```asm
0x1ed0  ldarg.0
0x1ed1  ldarg.1
0x1ed2  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::ContainsKey(var<u1>)
0x1ed7  brfalse.s loc_1EDF
0x1ed9  ldarg.1
0x1eda  call     void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.XmlParseExceptions::ThrowInvalidFormat(string)
0x1edf  newobj   instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::.ctor()
0x1ee4  stloc.0
0x1ee5  ldloc.0
0x1ee6  ldarg.2
0x1ee7  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::set_SpecifiedValue(string value)
0x1eec  ldarg.0
0x1eed  ldarg.1
0x1eee  ldloc.0
0x1eef  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::Add(var<u1>, !!T0)
0x1ef4  ret
```
