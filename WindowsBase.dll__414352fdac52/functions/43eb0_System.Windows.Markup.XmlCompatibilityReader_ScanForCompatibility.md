# System.Windows.Markup.XmlCompatibilityReader::ScanForCompatibility

- ea: `0x43eb0`
- end: `0x43f7a`
- name: `System.Windows.Markup.XmlCompatibilityReader::ScanForCompatibility`
- size: `202`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x43700`
- `0x43ff0`
- `0x44080`
- `0x44250`

## callees

- `0x2c100`
- `0x43390`
- `0x43e10`
- `0x43eb0`
- `0x445a0`
- `0x445e0`
- `0x447a0`
- `0x44b80`
- `0x59680`
- `0x599b0`

## string_xrefs

- `0x43f06`: `XCRUnknownCompatAttrib`

## pseudocode

```c

```

## disassembly

```asm
0x43eb0  ldarg.0
0x43eb1  call     instance class [System.Xml]System.Xml.XmlReader System.Windows.Markup.XmlWrappingReader::get_Reader()
0x43eb6  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToFirstAttribute()
0x43ebb  stloc.0
0x43ebc  ldarg.0
0x43ebd  ldc.i4.0
0x43ebe  stfld    int32 System.Windows.Markup.XmlCompatibilityReader::_ignoredAttributeCount
0x43ec3  ldloc.0
0x43ec4  brfalse  loc_43F79
0x43ec9  ldarg.0
0x43eca  ldc.i4.0
0x43ecb  stfld    int32 System.Windows.Markup.XmlCompatibilityReader::_attributePosition
0x43ed0  ldarg.0
0x43ed1  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x43ed6  stloc.1
0x43ed7  ldarg.0
0x43ed8  ldloc.1
0x43ed9  call     instance bool System.Windows.Markup.XmlCompatibilityReader::ShouldIgnoreNamespace(string namespaceName)
0x43ede  brfalse.s loc_43F34
0x43ee0  ldloc.1
0x43ee1  ldarg.0
0x43ee2  call     instance string System.Windows.Markup.XmlCompatibilityReader::get_CompatibilityUri()
0x43ee7  bne.un.s loc_43F26
0x43ee9  ldarg.0
0x43eea  call     instance class [System.Xml]System.Xml.XmlReader System.Windows.Markup.XmlWrappingReader::get_Reader()
0x43eef  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x43ef4  stloc.2
0x43ef5  ldarg.0
0x43ef6  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class System.Windows.Markup.HandleAttributeCallback> System.Windows.Markup.XmlCompatibilityReader::_attributeHandler
0x43efb  ldloc.2
0x43efc  ldloca.s 3
0x43efe  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class System.Windows.Markup.HandleAttributeCallback>::TryGetValue(var<u1>, !!T0)
0x43f03  brtrue.s loc_43F1F
0x43f05  ldarg.0
0x43f06  ldstr    aXcrunknowncomp_0// "XCRUnknownCompatAttrib"
0x43f0b  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x43f10  ldc.i4.1
0x43f11  newarr   [mscorlib]System.Object
0x43f16  dup
0x43f17  ldc.i4.0
0x43f18  ldloc.2
0x43f19  stelem.ref
0x43f1a  call     instance void System.Windows.Markup.XmlCompatibilityReader::Error(string message, object[] args)
0x43f1f  ldloc.3
0x43f20  ldarg.1
0x43f21  callvirt instance void System.Windows.Markup.HandleAttributeCallback::Invoke(int32 elementDepth)
0x43f26  ldarg.0
0x43f27  ldarg.0
0x43f28  ldfld    int32 System.Windows.Markup.XmlCompatibilityReader::_ignoredAttributeCount
0x43f2d  ldc.i4.1
0x43f2e  add
0x43f2f  stfld    int32 System.Windows.Markup.XmlCompatibilityReader::_ignoredAttributeCount
0x43f34  ldarg.0
0x43f35  call     instance class [System.Xml]System.Xml.XmlReader System.Windows.Markup.XmlWrappingReader::get_Reader()
0x43f3a  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToNextAttribute()
0x43f3f  stloc.0
0x43f40  ldarg.0
0x43f41  ldarg.0
0x43f42  ldfld    int32 System.Windows.Markup.XmlCompatibilityReader::_attributePosition
0x43f47  ldc.i4.1
0x43f48  add
0x43f49  stfld    int32 System.Windows.Markup.XmlCompatibilityReader::_attributePosition
0x43f4e  ldloc.0
0x43f4f  brtrue   loc_43ED0
0x43f54  ldarg.0
0x43f55  call     instance class CompatibilityScope System.Windows.Markup.XmlCompatibilityReader::get_Scope()
0x43f5a  callvirt instance int32 CompatibilityScope::get_Depth()
0x43f5f  ldarg.1
0x43f60  bne.un.s loc_43F6D
0x43f62  ldarg.0
0x43f63  call     instance class CompatibilityScope System.Windows.Markup.XmlCompatibilityReader::get_Scope()
0x43f68  callvirt instance void CompatibilityScope::Verify()
0x43f6d  ldarg.0
0x43f6e  call     instance class [System.Xml]System.Xml.XmlReader System.Windows.Markup.XmlWrappingReader::get_Reader()
0x43f73  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToElement()
0x43f78  pop
0x43f79  ret
```
