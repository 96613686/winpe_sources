# System.Net.Http.HttpContentMessageExtensions::IsHttpResponseMessageContent

- ea: `0x1820`
- end: `0x1841`
- name: `System.Net.Http.HttpContentMessageExtensions::IsHttpResponseMessageContent`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1820`
- `0x2070`
- `0xb3c0`

## pseudocode

```c

```

## disassembly

```asm
0x1820  ldarg.0
0x1821  brtrue.s loc_182E
0x1823  ldstr    aContent// "content"
0x1828  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x182d  throw
0x182e  nop
0x182f  ldarg.0
0x1830  ldc.i4.0
0x1831  ldc.i4.0
0x1832  call     bool System.Net.Http.HttpMessageContent::ValidateHttpMessageContent(class [System.Net.Http]System.Net.Http.HttpContent content, bool isRequest, bool throwOnError)
0x1837  stloc.0
0x1838  leave.s  loc_183F
0x183a  pop
0x183b  ldc.i4.0
0x183c  stloc.0
0x183d  leave.s  loc_183F
0x183f  ldloc.0
0x1840  ret
```
