# System.Net.Http.Formatting.BufferedMediaTypeFormatter::ReadFromStream_0

- ea: `0x6ac0`
- end: `0x6adf`
- name: `System.Net.Http.Formatting.BufferedMediaTypeFormatter::ReadFromStream_0`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x6ab0`

## callees

- `0x3670`
- `0xb4d0`

## pseudocode

```c

```

## disassembly

```asm
0x6ac0  call     string System.Net.Http.Properties.Resources::get_MediaTypeFormatterCannotReadSync()
0x6ac5  ldc.i4.1
0x6ac6  newarr   [mscorlib]System.Object
0x6acb  dup
0x6acc  ldc.i4.0
0x6acd  ldarg.0
0x6ace  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x6ad3  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x6ad8  stelem.ref
0x6ad9  call     class [mscorlib]System.NotSupportedException System.Web.Http.Error::NotSupported(string messageFormat, object[] messageArgs)
0x6ade  throw
```
