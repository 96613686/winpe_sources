# System.Xaml.XamlXmlReader::.ctor_0

- ea: `0x5eb0`
- end: `0x5ece`
- name: `System.Xaml.XamlXmlReader::.ctor_0`
- size: `30`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x5eb0`
- `0x6260`
- `0xb470`

## string_xrefs

- `0x5eb9`: `xmlReader`

## pseudocode

```c

```

## disassembly

```asm
0x5eb0  ldarg.0
0x5eb1  call     instance void System.Xaml.XamlReader::.ctor()
0x5eb6  ldarg.1
0x5eb7  brtrue.s loc_5EC4
0x5eb9  ldstr    aXmlreader// "xmlReader"
0x5ebe  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x5ec3  throw
0x5ec4  ldarg.0
0x5ec5  ldarg.1
0x5ec6  ldnull
0x5ec7  ldarg.2
0x5ec8  call     instance void System.Xaml.XamlXmlReader::Initialize(class [System.Xml]System.Xml.XmlReader givenXmlReader, class System.Xaml.XamlSchemaContext schemaContext, class System.Xaml.XamlXmlReaderSettings settings)
0x5ecd  ret
```
