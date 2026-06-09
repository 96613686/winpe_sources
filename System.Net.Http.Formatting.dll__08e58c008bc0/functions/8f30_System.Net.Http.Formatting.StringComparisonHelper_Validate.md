# System.Net.Http.Formatting.StringComparisonHelper::Validate

- ea: `0x8f30`
- end: `0x8f4b`
- name: `System.Net.Http.Formatting.StringComparisonHelper::Validate`
- size: `27`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x8db0`

## callees

- `0x8f10`
- `0x8f30`
- `0xb4a0`

## pseudocode

```c

```

## disassembly

```asm
0x8f30  ldarg.0
0x8f31  call     bool System.Net.Http.Formatting.StringComparisonHelper::IsDefined(valuetype [mscorlib]System.StringComparison value)
0x8f36  brtrue.s loc_8F4A
0x8f38  ldarg.1
0x8f39  ldarg.0
0x8f3a  ldtoken  [mscorlib]System.StringComparison
0x8f3f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x8f44  call     class [mscorlib]System.ArgumentException System.Web.Http.Error::InvalidEnumArgument(string parameterName, int32 invalidValue, class [mscorlib]System.Type enumClass)
0x8f49  throw
0x8f4a  ret
```
