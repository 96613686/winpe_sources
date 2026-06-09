# System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::WriteToStream

- ea: `0x5820`
- end: `0x5840`
- name: `System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::WriteToStream`
- size: `32`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x57d0`

## callees

- `0x5820`
- `0x5840`
- `0x8020`

## pseudocode

```c

```

## disassembly

```asm
0x5820  ldarg.0
0x5821  ldarg.s  4
0x5823  brfalse.s loc_582E
0x5825  ldarg.s  4
0x5827  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders [System.Net.Http]System.Net.Http.HttpContent::get_Headers()
0x582c  br.s     loc_582F
0x582e  ldnull
0x582f  call     instance class [mscorlib]System.Text.Encoding System.Net.Http.Formatting.MediaTypeFormatter::SelectCharacterEncoding(class [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders contentHeaders)
0x5834  stloc.0
0x5835  ldarg.0
0x5836  ldarg.1
0x5837  ldarg.2
0x5838  ldarg.3
0x5839  ldloc.0
0x583a  callvirt instance void System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::WriteToStream(class [mscorlib]System.Type type, object value, class [mscorlib]System.IO.Stream writeStream, class [mscorlib]System.Text.Encoding effectiveEncoding)
0x583f  ret
```
