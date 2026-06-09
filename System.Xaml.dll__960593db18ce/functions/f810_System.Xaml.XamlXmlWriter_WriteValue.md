# System.Xaml.XamlXmlWriter::WriteValue

- ea: `0xf810`
- end: `0xf858`
- name: `System.Xaml.XamlXmlWriter::WriteValue`
- size: `72`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x8960`
- `0xf350`
- `0xf360`
- `0xf810`
- `0xf910`
- `0x11f20`
- `0x2cdd0`

## string_xrefs

- `0xf835`: `XamlXmlWriterCannotWriteNonstringValue`

## pseudocode

```c

```

## disassembly

```asm
0xf810  ldarg.0
0xf811  call     instance void System.Xaml.XamlXmlWriter::CheckIsDisposed()
0xf816  ldarg.1
0xf817  brtrue.s loc_F82B
0xf819  ldarg.0
0xf81a  call     class System.Xaml.XamlType System.Xaml.XamlLanguage::get_Null()
0xf81f  callvirt instance void System.Xaml.XamlWriter::WriteStartObject(class System.Xaml.XamlType type)
0xf824  ldarg.0
0xf825  callvirt instance void System.Xaml.XamlWriter::WriteEndObject()
0xf82a  ret
0xf82b  ldarg.1
0xf82c  isinst   [mscorlib]System.String
0xf831  stloc.0
0xf832  ldloc.0
0xf833  brtrue.s loc_F84A
0xf835  ldstr    aXamlxmlwriterc// "XamlXmlWriterCannotWriteNonstringValue"
0xf83a  call     string System.Xaml.SR::Get(string id)
0xf83f  ldstr    aValue// "value"
0xf844  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0xf849  throw
0xf84a  ldarg.0
0xf84b  ldfld    class WriterState System.Xaml.XamlXmlWriter::currentState
0xf850  ldarg.0
0xf851  ldloc.0
0xf852  callvirt instance void WriterState::WriteValue(class System.Xaml.XamlXmlWriter writer, string value)
0xf857  ret
```
