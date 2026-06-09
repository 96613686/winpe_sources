# Microsoft.BIServer.Configuration.ConfigReader::ReadAttribute

- ea: `0x1650`
- end: `0x1683`
- name: `Microsoft.BIServer.Configuration.ConfigReader::ReadAttribute`
- size: `51`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x16f0`
- `0x6ff0`
- `0x7000`
- `0x70b0`

## callees

- `0x1650`
- `0x7880`

## string_xrefs

- `0x166c`: `Required config entry is missing: {0} under {1}.`

## pseudocode

```c

```

## disassembly

```asm
0x1650  ldarg.0
0x1651  ldarg.1
0x1652  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x1657  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XAttribute [System.Xml.Linq]System.Xml.Linq.XElement::Attribute(class [System.Xml.Linq]System.Xml.Linq.XName)
0x165c  stloc.0
0x165d  ldloc.0
0x165e  brfalse.s loc_1667
0x1660  ldloc.0
0x1661  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XAttribute::get_Value()
0x1666  ret
0x1667  ldarg.2
0x1668  brtrue.s loc_166C
0x166a  ldnull
0x166b  ret
0x166c  ldstr    aRequiredConfig// "Required config entry is missing: {0} u"...
0x1671  ldarg.1
0x1672  ldarg.0
0x1673  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XElement::get_Name()
0x1678  call     string [mscorlib]System.String::Format(string, object, object)
0x167d  newobj   instance void MissingConfigFileEntry::.ctor(string message)
0x1682  throw
```
