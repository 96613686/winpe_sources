# Microsoft.ReportingServices.Diagnostics.RDLSandboxingTypeInfo::Validate

- ea: `0x30e0`
- end: `0x31c4`
- name: `Microsoft.ReportingServices.Diagnostics.RDLSandboxingTypeInfo::Validate`
- size: `228`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x2c20`

## callees

- `0x1210`
- `0x1530`
- `0x1570`
- `0x17d0`
- `0x17e0`
- `0x30e0`

## pseudocode

```c

```

## disassembly

```asm
0x30e0  ldarg.2
0x30e1  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::GetEnumerator()
0x30e6  stloc.0
0x30e7  br       loc_31A7
0x30ec  ldloca.s 0
0x30ee  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::get_Current()
0x30f3  stloc.1
0x30f4  ldloca.s 1
0x30f6  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::get_Key()
0x30fb  stloc.2
0x30fc  ldloca.s 1
0x30fe  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::get_Value()
0x3103  stloc.3
0x3104  ldloc.2
0x3105  ldstr    aAllownew// "AllowNew"
0x310a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x310f  brtrue.s loc_312D
0x3111  ldloc.2
0x3112  ldstr    aNamespace// "Namespace"
0x3117  call     bool [mscorlib]System.String::op_Equality(string, string)
0x311c  brtrue.s loc_315F
0x311e  ldloc.2
0x311f  ldstr    aName_0// "Name"
0x3124  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3129  brtrue.s loc_3184
0x312b  br.s     loc_31A7
0x312d  ldarg.0
0x312e  ldarg.1
0x312f  ldloc.2
0x3130  ldloc.3
0x3131  callvirt instance string Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::get_SpecifiedValue()
0x3136  ldc.i4.0
0x3137  ldstr    asc_126C2// ""
0x313c  newobj   instance void Microsoft.ReportingServices.Diagnostics.BooleanParameter::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IParameterSource parameterSource, class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace tracer, string name, string configValue, bool defaultValue, string units)
0x3141  stloc.s  4
0x3143  ldloc.s  4
0x3145  ldc.i4.0
0x3146  callvirt instance void Microsoft.ReportingServices.Diagnostics.ApplicationParameter::set_TraceSuccess(bool value)
0x314b  ldloc.3
0x314c  ldloc.s  4
0x314e  callvirt instance bool Microsoft.ReportingServices.Diagnostics.BooleanParameter::get_Value()
0x3153  box      [mscorlib]System.Boolean
0x3158  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::set_Value(object value)
0x315d  br.s     loc_31A7
0x315f  ldloc.3
0x3160  callvirt instance string Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::get_SpecifiedValue()
0x3165  stloc.s  5
0x3167  ldloc.s  5
0x3169  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x316e  brfalse.s loc_317A
0x3170  ldstr    aAllow// "Allow"
0x3175  call     void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.XmlParseExceptions::ThrowInvalidFormat(string)
0x317a  ldloc.3
0x317b  ldloc.s  5
0x317d  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::set_Value(object value)
0x3182  br.s     loc_31A7
0x3184  ldloc.3
0x3185  callvirt instance string Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::get_SpecifiedValue()
0x318a  stloc.s  6
0x318c  ldloc.s  6
0x318e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3193  brfalse.s loc_319F
0x3195  ldstr    aAllow// "Allow"
0x319a  call     void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.XmlParseExceptions::ThrowInvalidFormat(string)
0x319f  ldloc.3
0x31a0  ldloc.s  6
0x31a2  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::set_Value(object value)
0x31a7  ldloca.s 0
0x31a9  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::MoveNext()
0x31ae  brtrue   loc_30EC
0x31b3  leave.s  loc_31C3
0x31b5  ldloca.s 0
0x31b7  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>
0x31bd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x31c2  endfinally
0x31c3  ret
```
