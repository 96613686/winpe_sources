# System.Xaml.XamlXmlReader::.ctor_2

- ea: `0x5f00`
- end: `0x5f2c`
- name: `System.Xaml.XamlXmlReader::.ctor_2`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x5f00`
- `0x6260`
- `0xb470`

## string_xrefs

- `0x5f17`: `xmlReader`

## pseudocode

```c

```

## disassembly

```asm
0x5f00  ldarg.0
0x5f01  call     instance void System.Xaml.XamlReader::.ctor()
0x5f06  ldarg.2
0x5f07  brtrue.s loc_5F14
0x5f09  ldstr    aSchemacontext// "schemaContext"
0x5f0e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x5f13  throw
0x5f14  ldarg.1
0x5f15  brtrue.s loc_5F22
0x5f17  ldstr    aXmlreader// "xmlReader"
0x5f1c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x5f21  throw
0x5f22  ldarg.0
0x5f23  ldarg.1
0x5f24  ldarg.2
0x5f25  ldarg.3
0x5f26  call     instance void System.Xaml.XamlXmlReader::Initialize(class [System.Xml]System.Xml.XmlReader givenXmlReader, class System.Xaml.XamlSchemaContext schemaContext, class System.Xaml.XamlXmlReaderSettings settings)
0x5f2b  ret
```
