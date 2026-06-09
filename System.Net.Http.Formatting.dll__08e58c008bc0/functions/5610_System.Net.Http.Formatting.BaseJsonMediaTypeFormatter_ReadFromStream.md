# System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::ReadFromStream

- ea: `0x5610`
- end: `0x567f`
- name: `System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::ReadFromStream`
- size: `111`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x55d0`

## callees

- `0x5610`
- `0x5680`
- `0x6910`
- `0x8020`
- `0x81f0`

## pseudocode

```c

```

## disassembly

```asm
0x5610  ldarg.3
0x5611  brfalse.s loc_561B
0x5613  ldarg.3
0x5614  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders [System.Net.Http]System.Net.Http.HttpContent::get_Headers()
0x5619  br.s     loc_561C
0x561b  ldnull
0x561c  stloc.0
0x561d  ldloc.0
0x561e  brfalse.s loc_5645
0x5620  ldloc.0
0x5621  callvirt instance valuetype [mscorlib]System.Nullable`1<int64> [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders::get_ContentLength()
0x5626  stloc.2
0x5627  ldc.i4.0
0x5628  conv.i8
0x5629  stloc.3
0x562a  ldloca.s 2
0x562c  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int64>::GetValueOrDefault()
0x5631  ldloc.3
0x5632  ceq
0x5634  ldloca.s 2
0x5636  call     instance bool valuetype [mscorlib]System.Nullable`1<int64>::get_HasValue()
0x563b  and
0x563c  brfalse.s loc_5645
0x563e  ldarg.1
0x563f  call     object System.Net.Http.Formatting.MediaTypeFormatter::GetDefaultValueForType(class [mscorlib]System.Type type)
0x5644  ret
0x5645  ldarg.0
0x5646  ldloc.0
0x5647  call     instance class [mscorlib]System.Text.Encoding System.Net.Http.Formatting.MediaTypeFormatter::SelectCharacterEncoding(class [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders contentHeaders)
0x564c  stloc.1
0x564d  ldarg.0
0x564e  ldarg.1
0x564f  ldarg.2
0x5650  ldloc.1
0x5651  ldarg.s  4
0x5653  callvirt instance object System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::ReadFromStream(class [mscorlib]System.Type type, class [mscorlib]System.IO.Stream readStream, class [mscorlib]System.Text.Encoding effectiveEncoding, class System.Net.Http.Formatting.IFormatterLogger formatterLogger)
0x5658  stloc.s  4
0x565a  leave.s  loc_567C
0x565c  stloc.s  5
0x565e  ldarg.s  4
0x5660  brtrue.s loc_5664
0x5662  rethrow
0x5664  ldarg.s  4
0x5666  ldsfld   string [mscorlib]System.String::Empty
0x566b  ldloc.s  5
0x566d  callvirt instance void System.Net.Http.Formatting.IFormatterLogger::LogError(string errorPath, class [mscorlib]System.Exception exception)
0x5672  ldarg.1
0x5673  call     object System.Net.Http.Formatting.MediaTypeFormatter::GetDefaultValueForType(class [mscorlib]System.Type type)
0x5678  stloc.s  4
0x567a  leave.s  loc_567C
0x567c  ldloc.s  4
0x567e  ret
```
