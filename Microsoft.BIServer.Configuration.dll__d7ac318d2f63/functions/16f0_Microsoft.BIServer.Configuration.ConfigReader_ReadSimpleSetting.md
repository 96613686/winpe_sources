# Microsoft.BIServer.Configuration.ConfigReader::ReadSimpleSetting

- ea: `0x16f0`
- end: `0x1736`
- name: `Microsoft.BIServer.Configuration.ConfigReader::ReadSimpleSetting`
- size: `70`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x17c0`

## callees

- `0x1650`
- `0x16f0`
- `0x70a0`

## pseudocode

```c

```

## disassembly

```asm
0x16f0  newobj   instance void <>c__DisplayClass70_0::.ctor()
0x16f5  stloc.0
0x16f6  ldloc.0
0x16f7  ldarg.1
0x16f8  stfld    string <>c__DisplayClass70_0::key
0x16fd  ldarg.0
0x16fe  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.BIServer.Configuration.ConfigReader::_rootElement
0x1703  ldstr    aAdd// "Add"
0x1708  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x170d  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml.Linq]System.Xml.Linq.XElement> [System.Xml.Linq]System.Xml.Linq.XContainer::Descendants(class [System.Xml.Linq]System.Xml.Linq.XName)
0x1712  ldloc.0
0x1713  ldftn    instance bool <>c__DisplayClass70_0::<ReadSimpleSetting>b__0(class [System.Xml.Linq]System.Xml.Linq.XElement s)
0x1719  newobj   instance void class [mscorlib]System.Func`2<class [System.Xml.Linq]System.Xml.Linq.XElement, bool>::.ctor(object, native int)
0x171e  call     T0x2B000019
0x1723  stloc.1
0x1724  ldloc.1
0x1725  brtrue.s loc_1729
0x1727  ldnull
0x1728  ret
0x1729  ldloc.1
0x172a  ldstr    aValue_0// "Value"
0x172f  ldc.i4.1
0x1730  call     string Microsoft.BIServer.Configuration.ConfigReader::ReadAttribute(class [System.Xml.Linq]System.Xml.Linq.XElement element, string attributeName, [opt] bool attributeRequired)
0x1735  ret
```
