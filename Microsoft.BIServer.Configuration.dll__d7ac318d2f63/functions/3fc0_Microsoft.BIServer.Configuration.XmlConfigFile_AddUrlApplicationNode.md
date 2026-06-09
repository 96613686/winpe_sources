# Microsoft.BIServer.Configuration.XmlConfigFile::AddUrlApplicationNode

- ea: `0x3fc0`
- end: `0x402f`
- name: `Microsoft.BIServer.Configuration.XmlConfigFile::AddUrlApplicationNode`
- size: `111`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4080`

## callees

- `0x3fc0`
- `0x4350`

## pseudocode

```c

```

## disassembly

```asm
0x3fc0  newobj   instance void [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces::.ctor()
0x3fc5  stloc.1
0x3fc6  ldloc.1
0x3fc7  ldsfld   string [mscorlib]System.String::Empty
0x3fcc  ldsfld   string [mscorlib]System.String::Empty
0x3fd1  callvirt instance void [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces::Add(string, string)
0x3fd6  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor()
0x3fdb  stloc.2
0x3fdc  ldloc.2
0x3fdd  newobj   instance void [mscorlib]System.IO.StreamWriter::.ctor(class [mscorlib]System.IO.Stream)
0x3fe2  stloc.3
0x3fe3  ldarg.1
0x3fe4  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3fe9  newobj   instance void [System.Xml]System.Xml.Serialization.XmlSerializer::.ctor(class [mscorlib]System.Type)
0x3fee  ldloc.3
0x3fef  ldarg.1
0x3ff0  ldloc.1
0x3ff1  callvirt instance void [System.Xml]System.Xml.Serialization.XmlSerializer::Serialize(class [mscorlib]System.IO.TextWriter, object, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x3ff6  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_ASCII()
0x3ffb  ldloc.2
0x3ffc  callvirt instance unsigned int8[] [mscorlib]System.IO.MemoryStream::ToArray()
0x4001  callvirt instance string [mscorlib]System.Text.Encoding::GetString(unsigned int8[])
0x4006  call     class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XElement::Parse(string)
0x400b  stloc.0
0x400c  leave.s  loc_4022
0x400e  ldloc.3
0x400f  brfalse.s loc_4017
0x4011  ldloc.3
0x4012  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4017  endfinally
0x4018  ldloc.2
0x4019  brfalse.s loc_4021
0x401b  ldloc.2
0x401c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4021  endfinally
0x4022  ldarg.0
0x4023  call     instance class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.BIServer.Configuration.XmlConfigFile::GetUrlReservations()
0x4028  ldloc.0
0x4029  callvirt instance void [System.Xml.Linq]System.Xml.Linq.XContainer::Add(object)
0x402e  ret
```
