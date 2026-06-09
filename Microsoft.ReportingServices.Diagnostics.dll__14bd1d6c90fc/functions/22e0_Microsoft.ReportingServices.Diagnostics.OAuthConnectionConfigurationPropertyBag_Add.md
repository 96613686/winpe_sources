# Microsoft.ReportingServices.Diagnostics.OAuthConnectionConfigurationPropertyBag::Add

- ea: `0x22e0`
- end: `0x230c`
- name: `Microsoft.ReportingServices.Diagnostics.OAuthConnectionConfigurationPropertyBag::Add`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x17d0`
- `0x17f0`
- `0x1820`
- `0x22e0`

## pseudocode

```c

```

## disassembly

```asm
0x22e0  ldarg.0
0x22e1  ldarg.1
0x22e2  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::ContainsKey(var<u1>)
0x22e7  brfalse.s loc_22EF
0x22e9  ldarg.1
0x22ea  call     void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.XmlParseExceptions::ThrowInvalidFormat(string)
0x22ef  newobj   instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::.ctor()
0x22f4  stloc.0
0x22f5  ldloc.0
0x22f6  ldarg.2
0x22f7  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::set_SpecifiedValue(string value)
0x22fc  ldloc.0
0x22fd  ldarg.2
0x22fe  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::set_Value(object value)
0x2303  ldarg.0
0x2304  ldarg.1
0x2305  ldloc.0
0x2306  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::Add(var<u1>, !!T0)
0x230b  ret
```
