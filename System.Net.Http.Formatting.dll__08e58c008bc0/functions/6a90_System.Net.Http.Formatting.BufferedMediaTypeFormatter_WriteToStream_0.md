# System.Net.Http.Formatting.BufferedMediaTypeFormatter::WriteToStream_0

- ea: `0x6a90`
- end: `0x6aaf`
- name: `System.Net.Http.Formatting.BufferedMediaTypeFormatter::WriteToStream_0`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x6a80`

## callees

- `0x36b0`
- `0xb4d0`

## pseudocode

```c

```

## disassembly

```asm
0x6a90  call     string System.Net.Http.Properties.Resources::get_MediaTypeFormatterCannotWriteSync()
0x6a95  ldc.i4.1
0x6a96  newarr   [mscorlib]System.Object
0x6a9b  dup
0x6a9c  ldc.i4.0
0x6a9d  ldarg.0
0x6a9e  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x6aa3  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x6aa8  stelem.ref
0x6aa9  call     class [mscorlib]System.NotSupportedException System.Web.Http.Error::NotSupported(string messageFormat, object[] messageArgs)
0x6aae  throw
```
