# System.Xaml.XamlXmlReader::.ctor_1

- ea: `0x5ed0`
- end: `0x5efc`
- name: `System.Xaml.XamlXmlReader::.ctor_1`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x5ed0`
- `0x6260`
- `0xb470`

## string_xrefs

- `0x5ee7`: `xmlReader`

## pseudocode

```c

```

## disassembly

```asm
0x5ed0  ldarg.0
0x5ed1  call     instance void System.Xaml.XamlReader::.ctor()
0x5ed6  ldarg.2
0x5ed7  brtrue.s loc_5EE4
0x5ed9  ldstr    aSchemacontext// "schemaContext"
0x5ede  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x5ee3  throw
0x5ee4  ldarg.1
0x5ee5  brtrue.s loc_5EF2
0x5ee7  ldstr    aXmlreader// "xmlReader"
0x5eec  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x5ef1  throw
0x5ef2  ldarg.0
0x5ef3  ldarg.1
0x5ef4  ldarg.2
0x5ef5  ldnull
0x5ef6  call     instance void System.Xaml.XamlXmlReader::Initialize(class [System.Xml]System.Xml.XmlReader givenXmlReader, class System.Xaml.XamlSchemaContext schemaContext, class System.Xaml.XamlXmlReaderSettings settings)
0x5efb  ret
```
