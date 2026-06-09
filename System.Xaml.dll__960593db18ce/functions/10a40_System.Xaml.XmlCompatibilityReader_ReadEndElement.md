# System.Xaml.XmlCompatibilityReader::ReadEndElement

- ea: `0x10a40`
- end: `0x10af1`
- name: `System.Xaml.XmlCompatibilityReader::ReadEndElement`
- size: `177`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10890`

## callees

- `0x10a40`
- `0x11010`
- `0x11180`
- `0x111d0`
- `0x117a0`
- `0x117e0`
- `0x117f0`
- `0x119a0`
- `0x11d80`
- `0x11f20`
- `0x2edc0`

## pseudocode

```c

```

## disassembly

```asm
0x10a40  ldarg.0
0x10a41  call     instance class [System.Xml]System.Xml.XmlReader System.Xaml.XmlWrappingReader::get_Reader()
0x10a46  callvirt instance int32 [System.Xml]System.Xml.XmlReader::get_Depth()
0x10a4b  stloc.0
0x10a4c  ldarg.0
0x10a4d  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x10a52  stloc.1
0x10a53  ldc.i4.0
0x10a54  stloc.2
0x10a55  ldloc.1
0x10a56  ldarg.0
0x10a57  call     instance string System.Xaml.XmlCompatibilityReader::get_CompatibilityUri()
0x10a5c  bne.un.s loc_10AB9
0x10a5e  ldarg.0
0x10a5f  call     instance class [System.Xml]System.Xml.XmlReader System.Xaml.XmlWrappingReader::get_Reader()
0x10a64  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x10a69  stloc.3
0x10a6a  ldloc.3
0x10a6b  ldarg.0
0x10a6c  call     instance string System.Xaml.XmlCompatibilityReader::get_AlternateContent()
0x10a71  bne.un.s loc_10A96
0x10a73  ldarg.0
0x10a74  call     instance class CompatibilityScope System.Xaml.XmlCompatibilityReader::get_Scope()
0x10a79  callvirt instance bool CompatibilityScope::get_ChoiceSeen()
0x10a7e  brtrue.s loc_10A96
0x10a80  ldarg.0
0x10a81  ldstr    aXcrchoicenotfo// "XCRChoiceNotFound"
0x10a86  call     string System.Xaml.SR::Get(string id)
0x10a8b  ldc.i4.0
0x10a8c  newarr   [mscorlib]System.Object
0x10a91  call     instance void System.Xaml.XmlCompatibilityReader::Error(string message, object[] args)
0x10a96  ldarg.0
0x10a97  ldarg.0
0x10a98  ldfld    int32 System.Xaml.XmlCompatibilityReader::_depthOffset
0x10a9d  ldc.i4.1
0x10a9e  sub
0x10a9f  stfld    int32 System.Xaml.XmlCompatibilityReader::_depthOffset
0x10aa4  ldarg.0
0x10aa5  call     instance void System.Xaml.XmlCompatibilityReader::PopScope()
0x10aaa  ldarg.1
0x10aab  ldarg.0
0x10aac  call     instance class [System.Xml]System.Xml.XmlReader System.Xaml.XmlWrappingReader::get_Reader()
0x10ab1  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x10ab6  stind.i1
0x10ab7  br.s     loc_10AEF
0x10ab9  ldarg.0
0x10aba  ldloc.1
0x10abb  call     instance bool System.Xaml.XmlCompatibilityReader::ShouldIgnoreNamespace(string namespaceName)
0x10ac0  brfalse.s loc_10AE6
0x10ac2  ldarg.0
0x10ac3  ldloc.0
0x10ac4  call     instance void System.Xaml.XmlCompatibilityReader::ScanForEndCompatibility(int32 elementDepth)
0x10ac9  ldarg.0
0x10aca  ldarg.0
0x10acb  ldfld    int32 System.Xaml.XmlCompatibilityReader::_depthOffset
0x10ad0  ldc.i4.1
0x10ad1  sub
0x10ad2  stfld    int32 System.Xaml.XmlCompatibilityReader::_depthOffset
0x10ad7  ldarg.1
0x10ad8  ldarg.0
0x10ad9  call     instance class [System.Xml]System.Xml.XmlReader System.Xaml.XmlWrappingReader::get_Reader()
0x10ade  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x10ae3  stind.i1
0x10ae4  br.s     loc_10AEF
0x10ae6  ldarg.0
0x10ae7  ldloc.0
0x10ae8  call     instance void System.Xaml.XmlCompatibilityReader::ScanForEndCompatibility(int32 elementDepth)
0x10aed  ldc.i4.1
0x10aee  stloc.2
0x10aef  ldloc.2
0x10af0  ret
```
