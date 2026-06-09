# Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag::Add_0

- ea: `0x1710`
- end: `0x174d`
- name: `Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag::Add_0`
- size: `61`
- prototype: ``
- caller_count: `9`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1700`
- `0x7390`
- `0x77e0`
- `0x7d20`
- `0x82e0`
- `0x8390`
- `0x8440`
- `0x8530`
- `0x8c50`

## callees

- `0x1710`
- `0x17f0`
- `0x1820`

## pseudocode

```c

```

## disassembly

```asm
0x1710  ldarg.0
0x1711  ldarg.1
0x1712  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.ReportingServices.Diagnostics.ConfigurationProperty, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::ContainsKey(var<u1>)
0x1717  brfalse.s loc_1737
0x1719  ldarg.3
0x171a  brtrue.s loc_172B
0x171c  ldarga.s 1
0x171e  constrained. Microsoft.ReportingServices.Diagnostics.ConfigurationProperty
0x1724  callvirt instance string [mscorlib]System.Object::ToString()
0x1729  starg.s  3
0x172b  ldarg.3
0x172c  call     string [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStringsWrapper::DuplicateConfigElement(string)
0x1731  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0x1736  throw
0x1737  newobj   instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::.ctor()
0x173c  stloc.0
0x173d  ldloc.0
0x173e  ldarg.2
0x173f  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::set_SpecifiedValue(string value)
0x1744  ldarg.0
0x1745  ldarg.1
0x1746  ldloc.0
0x1747  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.ReportingServices.Diagnostics.ConfigurationProperty, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::Add(var<u1>, !!T0)
0x174c  ret
```
