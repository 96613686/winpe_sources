# System.Xaml.XmlCompatibilityReader::ReadStartElement

- ea: `0x10900`
- end: `0x10a3c`
- name: `System.Xaml.XmlCompatibilityReader::ReadStartElement`
- size: `316`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10890`

## callees

- `0x10540`
- `0x10900`
- `0x11010`
- `0x110b0`
- `0x11180`
- `0x117a0`
- `0x117e0`
- `0x119a0`
- `0x11d80`
- `0x11f20`
- `0x2eca0`
- `0x2ed10`
- `0x2ed50`
- `0x2ee70`

## string_xrefs

- `0x10951`: `XCRUnknownCompatElement`

## pseudocode

```c

```

## disassembly

```asm
0x10900  ldarg.0
0x10901  call     instance class [System.Xml]System.Xml.XmlReader System.Xaml.XmlWrappingReader::get_Reader()
0x10906  callvirt instance int32 [System.Xml]System.Xml.XmlReader::get_Depth()
0x1090b  stloc.0
0x1090c  ldarg.0
0x1090d  ldfld    int32 System.Xaml.XmlCompatibilityReader::_depthOffset
0x10912  stloc.1
0x10913  ldarg.0
0x10914  call     instance class [System.Xml]System.Xml.XmlReader System.Xaml.XmlWrappingReader::get_Reader()
0x10919  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x1091e  stloc.2
0x1091f  ldarg.0
0x10920  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x10925  stloc.3
0x10926  ldc.i4.0
0x10927  stloc.s  4
0x10929  ldloc.3
0x1092a  ldarg.0
0x1092b  call     instance string System.Xaml.XmlCompatibilityReader::get_CompatibilityUri()
0x10930  bne.un.s loc_10979
0x10932  ldarg.0
0x10933  call     instance class [System.Xml]System.Xml.XmlReader System.Xaml.XmlWrappingReader::get_Reader()
0x10938  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x1093d  stloc.s  5
0x1093f  ldarg.0
0x10940  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class System.Xaml.HandleElementCallback> System.Xaml.XmlCompatibilityReader::_elementHandler
0x10945  ldloc.s  5
0x10947  ldloca.s 6
0x10949  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class System.Xaml.HandleElementCallback>::TryGetValue(var<u1>, !!T0)
0x1094e  brtrue.s loc_1096B
0x10950  ldarg.0
0x10951  ldstr    aXcrunknowncomp// "XCRUnknownCompatElement"
0x10956  call     string System.Xaml.SR::Get(string id)
0x1095b  ldc.i4.1
0x1095c  newarr   [mscorlib]System.Object
0x10961  dup
0x10962  ldc.i4.0
0x10963  ldloc.s  5
0x10965  stelem.ref
0x10966  call     instance void System.Xaml.XmlCompatibilityReader::Error(string message, object[] args)
0x1096b  ldloc.s  6
0x1096d  ldloc.0
0x1096e  ldarg.1
0x1096f  callvirt instance void System.Xaml.HandleElementCallback::Invoke(int32 elementDepth, bool& more)
0x10974  br       loc_10A21
0x10979  ldarg.0
0x1097a  ldloc.0
0x1097b  call     instance void System.Xaml.XmlCompatibilityReader::ScanForCompatibility(int32 elementDepth)
0x10980  ldarg.0
0x10981  ldloc.3
0x10982  call     instance bool System.Xaml.XmlCompatibilityReader::ShouldIgnoreNamespace(string namespaceName)
0x10987  brfalse.s loc_109ED
0x10989  ldarg.0
0x1098a  call     instance class CompatibilityScope System.Xaml.XmlCompatibilityReader::get_Scope()
0x1098f  ldloc.3
0x10990  ldarg.0
0x10991  call     instance class [System.Xml]System.Xml.XmlReader System.Xaml.XmlWrappingReader::get_Reader()
0x10996  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x1099b  callvirt instance bool CompatibilityScope::ShouldProcessContent(string namespaceName, string elementName)
0x109a0  brfalse.s loc_109D9
0x109a2  ldarg.0
0x109a3  call     instance class CompatibilityScope System.Xaml.XmlCompatibilityReader::get_Scope()
0x109a8  callvirt instance int32 CompatibilityScope::get_Depth()
0x109ad  ldloc.0
0x109ae  bne.un.s loc_109BC
0x109b0  ldarg.0
0x109b1  call     instance class CompatibilityScope System.Xaml.XmlCompatibilityReader::get_Scope()
0x109b6  ldc.i4.1
0x109b7  callvirt instance void CompatibilityScope::set_InProcessContent(bool value)
0x109bc  ldarg.0
0x109bd  ldarg.0
0x109be  ldfld    int32 System.Xaml.XmlCompatibilityReader::_depthOffset
0x109c3  ldc.i4.1
0x109c4  add
0x109c5  stfld    int32 System.Xaml.XmlCompatibilityReader::_depthOffset
0x109ca  ldarg.1
0x109cb  ldarg.0
0x109cc  call     instance class [System.Xml]System.Xml.XmlReader System.Xaml.XmlWrappingReader::get_Reader()
0x109d1  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x109d6  stind.i1
0x109d7  br.s     loc_10A21
0x109d9  ldarg.0
0x109da  ldloc.0
0x109db  call     instance void System.Xaml.XmlCompatibilityReader::ScanForEndCompatibility(int32 elementDepth)
0x109e0  ldarg.0
0x109e1  call     instance class [System.Xml]System.Xml.XmlReader System.Xaml.XmlWrappingReader::get_Reader()
0x109e6  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0x109eb  br.s     loc_10A21
0x109ed  ldarg.0
0x109ee  call     instance class CompatibilityScope System.Xaml.XmlCompatibilityReader::get_Scope()
0x109f3  callvirt instance bool CompatibilityScope::get_InAlternateContent()
0x109f8  brfalse.s loc_10A1E
0x109fa  ldarg.0
0x109fb  ldstr    aXcrinvalidacch// "XCRInvalidACChild"
0x10a00  call     string System.Xaml.SR::Get(string id)
0x10a05  ldc.i4.1
0x10a06  newarr   [mscorlib]System.Object
0x10a0b  dup
0x10a0c  ldc.i4.0
0x10a0d  ldarg.0
0x10a0e  call     instance class [System.Xml]System.Xml.XmlReader System.Xaml.XmlWrappingReader::get_Reader()
0x10a13  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x10a18  stelem.ref
0x10a19  call     instance void System.Xaml.XmlCompatibilityReader::Error(string message, object[] args)
0x10a1e  ldc.i4.1
0x10a1f  stloc.s  4
0x10a21  ldloc.2
0x10a22  brfalse.s loc_10A39
0x10a24  ldarg.0
0x10a25  ldc.i4.1
0x10a26  stfld    bool System.Xaml.XmlCompatibilityReader::isPreviousElementEmpty
0x10a2b  ldarg.0
0x10a2c  ldloc.0
0x10a2d  stfld    int32 System.Xaml.XmlCompatibilityReader::previousElementDepth
0x10a32  ldarg.0
0x10a33  ldloc.1
0x10a34  stfld    int32 System.Xaml.XmlCompatibilityReader::_depthOffset
0x10a39  ldloc.s  4
0x10a3b  ret
```
