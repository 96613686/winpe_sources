# System.Xaml.XamlXmlReader::.ctor_11

- ea: `0x6150`
- end: `0x6175`
- name: `System.Xaml.XamlXmlReader::.ctor_11`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x6150`
- `0x6230`
- `0x6260`
- `0xb470`

## string_xrefs

- `0x6159`: `textReader`

## pseudocode

```c

```

## disassembly

```asm
0x6150  ldarg.0
0x6151  call     instance void System.Xaml.XamlReader::.ctor()
0x6156  ldarg.1
0x6157  brtrue.s loc_6164
0x6159  ldstr    aTextreader// "textReader"
0x615e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x6163  throw
0x6164  ldarg.0
0x6165  ldarg.0
0x6166  ldarg.1
0x6167  ldnull
0x6168  call     instance class [System.Xml]System.Xml.XmlReader System.Xaml.XamlXmlReader::CreateXmlReader(class [mscorlib]System.IO.TextReader textReader, class System.Xaml.XamlXmlReaderSettings settings)
0x616d  ldnull
0x616e  ldnull
0x616f  call     instance void System.Xaml.XamlXmlReader::Initialize(class [System.Xml]System.Xml.XmlReader givenXmlReader, class System.Xaml.XamlSchemaContext schemaContext, class System.Xaml.XamlXmlReaderSettings settings)
0x6174  ret
```
