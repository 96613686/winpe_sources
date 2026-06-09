# System.Net.Http.Formatting.FormUrlEncodedMediaTypeFormatter::set_ReadBufferSize

- ea: `0x7550`
- end: `0x757b`
- name: `System.Net.Http.Formatting.FormUrlEncodedMediaTypeFormatter::set_ReadBufferSize`
- size: `43`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x7490`

## callees

- `0x7550`
- `0xb410`

## pseudocode

```c

```

## disassembly

```asm
0x7550  ldarg.1
0x7551  ldc.i4   0x100
0x7556  bge.s    loc_7573
0x7558  ldstr    aValue// "value"
0x755d  ldarg.1
0x755e  box      [mscorlib]System.Int32
0x7563  ldc.i4   0x100
0x7568  box      [mscorlib]System.Int32
0x756d  call     class [mscorlib]System.ArgumentOutOfRangeException System.Web.Http.Error::ArgumentMustBeGreaterThanOrEqualTo(string parameterName, object actualValue, object minValue)
0x7572  throw
0x7573  ldarg.0
0x7574  ldarg.1
0x7575  stfld    int32 System.Net.Http.Formatting.FormUrlEncodedMediaTypeFormatter::_readBufferSize
0x757a  ret
```
