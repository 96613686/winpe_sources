# Microsoft.ReportingServices.Diagnostics.OAuthConnectionConfiguration::GetProperties

- ea: `0x20a0`
- end: `0x2121`
- name: `Microsoft.ReportingServices.Diagnostics.OAuthConnectionConfiguration::GetProperties`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x17c0`
- `0x20a0`
- `0x101e0`

## pseudocode

```c

```

## disassembly

```asm
0x20a0  newobj   instance void <>c__DisplayClass45_0::.ctor()
0x20a5  stloc.0
0x20a6  ldloc.0
0x20a7  ldarg.1
0x20a8  stfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<string> <>c__DisplayClass45_0::requestedProperties
0x20ad  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x20b2  stloc.1
0x20b3  ldarg.0
0x20b4  ldfld    class Microsoft.ReportingServices.Diagnostics.OAuthConnectionConfigurationPropertyBag Microsoft.ReportingServices.Diagnostics.OAuthConnectionConfiguration::m_properties
0x20b9  ldloc.0
0x20ba  ldfld    class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>, bool> <>c__DisplayClass45_0::<>9__0
0x20bf  dup
0x20c0  brtrue.s loc_20D8
0x20c2  pop
0x20c3  ldloc.0
0x20c4  ldloc.0
0x20c5  ldftn    instance bool <>c__DisplayClass45_0::<GetProperties>b__0(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo> p)
0x20cb  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>, bool>::.ctor(object, native int)
0x20d0  dup
0x20d1  stloc.3
0x20d2  stfld    class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>, bool> <>c__DisplayClass45_0::<>9__0
0x20d7  ldloc.3
0x20d8  call     T0x2B000006
0x20dd  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>>::GetEnumerator()
0x20e2  stloc.2
0x20e3  br.s     loc_210B
0x20e5  ldloc.2
0x20e6  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>>::get_Current()
0x20eb  stloc.s  4
0x20ed  ldloc.1
0x20ee  ldloca.s 4
0x20f0  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::get_Key()
0x20f5  ldloca.s 4
0x20f7  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::get_Value()
0x20fc  callvirt instance object Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::get_Value()
0x2101  castclass [mscorlib]System.String
0x2106  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x210b  ldloc.2
0x210c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2111  brtrue.s loc_20E5
0x2113  leave.s  loc_211F
0x2115  ldloc.2
0x2116  brfalse.s loc_211E
0x2118  ldloc.2
0x2119  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x211e  endfinally
0x211f  ldloc.1
0x2120  ret
```
