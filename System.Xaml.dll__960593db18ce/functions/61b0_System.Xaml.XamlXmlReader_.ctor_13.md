# System.Xaml.XamlXmlReader::.ctor_13

- ea: `0x61b0`
- end: `0x61e3`
- name: `System.Xaml.XamlXmlReader::.ctor_13`
- size: `51`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x61b0`
- `0x6230`
- `0x6260`
- `0xb470`

## string_xrefs

- `0x61b9`: `textReader`

## pseudocode

```c

```

## disassembly

```asm
0x61b0  ldarg.0
0x61b1  call     instance void System.Xaml.XamlReader::.ctor()
0x61b6  ldarg.1
0x61b7  brtrue.s loc_61C4
0x61b9  ldstr    aTextreader// "textReader"
0x61be  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x61c3  throw
0x61c4  ldarg.2
0x61c5  brtrue.s loc_61D2
0x61c7  ldstr    aSchemacontext// "schemaContext"
0x61cc  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x61d1  throw
0x61d2  ldarg.0
0x61d3  ldarg.0
0x61d4  ldarg.1
0x61d5  ldnull
0x61d6  call     instance class [System.Xml]System.Xml.XmlReader System.Xaml.XamlXmlReader::CreateXmlReader(class [mscorlib]System.IO.TextReader textReader, class System.Xaml.XamlXmlReaderSettings settings)
0x61db  ldarg.2
0x61dc  ldnull
0x61dd  call     instance void System.Xaml.XamlXmlReader::Initialize(class [System.Xml]System.Xml.XmlReader givenXmlReader, class System.Xaml.XamlSchemaContext schemaContext, class System.Xaml.XamlXmlReaderSettings settings)
0x61e2  ret
```
