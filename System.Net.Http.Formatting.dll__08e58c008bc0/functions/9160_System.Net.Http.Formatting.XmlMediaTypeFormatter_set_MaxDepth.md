# System.Net.Http.Formatting.XmlMediaTypeFormatter::set_MaxDepth

- ea: `0x9160`
- end: `0x9188`
- name: `System.Net.Http.Formatting.XmlMediaTypeFormatter::set_MaxDepth`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x9090`

## callees

- `0x9160`
- `0xb410`

## pseudocode

```c

```

## disassembly

```asm
0x9160  ldarg.1
0x9161  ldc.i4.1
0x9162  bge.s    loc_917B
0x9164  ldstr    aValue// "value"
0x9169  ldarg.1
0x916a  box      [mscorlib]System.Int32
0x916f  ldc.i4.1
0x9170  box      [mscorlib]System.Int32
0x9175  call     class [mscorlib]System.ArgumentOutOfRangeException System.Web.Http.Error::ArgumentMustBeGreaterThanOrEqualTo(string parameterName, object actualValue, object minValue)
0x917a  throw
0x917b  ldarg.0
0x917c  ldfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas System.Net.Http.Formatting.XmlMediaTypeFormatter::_readerQuotas
0x9181  ldarg.1
0x9182  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas::set_MaxDepth(int32)
0x9187  ret
```
