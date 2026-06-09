# System.Windows.Markup.XmlCompatibilityReader::ReadStartElement

- ea: `0x43700`
- end: `0x4383c`
- name: `System.Windows.Markup.XmlCompatibilityReader::ReadStartElement`
- size: `316`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x43690`

## callees

- `0x2c100`
- `0x43340`
- `0x43700`
- `0x43e10`
- `0x43eb0`
- `0x43f80`
- `0x445a0`
- `0x445e0`
- `0x447a0`
- `0x44b80`
- `0x59680`
- `0x596f0`
- `0x59730`
- `0x59850`

## string_xrefs

- `0x43751`: `XCRUnknownCompatElement`

## pseudocode

```c

```

## disassembly

```asm
0x43700  ldarg.0
0x43701  call     instance class [System.Xml]System.Xml.XmlReader System.Windows.Markup.XmlWrappingReader::get_Reader()
0x43706  callvirt instance int32 [System.Xml]System.Xml.XmlReader::get_Depth()
0x4370b  stloc.0
0x4370c  ldarg.0
0x4370d  ldfld    int32 System.Windows.Markup.XmlCompatibilityReader::_depthOffset
0x43712  stloc.1
0x43713  ldarg.0
0x43714  call     instance class [System.Xml]System.Xml.XmlReader System.Windows.Markup.XmlWrappingReader::get_Reader()
0x43719  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x4371e  stloc.2
0x4371f  ldarg.0
0x43720  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x43725  stloc.3
0x43726  ldc.i4.0
0x43727  stloc.s  4
0x43729  ldloc.3
0x4372a  ldarg.0
0x4372b  call     instance string System.Windows.Markup.XmlCompatibilityReader::get_CompatibilityUri()
0x43730  bne.un.s loc_43779
0x43732  ldarg.0
0x43733  call     instance class [System.Xml]System.Xml.XmlReader System.Windows.Markup.XmlWrappingReader::get_Reader()
0x43738  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x4373d  stloc.s  5
0x4373f  ldarg.0
0x43740  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class System.Windows.Markup.HandleElementCallback> System.Windows.Markup.XmlCompatibilityReader::_elementHandler
0x43745  ldloc.s  5
0x43747  ldloca.s 6
0x43749  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class System.Windows.Markup.HandleElementCallback>::TryGetValue(var<u1>, !!T0)
0x4374e  brtrue.s loc_4376B
0x43750  ldarg.0
0x43751  ldstr    aXcrunknowncomp// "XCRUnknownCompatElement"
0x43756  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x4375b  ldc.i4.1
0x4375c  newarr   [mscorlib]System.Object
0x43761  dup
0x43762  ldc.i4.0
0x43763  ldloc.s  5
0x43765  stelem.ref
0x43766  call     instance void System.Windows.Markup.XmlCompatibilityReader::Error(string message, object[] args)
0x4376b  ldloc.s  6
0x4376d  ldloc.0
0x4376e  ldarg.1
0x4376f  callvirt instance void System.Windows.Markup.HandleElementCallback::Invoke(int32 elementDepth, bool& more)
0x43774  br       loc_43821
0x43779  ldarg.0
0x4377a  ldloc.0
0x4377b  call     instance void System.Windows.Markup.XmlCompatibilityReader::ScanForCompatibility(int32 elementDepth)
0x43780  ldarg.0
0x43781  ldloc.3
0x43782  call     instance bool System.Windows.Markup.XmlCompatibilityReader::ShouldIgnoreNamespace(string namespaceName)
0x43787  brfalse.s loc_437ED
0x43789  ldarg.0
0x4378a  call     instance class CompatibilityScope System.Windows.Markup.XmlCompatibilityReader::get_Scope()
0x4378f  ldloc.3
0x43790  ldarg.0
0x43791  call     instance class [System.Xml]System.Xml.XmlReader System.Windows.Markup.XmlWrappingReader::get_Reader()
0x43796  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x4379b  callvirt instance bool CompatibilityScope::ShouldProcessContent(string namespaceName, string elementName)
0x437a0  brfalse.s loc_437D9
0x437a2  ldarg.0
0x437a3  call     instance class CompatibilityScope System.Windows.Markup.XmlCompatibilityReader::get_Scope()
0x437a8  callvirt instance int32 CompatibilityScope::get_Depth()
0x437ad  ldloc.0
0x437ae  bne.un.s loc_437BC
0x437b0  ldarg.0
0x437b1  call     instance class CompatibilityScope System.Windows.Markup.XmlCompatibilityReader::get_Scope()
0x437b6  ldc.i4.1
0x437b7  callvirt instance void CompatibilityScope::set_InProcessContent(bool value)
0x437bc  ldarg.0
0x437bd  ldarg.0
0x437be  ldfld    int32 System.Windows.Markup.XmlCompatibilityReader::_depthOffset
0x437c3  ldc.i4.1
0x437c4  add
0x437c5  stfld    int32 System.Windows.Markup.XmlCompatibilityReader::_depthOffset
0x437ca  ldarg.1
0x437cb  ldarg.0
0x437cc  call     instance class [System.Xml]System.Xml.XmlReader System.Windows.Markup.XmlWrappingReader::get_Reader()
0x437d1  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x437d6  stind.i1
0x437d7  br.s     loc_43821
0x437d9  ldarg.0
0x437da  ldloc.0
0x437db  call     instance void System.Windows.Markup.XmlCompatibilityReader::ScanForEndCompatibility(int32 elementDepth)
0x437e0  ldarg.0
0x437e1  call     instance class [System.Xml]System.Xml.XmlReader System.Windows.Markup.XmlWrappingReader::get_Reader()
0x437e6  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0x437eb  br.s     loc_43821
0x437ed  ldarg.0
0x437ee  call     instance class CompatibilityScope System.Windows.Markup.XmlCompatibilityReader::get_Scope()
0x437f3  callvirt instance bool CompatibilityScope::get_InAlternateContent()
0x437f8  brfalse.s loc_4381E
0x437fa  ldarg.0
0x437fb  ldstr    aXcrinvalidacch// "XCRInvalidACChild"
0x43800  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x43805  ldc.i4.1
0x43806  newarr   [mscorlib]System.Object
0x4380b  dup
0x4380c  ldc.i4.0
0x4380d  ldarg.0
0x4380e  call     instance class [System.Xml]System.Xml.XmlReader System.Windows.Markup.XmlWrappingReader::get_Reader()
0x43813  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x43818  stelem.ref
0x43819  call     instance void System.Windows.Markup.XmlCompatibilityReader::Error(string message, object[] args)
0x4381e  ldc.i4.1
0x4381f  stloc.s  4
0x43821  ldloc.2
0x43822  brfalse.s loc_43839
0x43824  ldarg.0
0x43825  ldc.i4.1
0x43826  stfld    bool System.Windows.Markup.XmlCompatibilityReader::isPreviousElementEmpty
0x4382b  ldarg.0
0x4382c  ldloc.0
0x4382d  stfld    int32 System.Windows.Markup.XmlCompatibilityReader::previousElementDepth
0x43832  ldarg.0
0x43833  ldloc.1
0x43834  stfld    int32 System.Windows.Markup.XmlCompatibilityReader::_depthOffset
0x43839  ldloc.s  4
0x4383b  ret
```
