# System.Net.Http.Formatting.FormUrlEncodedMediaTypeFormatter::CanReadType

- ea: `0x7590`
- end: `0x75bf`
- name: `System.Net.Http.Formatting.FormUrlEncodedMediaTypeFormatter::CanReadType`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x12c0`
- `0x7590`
- `0xb3c0`

## pseudocode

```c

```

## disassembly

```asm
0x7590  ldarg.1
0x7591  ldnull
0x7592  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x7597  brfalse.s loc_75A4
0x7599  ldstr    aType// "type"
0x759e  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x75a3  throw
0x75a4  ldarg.1
0x75a5  ldtoken  System.Net.Http.Formatting.FormDataCollection
0x75aa  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x75af  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x75b4  brtrue.s loc_75BD
0x75b6  ldarg.1
0x75b7  call     bool System.Net.Http.FormattingUtilities::IsJTokenType(class [mscorlib]System.Type type)
0x75bc  ret
0x75bd  ldc.i4.1
0x75be  ret
```
