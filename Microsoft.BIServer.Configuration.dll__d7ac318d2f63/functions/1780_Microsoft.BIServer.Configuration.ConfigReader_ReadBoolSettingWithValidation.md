# Microsoft.BIServer.Configuration.ConfigReader::ReadBoolSettingWithValidation

- ea: `0x1780`
- end: `0x17bf`
- name: `Microsoft.BIServer.Configuration.ConfigReader::ReadBoolSettingWithValidation`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1430`

## callees

- `0x1780`
- `0x7840`

## pseudocode

```c

```

## disassembly

```asm
0x1780  ldarg.3
0x1781  stloc.0
0x1782  ldarg.2
0x1783  ldarg.1
0x1784  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x1789  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x178e  brtrue.s loc_1792
0x1790  ldloc.0
0x1791  ret
0x1792  ldarg.2
0x1793  ldarg.1
0x1794  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x1799  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x179e  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XElement::get_Value()
0x17a3  ldloca.s 0
0x17a5  call     bool [mscorlib]System.Boolean::TryParse(string, bool&)
0x17aa  brtrue.s loc_17BD
0x17ac  ldstr    aSetting0HasAnI// "Setting {0} has an invalid value."
0x17b1  ldarg.1
0x17b2  call     string [mscorlib]System.String::Format(string, object)
0x17b7  newobj   instance void InvalidSettingValue::.ctor(string message)
0x17bc  throw
0x17bd  ldloc.0
0x17be  ret
```
