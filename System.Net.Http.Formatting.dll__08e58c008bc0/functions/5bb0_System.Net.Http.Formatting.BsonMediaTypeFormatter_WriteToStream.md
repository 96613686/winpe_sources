# System.Net.Http.Formatting.BsonMediaTypeFormatter::WriteToStream

- ea: `0x5bb0`
- end: `0x5c42`
- name: `System.Net.Http.Formatting.BsonMediaTypeFormatter::WriteToStream`
- size: `146`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x5840`
- `0x5bb0`
- `0x5c90`
- `0xb3c0`

## string_xrefs

- `0x5bc7`: `writeStream`

## pseudocode

```c

```

## disassembly

```asm
0x5bb0  ldarg.1
0x5bb1  ldnull
0x5bb2  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x5bb7  brfalse.s loc_5BC4
0x5bb9  ldstr    aType// "type"
0x5bbe  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x5bc3  throw
0x5bc4  ldarg.3
0x5bc5  brtrue.s loc_5BD2
0x5bc7  ldstr    aWritestream// "writeStream"
0x5bcc  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x5bd1  throw
0x5bd2  ldarg.s  4
0x5bd4  brtrue.s loc_5BE1
0x5bd6  ldstr    aEffectiveencod// "effectiveEncoding"
0x5bdb  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x5be0  throw
0x5be1  ldarg.2
0x5be2  brtrue.s loc_5BE5
0x5be4  ret
0x5be5  ldarg.2
0x5be6  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x5beb  bne.un.s loc_5BEE
0x5bed  ret
0x5bee  ldarg.2
0x5bef  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x5bf4  stloc.0
0x5bf5  ldloc.0
0x5bf6  call     bool System.Net.Http.Formatting.BsonMediaTypeFormatter::IsSimpleType(class [mscorlib]System.Type type)
0x5bfb  brtrue.s loc_5C0F
0x5bfd  ldloc.0
0x5bfe  ldtoken  unsigned int8[]
0x5c03  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5c08  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x5c0d  brfalse.s loc_5C36
0x5c0f  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x5c14  dup
0x5c15  ldstr    aValue_0// "Value"
0x5c1a  ldarg.2
0x5c1b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x5c20  stloc.1
0x5c21  ldarg.0
0x5c22  ldtoken  class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>
0x5c27  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5c2c  ldloc.1
0x5c2d  ldarg.3
0x5c2e  ldarg.s  4
0x5c30  call     instance void System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::WriteToStream(class [mscorlib]System.Type type, object value, class [mscorlib]System.IO.Stream writeStream, class [mscorlib]System.Text.Encoding effectiveEncoding)
0x5c35  ret
0x5c36  ldarg.0
0x5c37  ldarg.1
0x5c38  ldarg.2
0x5c39  ldarg.3
0x5c3a  ldarg.s  4
0x5c3c  call     instance void System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::WriteToStream(class [mscorlib]System.Type type, object value, class [mscorlib]System.IO.Stream writeStream, class [mscorlib]System.Text.Encoding effectiveEncoding)
0x5c41  ret
```
