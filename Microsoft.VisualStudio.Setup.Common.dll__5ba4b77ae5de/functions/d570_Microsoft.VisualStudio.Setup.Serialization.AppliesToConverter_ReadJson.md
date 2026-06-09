# Microsoft.VisualStudio.Setup.Serialization.AppliesToConverter::ReadJson

- ea: `0xd570`
- end: `0xd5f3`
- name: `Microsoft.VisualStudio.Setup.Serialization.AppliesToConverter::ReadJson`
- size: `131`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x21e0`
- `0x21f0`
- `0x2200`
- `0x22a0`
- `0xc1a0`
- `0xd570`
- `0x10900`

## string_xrefs

- `0xd571`: `reader`

## pseudocode

```c

```

## disassembly

```asm
0xd570  ldarg.1
0xd571  ldstr    aReader// "reader"
0xd576  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0xd57b  ldarg.s  4
0xd57d  ldstr    aSerializer// "serializer"
0xd582  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0xd587  ldarg.1
0xd588  callvirt instance valuetype [Newtonsoft.Json]Newtonsoft.Json.JsonToken [Newtonsoft.Json]Newtonsoft.Json.JsonReader::get_TokenType()
0xd58d  ldc.i4.s 0xB
0xd58f  bne.un.s loc_D593
0xd591  ldnull
0xd592  ret
0xd593  ldarg.1
0xd594  callvirt instance valuetype [Newtonsoft.Json]Newtonsoft.Json.JsonToken [Newtonsoft.Json]Newtonsoft.Json.JsonReader::get_TokenType()
0xd599  ldc.i4.s 9
0xd59b  bne.un.s loc_D5C2
0xd59d  ldarg.s  4
0xd59f  ldarg.1
0xd5a0  callvirt T0x2B000057
0xd5a5  dup
0xd5a6  brtrue.s loc_D5B4
0xd5a8  pop
0xd5a9  ldstr    aExpectedNonNul// "Expected non-null 'Version' when deseri"...
0xd5ae  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializationException::.ctor(string)
0xd5b3  throw
0xd5b4  stloc.0
0xd5b5  newobj   instance void Microsoft.VisualStudio.Setup.AppliesTo::.ctor()
0xd5ba  dup
0xd5bb  ldloc.0
0xd5bc  callvirt instance void Microsoft.VisualStudio.Setup.AppliesTo::set_Version(class Microsoft.VisualStudio.Setup.VersionRange value)
0xd5c1  ret
0xd5c2  ldarg.1
0xd5c3  callvirt instance valuetype [Newtonsoft.Json]Newtonsoft.Json.JsonToken [Newtonsoft.Json]Newtonsoft.Json.JsonReader::get_TokenType()
0xd5c8  ldc.i4.1
0xd5c9  bne.un.s loc_D5ED
0xd5cb  newobj   instance void Microsoft.VisualStudio.Setup.AppliesTo::.ctor()
0xd5d0  stloc.1
0xd5d1  ldarg.s  4
0xd5d3  ldarg.1
0xd5d4  ldloc.1
0xd5d5  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializer::Populate(class [Newtonsoft.Json]Newtonsoft.Json.JsonReader, object)
0xd5da  ldloc.1
0xd5db  ldloc.1
0xd5dc  callvirt instance string Microsoft.VisualStudio.Setup.AppliesTo::get_Branch()
0xd5e1  call     string Microsoft.VisualStudio.Setup.Serialization.TokenMapper::MapMatchAnythingToken(string value)
0xd5e6  callvirt instance void Microsoft.VisualStudio.Setup.AppliesTo::set_Branch(string value)
0xd5eb  ldloc.1
0xd5ec  ret
0xd5ed  newobj   instance void [mscorlib]System.NotSupportedException::.ctor()
0xd5f2  throw
```
