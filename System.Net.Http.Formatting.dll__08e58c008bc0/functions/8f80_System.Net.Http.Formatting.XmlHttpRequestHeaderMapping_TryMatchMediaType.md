# System.Net.Http.Formatting.XmlHttpRequestHeaderMapping::TryMatchMediaType

- ea: `0x8f80`
- end: `0x8fe7`
- name: `System.Net.Http.Formatting.XmlHttpRequestHeaderMapping::TryMatchMediaType`
- size: `103`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x8d00`
- `0x8f80`
- `0xb3c0`

## pseudocode

```c

```

## disassembly

```asm
0x8f80  ldarg.1
0x8f81  brtrue.s loc_8F8E
0x8f83  ldstr    aRequest// "request"
0x8f88  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x8f8d  throw
0x8f8e  ldarg.1
0x8f8f  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpRequestHeaders [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Headers()
0x8f94  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpHeaderValueCollection`1<class [System.Net.Http]System.Net.Http.Headers.MediaTypeWithQualityHeaderValue> [System.Net.Http]System.Net.Http.Headers.HttpRequestHeaders::get_Accept()
0x8f99  callvirt instance int32 class [System.Net.Http]System.Net.Http.Headers.HttpHeaderValueCollection`1<class [System.Net.Http]System.Net.Http.Headers.MediaTypeWithQualityHeaderValue>::get_Count()
0x8f9e  brfalse.s loc_8FD5
0x8fa0  ldarg.1
0x8fa1  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpRequestHeaders [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Headers()
0x8fa6  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpHeaderValueCollection`1<class [System.Net.Http]System.Net.Http.Headers.MediaTypeWithQualityHeaderValue> [System.Net.Http]System.Net.Http.Headers.HttpRequestHeaders::get_Accept()
0x8fab  callvirt instance int32 class [System.Net.Http]System.Net.Http.Headers.HttpHeaderValueCollection`1<class [System.Net.Http]System.Net.Http.Headers.MediaTypeWithQualityHeaderValue>::get_Count()
0x8fb0  ldc.i4.1
0x8fb1  bne.un.s loc_8FDD
0x8fb3  ldarg.1
0x8fb4  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpRequestHeaders [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Headers()
0x8fb9  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpHeaderValueCollection`1<class [System.Net.Http]System.Net.Http.Headers.MediaTypeWithQualityHeaderValue> [System.Net.Http]System.Net.Http.Headers.HttpRequestHeaders::get_Accept()
0x8fbe  call     T0x2B00005A
0x8fc3  callvirt instance string [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue::get_MediaType()
0x8fc8  ldstr    asc_10E98// "*/*"
0x8fcd  ldc.i4.4
0x8fce  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x8fd3  brfalse.s loc_8FDD
0x8fd5  ldarg.0
0x8fd6  ldarg.1
0x8fd7  call     instance float64 System.Net.Http.Formatting.RequestHeaderMapping::TryMatchMediaType(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x8fdc  ret
0x8fdd  ldc.r8   0.0
0x8fe6  ret
```
