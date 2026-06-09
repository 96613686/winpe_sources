# System.Net.Http.Formatting.RequestHeaderMapping::Initialize

- ea: `0x8db0`
- end: `0x8dff`
- name: `System.Net.Http.Formatting.RequestHeaderMapping::Initialize`
- size: `79`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x8c40`
- `0x8c60`

## callees

- `0x8c90`
- `0x8cb0`
- `0x8cd0`
- `0x8cf0`
- `0x8db0`
- `0x8f30`
- `0xb3c0`

## string_xrefs

- `0x8dd7`: `valueComparison`

## pseudocode

```c

```

## disassembly

```asm
0x8db0  ldarg.1
0x8db1  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x8db6  brfalse.s loc_8DC3
0x8db8  ldstr    aHeadername// "headerName"
0x8dbd  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x8dc2  throw
0x8dc3  ldarg.2
0x8dc4  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x8dc9  brfalse.s loc_8DD6
0x8dcb  ldstr    aHeadervalue// "headerValue"
0x8dd0  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x8dd5  throw
0x8dd6  ldarg.3
0x8dd7  ldstr    aValuecompariso// "valueComparison"
0x8ddc  call     void System.Net.Http.Formatting.StringComparisonHelper::Validate(valuetype [mscorlib]System.StringComparison value, string parameterName)
0x8de1  ldarg.0
0x8de2  ldarg.1
0x8de3  call     instance void System.Net.Http.Formatting.RequestHeaderMapping::set_HeaderName(string value)
0x8de8  ldarg.0
0x8de9  ldarg.2
0x8dea  call     instance void System.Net.Http.Formatting.RequestHeaderMapping::set_HeaderValue(string value)
0x8def  ldarg.0
0x8df0  ldarg.3
0x8df1  call     instance void System.Net.Http.Formatting.RequestHeaderMapping::set_HeaderValueComparison(valuetype [mscorlib]System.StringComparison value)
0x8df6  ldarg.0
0x8df7  ldarg.s  4
0x8df9  call     instance void System.Net.Http.Formatting.RequestHeaderMapping::set_IsValueSubstring(bool value)
0x8dfe  ret
```
