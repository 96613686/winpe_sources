# Microsoft.ReportingServices.Diagnostics.MapTileServerConfiguration::Validate

- ea: `0x1c40`
- end: `0x1d91`
- name: `Microsoft.ReportingServices.Diagnostics.MapTileServerConfiguration::Validate`
- size: `337`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x4bd0`

## callees

- `0x17d0`
- `0x17e0`
- `0x1980`
- `0x1c40`
- `0x9390`
- `0x93a0`

## string_xrefs

- `0x1c8f`: `CacheLevel`

## pseudocode

```c

```

## disassembly

```asm
0x1c40  ldarg.2
0x1c41  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::GetEnumerator()
0x1c46  stloc.0
0x1c47  br       loc_1D74
0x1c4c  ldloca.s 0
0x1c4e  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::get_Current()
0x1c53  stloc.1
0x1c54  ldloca.s 1
0x1c56  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::get_Key()
0x1c5b  stloc.2
0x1c5c  ldloca.s 1
0x1c5e  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::get_Value()
0x1c63  stloc.3
0x1c64  ldloc.2
0x1c65  ldstr    aMaxconnections// "MaxConnections"
0x1c6a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1c6f  brtrue.s loc_1CA3
0x1c71  ldloc.2
0x1c72  ldstr    aTimeout// "Timeout"
0x1c77  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1c7c  brtrue.s loc_1CE4
0x1c7e  ldloc.2
0x1c7f  ldstr    aAppid// "AppID"
0x1c84  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1c89  brtrue   loc_1D23
0x1c8e  ldloc.2
0x1c8f  ldstr    aCachelevel// "CacheLevel"
0x1c94  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1c99  brtrue   loc_1D4C
0x1c9e  br       loc_1D74
0x1ca3  ldarg.0
0x1ca4  ldarg.1
0x1ca5  ldloc.2
0x1ca6  ldloc.3
0x1ca7  callvirt instance string Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::get_SpecifiedValue()
0x1cac  ldc.i4.2
0x1cad  ldstr    asc_126C2// ""
0x1cb2  newobj   instance void Microsoft.ReportingServices.Diagnostics.IntParameter::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IParameterSource parameterSource, class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace tracer, string name, string configValue, int32 defaultValue, string units)
0x1cb7  stloc.s  4
0x1cb9  ldloc.s  4
0x1cbb  ldc.i4.1
0x1cbc  callvirt instance void class Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::set_MinValue(var<u1>)
0x1cc1  ldloc.s  4
0x1cc3  ldc.i4   0x7FFFFFFF
0x1cc8  callvirt instance void class Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::set_MaxValue(var<u1>)
0x1ccd  ldloc.3
0x1cce  ldloc.s  4
0x1cd0  callvirt instance var<u1> class Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::get_Value()
0x1cd5  box      [mscorlib]System.Int32
0x1cda  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::set_Value(object value)
0x1cdf  br       loc_1D74
0x1ce4  ldarg.0
0x1ce5  ldarg.1
0x1ce6  ldloc.2
0x1ce7  ldloc.3
0x1ce8  callvirt instance string Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::get_SpecifiedValue()
0x1ced  ldc.i4.s 0xA
0x1cef  ldstr    aSecondS// "second(s)"
0x1cf4  newobj   instance void Microsoft.ReportingServices.Diagnostics.IntParameter::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IParameterSource parameterSource, class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace tracer, string name, string configValue, int32 defaultValue, string units)
0x1cf9  stloc.s  5
0x1cfb  ldloc.s  5
0x1cfd  ldc.i4.1
0x1cfe  callvirt instance void class Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::set_MinValue(var<u1>)
0x1d03  ldloc.s  5
0x1d05  ldc.i4   0x7FFFFFFF
0x1d0a  callvirt instance void class Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::set_MaxValue(var<u1>)
0x1d0f  ldloc.3
0x1d10  ldloc.s  5
0x1d12  callvirt instance var<u1> class Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::get_Value()
0x1d17  box      [mscorlib]System.Int32
0x1d1c  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::set_Value(object value)
0x1d21  br.s     loc_1D74
0x1d23  ldarg.0
0x1d24  ldarg.1
0x1d25  ldloc.2
0x1d26  ldloc.3
0x1d27  callvirt instance string Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::get_SpecifiedValue()
0x1d2c  ldstr    aDefault_0// "(Default)"
0x1d31  ldstr    asc_126C2// ""
0x1d36  newobj   instance void Microsoft.ReportingServices.Diagnostics.StringParameter::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IParameterSource parameterSource, class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace tracer, string name, string configValue, string defaultValue, string units)
0x1d3b  stloc.s  6
0x1d3d  ldloc.3
0x1d3e  ldloc.s  6
0x1d40  callvirt instance string Microsoft.ReportingServices.Diagnostics.StringParameter::get_Value()
0x1d45  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::set_Value(object value)
0x1d4a  br.s     loc_1D74
0x1d4c  ldarg.0
0x1d4d  ldarg.1
0x1d4e  ldloc.2
0x1d4f  ldloc.3
0x1d50  callvirt instance string Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::get_SpecifiedValue()
0x1d55  ldc.i4.0
0x1d56  ldstr    asc_126C2// ""
0x1d5b  newobj   instance void class Microsoft.ReportingServices.Diagnostics.EnumParameter`1<valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MapTileCacheLevel>::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IParameterSource, class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace, string, string, var<u1>, !!T0)
0x1d60  stloc.s  7
0x1d62  ldloc.3
0x1d63  ldloc.s  7
0x1d65  callvirt instance var<u1> class Microsoft.ReportingServices.Diagnostics.EnumParameter`1<valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MapTileCacheLevel>::get_Value()
0x1d6a  box      [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MapTileCacheLevel
0x1d6f  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::set_Value(object value)
0x1d74  ldloca.s 0
0x1d76  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::MoveNext()
0x1d7b  brtrue   loc_1C4C
0x1d80  leave.s  loc_1D90
0x1d82  ldloca.s 0
0x1d84  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>
0x1d8a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1d8f  endfinally
0x1d90  ret
```
