# System.Xaml.XamlServices::Save_2

- ea: `0xcd70`
- end: `0xcdb2`
- name: `System.Xaml.XamlServices::Save_2`
- size: `66`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0xcd70`
- `0xcdc0`

## string_xrefs

- `0xcd73`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0xcd70  ldarg.0
0xcd71  brtrue.s loc_CD7E
0xcd73  ldstr    aWriter// "writer"
0xcd78  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xcd7d  throw
0xcd7e  ldarg.0
0xcd7f  newobj   instance void [System.Xml]System.Xml.XmlWriterSettings::.ctor()
0xcd84  dup
0xcd85  ldc.i4.1
0xcd86  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_Indent(bool)
0xcd8b  dup
0xcd8c  ldc.i4.1
0xcd8d  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_OmitXmlDeclaration(bool)
0xcd92  call     class [System.Xml]System.Xml.XmlWriter [System.Xml]System.Xml.XmlWriter::Create(class [mscorlib]System.IO.TextWriter, class [System.Xml]System.Xml.XmlWriterSettings)
0xcd97  stloc.0
0xcd98  ldloc.0
0xcd99  ldarg.1
0xcd9a  call     void System.Xaml.XamlServices::Save(class [System.Xml]System.Xml.XmlWriter writer, object instance)
0xcd9f  ldloc.0
0xcda0  callvirt instance void [System.Xml]System.Xml.XmlWriter::Flush()
0xcda5  leave.s  loc_CDB1
0xcda7  ldloc.0
0xcda8  brfalse.s loc_CDB0
0xcdaa  ldloc.0
0xcdab  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xcdb0  endfinally
0xcdb1  ret
```
