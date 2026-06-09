# System.Net.Http.Formatting.BufferedMediaTypeFormatter::WriteToStreamSync

- ea: `0x6b50`
- end: `0x6b77`
- name: `System.Net.Http.Formatting.BufferedMediaTypeFormatter::WriteToStreamSync`
- size: `39`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x6b00`

## callees

- `0x6a80`
- `0x6b50`
- `0x6c60`

## pseudocode

```c

```

## disassembly

```asm
0x6b50  ldarg.3
0x6b51  ldarg.0
0x6b52  ldfld    int32 System.Net.Http.Formatting.BufferedMediaTypeFormatter::_bufferSizeInBytes
0x6b57  call     class [mscorlib]System.IO.Stream System.Net.Http.Formatting.BufferedMediaTypeFormatter::GetBufferStream(class [mscorlib]System.IO.Stream innerStream, int32 bufferSize)
0x6b5c  stloc.0
0x6b5d  ldarg.0
0x6b5e  ldarg.1
0x6b5f  ldarg.2
0x6b60  ldloc.0
0x6b61  ldarg.s  4
0x6b63  ldarg.s  5
0x6b65  callvirt instance void System.Net.Http.Formatting.BufferedMediaTypeFormatter::WriteToStream(class [mscorlib]System.Type type, object value, class [mscorlib]System.IO.Stream writeStream, class [System.Net.Http]System.Net.Http.HttpContent content, valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x6b6a  leave.s  loc_6B76
0x6b6c  ldloc.0
0x6b6d  brfalse.s loc_6B75
0x6b6f  ldloc.0
0x6b70  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6b75  endfinally
0x6b76  ret
```
