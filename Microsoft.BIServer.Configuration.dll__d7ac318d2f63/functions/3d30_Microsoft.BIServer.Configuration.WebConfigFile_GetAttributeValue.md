# Microsoft.BIServer.Configuration.WebConfigFile::GetAttributeValue

- ea: `0x3d30`
- end: `0x3d56`
- name: `Microsoft.BIServer.Configuration.WebConfigFile::GetAttributeValue`
- size: `38`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x3c40`
- `0x3c60`
- `0x3c80`
- `0x3ca0`
- `0x3cd0`
- `0x3d00`

## callees

- `0x3d30`

## pseudocode

```c

```

## disassembly

```asm
0x3d30  ldarg.1
0x3d31  brtrue.s loc_3D39
0x3d33  ldsfld   string [mscorlib]System.String::Empty
0x3d38  ret
0x3d39  ldarg.1
0x3d3a  ldarg.2
0x3d3b  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x3d40  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XAttribute [System.Xml.Linq]System.Xml.Linq.XElement::Attribute(class [System.Xml.Linq]System.Xml.Linq.XName)
0x3d45  stloc.0
0x3d46  ldloc.0
0x3d47  brfalse.s loc_3D50
0x3d49  ldloc.0
0x3d4a  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XAttribute::get_Value()
0x3d4f  ret
0x3d50  ldsfld   string [mscorlib]System.String::Empty
0x3d55  ret
```
