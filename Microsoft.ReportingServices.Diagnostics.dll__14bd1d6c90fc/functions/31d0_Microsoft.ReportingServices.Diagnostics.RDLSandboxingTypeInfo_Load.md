# Microsoft.ReportingServices.Diagnostics.RDLSandboxingTypeInfo::Load

- ea: `0x31d0`
- end: `0x326e`
- name: `Microsoft.ReportingServices.Diagnostics.RDLSandboxingTypeInfo::Load`
- size: `158`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x2e10`

## callees

- `0x17c0`
- `0x31d0`

## pseudocode

```c

```

## disassembly

```asm
0x31d0  ldarg.1
0x31d1  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::GetEnumerator()
0x31d6  stloc.0
0x31d7  br.s     loc_3251
0x31d9  ldloca.s 0
0x31db  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::get_Current()
0x31e0  stloc.1
0x31e1  ldloca.s 1
0x31e3  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::get_Key()
0x31e8  stloc.2
0x31e9  ldloca.s 1
0x31eb  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::get_Value()
0x31f0  stloc.3
0x31f1  ldloc.2
0x31f2  ldstr    aNamespace// "Namespace"
0x31f7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x31fc  brtrue.s loc_321A
0x31fe  ldloc.2
0x31ff  ldstr    aAllownew// "AllowNew"
0x3204  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3209  brtrue.s loc_322D
0x320b  ldloc.2
0x320c  ldstr    aName_0// "Name"
0x3211  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3216  brtrue.s loc_3240
0x3218  br.s     loc_3251
0x321a  ldarg.0
0x321b  ldloc.3
0x321c  callvirt instance object Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::get_Value()
0x3221  castclass [mscorlib]System.String
0x3226  stfld    string Microsoft.ReportingServices.Diagnostics.RDLSandboxingTypeInfo::m_namespace
0x322b  br.s     loc_3251
0x322d  ldarg.0
0x322e  ldloc.3
0x322f  callvirt instance object Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::get_Value()
0x3234  unbox.any [mscorlib]System.Boolean
0x3239  stfld    bool Microsoft.ReportingServices.Diagnostics.RDLSandboxingTypeInfo::m_allowNew
0x323e  br.s     loc_3251
0x3240  ldarg.0
0x3241  ldloc.3
0x3242  callvirt instance object Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::get_Value()
0x3247  castclass [mscorlib]System.String
0x324c  stfld    string Microsoft.ReportingServices.Diagnostics.RDLSandboxingTypeInfo::m_name
0x3251  ldloca.s 0
0x3253  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::MoveNext()
0x3258  brtrue   loc_31D9
0x325d  leave.s  loc_326D
0x325f  ldloca.s 0
0x3261  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>
0x3267  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x326c  endfinally
0x326d  ret
```
