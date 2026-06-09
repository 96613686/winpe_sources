# System.Net.Http.HttpContentMessageExtensions::ReadAsHttpRequestMessageAsync_6

- ea: `0x18e0`
- end: `0x1983`
- name: `System.Net.Http.HttpContentMessageExtensions::ReadAsHttpRequestMessageAsync_6`
- size: `163`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18c0`
- `0x18d0`

## callees

- `0x18e0`
- `0x1990`
- `0x2070`
- `0x34f0`
- `0xb330`
- `0xb3c0`
- `0xb410`

## string_xrefs

- `0x18f1`: `uriScheme`
- `0x1904`: `uriScheme`

## pseudocode

```c

```

## disassembly

```asm
0x18e0  ldarg.0
0x18e1  brtrue.s loc_18EE
0x18e3  ldstr    aContent// "content"
0x18e8  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x18ed  throw
0x18ee  ldarg.1
0x18ef  brtrue.s loc_18FC
0x18f1  ldstr    aUrischeme// "uriScheme"
0x18f6  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x18fb  throw
0x18fc  ldarg.1
0x18fd  call     bool [System]System.Uri::CheckSchemeName(string)
0x1902  brtrue.s loc_1930
0x1904  ldstr    aUrischeme// "uriScheme"
0x1909  call     string System.Net.Http.Properties.Resources::get_HttpMessageParserInvalidUriScheme()
0x190e  ldc.i4.2
0x190f  newarr   [mscorlib]System.Object
0x1914  dup
0x1915  ldc.i4.0
0x1916  ldarg.1
0x1917  stelem.ref
0x1918  dup
0x1919  ldc.i4.1
0x191a  ldtoken  [System]System.Uri
0x191f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1924  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x1929  stelem.ref
0x192a  call     class [mscorlib]System.ArgumentException System.Web.Http.Error::Argument(string parameterName, string messageFormat, object[] messageArgs)
0x192f  throw
0x1930  ldarg.2
0x1931  ldc.i4   0x100
0x1936  bge.s    loc_1953
0x1938  ldstr    aBuffersize// "bufferSize"
0x193d  ldarg.2
0x193e  box      [mscorlib]System.Int32
0x1943  ldc.i4   0x100
0x1948  box      [mscorlib]System.Int32
0x194d  call     class [mscorlib]System.ArgumentOutOfRangeException System.Web.Http.Error::ArgumentMustBeGreaterThanOrEqualTo(string parameterName, object actualValue, object minValue)
0x1952  throw
0x1953  ldarg.3
0x1954  ldc.i4.2
0x1955  bge.s    loc_196E
0x1957  ldstr    aMaxheadersize// "maxHeaderSize"
0x195c  ldarg.3
0x195d  box      [mscorlib]System.Int32
0x1962  ldc.i4.2
0x1963  box      [mscorlib]System.Int32
0x1968  call     class [mscorlib]System.ArgumentOutOfRangeException System.Web.Http.Error::ArgumentMustBeGreaterThanOrEqualTo(string parameterName, object actualValue, object minValue)
0x196d  throw
0x196e  ldarg.0
0x196f  ldc.i4.1
0x1970  ldc.i4.1
0x1971  call     bool System.Net.Http.HttpMessageContent::ValidateHttpMessageContent(class [System.Net.Http]System.Net.Http.HttpContent content, bool isRequest, bool throwOnError)
0x1976  pop
0x1977  ldarg.0
0x1978  ldarg.1
0x1979  ldarg.2
0x197a  ldarg.3
0x197b  ldarg.s  4
0x197d  call     class [mscorlib]System.Threading.Tasks.Task`1<class [System.Net.Http]System.Net.Http.HttpRequestMessage> System.Net.Http.HttpContentMessageExtensions::ReadAsHttpRequestMessageAsyncCore(class [System.Net.Http]System.Net.Http.HttpContent content, string uriScheme, int32 bufferSize, int32 maxHeaderSize, valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x1982  ret
```
