# Microsoft.BIServer.Configuration.ConfigReader::ReadString_0

- ea: `0x1610`
- end: `0x1643`
- name: `Microsoft.BIServer.Configuration.ConfigReader::ReadString_0`
- size: `51`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x15d0`
- `0x1d70`
- `0x6fc0`

## callees

- `0x1610`
- `0x7880`

## string_xrefs

- `0x162c`: `Required config entry is missing: {0} under {1}.`

## pseudocode

```c

```

## disassembly

```asm
0x1610  ldarg.0
0x1611  ldarg.1
0x1612  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x1617  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x161c  stloc.0
0x161d  ldloc.0
0x161e  brfalse.s loc_1627
0x1620  ldloc.0
0x1621  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XElement::get_Value()
0x1626  ret
0x1627  ldarg.2
0x1628  brtrue.s loc_162C
0x162a  ldnull
0x162b  ret
0x162c  ldstr    aRequiredConfig// "Required config entry is missing: {0} u"...
0x1631  ldarg.1
0x1632  ldarg.0
0x1633  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XElement::get_Name()
0x1638  call     string [mscorlib]System.String::Format(string, object, object)
0x163d  newobj   instance void MissingConfigFileEntry::.ctor(string message)
0x1642  throw
```
