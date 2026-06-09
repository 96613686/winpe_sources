# Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::IsConfigSwitchEnabled

- ea: `0x4fa0`
- end: `0x4fbe`
- name: `Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::IsConfigSwitchEnabled`
- size: `30`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x800`

## pseudocode

```c

```

## disassembly

```asm
0x4fa0  ldsfld   class Microsoft.BIServer.HostingEnvironment.StaticConfig Microsoft.BIServer.HostingEnvironment.StaticConfig::Current
0x4fa5  ldarga.s 1
0x4fa7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4fac  constrained. Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSwitches
0x4fb2  callvirt instance string [mscorlib]System.Enum::ToString(class [mscorlib]System.IFormatProvider)
0x4fb7  ldarg.2
0x4fb8  callvirt instance bool Microsoft.BIServer.HostingEnvironment.StaticConfig::GetOrDefault(string key, bool defaultValue)
0x4fbd  ret
```
