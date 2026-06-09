# MS.Internal.Xaml.NodeStreamSorter::EnqueueInitialXmlState

- ea: `0x1da80`
- end: `0x1db11`
- name: `MS.Internal.Xaml.NodeStreamSorter::EnqueueInitialXmlState`
- size: `145`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x1d980`

## callees

- `0x23e0`
- `0x6600`
- `0x6620`
- `0x8bf0`
- `0x8c00`
- `0x8c10`
- `0x1d1b0`
- `0x1d450`
- `0x1da80`
- `0x1db20`

## pseudocode

```c

```

## disassembly

```asm
0x1da80  ldarg.0
0x1da81  ldfld    class MS.Internal.Xaml.Context.XamlParserContext MS.Internal.Xaml.NodeStreamSorter::_context
0x1da86  ldstr    aXml// "xml"
0x1da8b  callvirt instance string MS.Internal.Xaml.XamlContext::FindNamespaceByPrefix(string prefix)
0x1da90  stloc.0
0x1da91  ldarg.0
0x1da92  ldfld    class MS.Internal.Xaml.Context.XamlParserContext MS.Internal.Xaml.NodeStreamSorter::_context
0x1da97  callvirt instance class System.Xaml.XamlSchemaContext MS.Internal.Xaml.XamlContext::get_SchemaContext()
0x1da9c  stloc.1
0x1da9d  ldarg.0
0x1da9e  ldfld    class System.Xaml.XamlXmlReaderSettings MS.Internal.Xaml.NodeStreamSorter::_settings
0x1daa3  callvirt instance bool System.Xaml.XamlXmlReaderSettings::get_XmlSpacePreserve()
0x1daa8  brfalse.s loc_1DABA
0x1daaa  ldarg.0
0x1daab  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_Space()
0x1dab0  ldstr    aPreserve// "preserve"
0x1dab5  call     instance void MS.Internal.Xaml.NodeStreamSorter::EnqueueOneXmlDirectiveProperty(class System.Xaml.XamlMember xmlDirectiveProperty, string textValue)
0x1daba  ldarg.0
0x1dabb  ldfld    class System.Xaml.XamlXmlReaderSettings MS.Internal.Xaml.NodeStreamSorter::_settings
0x1dac0  callvirt instance string System.Xaml.XamlXmlReaderSettings::get_XmlLang()
0x1dac5  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1daca  brtrue.s loc_1DAE2
0x1dacc  ldarg.0
0x1dacd  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_Lang()
0x1dad2  ldarg.0
0x1dad3  ldfld    class System.Xaml.XamlXmlReaderSettings MS.Internal.Xaml.NodeStreamSorter::_settings
0x1dad8  callvirt instance string System.Xaml.XamlXmlReaderSettings::get_XmlLang()
0x1dadd  call     instance void MS.Internal.Xaml.NodeStreamSorter::EnqueueOneXmlDirectiveProperty(class System.Xaml.XamlMember xmlDirectiveProperty, string textValue)
0x1dae2  ldarg.0
0x1dae3  ldfld    class System.Xaml.XamlXmlReaderSettings MS.Internal.Xaml.NodeStreamSorter::_settings
0x1dae8  callvirt instance class [System]System.Uri System.Xaml.XamlReaderSettings::get_BaseUri()
0x1daed  ldnull
0x1daee  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x1daf3  brfalse.s loc_1DB10
0x1daf5  ldarg.0
0x1daf6  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_Base()
0x1dafb  ldarg.0
0x1dafc  ldfld    class System.Xaml.XamlXmlReaderSettings MS.Internal.Xaml.NodeStreamSorter::_settings
0x1db01  callvirt instance class [System]System.Uri System.Xaml.XamlReaderSettings::get_BaseUri()
0x1db06  callvirt instance string [mscorlib]System.Object::ToString()
0x1db0b  call     instance void MS.Internal.Xaml.NodeStreamSorter::EnqueueOneXmlDirectiveProperty(class System.Xaml.XamlMember xmlDirectiveProperty, string textValue)
0x1db10  ret
```
