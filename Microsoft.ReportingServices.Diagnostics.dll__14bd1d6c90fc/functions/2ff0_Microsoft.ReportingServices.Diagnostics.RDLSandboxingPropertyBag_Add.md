# Microsoft.ReportingServices.Diagnostics.RDLSandboxingPropertyBag::Add

- ea: `0x2ff0`
- end: `0x3015`
- name: `Microsoft.ReportingServices.Diagnostics.RDLSandboxingPropertyBag::Add`
- size: `37`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x2970`
- `0x3060`

## callees

- `0x17f0`
- `0x1820`
- `0x2ff0`

## pseudocode

```c

```

## disassembly

```asm
0x2ff0  ldarg.0
0x2ff1  ldarg.1
0x2ff2  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::ContainsKey(var<u1>)
0x2ff7  brfalse.s loc_2FFF
0x2ff9  ldarg.1
0x2ffa  call     void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.XmlParseExceptions::ThrowInvalidFormat(string)
0x2fff  newobj   instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::.ctor()
0x3004  stloc.0
0x3005  ldloc.0
0x3006  ldarg.2
0x3007  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::set_SpecifiedValue(string value)
0x300c  ldarg.0
0x300d  ldarg.1
0x300e  ldloc.0
0x300f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::Add(var<u1>, !!T0)
0x3014  ret
```
