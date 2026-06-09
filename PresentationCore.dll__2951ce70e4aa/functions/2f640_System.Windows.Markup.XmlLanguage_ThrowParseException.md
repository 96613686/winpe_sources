# System.Windows.Markup.XmlLanguage::ThrowParseException

- ea: `0x2f640`
- end: `0x2f65f`
- name: `System.Windows.Markup.XmlLanguage::ThrowParseException`
- size: `31`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x2f5b0`
- `0x2f660`

## callees

- `0x146e70`

## string_xrefs

- `0x2f640`: `XmlLangMalformed`

## pseudocode

```c

```

## disassembly

```asm
0x2f640  ldstr    aXmllangmalform// "XmlLangMalformed"
0x2f645  ldc.i4.1
0x2f646  newarr   [mscorlib]System.Object
0x2f64b  dup
0x2f64c  ldc.i4.0
0x2f64d  ldarg.0
0x2f64e  stelem.ref
0x2f64f  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0x2f654  ldstr    aIetflanguageta// "ietfLanguageTag"
0x2f659  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x2f65e  throw
```
