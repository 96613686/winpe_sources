# Microsoft.VisualStudio.Setup.Serialization.ConditionGroupConverter::ReadJson

- ea: `0xe3e0`
- end: `0xe44f`
- name: `Microsoft.VisualStudio.Setup.Serialization.ConditionGroupConverter::ReadJson`
- size: `111`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x3eb0`
- `0x3f00`
- `0xc1a0`
- `0xe3e0`

## string_xrefs

- `0xe3e1`: `reader`

## pseudocode

```c

```

## disassembly

```asm
0xe3e0  ldarg.1
0xe3e1  ldstr    aReader// "reader"
0xe3e6  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0xe3eb  ldarg.s  4
0xe3ed  ldstr    aSerializer// "serializer"
0xe3f2  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0xe3f7  ldarg.1
0xe3f8  callvirt instance valuetype [Newtonsoft.Json]Newtonsoft.Json.JsonToken [Newtonsoft.Json]Newtonsoft.Json.JsonReader::get_TokenType()
0xe3fd  ldc.i4.s 0xB
0xe3ff  bne.un.s loc_E403
0xe401  ldnull
0xe402  ret
0xe403  ldarg.1
0xe404  callvirt instance valuetype [Newtonsoft.Json]Newtonsoft.Json.JsonToken [Newtonsoft.Json]Newtonsoft.Json.JsonReader::get_TokenType()
0xe409  ldc.i4.2
0xe40a  bne.un.s loc_E42F
0xe40c  newobj   instance void Microsoft.VisualStudio.Setup.ConditionGroup::.ctor()
0xe411  dup
0xe412  ldarg.s  4
0xe414  ldarg.1
0xe415  callvirt T0x2B000069
0xe41a  dup
0xe41b  brtrue.s loc_E429
0xe41d  pop
0xe41e  ldstr    aExpectedNonNul_16// "Expected non-null 'Conditions' when des"...
0xe423  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializationException::.ctor(string)
0xe428  throw
0xe429  callvirt instance void Microsoft.VisualStudio.Setup.ConditionGroup::set_Conditions(class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.VisualStudio.Setup.Condition> value)
0xe42e  ret
0xe42f  ldarg.1
0xe430  callvirt instance valuetype [Newtonsoft.Json]Newtonsoft.Json.JsonToken [Newtonsoft.Json]Newtonsoft.Json.JsonReader::get_TokenType()
0xe435  ldc.i4.1
0xe436  bne.un.s loc_E449
0xe438  newobj   instance void Microsoft.VisualStudio.Setup.ConditionGroup::.ctor()
0xe43d  stloc.0
0xe43e  ldarg.s  4
0xe440  ldarg.1
0xe441  ldloc.0
0xe442  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializer::Populate(class [Newtonsoft.Json]Newtonsoft.Json.JsonReader, object)
0xe447  ldloc.0
0xe448  ret
0xe449  newobj   instance void [mscorlib]System.NotSupportedException::.ctor()
0xe44e  throw
```
