# System.Net.Http.Formatting.FormUrlEncodedMediaTypeFormatter::ReadFromStream

- ea: `0x7620`
- end: `0x7689`
- name: `System.Net.Http.Formatting.FormUrlEncodedMediaTypeFormatter::ReadFromStream`
- size: `105`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x75e0`

## callees

- `0x12c0`
- `0x39b0`
- `0x5ed0`
- `0x60f0`
- `0x7540`
- `0x7620`
- `0x7690`
- `0xb4b0`

## pseudocode

```c

```

## disassembly

```asm
0x7620  ldarg.2
0x7621  ldarg.0
0x7622  call     instance int32 System.Net.Http.Formatting.FormUrlEncodedMediaTypeFormatter::get_ReadBufferSize()
0x7627  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>> System.Net.Http.Formatting.FormUrlEncodedMediaTypeFormatter::ReadFormUrlEncoded(class [mscorlib]System.IO.Stream input, int32 bufferSize)
0x762c  stloc.1
0x762d  ldarg.1
0x762e  ldtoken  System.Net.Http.Formatting.FormDataCollection
0x7633  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7638  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x763d  brfalse.s loc_7648
0x763f  ldloc.1
0x7640  newobj   instance void System.Net.Http.Formatting.FormDataCollection::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>> pairs)
0x7645  stloc.0
0x7646  br.s     loc_7687
0x7648  ldarg.1
0x7649  call     bool System.Net.Http.FormattingUtilities::IsJTokenType(class [mscorlib]System.Type type)
0x764e  brfalse.s loc_765F
0x7650  ldloc.1
0x7651  ldarg.0
0x7652  ldfld    int32 System.Net.Http.Formatting.FormUrlEncodedMediaTypeFormatter::_maxDepth
0x7657  call     class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject System.Net.Http.Formatting.FormUrlEncodedJson::Parse(class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>> nameValuePairs, int32 maxDepth)
0x765c  stloc.0
0x765d  br.s     loc_7687
0x765f  call     string System.Net.Http.Properties.Resources::get_SerializerCannotSerializeType()
0x7664  ldc.i4.2
0x7665  newarr   [mscorlib]System.Object
0x766a  dup
0x766b  ldc.i4.0
0x766c  ldarg.0
0x766d  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x7672  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x7677  stelem.ref
0x7678  dup
0x7679  ldc.i4.1
0x767a  ldarg.1
0x767b  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x7680  stelem.ref
0x7681  call     class [mscorlib]System.InvalidOperationException System.Web.Http.Error::InvalidOperation(string messageFormat, object[] messageArgs)
0x7686  throw
0x7687  ldloc.0
0x7688  ret
```
