# System.Xaml.XmlCompatibilityReader::ScanForCompatibility

- ea: `0x110b0`
- end: `0x1117a`
- name: `System.Xaml.XmlCompatibilityReader::ScanForCompatibility`
- size: `202`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10900`
- `0x111f0`
- `0x11280`
- `0x11450`

## callees

- `0x10590`
- `0x11010`
- `0x110b0`
- `0x117a0`
- `0x117e0`
- `0x119a0`
- `0x11d80`
- `0x11f20`
- `0x2eca0`
- `0x2efd0`

## string_xrefs

- `0x11106`: `XCRUnknownCompatAttrib`

## pseudocode

```c

```

## disassembly

```asm
0x110b0  ldarg.0
0x110b1  call     instance class [System.Xml]System.Xml.XmlReader System.Xaml.XmlWrappingReader::get_Reader()
0x110b6  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToFirstAttribute()
0x110bb  stloc.0
0x110bc  ldarg.0
0x110bd  ldc.i4.0
0x110be  stfld    int32 System.Xaml.XmlCompatibilityReader::_ignoredAttributeCount
0x110c3  ldloc.0
0x110c4  brfalse  loc_11179
0x110c9  ldarg.0
0x110ca  ldc.i4.0
0x110cb  stfld    int32 System.Xaml.XmlCompatibilityReader::_attributePosition
0x110d0  ldarg.0
0x110d1  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x110d6  stloc.1
0x110d7  ldarg.0
0x110d8  ldloc.1
0x110d9  call     instance bool System.Xaml.XmlCompatibilityReader::ShouldIgnoreNamespace(string namespaceName)
0x110de  brfalse.s loc_11134
0x110e0  ldloc.1
0x110e1  ldarg.0
0x110e2  call     instance string System.Xaml.XmlCompatibilityReader::get_CompatibilityUri()
0x110e7  bne.un.s loc_11126
0x110e9  ldarg.0
0x110ea  call     instance class [System.Xml]System.Xml.XmlReader System.Xaml.XmlWrappingReader::get_Reader()
0x110ef  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x110f4  stloc.2
0x110f5  ldarg.0
0x110f6  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class System.Xaml.HandleAttributeCallback> System.Xaml.XmlCompatibilityReader::_attributeHandler
0x110fb  ldloc.2
0x110fc  ldloca.s 3
0x110fe  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class System.Xaml.HandleAttributeCallback>::TryGetValue(var<u1>, !!T0)
0x11103  brtrue.s loc_1111F
0x11105  ldarg.0
0x11106  ldstr    aXcrunknowncomp_0// "XCRUnknownCompatAttrib"
0x1110b  call     string System.Xaml.SR::Get(string id)
0x11110  ldc.i4.1
0x11111  newarr   [mscorlib]System.Object
0x11116  dup
0x11117  ldc.i4.0
0x11118  ldloc.2
0x11119  stelem.ref
0x1111a  call     instance void System.Xaml.XmlCompatibilityReader::Error(string message, object[] args)
0x1111f  ldloc.3
0x11120  ldarg.1
0x11121  callvirt instance void System.Xaml.HandleAttributeCallback::Invoke(int32 elementDepth)
0x11126  ldarg.0
0x11127  ldarg.0
0x11128  ldfld    int32 System.Xaml.XmlCompatibilityReader::_ignoredAttributeCount
0x1112d  ldc.i4.1
0x1112e  add
0x1112f  stfld    int32 System.Xaml.XmlCompatibilityReader::_ignoredAttributeCount
0x11134  ldarg.0
0x11135  call     instance class [System.Xml]System.Xml.XmlReader System.Xaml.XmlWrappingReader::get_Reader()
0x1113a  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToNextAttribute()
0x1113f  stloc.0
0x11140  ldarg.0
0x11141  ldarg.0
0x11142  ldfld    int32 System.Xaml.XmlCompatibilityReader::_attributePosition
0x11147  ldc.i4.1
0x11148  add
0x11149  stfld    int32 System.Xaml.XmlCompatibilityReader::_attributePosition
0x1114e  ldloc.0
0x1114f  brtrue   loc_110D0
0x11154  ldarg.0
0x11155  call     instance class CompatibilityScope System.Xaml.XmlCompatibilityReader::get_Scope()
0x1115a  callvirt instance int32 CompatibilityScope::get_Depth()
0x1115f  ldarg.1
0x11160  bne.un.s loc_1116D
0x11162  ldarg.0
0x11163  call     instance class CompatibilityScope System.Xaml.XmlCompatibilityReader::get_Scope()
0x11168  callvirt instance void CompatibilityScope::Verify()
0x1116d  ldarg.0
0x1116e  call     instance class [System.Xml]System.Xml.XmlReader System.Xaml.XmlWrappingReader::get_Reader()
0x11173  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToElement()
0x11178  pop
0x11179  ret
```
