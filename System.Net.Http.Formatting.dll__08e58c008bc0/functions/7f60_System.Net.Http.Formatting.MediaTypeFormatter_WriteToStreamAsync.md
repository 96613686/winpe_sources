# System.Net.Http.Formatting.MediaTypeFormatter::WriteToStreamAsync

- ea: `0x7f60`
- end: `0x7f73`
- name: `System.Net.Http.Formatting.MediaTypeFormatter::WriteToStreamAsync`
- size: `19`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x2e50`

## callees

- `0x7f80`

## pseudocode

```c

```

## disassembly

```asm
0x7f60  ldarg.0
0x7f61  ldarg.1
0x7f62  ldarg.2
0x7f63  ldarg.3
0x7f64  ldarg.s  4
0x7f66  ldarg.s  5
0x7f68  call     valuetype [mscorlib]System.Threading.CancellationToken [mscorlib]System.Threading.CancellationToken::get_None()
0x7f6d  callvirt instance class [mscorlib]System.Threading.Tasks.Task System.Net.Http.Formatting.MediaTypeFormatter::WriteToStreamAsync(class [mscorlib]System.Type type, object value, class [mscorlib]System.IO.Stream writeStream, class [System.Net.Http]System.Net.Http.HttpContent content, class [System]System.Net.TransportContext transportContext, valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x7f72  ret
```
