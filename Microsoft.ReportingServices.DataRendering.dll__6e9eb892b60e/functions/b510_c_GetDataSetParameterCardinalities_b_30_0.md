# <>c::<GetDataSetParameterCardinalities>b__30_0

- ea: `0xb510`
- end: `0xb555`
- name: `<>c::<GetDataSetParameterCardinalities>b__30_0`
- size: `69`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xb510`

## string_xrefs

- `0xb518`: `http://schemas.microsoft.com/SQLServer/reporting/reportdesigner`

## pseudocode

```c

```

## disassembly

```asm
0xb510  ldc.i4.0
0xb511  stloc.0
0xb512  ldarg.1
0xb513  ldstr    aIsmultivalued// "IsMultiValued"
0xb518  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/SQLServer/"...
0xb51d  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::Get(string, string)
0xb522  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0xb527  stloc.1
0xb528  ldloc.1
0xb529  brfalse.s loc_B539
0xb52b  ldloc.1
0xb52c  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XElement::get_Value()
0xb531  ldloca.s 0
0xb533  call     bool [mscorlib]System.Boolean::TryParse(string, bool&)
0xb538  pop
0xb539  ldarg.1
0xb53a  ldstr    aName// "Name"
0xb53f  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0xb544  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XAttribute [System.Xml.Linq]System.Xml.Linq.XElement::Attribute(class [System.Xml.Linq]System.Xml.Linq.XName)
0xb549  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XAttribute::get_Value()
0xb54e  ldloc.0
0xb54f  newobj   instance void valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, bool>::.ctor(var<u1>, !!T0)
0xb554  ret
```
