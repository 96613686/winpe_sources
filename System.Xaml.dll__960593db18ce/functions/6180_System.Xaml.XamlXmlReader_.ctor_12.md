# System.Xaml.XamlXmlReader::.ctor_12

- ea: `0x6180`
- end: `0x61a5`
- name: `System.Xaml.XamlXmlReader::.ctor_12`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x6180`
- `0x6230`
- `0x6260`
- `0xb470`

## string_xrefs

- `0x6189`: `textReader`

## pseudocode

```c

```

## disassembly

```asm
0x6180  ldarg.0
0x6181  call     instance void System.Xaml.XamlReader::.ctor()
0x6186  ldarg.1
0x6187  brtrue.s loc_6194
0x6189  ldstr    aTextreader// "textReader"
0x618e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x6193  throw
0x6194  ldarg.0
0x6195  ldarg.0
0x6196  ldarg.1
0x6197  ldarg.2
0x6198  call     instance class [System.Xml]System.Xml.XmlReader System.Xaml.XamlXmlReader::CreateXmlReader(class [mscorlib]System.IO.TextReader textReader, class System.Xaml.XamlXmlReaderSettings settings)
0x619d  ldnull
0x619e  ldarg.2
0x619f  call     instance void System.Xaml.XamlXmlReader::Initialize(class [System.Xml]System.Xml.XmlReader givenXmlReader, class System.Xaml.XamlSchemaContext schemaContext, class System.Xaml.XamlXmlReaderSettings settings)
0x61a4  ret
```
