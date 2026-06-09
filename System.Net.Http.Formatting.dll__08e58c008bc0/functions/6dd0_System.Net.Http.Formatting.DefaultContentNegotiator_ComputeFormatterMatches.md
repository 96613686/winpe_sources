# System.Net.Http.Formatting.DefaultContentNegotiator::ComputeFormatterMatches

- ea: `0x6dd0`
- end: `0x6eb3`
- name: `System.Net.Http.Formatting.DefaultContentNegotiator::ComputeFormatterMatches`
- size: `227`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x6d40`

## callees

- `0x6dd0`
- `0x7100`
- `0x7170`
- `0x7240`
- `0x72c0`
- `0x72f0`
- `0x7350`
- `0x7410`
- `0x81b0`
- `0xb3c0`

## pseudocode

```c

```

## disassembly

```asm
0x6dd0  ldarg.1
0x6dd1  ldnull
0x6dd2  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x6dd7  brfalse.s loc_6DE4
0x6dd9  ldstr    aType// "type"
0x6dde  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x6de3  throw
0x6de4  ldarg.2
0x6de5  brtrue.s loc_6DF2
0x6de7  ldstr    aRequest// "request"
0x6dec  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x6df1  throw
0x6df2  ldarg.3
0x6df3  brtrue.s loc_6E00
0x6df5  ldstr    aFormatters// "formatters"
0x6dfa  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x6dff  throw
0x6e00  ldnull
0x6e01  stloc.0
0x6e02  newobj   instance void class System.Collections.ObjectModel.ListWrapperCollection`1<class System.Net.Http.Formatting.MediaTypeFormatterMatch>::.ctor()
0x6e07  stloc.1
0x6e08  ldarg.3
0x6e09  call     class System.Net.Http.Formatting.MediaTypeFormatter[] System.Net.Http.Formatting.DefaultContentNegotiator::GetWritingFormatters(class [mscorlib]System.Collections.Generic.IEnumerable`1<class System.Net.Http.Formatting.MediaTypeFormatter> formatters)
0x6e0e  stloc.2
0x6e0f  ldc.i4.0
0x6e10  stloc.3
0x6e11  br       loc_6EA8
0x6e16  ldloc.2
0x6e17  ldloc.3
0x6e18  ldelem.ref
0x6e19  stloc.s  4
0x6e1b  ldnull
0x6e1c  stloc.s  5
0x6e1e  ldloc.s  4
0x6e20  ldarg.1
0x6e21  callvirt instance bool System.Net.Http.Formatting.MediaTypeFormatter::CanWriteType(class [mscorlib]System.Type type)
0x6e26  brfalse.s loc_6EA4
0x6e28  ldarg.0
0x6e29  ldarg.2
0x6e2a  ldloc.s  4
0x6e2c  callvirt instance class System.Net.Http.Formatting.MediaTypeFormatterMatch System.Net.Http.Formatting.DefaultContentNegotiator::MatchMediaTypeMapping(class [System.Net.Http]System.Net.Http.HttpRequestMessage request, class System.Net.Http.Formatting.MediaTypeFormatter formatter)
0x6e31  dup
0x6e32  stloc.s  5
0x6e34  brfalse.s loc_6E40
0x6e36  ldloc.1
0x6e37  ldloc.s  5
0x6e39  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class System.Net.Http.Formatting.MediaTypeFormatterMatch>::Add(var<u1>)
0x6e3e  br.s     loc_6EA4
0x6e40  ldloc.0
0x6e41  brtrue.s loc_6E55
0x6e43  ldarg.0
0x6e44  ldarg.2
0x6e45  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpRequestHeaders [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Headers()
0x6e4a  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpHeaderValueCollection`1<class [System.Net.Http]System.Net.Http.Headers.MediaTypeWithQualityHeaderValue> [System.Net.Http]System.Net.Http.Headers.HttpRequestHeaders::get_Accept()
0x6e4f  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Net.Http]System.Net.Http.Headers.MediaTypeWithQualityHeaderValue> System.Net.Http.Formatting.DefaultContentNegotiator::SortMediaTypeWithQualityHeaderValuesByQFactor(class [mscorlib]System.Collections.Generic.ICollection`1<class [System.Net.Http]System.Net.Http.Headers.MediaTypeWithQualityHeaderValue> headerValues)
0x6e54  stloc.0
0x6e55  ldarg.0
0x6e56  ldloc.0
0x6e57  ldloc.s  4
0x6e59  callvirt instance class System.Net.Http.Formatting.MediaTypeFormatterMatch System.Net.Http.Formatting.DefaultContentNegotiator::MatchAcceptHeader(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Net.Http]System.Net.Http.Headers.MediaTypeWithQualityHeaderValue> sortedAcceptValues, class System.Net.Http.Formatting.MediaTypeFormatter formatter)
0x6e5e  dup
0x6e5f  stloc.s  5
0x6e61  brfalse.s loc_6E6D
0x6e63  ldloc.1
0x6e64  ldloc.s  5
0x6e66  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class System.Net.Http.Formatting.MediaTypeFormatterMatch>::Add(var<u1>)
0x6e6b  br.s     loc_6EA4
0x6e6d  ldarg.0
0x6e6e  ldarg.2
0x6e6f  ldloc.s  4
0x6e71  callvirt instance class System.Net.Http.Formatting.MediaTypeFormatterMatch System.Net.Http.Formatting.DefaultContentNegotiator::MatchRequestMediaType(class [System.Net.Http]System.Net.Http.HttpRequestMessage request, class System.Net.Http.Formatting.MediaTypeFormatter formatter)
0x6e76  dup
0x6e77  stloc.s  5
0x6e79  brfalse.s loc_6E85
0x6e7b  ldloc.1
0x6e7c  ldloc.s  5
0x6e7e  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class System.Net.Http.Formatting.MediaTypeFormatterMatch>::Add(var<u1>)
0x6e83  br.s     loc_6EA4
0x6e85  ldarg.0
0x6e86  ldloc.0
0x6e87  callvirt instance bool System.Net.Http.Formatting.DefaultContentNegotiator::ShouldMatchOnType(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Net.Http]System.Net.Http.Headers.MediaTypeWithQualityHeaderValue> sortedAcceptValues)
0x6e8c  brfalse.s loc_6EA4
0x6e8e  ldarg.0
0x6e8f  ldarg.1
0x6e90  ldloc.s  4
0x6e92  callvirt instance class System.Net.Http.Formatting.MediaTypeFormatterMatch System.Net.Http.Formatting.DefaultContentNegotiator::MatchType(class [mscorlib]System.Type type, class System.Net.Http.Formatting.MediaTypeFormatter formatter)
0x6e97  dup
0x6e98  stloc.s  5
0x6e9a  brfalse.s loc_6EA4
0x6e9c  ldloc.1
0x6e9d  ldloc.s  5
0x6e9f  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class System.Net.Http.Formatting.MediaTypeFormatterMatch>::Add(var<u1>)
0x6ea4  ldloc.3
0x6ea5  ldc.i4.1
0x6ea6  add
0x6ea7  stloc.3
0x6ea8  ldloc.3
0x6ea9  ldloc.2
0x6eaa  ldlen
0x6eab  conv.i4
0x6eac  blt      loc_6E16
0x6eb1  ldloc.1
0x6eb2  ret
```
