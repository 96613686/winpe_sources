# System.Xaml.XamlXmlReader::.ctor

- ea: `0x5e90`
- end: `0x5eae`
- name: `System.Xaml.XamlXmlReader::.ctor`
- size: `30`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0xca90`
- `0xcad0`
- `0xcb10`
- `0xcb50`
- `0xcb90`

## callees

- `0x5e90`
- `0x6260`
- `0xb470`

## string_xrefs

- `0x5e99`: `xmlReader`

## pseudocode

```c

```

## disassembly

```asm
0x5e90  ldarg.0
0x5e91  call     instance void System.Xaml.XamlReader::.ctor()
0x5e96  ldarg.1
0x5e97  brtrue.s loc_5EA4
0x5e99  ldstr    aXmlreader// "xmlReader"
0x5e9e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x5ea3  throw
0x5ea4  ldarg.0
0x5ea5  ldarg.1
0x5ea6  ldnull
0x5ea7  ldnull
0x5ea8  call     instance void System.Xaml.XamlXmlReader::Initialize(class [System.Xml]System.Xml.XmlReader givenXmlReader, class System.Xaml.XamlSchemaContext schemaContext, class System.Xaml.XamlXmlReaderSettings settings)
0x5ead  ret
```
