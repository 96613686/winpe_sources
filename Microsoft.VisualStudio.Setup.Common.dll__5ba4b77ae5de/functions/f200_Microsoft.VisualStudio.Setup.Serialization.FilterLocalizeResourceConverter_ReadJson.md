# Microsoft.VisualStudio.Setup.Serialization.FilterLocalizeResourceConverter::ReadJson

- ea: `0xf200`
- end: `0xf297`
- name: `Microsoft.VisualStudio.Setup.Serialization.FilterLocalizeResourceConverter::ReadJson`
- size: `151`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x8890`
- `0x8920`
- `0xc1a0`
- `0xf200`

## string_xrefs

- `0xf201`: `reader`

## pseudocode

```c

```

## disassembly

```asm
0xf200  ldarg.1
0xf201  ldstr    aReader// "reader"
0xf206  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0xf20b  ldarg.s  4
0xf20d  ldstr    aSerializer// "serializer"
0xf212  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0xf217  ldarg.1
0xf218  callvirt instance valuetype [Newtonsoft.Json]Newtonsoft.Json.JsonToken [Newtonsoft.Json]Newtonsoft.Json.JsonReader::get_TokenType()
0xf21d  ldc.i4.s 0xB
0xf21f  bne.un.s loc_F223
0xf221  ldnull
0xf222  ret
0xf223  ldarg.1
0xf224  callvirt instance valuetype [Newtonsoft.Json]Newtonsoft.Json.JsonToken [Newtonsoft.Json]Newtonsoft.Json.JsonReader::get_TokenType()
0xf229  ldc.i4.1
0xf22a  bne.un.s loc_F291
0xf22c  ldarg.1
0xf22d  call     class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::Load(class [Newtonsoft.Json]Newtonsoft.Json.JsonReader)
0xf232  stloc.0
0xf233  ldloc.0
0xf234  ldstr    aLanguage// "language"
0xf239  ldc.i4.5
0xf23a  ldloca.s 1
0xf23c  callvirt instance bool [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::TryGetValue(string, valuetype [mscorlib]System.StringComparison, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken&)
0xf241  brfalse.s loc_F291
0xf243  ldloc.1
0xf244  callvirt instance valuetype [Newtonsoft.Json]Newtonsoft.Json.Linq.JTokenType [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken::get_Type()
0xf249  ldc.i4.8
0xf24a  bne.un.s loc_F291
0xf24c  ldarg.0
0xf24d  ldfld    string Microsoft.VisualStudio.Setup.Serialization.FilterLocalizeResourceConverter::filterLanguage
0xf252  ldloc.1
0xf253  call     T0x2B000064
0xf258  ldc.i4.5
0xf259  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0xf25e  brtrue.s loc_F262
0xf260  ldnull
0xf261  ret
0xf262  ldarg.2
0xf263  ldtoken  Microsoft.VisualStudio.Setup.LocalizedResourceTemplate
0xf268  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xf26d  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xf272  brtrue.s loc_F27B
0xf274  newobj   instance void Microsoft.VisualStudio.Setup.LocalizedResource::.ctor()
0xf279  br.s     loc_F280
0xf27b  newobj   instance void Microsoft.VisualStudio.Setup.LocalizedResourceTemplate::.ctor()
0xf280  stloc.2
0xf281  ldarg.s  4
0xf283  ldloc.0
0xf284  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.JsonReader [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken::CreateReader()
0xf289  ldloc.2
0xf28a  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializer::Populate(class [Newtonsoft.Json]Newtonsoft.Json.JsonReader, object)
0xf28f  ldloc.2
0xf290  ret
0xf291  newobj   instance void [mscorlib]System.NotSupportedException::.ctor()
0xf296  throw
```
