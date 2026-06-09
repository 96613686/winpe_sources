# Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigUpgrade::UpdateSettingIfEqualsOldDefault

- ea: `0x4670`
- end: `0x46c5`
- name: `Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigUpgrade::UpdateSettingIfEqualsOldDefault`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x43a0`

## callees

- `0x4670`

## pseudocode

```c

```

## disassembly

```asm
0x4670  ldarg.0
0x4671  ldarga.s 1
0x4673  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4678  constrained. Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings
0x467e  callvirt instance string [mscorlib]System.Enum::ToString(class [mscorlib]System.IFormatProvider)
0x4683  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::ContainsKey(var<u1>)
0x4688  brfalse.s loc_46C4
0x468a  ldarg.0
0x468b  ldarga.s 1
0x468d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4692  constrained. Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings
0x4698  callvirt instance string [mscorlib]System.Enum::ToString(class [mscorlib]System.IFormatProvider)
0x469d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::get_Item(void)
0x46a2  ldarg.2
0x46a3  ldc.i4.3
0x46a4  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x46a9  brfalse.s loc_46C4
0x46ab  ldarg.0
0x46ac  ldarga.s 1
0x46ae  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x46b3  constrained. Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings
0x46b9  callvirt instance string [mscorlib]System.Enum::ToString(class [mscorlib]System.IFormatProvider)
0x46be  ldarg.3
0x46bf  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x46c4  ret
```
