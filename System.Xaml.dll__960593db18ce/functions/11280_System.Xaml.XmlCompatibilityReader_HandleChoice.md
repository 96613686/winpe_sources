# System.Xaml.XmlCompatibilityReader::HandleChoice

- ea: `0x11280`
- end: `0x11444`
- name: `System.Xaml.XmlCompatibilityReader::HandleChoice`
- size: `452`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callees

- `0x10fc0`
- `0x11060`
- `0x110b0`
- `0x11180`
- `0x111a0`
- `0x11280`
- `0x117a0`
- `0x117e0`
- `0x11820`
- `0x11880`
- `0x11d80`
- `0x11f20`
- `0x2ecb0`
- `0x2ed10`
- `0x2ed60`
- `0x2ed90`
- `0x2edf0`

## pseudocode

```c

```

## disassembly

```asm
0x11280  ldarg.0
0x11281  call     instance class CompatibilityScope System.Xaml.XmlCompatibilityReader::get_Scope()
0x11286  callvirt instance bool CompatibilityScope::get_InAlternateContent()
0x1128b  brtrue.s loc_112A3
0x1128d  ldarg.0
0x1128e  ldstr    aXcrchoiceonlyi// "XCRChoiceOnlyInAC"
0x11293  call     string System.Xaml.SR::Get(string id)
0x11298  ldc.i4.0
0x11299  newarr   [mscorlib]System.Object
0x1129e  call     instance void System.Xaml.XmlCompatibilityReader::Error(string message, object[] args)
0x112a3  ldarg.0
0x112a4  call     instance class CompatibilityScope System.Xaml.XmlCompatibilityReader::get_Scope()
0x112a9  callvirt instance bool CompatibilityScope::get_FallbackSeen()
0x112ae  brfalse.s loc_112C6
0x112b0  ldarg.0
0x112b1  ldstr    aXcrchoiceafter// "XCRChoiceAfterFallback"
0x112b6  call     string System.Xaml.SR::Get(string id)
0x112bb  ldc.i4.0
0x112bc  newarr   [mscorlib]System.Object
0x112c1  call     instance void System.Xaml.XmlCompatibilityReader::Error(string message, object[] args)
0x112c6  ldarg.0
0x112c7  call     instance class [System.Xml]System.Xml.XmlReader System.Xaml.XmlWrappingReader::get_Reader()
0x112cc  ldarg.0
0x112cd  call     instance string System.Xaml.XmlCompatibilityReader::get_Requires()
0x112d2  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string)
0x112d7  stloc.0
0x112d8  ldloc.0
0x112d9  brtrue.s loc_112F1
0x112db  ldarg.0
0x112dc  ldstr    aXcrrequiresatt// "XCRRequiresAttribNotFound"
0x112e1  call     string System.Xaml.SR::Get(string id)
0x112e6  ldc.i4.0
0x112e7  newarr   [mscorlib]System.Object
0x112ec  call     instance void System.Xaml.XmlCompatibilityReader::Error(string message, object[] args)
0x112f1  ldloc.0
0x112f2  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x112f7  brfalse.s loc_1130F
0x112f9  ldarg.0
0x112fa  ldstr    aXcrinvalidrequ// "XCRInvalidRequiresAttribute"
0x112ff  call     string System.Xaml.SR::Get(string id)
0x11304  ldc.i4.0
0x11305  newarr   [mscorlib]System.Object
0x1130a  call     instance void System.Xaml.XmlCompatibilityReader::Error(string message, object[] args)
0x1130f  ldarg.0
0x11310  call     instance class CompatibilityScope System.Xaml.XmlCompatibilityReader::get_Scope()
0x11315  stloc.1
0x11316  ldarg.0
0x11317  ldarg.1
0x11318  call     instance void System.Xaml.XmlCompatibilityReader::ScanForCompatibility(int32 elementDepth)
0x1131d  ldarg.0
0x1131e  callvirt instance int32 [System.Xml]System.Xml.XmlReader::get_AttributeCount()
0x11323  ldc.i4.1
0x11324  beq.s    loc_11382
0x11326  ldarg.0
0x11327  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToFirstAttribute()
0x1132c  pop
0x1132d  ldarg.0
0x1132e  call     instance class [System.Xml]System.Xml.XmlReader System.Xaml.XmlWrappingReader::get_Reader()
0x11333  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x11338  ldarg.0
0x11339  call     instance string System.Xaml.XmlCompatibilityReader::get_Requires()
0x1133e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x11343  brfalse.s loc_1134C
0x11345  ldarg.0
0x11346  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToNextAttribute()
0x1134b  pop
0x1134c  ldarg.0
0x1134d  call     instance class [System.Xml]System.Xml.XmlReader System.Xaml.XmlWrappingReader::get_Reader()
0x11352  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x11357  stloc.2
0x11358  ldarg.0
0x11359  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToElement()
0x1135e  pop
0x1135f  ldarg.0
0x11360  ldstr    aXcrinvalidattr// "XCRInvalidAttribInElement"
0x11365  call     string System.Xaml.SR::Get(string id)
0x1136a  ldc.i4.2
0x1136b  newarr   [mscorlib]System.Object
0x11370  dup
0x11371  ldc.i4.0
0x11372  ldloc.2
0x11373  stelem.ref
0x11374  dup
0x11375  ldc.i4.1
0x11376  ldarg.0
0x11377  call     instance string System.Xaml.XmlCompatibilityReader::get_Choice()
0x1137c  stelem.ref
0x1137d  call     instance void System.Xaml.XmlCompatibilityReader::Error(string message, object[] args)
0x11382  ldloc.1
0x11383  callvirt instance bool CompatibilityScope::get_ChoiceTaken()
0x11388  brfalse.s loc_1139D
0x1138a  ldarg.0
0x1138b  ldarg.1
0x1138c  call     instance void System.Xaml.XmlCompatibilityReader::ScanForEndCompatibility(int32 elementDepth)
0x11391  ldarg.0
0x11392  call     instance class [System.Xml]System.Xml.XmlReader System.Xaml.XmlWrappingReader::get_Reader()
0x11397  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0x1139c  ret
0x1139d  ldloc.1
0x1139e  ldc.i4.1
0x1139f  callvirt instance void CompatibilityScope::set_ChoiceSeen(bool value)
0x113a4  ldc.i4.1
0x113a5  stloc.3
0x113a6  ldc.i4.0
0x113a7  stloc.s  4
0x113a9  ldarg.0
0x113aa  ldloc.0
0x113ab  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> System.Xaml.XmlCompatibilityReader::PrefixesToNamespaces(string prefixes)
0x113b0  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x113b5  stloc.s  5
0x113b7  br.s     loc_113D3
0x113b9  ldloc.s  5
0x113bb  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x113c0  stloc.s  6
0x113c2  ldc.i4.1
0x113c3  stloc.s  4
0x113c5  ldarg.0
0x113c6  ldloc.s  6
0x113c8  call     instance bool System.Xaml.XmlCompatibilityReader::IsNamespaceKnown(string namespaceName)
0x113cd  brtrue.s loc_113D3
0x113cf  ldc.i4.0
0x113d0  stloc.3
0x113d1  leave.s  loc_113EA
0x113d3  ldloc.s  5
0x113d5  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x113da  brtrue.s loc_113B9
0x113dc  leave.s  loc_113EA
0x113de  ldloc.s  5
0x113e0  brfalse.s loc_113E9
0x113e2  ldloc.s  5
0x113e4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x113e9  endfinally
0x113ea  ldloc.s  4
0x113ec  brtrue.s loc_11404
0x113ee  ldarg.0
0x113ef  ldstr    aXcrinvalidrequ// "XCRInvalidRequiresAttribute"
0x113f4  call     string System.Xaml.SR::Get(string id)
0x113f9  ldc.i4.0
0x113fa  newarr   [mscorlib]System.Object
0x113ff  call     instance void System.Xaml.XmlCompatibilityReader::Error(string message, object[] args)
0x11404  ldloc.3
0x11405  brfalse.s loc_11431
0x11407  ldloc.1
0x11408  ldc.i4.1
0x11409  callvirt instance void CompatibilityScope::set_ChoiceTaken(bool value)
0x1140e  ldarg.0
0x1140f  ldarg.1
0x11410  call     instance void System.Xaml.XmlCompatibilityReader::PushScope(int32 elementDepth)
0x11415  ldarg.0
0x11416  ldarg.0
0x11417  ldfld    int32 System.Xaml.XmlCompatibilityReader::_depthOffset
0x1141c  ldc.i4.1
0x1141d  add
0x1141e  stfld    int32 System.Xaml.XmlCompatibilityReader::_depthOffset
0x11423  ldarg.2
0x11424  ldarg.0
0x11425  call     instance class [System.Xml]System.Xml.XmlReader System.Xaml.XmlWrappingReader::get_Reader()
0x1142a  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x1142f  stind.i1
0x11430  ret
0x11431  ldarg.0
0x11432  ldarg.1
0x11433  call     instance void System.Xaml.XmlCompatibilityReader::ScanForEndCompatibility(int32 elementDepth)
0x11438  ldarg.0
0x11439  call     instance class [System.Xml]System.Xml.XmlReader System.Xaml.XmlWrappingReader::get_Reader()
0x1143e  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0x11443  ret
```
