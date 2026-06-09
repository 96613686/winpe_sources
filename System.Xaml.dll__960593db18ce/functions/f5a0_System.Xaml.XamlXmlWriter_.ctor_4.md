# System.Xaml.XamlXmlWriter::.ctor_4

- ea: `0xf5a0`
- end: `0xf5be`
- name: `System.Xaml.XamlXmlWriter::.ctor_4`
- size: `30`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0xf590`

## callees

- `0xf4b0`
- `0xf5a0`
- `0xf5c0`

## string_xrefs

- `0xf5a9`: `xmlWriter`

## pseudocode

```c

```

## disassembly

```asm
0xf5a0  ldarg.0
0xf5a1  call     instance void System.Xaml.XamlWriter::.ctor()
0xf5a6  ldarg.1
0xf5a7  brtrue.s loc_F5B4
0xf5a9  ldstr    aXmlwriter// "xmlWriter"
0xf5ae  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xf5b3  throw
0xf5b4  ldarg.0
0xf5b5  ldarg.1
0xf5b6  ldarg.2
0xf5b7  ldarg.3
0xf5b8  call     instance void System.Xaml.XamlXmlWriter::InitializeXamlXmlWriter(class [System.Xml]System.Xml.XmlWriter xmlWriter, class System.Xaml.XamlSchemaContext schemaContext, class System.Xaml.XamlXmlWriterSettings settings)
0xf5bd  ret
```
