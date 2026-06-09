# System.Net.Http.HttpContentMultipartExtensions::IsMimeMultipartContent

- ea: `0x1d00`
- end: `0x1d15`
- name: `System.Net.Http.HttpContentMultipartExtensions::IsMimeMultipartContent`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1d20`

## callees

- `0x1d00`
- `0xa830`
- `0xb3c0`

## pseudocode

```c

```

## disassembly

```asm
0x1d00  ldarg.0
0x1d01  brtrue.s loc_1D0E
0x1d03  ldstr    aContent// "content"
0x1d08  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x1d0d  throw
0x1d0e  ldarg.0
0x1d0f  call     bool System.Net.Http.Formatting.Parsers.MimeMultipartBodyPartParser::IsMimeMultipartContent(class [System.Net.Http]System.Net.Http.HttpContent content)
0x1d14  ret
```
