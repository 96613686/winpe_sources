# System.Net.Http.MimeBodyPart::GetCompletedHttpContent

- ea: `0x2830`
- end: `0x2857`
- name: `System.Net.Http.MimeBodyPart::GetCompletedHttpContent`
- size: `39`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1e90`

## callees

- `0x1ed0`
- `0x2830`

## pseudocode

```c

```

## disassembly

```asm
0x2830  ldarg.0
0x2831  ldfld    class [System.Net.Http]System.Net.Http.HttpContent System.Net.Http.MimeBodyPart::_content
0x2836  brtrue.s loc_283A
0x2838  ldnull
0x2839  ret
0x283a  ldarg.0
0x283b  ldfld    class [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders System.Net.Http.MimeBodyPart::_headers
0x2840  ldarg.0
0x2841  ldfld    class [System.Net.Http]System.Net.Http.HttpContent System.Net.Http.MimeBodyPart::_content
0x2846  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders [System.Net.Http]System.Net.Http.HttpContent::get_Headers()
0x284b  call     void System.Net.Http.HttpHeaderExtensions::CopyTo(class [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders fromHeaders, class [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders toHeaders)
0x2850  ldarg.0
0x2851  ldfld    class [System.Net.Http]System.Net.Http.HttpContent System.Net.Http.MimeBodyPart::_content
0x2856  ret
```
