# Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigDefaults::AddDefault

- ea: `0x4c60`
- end: `0x4c73`
- name: `Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigDefaults::AddDefault`
- size: `19`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4990`

## pseudocode

```c

```

## disassembly

```asm
0x4c60  ldarg.0
0x4c61  ldarg.1
0x4c62  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4c67  callvirt instance string [mscorlib]System.Enum::ToString(class [mscorlib]System.IFormatProvider)
0x4c6c  ldarg.2
0x4c6d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x4c72  ret
```
