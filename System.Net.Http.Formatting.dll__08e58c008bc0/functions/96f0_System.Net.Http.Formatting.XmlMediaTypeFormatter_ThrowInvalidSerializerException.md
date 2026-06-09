# System.Net.Http.Formatting.XmlMediaTypeFormatter::ThrowInvalidSerializerException

- ea: `0x96f0`
- end: `0x972b`
- name: `System.Net.Http.Formatting.XmlMediaTypeFormatter::ThrowInvalidSerializerException`
- size: `59`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x92c0`
- `0x9400`

## callees

- `0x3a10`
- `0x3a30`
- `0x96f0`
- `0xb4b0`

## pseudocode

```c

```

## disassembly

```asm
0x96f0  ldarg.0
0x96f1  brtrue.s loc_9708
0x96f3  call     string System.Net.Http.Properties.Resources::get_XmlMediaTypeFormatter_NullReturnedSerializer()
0x96f8  ldc.i4.1
0x96f9  newarr   [mscorlib]System.Object
0x96fe  dup
0x96ff  ldc.i4.0
0x9700  ldarg.1
0x9701  stelem.ref
0x9702  call     class [mscorlib]System.InvalidOperationException System.Web.Http.Error::InvalidOperation(string messageFormat, object[] messageArgs)
0x9707  throw
0x9708  call     string System.Net.Http.Properties.Resources::get_XmlMediaTypeFormatter_InvalidSerializerType()
0x970d  ldc.i4.2
0x970e  newarr   [mscorlib]System.Object
0x9713  dup
0x9714  ldc.i4.0
0x9715  ldarg.0
0x9716  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x971b  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x9720  stelem.ref
0x9721  dup
0x9722  ldc.i4.1
0x9723  ldarg.1
0x9724  stelem.ref
0x9725  call     class [mscorlib]System.InvalidOperationException System.Web.Http.Error::InvalidOperation(string messageFormat, object[] messageArgs)
0x972a  throw
```
