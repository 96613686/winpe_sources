# System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::set_MaxDepth

- ea: `0x5540`
- end: `0x5563`
- name: `System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::set_MaxDepth`
- size: `35`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x54d0`
- `0x5950`
- `0x7840`

## callees

- `0x5540`
- `0xb410`

## pseudocode

```c

```

## disassembly

```asm
0x5540  ldarg.1
0x5541  ldc.i4.1
0x5542  bge.s    loc_555B
0x5544  ldstr    aValue// "value"
0x5549  ldarg.1
0x554a  box      [mscorlib]System.Int32
0x554f  ldc.i4.1
0x5550  box      [mscorlib]System.Int32
0x5555  call     class [mscorlib]System.ArgumentOutOfRangeException System.Web.Http.Error::ArgumentMustBeGreaterThanOrEqualTo(string parameterName, object actualValue, object minValue)
0x555a  throw
0x555b  ldarg.0
0x555c  ldarg.1
0x555d  stfld    int32 System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::_maxDepth
0x5562  ret
```
