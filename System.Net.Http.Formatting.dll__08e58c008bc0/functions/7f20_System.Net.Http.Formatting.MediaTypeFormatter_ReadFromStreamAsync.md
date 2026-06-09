# System.Net.Http.Formatting.MediaTypeFormatter::ReadFromStreamAsync

- ea: `0x7f20`
- end: `0x7f3f`
- name: `System.Net.Http.Formatting.MediaTypeFormatter::ReadFromStreamAsync`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x7f40`

## callees

- `0x3650`
- `0xb4d0`

## pseudocode

```c

```

## disassembly

```asm
0x7f20  call     string System.Net.Http.Properties.Resources::get_MediaTypeFormatterCannotRead()
0x7f25  ldc.i4.1
0x7f26  newarr   [mscorlib]System.Object
0x7f2b  dup
0x7f2c  ldc.i4.0
0x7f2d  ldarg.0
0x7f2e  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x7f33  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x7f38  stelem.ref
0x7f39  call     class [mscorlib]System.NotSupportedException System.Web.Http.Error::NotSupported(string messageFormat, object[] messageArgs)
0x7f3e  throw
```
