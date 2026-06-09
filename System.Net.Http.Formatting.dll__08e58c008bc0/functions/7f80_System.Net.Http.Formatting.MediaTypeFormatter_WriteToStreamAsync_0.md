# System.Net.Http.Formatting.MediaTypeFormatter::WriteToStreamAsync_0

- ea: `0x7f80`
- end: `0x7f9f`
- name: `System.Net.Http.Formatting.MediaTypeFormatter::WriteToStreamAsync_0`
- size: `31`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x6ae0`
- `0x7f60`

## callees

- `0x3690`
- `0xb4d0`

## pseudocode

```c

```

## disassembly

```asm
0x7f80  call     string System.Net.Http.Properties.Resources::get_MediaTypeFormatterCannotWrite()
0x7f85  ldc.i4.1
0x7f86  newarr   [mscorlib]System.Object
0x7f8b  dup
0x7f8c  ldc.i4.0
0x7f8d  ldarg.0
0x7f8e  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x7f93  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x7f98  stelem.ref
0x7f99  call     class [mscorlib]System.NotSupportedException System.Web.Http.Error::NotSupported(string messageFormat, object[] messageArgs)
0x7f9e  throw
```
