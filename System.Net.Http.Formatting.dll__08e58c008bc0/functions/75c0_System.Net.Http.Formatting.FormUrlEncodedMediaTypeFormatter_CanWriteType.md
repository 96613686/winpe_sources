# System.Net.Http.Formatting.FormUrlEncodedMediaTypeFormatter::CanWriteType

- ea: `0x75c0`
- end: `0x75d6`
- name: `System.Net.Http.Formatting.FormUrlEncodedMediaTypeFormatter::CanWriteType`
- size: `22`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x75c0`
- `0xb3c0`

## pseudocode

```c

```

## disassembly

```asm
0x75c0  ldarg.1
0x75c1  ldnull
0x75c2  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x75c7  brfalse.s loc_75D4
0x75c9  ldstr    aType// "type"
0x75ce  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x75d3  throw
0x75d4  ldc.i4.0
0x75d5  ret
```
