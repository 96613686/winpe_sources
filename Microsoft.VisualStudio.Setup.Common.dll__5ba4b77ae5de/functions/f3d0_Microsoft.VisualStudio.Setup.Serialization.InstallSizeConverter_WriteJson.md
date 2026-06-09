# Microsoft.VisualStudio.Setup.Serialization.InstallSizeConverter::WriteJson

- ea: `0xf3d0`
- end: `0xf47e`
- name: `Microsoft.VisualStudio.Setup.Serialization.InstallSizeConverter::WriteJson`
- size: `174`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0xc1a0`
- `0xf3d0`

## string_xrefs

- `0xf3d1`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0xf3d0  ldarg.1
0xf3d1  ldstr    aWriter// "writer"
0xf3d6  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0xf3db  ldarg.3
0xf3dc  ldstr    aSerializer// "serializer"
0xf3e1  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0xf3e6  ldarg.2
0xf3e7  isinst   Microsoft.VisualStudio.Setup.InstallSize
0xf3ec  stloc.0
0xf3ed  ldloc.0
0xf3ee  brtrue.s loc_F3F7
0xf3f0  ldarg.1
0xf3f1  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WriteNull()
0xf3f6  ret
0xf3f7  ldarg.3
0xf3f8  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.Serialization.IContractResolver [Newtonsoft.Json]Newtonsoft.Json.JsonSerializer::get_ContractResolver()
0xf3fd  isinst   [Newtonsoft.Json]Newtonsoft.Json.Serialization.DefaultContractResolver
0xf402  stloc.1
0xf403  ldarg.1
0xf404  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WriteStartObject()
0xf409  ldloc.0
0xf40a  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int64>::GetEnumerator()
0xf40f  stloc.2
0xf410  br.s     loc_F45D
0xf412  ldloca.s 2
0xf414  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, int64>::get_Current()
0xf419  stloc.3
0xf41a  ldloca.s 3
0xf41c  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, int64>::get_Value()
0xf421  brfalse.s loc_F45D
0xf423  ldarg.1
0xf424  ldloc.1
0xf425  brtrue.s loc_F42A
0xf427  ldnull
0xf428  br.s     loc_F437
0xf42a  ldloc.1
0xf42b  ldloca.s 3
0xf42d  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, int64>::get_Key()
0xf432  call     instance string [Newtonsoft.Json]Newtonsoft.Json.Serialization.DefaultContractResolver::GetResolvedPropertyName(string)
0xf437  dup
0xf438  brtrue.s loc_F442
0xf43a  pop
0xf43b  ldloca.s 3
0xf43d  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, int64>::get_Key()
0xf442  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WritePropertyName(string)
0xf447  ldarg.1
0xf448  ldloca.s 3
0xf44a  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, int64>::get_Value()
0xf44f  stloc.s  4
0xf451  ldloca.s 4
0xf453  call     instance string [mscorlib]System.Int64::ToString()
0xf458  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WriteRawValue(string)
0xf45d  ldloca.s 2
0xf45f  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, int64>::MoveNext()
0xf464  brtrue.s loc_F412
0xf466  leave.s  loc_F47D
0xf468  ldloca.s 2
0xf46a  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, int64>
0xf470  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xf475  endfinally
0xf476  ldarg.1
0xf477  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WriteEndObject()
0xf47c  endfinally
0xf47d  ret
```
