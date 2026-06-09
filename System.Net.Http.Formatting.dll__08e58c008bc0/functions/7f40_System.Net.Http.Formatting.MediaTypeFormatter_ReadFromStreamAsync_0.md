# System.Net.Http.Formatting.MediaTypeFormatter::ReadFromStreamAsync_0

- ea: `0x7f40`
- end: `0x7f5b`
- name: `System.Net.Http.Formatting.MediaTypeFormatter::ReadFromStreamAsync_0`
- size: `27`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x6b80`
- `0xc220`

## callees

- `0x7f20`
- `0x7f40`

## pseudocode

```c

```

## disassembly

```asm
0x7f40  ldarga.s 5
0x7f42  call     instance bool [mscorlib]System.Threading.CancellationToken::get_IsCancellationRequested()
0x7f47  brfalse.s loc_7F4F
0x7f49  call     T0x2B000050
0x7f4e  ret
0x7f4f  ldarg.0
0x7f50  ldarg.1
0x7f51  ldarg.2
0x7f52  ldarg.3
0x7f53  ldarg.s  4
0x7f55  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<object> System.Net.Http.Formatting.MediaTypeFormatter::ReadFromStreamAsync(class [mscorlib]System.Type type, class [mscorlib]System.IO.Stream readStream, class [System.Net.Http]System.Net.Http.HttpContent content, class System.Net.Http.Formatting.IFormatterLogger formatterLogger)
0x7f5a  ret
```
