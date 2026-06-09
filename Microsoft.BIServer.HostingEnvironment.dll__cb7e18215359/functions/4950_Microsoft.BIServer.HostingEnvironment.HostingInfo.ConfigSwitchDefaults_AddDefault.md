# Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSwitchDefaults::AddDefault

- ea: `0x4950`
- end: `0x4970`
- name: `Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSwitchDefaults::AddDefault`
- size: `32`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x48a0`

## pseudocode

```c

```

## disassembly

```asm
0x4950  ldarg.0
0x4951  ldarga.s 1
0x4953  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4958  constrained. Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSwitches
0x495e  callvirt instance string [mscorlib]System.Enum::ToString(class [mscorlib]System.IFormatProvider)
0x4963  ldarga.s 2
0x4965  call     instance string [mscorlib]System.Boolean::ToString()
0x496a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x496f  ret
```
