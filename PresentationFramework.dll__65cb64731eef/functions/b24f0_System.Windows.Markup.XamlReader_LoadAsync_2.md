# System.Windows.Markup.XamlReader::LoadAsync_2

- ea: `0xb24f0`
- end: `0xb289f`
- name: `System.Windows.Markup.XamlReader::LoadAsync_2`
- size: `943`
- prototype: ``
- caller_count: `3`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0xb2440`
- `0xb2460`
- `0xb2da0`

## callees

- `0x78a0`
- `0xab350`
- `0xacd00`
- `0xad1b0`
- `0xad210`
- `0xad220`
- `0xad230`
- `0xad3a0`
- `0xae030`
- `0xaf080`
- `0xaf1d0`
- `0xb24c0`
- `0xb24f0`
- `0xb28a0`
- `0xb29a0`
- `0xb2ba0`
- `0xb2c60`
- `0xb2d10`
- `0xb31e0`
- `0x264f90`

## string_xrefs

- `0xb265c`: `http://schemas.microsoft.com/winfx/2006/xaml`
- `0xb2678`: `http://schemas.microsoft.com/winfx/2006/xaml`
- `0xb2500`: `reader`

## pseudocode

```c

```

## disassembly

```asm
0xb24f0  newobj   instance void <>c__DisplayClass9_0::.ctor()
0xb24f5  stloc.0
0xb24f6  ldloc.0
0xb24f7  ldarg.0
0xb24f8  stfld    class System.Windows.Markup.XamlReader <>c__DisplayClass9_0::<>4__this
0xb24fd  ldarg.1
0xb24fe  brtrue.s loc_B250B
0xb2500  ldstr    aReader// "reader"
0xb2505  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xb250a  throw
0xb250b  ldarg.2
0xb250c  brtrue.s loc_B2515
0xb250e  newobj   instance void System.Windows.Markup.ParserContext::.ctor()
0xb2513  starg.s  2
0xb2515  ldarg.0
0xb2516  ldarg.1
0xb2517  stfld    class [System.Xml]System.Xml.XmlReader System.Windows.Markup.XamlReader::_xmlReader
0xb251c  ldloc.0
0xb251d  ldnull
0xb251e  stfld    object <>c__DisplayClass9_0::rootObject
0xb2523  ldarg.2
0xb2524  callvirt instance class [System]System.Uri System.Windows.Markup.ParserContext::get_BaseUri()
0xb2529  ldnull
0xb252a  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0xb252f  brtrue.s loc_B2543
0xb2531  ldarg.2
0xb2532  callvirt instance class [System]System.Uri System.Windows.Markup.ParserContext::get_BaseUri()
0xb2537  callvirt instance string [mscorlib]System.Object::ToString()
0xb253c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xb2541  brfalse.s loc_B257B
0xb2543  ldarg.1
0xb2544  callvirt instance string [System.Xml]System.Xml.XmlReader::get_BaseURI()
0xb2549  brfalse.s loc_B255D
0xb254b  ldarg.1
0xb254c  callvirt instance string [System.Xml]System.Xml.XmlReader::get_BaseURI()
0xb2551  callvirt instance string [mscorlib]System.Object::ToString()
0xb2556  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xb255b  brfalse.s loc_B256A
0xb255d  ldarg.2
0xb255e  call     class [System]System.Uri [PresentationCore]System.Windows.Navigation.BaseUriHelper::get_PackAppBaseUri()
0xb2563  callvirt instance void System.Windows.Markup.ParserContext::set_BaseUri(class [System]System.Uri value)
0xb2568  br.s     loc_B257B
0xb256a  ldarg.2
0xb256b  ldarg.1
0xb256c  callvirt instance string [System.Xml]System.Xml.XmlReader::get_BaseURI()
0xb2571  newobj   instance void [System]System.Uri::.ctor(string)
0xb2576  callvirt instance void System.Windows.Markup.ParserContext::set_BaseUri(class [System]System.Uri value)
0xb257b  ldarg.0
0xb257c  ldarg.2
0xb257d  callvirt instance class [System]System.Uri System.Windows.Markup.ParserContext::get_BaseUri()
0xb2582  stfld    class [System]System.Uri System.Windows.Markup.XamlReader::_baseUri
0xb2587  newobj   instance void [System.Xaml]System.Xaml.XamlXmlReaderSettings::.ctor()
0xb258c  stloc.1
0xb258d  ldloc.1
0xb258e  ldc.i4.1
0xb258f  callvirt instance void [System.Xaml]System.Xaml.XamlReaderSettings::set_IgnoreUidsOnPropertyElements(bool)
0xb2594  ldloc.1
0xb2595  ldarg.2
0xb2596  callvirt instance class [System]System.Uri System.Windows.Markup.ParserContext::get_BaseUri()
0xb259b  callvirt instance void [System.Xaml]System.Xaml.XamlReaderSettings::set_BaseUri(class [System]System.Uri)
0xb25a0  ldloc.1
0xb25a1  ldc.i4.1
0xb25a2  callvirt instance void [System.Xaml]System.Xaml.XamlReaderSettings::set_ProvideLineInfo(bool)
0xb25a7  ldarg.2
0xb25a8  callvirt instance class System.Windows.Markup.XamlTypeMapper System.Windows.Markup.ParserContext::get_XamlTypeMapper()
0xb25ad  brtrue.s loc_B25B6
0xb25af  call     class [System.Xaml]System.Xaml.XamlSchemaContext System.Windows.Markup.XamlReader::GetWpfSchemaContext()
0xb25b4  br.s     loc_B25C1
0xb25b6  ldarg.2
0xb25b7  callvirt instance class System.Windows.Markup.XamlTypeMapper System.Windows.Markup.ParserContext::get_XamlTypeMapper()
0xb25bc  callvirt instance class [System.Xaml]System.Xaml.XamlSchemaContext System.Windows.Markup.XamlTypeMapper::get_SchemaContext()
0xb25c1  stloc.2
0xb25c2  ldarg.0
0xb25c3  ldarg.2
0xb25c4  callvirt instance bool System.Windows.Markup.ParserContext::get_FromRestrictiveReader()
0xb25c9  brtrue.s loc_B25D5
0xb25cb  ldarg.1
0xb25cc  ldloc.2
0xb25cd  ldloc.1
0xb25ce  newobj   instance void [System.Xaml]System.Xaml.XamlXmlReader::.ctor(class [System.Xml]System.Xml.XmlReader, class [System.Xaml]System.Xaml.XamlSchemaContext, class [System.Xaml]System.Xaml.XamlXmlReaderSettings)
0xb25d3  br.s     loc_B25DD
0xb25d5  ldarg.1
0xb25d6  ldloc.2
0xb25d7  ldloc.1
0xb25d8  newobj   instance void System.Windows.Markup.RestrictiveXamlXmlReader::.ctor(class [System.Xml]System.Xml.XmlReader xmlReader, class [System.Xaml]System.Xaml.XamlSchemaContext schemaContext, class [System.Xaml]System.Xaml.XamlXmlReaderSettings settings)
0xb25dd  stfld    class [System.Xaml]System.Xaml.XamlReader System.Windows.Markup.XamlReader::_textReader
0xb25e2  ldarg.0
0xb25e3  ldsfld   class [mscorlib]System.Func`1<class System.Windows.Markup.WpfXamlFrame> <>c::<>9__9_0
0xb25e8  dup
0xb25e9  brtrue.s loc_B2602
0xb25eb  pop
0xb25ec  ldsfld   class <>c <>c::<>9
0xb25f1  ldftn    instance class System.Windows.Markup.WpfXamlFrame <>c::<LoadAsync>b__9_0()
0xb25f7  newobj   instance void class [mscorlib]System.Func`1<class System.Windows.Markup.WpfXamlFrame>::.ctor(object, native int)
0xb25fc  dup
0xb25fd  stsfld   class [mscorlib]System.Func`1<class System.Windows.Markup.WpfXamlFrame> <>c::<>9__9_0
0xb2602  newobj   instance void class MS.Internal.Xaml.Context.XamlContextStack`1<class System.Windows.Markup.WpfXamlFrame>::.ctor(class [mscorlib]System.Func`1<var<u1>>)
0xb2607  stfld    class MS.Internal.Xaml.Context.XamlContextStack`1<class System.Windows.Markup.WpfXamlFrame> System.Windows.Markup.XamlReader::_stack
0xb260c  call     class [System.Xaml]System.Xaml.XamlObjectWriterSettings System.Windows.Markup.XamlReader::CreateObjectWriterSettings()
0xb2611  stloc.s  4
0xb2613  ldloc.s  4
0xb2615  ldloc.0
0xb2616  ldftn    instance void <>c__DisplayClass9_0::<LoadAsync>b__1(object sender, class [System.Xaml]System.Xaml.XamlObjectEventArgs args)
0xb261c  newobj   instance void class [mscorlib]System.EventHandler`1<class [System.Xaml]System.Xaml.XamlObjectEventArgs>::.ctor(object, native int)
0xb2621  callvirt instance void [System.Xaml]System.Xaml.XamlObjectWriterSettings::set_AfterBeginInitHandler(class [mscorlib]System.EventHandler`1<class [System.Xaml]System.Xaml.XamlObjectEventArgs>)
0xb2626  ldarg.0
0xb2627  ldarg.0
0xb2628  ldfld    class [System.Xaml]System.Xaml.XamlReader System.Windows.Markup.XamlReader::_textReader
0xb262d  callvirt instance class [System.Xaml]System.Xaml.XamlSchemaContext [System.Xaml]System.Xaml.XamlReader::get_SchemaContext()
0xb2632  ldloc.s  4
0xb2634  newobj   instance void [System.Xaml]System.Xaml.XamlObjectWriter::.ctor(class [System.Xaml]System.Xaml.XamlSchemaContext, class [System.Xaml]System.Xaml.XamlObjectWriterSettings)
0xb2639  stfld    class [System.Xaml]System.Xaml.XamlObjectWriter System.Windows.Markup.XamlReader::_objectWriter
0xb263e  ldarg.0
0xb263f  ldc.i4.0
0xb2640  stfld    bool System.Windows.Markup.XamlReader::_parseCancelled
0xb2645  ldarg.0
0xb2646  ldarg.2
0xb2647  callvirt instance bool System.Windows.Markup.ParserContext::get_SkipJournaledProperties()
0xb264c  stfld    bool System.Windows.Markup.XamlReader::_skipJournaledProperties
0xb2651  ldarg.0
0xb2652  ldfld    class [System.Xaml]System.Xaml.XamlReader System.Windows.Markup.XamlReader::_textReader
0xb2657  callvirt instance class [System.Xaml]System.Xaml.XamlSchemaContext [System.Xaml]System.Xaml.XamlReader::get_SchemaContext()
0xb265c  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/winfx/2006"...
0xb2661  ldstr    aSynchronousmod// "SynchronousMode"
0xb2666  callvirt instance class [System.Xaml]System.Xaml.XamlDirective [System.Xaml]System.Xaml.XamlSchemaContext::GetXamlDirective(string, string)
0xb266b  stloc.s  5
0xb266d  ldarg.0
0xb266e  ldfld    class [System.Xaml]System.Xaml.XamlReader System.Windows.Markup.XamlReader::_textReader
0xb2673  callvirt instance class [System.Xaml]System.Xaml.XamlSchemaContext [System.Xaml]System.Xaml.XamlReader::get_SchemaContext()
0xb2678  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/winfx/2006"...
0xb267d  ldstr    aAsyncrecords// "AsyncRecords"
0xb2682  callvirt instance class [System.Xaml]System.Xaml.XamlDirective [System.Xaml]System.Xaml.XamlSchemaContext::GetXamlDirective(string, string)
0xb2687  stloc.s  6
0xb2689  ldarg.0
0xb268a  ldfld    class [System.Xaml]System.Xaml.XamlReader System.Windows.Markup.XamlReader::_textReader
0xb268f  stloc.s  7
0xb2691  ldloc.s  7
0xb2693  isinst   [System.Xaml]System.Xaml.IXamlLineInfo
0xb2698  stloc.s  8
0xb269a  ldarg.0
0xb269b  ldfld    class [System.Xaml]System.Xaml.XamlObjectWriter System.Windows.Markup.XamlReader::_objectWriter
0xb26a0  stloc.s  9
0xb26a2  ldc.i4.0
0xb26a3  stloc.s  0xA
0xb26a5  ldloc.s  8
0xb26a7  brfalse.s loc_B26C2
0xb26a9  ldloc.s  8
0xb26ab  callvirt instance bool [System.Xaml]System.Xaml.IXamlLineInfo::get_HasLineInfo()
0xb26b0  brfalse.s loc_B26C2
0xb26b2  ldloc.s  9
0xb26b4  brfalse.s loc_B26C2
0xb26b6  ldloc.s  9
0xb26b8  callvirt instance bool [System.Xaml]System.Xaml.IXamlLineInfoConsumer::get_ShouldProvideLineInfo()
0xb26bd  brfalse.s loc_B26C2
0xb26bf  ldc.i4.1
0xb26c0  stloc.s  0xA
0xb26c2  ldc.i4.0
0xb26c3  stloc.s  0xB
0xb26c5  ldc.i4.0
0xb26c6  stloc.s  0xC
0xb26c8  ldc.i4.0
0xb26c9  stloc.s  0xD
0xb26cb  br       loc_B27CC
0xb26d0  ldloc.s  7
0xb26d2  ldarg.0
0xb26d3  ldfld    class [System.Xaml]System.Xaml.XamlObjectWriter System.Windows.Markup.XamlReader::_objectWriter
0xb26d8  ldc.i4.1
0xb26d9  ldarg.0
0xb26da  ldfld    bool System.Windows.Markup.XamlReader::_skipJournaledProperties
0xb26df  ldloc.s  0xA
0xb26e1  ldloc.s  8
0xb26e3  ldloc.s  9
0xb26e5  ldarg.0
0xb26e6  ldfld    class MS.Internal.Xaml.Context.XamlContextStack`1<class System.Windows.Markup.WpfXamlFrame> System.Windows.Markup.XamlReader::_stack
0xb26eb  ldarg.0
0xb26ec  ldfld    class System.Windows.Markup.IStyleConnector System.Windows.Markup.XamlReader::_styleConnector
0xb26f1  call     void System.Windows.Markup.WpfXamlLoader::TransformNodes(class [System.Xaml]System.Xaml.XamlReader xamlReader, class [System.Xaml]System.Xaml.XamlObjectWriter xamlWriter, bool onlyLoadOneNode, bool skipJournaledProperties, bool shouldPassLineNumberInfo, class [System.Xaml]System.Xaml.IXamlLineInfo xamlLineInfo, class [System.Xaml]System.Xaml.IXamlLineInfoConsumer xamlLineInfoConsumer, class MS.Internal.Xaml.Context.XamlContextStack`1<class System.Windows.Markup.WpfXamlFrame> stack, class System.Windows.Markup.IStyleConnector styleConnector)
0xb26f6  ldloc.s  7
0xb26f8  callvirt instance valuetype [System.Xaml]System.Xaml.XamlNodeType [System.Xaml]System.Xaml.XamlReader::get_NodeType()
0xb26fd  ldc.i4.4
0xb26fe  bne.un.s loc_B2733
0xb2700  ldloc.s  7
0xb2702  callvirt instance class [System.Xaml]System.Xaml.XamlMember [System.Xaml]System.Xaml.XamlReader::get_Member()
0xb2707  ldloc.s  5
0xb2709  call     bool [System.Xaml]System.Xaml.XamlMember::op_Equality(class [System.Xaml]System.Xaml.XamlMember, class [System.Xaml]System.Xaml.XamlMember)
0xb270e  brfalse.s loc_B2718
0xb2710  ldc.i4.1
0xb2711  stloc.s  0xC
0xb2713  br       loc_B27C0
0xb2718  ldloc.s  7
0xb271a  callvirt instance class [System.Xaml]System.Xaml.XamlMember [System.Xaml]System.Xaml.XamlReader::get_Member()
0xb271f  ldloc.s  6
0xb2721  call     bool [System.Xaml]System.Xaml.XamlMember::op_Equality(class [System.Xaml]System.Xaml.XamlMember, class [System.Xaml]System.Xaml.XamlMember)
0xb2726  brfalse  loc_B27C0
0xb272b  ldc.i4.1
0xb272c  stloc.s  0xD
0xb272e  br       loc_B27C0
0xb2733  ldloc.s  7
0xb2735  callvirt instance valuetype [System.Xaml]System.Xaml.XamlNodeType [System.Xaml]System.Xaml.XamlReader::get_NodeType()
0xb273a  ldc.i4.6
0xb273b  bne.un.s loc_B27B0
0xb273d  ldloc.s  0xC
0xb273f  brfalse.s loc_B275E
0xb2741  ldloc.s  7
0xb2743  callvirt instance object [System.Xaml]System.Xaml.XamlReader::get_Value()
0xb2748  isinst   [mscorlib]System.String
0xb274d  ldstr    aAsync// "Async"
0xb2752  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb2757  brfalse.s loc_B27C0
0xb2759  ldc.i4.1
0xb275a  stloc.s  0xB
0xb275c  br.s     loc_B27C0
0xb275e  ldloc.s  0xD
0xb2760  brfalse.s loc_B27C0
0xb2762  ldloc.s  7
0xb2764  callvirt instance object [System.Xaml]System.Xaml.XamlReader::get_Value()
0xb2769  isinst   [mscorlib]System.Int32
0xb276e  brfalse.s loc_B2784
0xb2770  ldarg.0
0xb2771  ldloc.s  7
0xb2773  callvirt instance object [System.Xaml]System.Xaml.XamlReader::get_Value()
0xb2778  unbox.any [mscorlib]System.Int32
0xb277d  stfld    int32 System.Windows.Markup.XamlReader::_maxAsynxRecords
0xb2782  br.s     loc_B27C0
0xb2784  ldloc.s  7
0xb2786  callvirt instance object [System.Xaml]System.Xaml.XamlReader::get_Value()
0xb278b  isinst   [mscorlib]System.String
0xb2790  brfalse.s loc_B27C0
0xb2792  ldarg.0
0xb2793  ldloc.s  7
0xb2795  callvirt instance object [System.Xaml]System.Xaml.XamlReader::get_Value()
0xb279a  isinst   [mscorlib]System.String
0xb279f  call     class [mscorlib]System.Globalization.CultureInfo [WindowsBase]System.Windows.Markup.TypeConverterHelper::get_InvariantEnglishUS()
0xb27a4  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0xb27a9  stfld    int32 System.Windows.Markup.XamlReader::_maxAsynxRecords
0xb27ae  br.s     loc_B27C0
0xb27b0  ldloc.s  7
0xb27b2  callvirt instance valuetype [System.Xaml]System.Xaml.XamlNodeType [System.Xaml]System.Xaml.XamlReader::get_NodeType()
0xb27b7  ldc.i4.5
0xb27b8  bne.un.s loc_B27C0
0xb27ba  ldc.i4.0
0xb27bb  stloc.s  0xC
0xb27bd  ldc.i4.0
0xb27be  stloc.s  0xD
0xb27c0  ldloc.s  0xB
0xb27c2  brfalse.s loc_B27CC
0xb27c4  ldloc.0
0xb27c5  ldfld    object <>c__DisplayClass9_0::rootObject
0xb27ca  brtrue.s loc_B27DC
0xb27cc  ldarg.0
0xb27cd  ldfld    class [System.Xaml]System.Xaml.XamlReader System.Windows.Markup.XamlReader::_textReader
0xb27d2  callvirt instance bool [System.Xaml]System.Xaml.XamlReader::get_IsEof()
0xb27d7  brfalse  loc_B26D0
0xb27dc  leave.s  loc_B2809
0xb27de  stloc.s  0xE
0xb27e0  ldloc.s  0xE
0xb27e2  call     bool [WindowsBase]MS.Internal.CriticalExceptions::IsCriticalException(class [mscorlib]System.Exception)
0xb27e7  brtrue.s loc_B27F8
0xb27e9  ldloc.s  0xE
0xb27eb  ldarg.2
0xb27ec  callvirt instance class [System]System.Uri System.Windows.Markup.ParserContext::get_BaseUri()
0xb27f1  call     bool System.Windows.Markup.XamlReader::ShouldReWrapException(class [mscorlib]System.Exception e, class [System]System.Uri baseUri)
0xb27f6  brtrue.s loc_B27FA
0xb27f8  rethrow
0xb27fa  ldloc.s  0xE
0xb27fc  ldarg.2
0xb27fd  callvirt instance class [System]System.Uri System.Windows.Markup.ParserContext::get_BaseUri()
0xb2802  call     void System.Windows.Markup.XamlReader::RewrapException(class [mscorlib]System.Exception e, class [System]System.Uri baseUri)
0xb2807  leave.s  loc_B2809
0xb2809  ldarg.0
0xb280a  ldfld    class [System.Xaml]System.Xaml.XamlReader System.Windows.Markup.XamlReader::_textReader
0xb280f  callvirt instance bool [System.Xaml]System.Xaml.XamlReader::get_IsEof()
0xb2814  brtrue.s loc_B281E
0xb2816  ldarg.0
0xb2817  call     instance void System.Windows.Markup.XamlReader::Post()
0xb281c  br.s     loc_B2824
0xb281e  ldarg.0
0xb281f  call     instance void System.Windows.Markup.XamlReader::TreeBuildComplete()
0xb2824  ldloc.0
0xb2825  ldfld    object <>c__DisplayClass9_0::rootObject
0xb282a  isinst   [WindowsBase]System.Windows.DependencyObject
0xb282f  brfalse.s loc_B2878
0xb2831  ldarg.2
0xb2832  callvirt instance class [System]System.Uri System.Windows.Markup.ParserContext::get_BaseUri()
0xb2837  ldnull
0xb2838  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0xb283d  brfalse.s loc_B286C
0xb283f  ldarg.2
0xb2840  callvirt instance class [System]System.Uri System.Windows.Markup.ParserContext::get_BaseUri()
0xb2845  callvirt instance string [mscorlib]System.Object::ToString()
0xb284a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xb284f  brtrue.s loc_B286C
0xb2851  ldloc.0
0xb2852  ldfld    object <>c__DisplayClass9_0::rootObject
0xb2857  isinst   [WindowsBase]System.Windows.DependencyObject
0xb285c  ldsfld   class [WindowsBase]System.Windows.DependencyProperty [PresentationCore]System.Windows.Navigation.BaseUriHelper::BaseUriProperty
0xb2861  ldarg.2
0xb2862  callvirt instance class [System]System.Uri System.Windows.Markup.ParserContext::get_BaseUri()
0xb2867  callvirt instance void [WindowsBase]System.Windows.DependencyObject::SetValue(class [WindowsBase]System.Windows.DependencyProperty, object)
0xb286c  ldloc.0
  ... truncated ...
```
