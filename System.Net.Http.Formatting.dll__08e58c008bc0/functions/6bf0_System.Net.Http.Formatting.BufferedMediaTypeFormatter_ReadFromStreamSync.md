# System.Net.Http.Formatting.BufferedMediaTypeFormatter::ReadFromStreamSync

- ea: `0x6bf0`
- end: `0x6c54`
- name: `System.Net.Http.Formatting.BufferedMediaTypeFormatter::ReadFromStreamSync`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x6ba0`

## callees

- `0x6ab0`
- `0x6bf0`
- `0x6c60`
- `0x81f0`

## pseudocode

```c

```

## disassembly

```asm
0x6bf0  ldarg.3
0x6bf1  brfalse.s loc_6BFB
0x6bf3  ldarg.3
0x6bf4  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders [System.Net.Http]System.Net.Http.HttpContent::get_Headers()
0x6bf9  br.s     loc_6BFC
0x6bfb  ldnull
0x6bfc  stloc.1
0x6bfd  ldloc.1
0x6bfe  brfalse.s loc_6C27
0x6c00  ldloc.1
0x6c01  callvirt instance valuetype [mscorlib]System.Nullable`1<int64> [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders::get_ContentLength()
0x6c06  stloc.2
0x6c07  ldc.i4.0
0x6c08  conv.i8
0x6c09  stloc.3
0x6c0a  ldloca.s 2
0x6c0c  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int64>::GetValueOrDefault()
0x6c11  ldloc.3
0x6c12  ceq
0x6c14  ldloca.s 2
0x6c16  call     instance bool valuetype [mscorlib]System.Nullable`1<int64>::get_HasValue()
0x6c1b  and
0x6c1c  brfalse.s loc_6C27
0x6c1e  ldarg.1
0x6c1f  call     object System.Net.Http.Formatting.MediaTypeFormatter::GetDefaultValueForType(class [mscorlib]System.Type type)
0x6c24  stloc.0
0x6c25  br.s     loc_6C52
0x6c27  ldarg.2
0x6c28  ldarg.0
0x6c29  ldfld    int32 System.Net.Http.Formatting.BufferedMediaTypeFormatter::_bufferSizeInBytes
0x6c2e  call     class [mscorlib]System.IO.Stream System.Net.Http.Formatting.BufferedMediaTypeFormatter::GetBufferStream(class [mscorlib]System.IO.Stream innerStream, int32 bufferSize)
0x6c33  stloc.s  4
0x6c35  ldarg.0
0x6c36  ldarg.1
0x6c37  ldloc.s  4
0x6c39  ldarg.3
0x6c3a  ldarg.s  4
0x6c3c  ldarg.s  5
0x6c3e  callvirt instance object System.Net.Http.Formatting.BufferedMediaTypeFormatter::ReadFromStream(class [mscorlib]System.Type type, class [mscorlib]System.IO.Stream readStream, class [System.Net.Http]System.Net.Http.HttpContent content, class System.Net.Http.Formatting.IFormatterLogger formatterLogger, valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x6c43  stloc.0
0x6c44  leave.s  loc_6C52
0x6c46  ldloc.s  4
0x6c48  brfalse.s loc_6C51
0x6c4a  ldloc.s  4
0x6c4c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6c51  endfinally
0x6c52  ldloc.0
0x6c53  ret
```
