# System.Net.Http.HttpContentMultipartExtensions::IsMimeMultipartContent_0

- ea: `0x1d20`
- end: `0x1d62`
- name: `System.Net.Http.HttpContentMultipartExtensions::IsMimeMultipartContent_0`
- size: `66`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x9d0`

## callees

- `0x1d00`
- `0x1d20`
- `0xb3c0`

## pseudocode

```c

```

## disassembly

```asm
0x1d20  ldarg.1
0x1d21  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x1d26  brfalse.s loc_1D33
0x1d28  ldstr    aSubtype// "subtype"
0x1d2d  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x1d32  throw
0x1d33  ldarg.0
0x1d34  call     bool System.Net.Http.HttpContentMultipartExtensions::IsMimeMultipartContent(class [System.Net.Http]System.Net.Http.HttpContent content)
0x1d39  brfalse.s loc_1D60
0x1d3b  ldarg.0
0x1d3c  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders [System.Net.Http]System.Net.Http.HttpContent::get_Headers()
0x1d41  callvirt instance class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders::get_ContentType()
0x1d46  callvirt instance string [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue::get_MediaType()
0x1d4b  ldstr    aMultipart// "multipart/"
0x1d50  ldarg.1
0x1d51  call     string [mscorlib]System.String::Concat(string, string)
0x1d56  ldc.i4.5
0x1d57  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x1d5c  brfalse.s loc_1D60
0x1d5e  ldc.i4.1
0x1d5f  ret
0x1d60  ldc.i4.0
0x1d61  ret
```
