# System.Net.Http.HttpContentMessageExtensions::IsHttpRequestMessageContent

- ea: `0x17f0`
- end: `0x1811`
- name: `System.Net.Http.HttpContentMessageExtensions::IsHttpRequestMessageContent`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x17f0`
- `0x2070`
- `0xb3c0`

## pseudocode

```c

```

## disassembly

```asm
0x17f0  ldarg.0
0x17f1  brtrue.s loc_17FE
0x17f3  ldstr    aContent// "content"
0x17f8  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x17fd  throw
0x17fe  nop
0x17ff  ldarg.0
0x1800  ldc.i4.1
0x1801  ldc.i4.0
0x1802  call     bool System.Net.Http.HttpMessageContent::ValidateHttpMessageContent(class [System.Net.Http]System.Net.Http.HttpContent content, bool isRequest, bool throwOnError)
0x1807  stloc.0
0x1808  leave.s  loc_180F
0x180a  pop
0x180b  ldc.i4.0
0x180c  stloc.0
0x180d  leave.s  loc_180F
0x180f  ldloc.0
0x1810  ret
```
