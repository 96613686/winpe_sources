# Microsoft.ReportingServices.Diagnostics.MapTileServerConfiguration::Load

- ea: `0x1da0`
- end: `0x1e61`
- name: `Microsoft.ReportingServices.Diagnostics.MapTileServerConfiguration::Load`
- size: `193`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x4170`

## callees

- `0x17c0`
- `0x1da0`

## string_xrefs

- `0x1dec`: `CacheLevel`

## pseudocode

```c

```

## disassembly

```asm
0x1da0  ldarg.1
0x1da1  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::GetEnumerator()
0x1da6  stloc.0
0x1da7  br       loc_1E44
0x1dac  ldloca.s 0
0x1dae  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::get_Current()
0x1db3  stloc.1
0x1db4  ldloca.s 1
0x1db6  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::get_Key()
0x1dbb  stloc.2
0x1dbc  ldloca.s 1
0x1dbe  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::get_Value()
0x1dc3  stloc.3
0x1dc4  ldloc.2
0x1dc5  ldstr    aMaxconnections// "MaxConnections"
0x1dca  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1dcf  brtrue.s loc_1DFA
0x1dd1  ldloc.2
0x1dd2  ldstr    aTimeout// "Timeout"
0x1dd7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1ddc  brtrue.s loc_1E0D
0x1dde  ldloc.2
0x1ddf  ldstr    aAppid// "AppID"
0x1de4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1de9  brtrue.s loc_1E20
0x1deb  ldloc.2
0x1dec  ldstr    aCachelevel// "CacheLevel"
0x1df1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1df6  brtrue.s loc_1E33
0x1df8  br.s     loc_1E44
0x1dfa  ldarg.0
0x1dfb  ldloc.3
0x1dfc  callvirt instance object Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::get_Value()
0x1e01  unbox.any [mscorlib]System.Int32
0x1e06  stfld    int32 Microsoft.ReportingServices.Diagnostics.MapTileServerConfiguration::m_maxConnections
0x1e0b  br.s     loc_1E44
0x1e0d  ldarg.0
0x1e0e  ldloc.3
0x1e0f  callvirt instance object Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::get_Value()
0x1e14  unbox.any [mscorlib]System.Int32
0x1e19  stfld    int32 Microsoft.ReportingServices.Diagnostics.MapTileServerConfiguration::m_timeout
0x1e1e  br.s     loc_1E44
0x1e20  ldarg.0
0x1e21  ldloc.3
0x1e22  callvirt instance object Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::get_Value()
0x1e27  castclass [mscorlib]System.String
0x1e2c  stfld    string Microsoft.ReportingServices.Diagnostics.MapTileServerConfiguration::m_appID
0x1e31  br.s     loc_1E44
0x1e33  ldarg.0
0x1e34  ldloc.3
0x1e35  callvirt instance object Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::get_Value()
0x1e3a  unbox.any [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MapTileCacheLevel
0x1e3f  stfld    valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MapTileCacheLevel Microsoft.ReportingServices.Diagnostics.MapTileServerConfiguration::m_cacheLevel
0x1e44  ldloca.s 0
0x1e46  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::MoveNext()
0x1e4b  brtrue   loc_1DAC
0x1e50  leave.s  loc_1E60
0x1e52  ldloca.s 0
0x1e54  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>
0x1e5a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1e5f  endfinally
0x1e60  ret
```
