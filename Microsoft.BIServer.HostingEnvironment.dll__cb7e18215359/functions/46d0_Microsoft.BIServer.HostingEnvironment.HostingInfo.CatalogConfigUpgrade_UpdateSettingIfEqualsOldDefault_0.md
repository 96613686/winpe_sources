# Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigUpgrade::UpdateSettingIfEqualsOldDefault_0

- ea: `0x46d0`
- end: `0x4724`
- name: `Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigUpgrade::UpdateSettingIfEqualsOldDefault_0`
- size: `84`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x43a0`

## callees

- `0x46d0`

## pseudocode

```c

```

## disassembly

```asm
0x46d0  ldarg.0
0x46d1  ldarga.s 1
0x46d3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x46d8  constrained. Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings
0x46de  callvirt instance string [mscorlib]System.Enum::ToString(class [mscorlib]System.IFormatProvider)
0x46e3  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::ContainsKey(var<u1>)
0x46e8  brfalse.s loc_4723
0x46ea  ldarg.2
0x46eb  ldarg.0
0x46ec  ldarga.s 1
0x46ee  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x46f3  constrained. Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings
0x46f9  callvirt instance string [mscorlib]System.Enum::ToString(class [mscorlib]System.IFormatProvider)
0x46fe  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::get_Item(void)
0x4703  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0x4708  brfalse.s loc_4723
0x470a  ldarg.0
0x470b  ldarga.s 1
0x470d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4712  constrained. Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings
0x4718  callvirt instance string [mscorlib]System.Enum::ToString(class [mscorlib]System.IFormatProvider)
0x471d  ldarg.3
0x471e  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x4723  ret
```
