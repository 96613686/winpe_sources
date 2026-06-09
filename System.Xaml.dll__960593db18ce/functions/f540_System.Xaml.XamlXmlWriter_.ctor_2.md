# System.Xaml.XamlXmlWriter::.ctor_2

- ea: `0xf540`
- end: `0xf589`
- name: `System.Xaml.XamlXmlWriter::.ctor_2`
- size: `73`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0xf530`

## callees

- `0xf4b0`
- `0xf540`
- `0xf5c0`
- `0x101e0`

## string_xrefs

- `0xf549`: `textWriter`

## pseudocode

```c

```

## disassembly

```asm
0xf540  ldarg.0
0xf541  call     instance void System.Xaml.XamlWriter::.ctor()
0xf546  ldarg.1
0xf547  brtrue.s loc_F554
0xf549  ldstr    aTextwriter// "textWriter"
0xf54e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xf553  throw
0xf554  ldarg.3
0xf555  brfalse.s loc_F57A
0xf557  ldarg.3
0xf558  callvirt instance bool System.Xaml.XamlXmlWriterSettings::get_CloseOutput()
0xf55d  brfalse.s loc_F57A
0xf55f  ldarg.0
0xf560  ldarg.1
0xf561  newobj   instance void [System.Xml]System.Xml.XmlWriterSettings::.ctor()
0xf566  dup
0xf567  ldc.i4.1
0xf568  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_CloseOutput(bool)
0xf56d  call     class [System.Xml]System.Xml.XmlWriter [System.Xml]System.Xml.XmlWriter::Create(class [mscorlib]System.IO.TextWriter, class [System.Xml]System.Xml.XmlWriterSettings)
0xf572  ldarg.2
0xf573  ldarg.3
0xf574  call     instance void System.Xaml.XamlXmlWriter::InitializeXamlXmlWriter(class [System.Xml]System.Xml.XmlWriter xmlWriter, class System.Xaml.XamlSchemaContext schemaContext, class System.Xaml.XamlXmlWriterSettings settings)
0xf579  ret
0xf57a  ldarg.0
0xf57b  ldarg.1
0xf57c  call     class [System.Xml]System.Xml.XmlWriter [System.Xml]System.Xml.XmlWriter::Create(class [mscorlib]System.IO.TextWriter)
0xf581  ldarg.2
0xf582  ldarg.3
0xf583  call     instance void System.Xaml.XamlXmlWriter::InitializeXamlXmlWriter(class [System.Xml]System.Xml.XmlWriter xmlWriter, class System.Xaml.XamlSchemaContext schemaContext, class System.Xaml.XamlXmlWriterSettings settings)
0xf588  ret
```
