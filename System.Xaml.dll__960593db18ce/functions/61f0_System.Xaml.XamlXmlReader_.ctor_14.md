# System.Xaml.XamlXmlReader::.ctor_14

- ea: `0x61f0`
- end: `0x6223`
- name: `System.Xaml.XamlXmlReader::.ctor_14`
- size: `51`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x61f0`
- `0x6230`
- `0x6260`
- `0xb470`

## string_xrefs

- `0x61f9`: `textReader`

## pseudocode

```c

```

## disassembly

```asm
0x61f0  ldarg.0
0x61f1  call     instance void System.Xaml.XamlReader::.ctor()
0x61f6  ldarg.1
0x61f7  brtrue.s loc_6204
0x61f9  ldstr    aTextreader// "textReader"
0x61fe  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x6203  throw
0x6204  ldarg.2
0x6205  brtrue.s loc_6212
0x6207  ldstr    aSchemacontext// "schemaContext"
0x620c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x6211  throw
0x6212  ldarg.0
0x6213  ldarg.0
0x6214  ldarg.1
0x6215  ldarg.3
0x6216  call     instance class [System.Xml]System.Xml.XmlReader System.Xaml.XamlXmlReader::CreateXmlReader(class [mscorlib]System.IO.TextReader textReader, class System.Xaml.XamlXmlReaderSettings settings)
0x621b  ldarg.2
0x621c  ldarg.3
0x621d  call     instance void System.Xaml.XamlXmlReader::Initialize(class [System.Xml]System.Xml.XmlReader givenXmlReader, class System.Xaml.XamlSchemaContext schemaContext, class System.Xaml.XamlXmlReaderSettings settings)
0x6222  ret
```
