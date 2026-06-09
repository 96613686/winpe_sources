# System.Xaml.XmlCompatibilityReader::HandleFallback

- ea: `0x11450`
- end: `0x11563`
- name: `System.Xaml.XmlCompatibilityReader::HandleFallback`
- size: `275`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callees

- `0x110b0`
- `0x11180`
- `0x111a0`
- `0x11450`
- `0x117a0`
- `0x117e0`
- `0x11850`
- `0x11d80`
- `0x11f20`
- `0x2ecb0`
- `0x2ece0`
- `0x2ed10`
- `0x2ed60`
- `0x2edc0`

## pseudocode

```c

```

## disassembly

```asm
0x11450  ldarg.0
0x11451  call     instance class CompatibilityScope System.Xaml.XmlCompatibilityReader::get_Scope()
0x11456  callvirt instance bool CompatibilityScope::get_InAlternateContent()
0x1145b  brtrue.s loc_11473
0x1145d  ldarg.0
0x1145e  ldstr    aXcrfallbackonl// "XCRFallbackOnlyInAC"
0x11463  call     string System.Xaml.SR::Get(string id)
0x11468  ldc.i4.0
0x11469  newarr   [mscorlib]System.Object
0x1146e  call     instance void System.Xaml.XmlCompatibilityReader::Error(string message, object[] args)
0x11473  ldarg.0
0x11474  call     instance class CompatibilityScope System.Xaml.XmlCompatibilityReader::get_Scope()
0x11479  callvirt instance bool CompatibilityScope::get_ChoiceSeen()
0x1147e  brtrue.s loc_11496
0x11480  ldarg.0
0x11481  ldstr    aXcrchoicenotfo// "XCRChoiceNotFound"
0x11486  call     string System.Xaml.SR::Get(string id)
0x1148b  ldc.i4.0
0x1148c  newarr   [mscorlib]System.Object
0x11491  call     instance void System.Xaml.XmlCompatibilityReader::Error(string message, object[] args)
0x11496  ldarg.0
0x11497  call     instance class CompatibilityScope System.Xaml.XmlCompatibilityReader::get_Scope()
0x1149c  callvirt instance bool CompatibilityScope::get_FallbackSeen()
0x114a1  brfalse.s loc_114B9
0x114a3  ldarg.0
0x114a4  ldstr    aXcrmultiplefal// "XCRMultipleFallbackFound"
0x114a9  call     string System.Xaml.SR::Get(string id)
0x114ae  ldc.i4.0
0x114af  newarr   [mscorlib]System.Object
0x114b4  call     instance void System.Xaml.XmlCompatibilityReader::Error(string message, object[] args)
0x114b9  ldarg.0
0x114ba  call     instance class CompatibilityScope System.Xaml.XmlCompatibilityReader::get_Scope()
0x114bf  ldc.i4.1
0x114c0  callvirt instance void CompatibilityScope::set_FallbackSeen(bool value)
0x114c5  ldarg.0
0x114c6  call     instance class CompatibilityScope System.Xaml.XmlCompatibilityReader::get_Scope()
0x114cb  callvirt instance bool CompatibilityScope::get_ChoiceTaken()
0x114d0  stloc.0
0x114d1  ldarg.0
0x114d2  ldarg.1
0x114d3  call     instance void System.Xaml.XmlCompatibilityReader::ScanForCompatibility(int32 elementDepth)
0x114d8  ldarg.0
0x114d9  callvirt instance int32 [System.Xml]System.Xml.XmlReader::get_AttributeCount()
0x114de  brfalse.s loc_1151D
0x114e0  ldarg.0
0x114e1  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToFirstAttribute()
0x114e6  pop
0x114e7  ldarg.0
0x114e8  call     instance class [System.Xml]System.Xml.XmlReader System.Xaml.XmlWrappingReader::get_Reader()
0x114ed  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x114f2  stloc.1
0x114f3  ldarg.0
0x114f4  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToElement()
0x114f9  pop
0x114fa  ldarg.0
0x114fb  ldstr    aXcrinvalidattr// "XCRInvalidAttribInElement"
0x11500  call     string System.Xaml.SR::Get(string id)
0x11505  ldc.i4.2
0x11506  newarr   [mscorlib]System.Object
0x1150b  dup
0x1150c  ldc.i4.0
0x1150d  ldloc.1
0x1150e  stelem.ref
0x1150f  dup
0x11510  ldc.i4.1
0x11511  ldarg.0
0x11512  call     instance string System.Xaml.XmlCompatibilityReader::get_Fallback()
0x11517  stelem.ref
0x11518  call     instance void System.Xaml.XmlCompatibilityReader::Error(string message, object[] args)
0x1151d  ldloc.0
0x1151e  brfalse.s loc_11533
0x11520  ldarg.0
0x11521  ldarg.1
0x11522  call     instance void System.Xaml.XmlCompatibilityReader::ScanForEndCompatibility(int32 elementDepth)
0x11527  ldarg.0
0x11528  call     instance class [System.Xml]System.Xml.XmlReader System.Xaml.XmlWrappingReader::get_Reader()
0x1152d  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0x11532  ret
0x11533  ldarg.0
0x11534  call     instance class [System.Xml]System.Xml.XmlReader System.Xaml.XmlWrappingReader::get_Reader()
0x11539  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x1153e  brtrue.s loc_11555
0x11540  ldarg.0
0x11541  ldarg.1
0x11542  call     instance void System.Xaml.XmlCompatibilityReader::PushScope(int32 elementDepth)
0x11547  ldarg.0
0x11548  ldarg.0
0x11549  ldfld    int32 System.Xaml.XmlCompatibilityReader::_depthOffset
0x1154e  ldc.i4.1
0x1154f  add
0x11550  stfld    int32 System.Xaml.XmlCompatibilityReader::_depthOffset
0x11555  ldarg.2
0x11556  ldarg.0
0x11557  call     instance class [System.Xml]System.Xml.XmlReader System.Xaml.XmlWrappingReader::get_Reader()
0x1155c  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x11561  stind.i1
0x11562  ret
```
