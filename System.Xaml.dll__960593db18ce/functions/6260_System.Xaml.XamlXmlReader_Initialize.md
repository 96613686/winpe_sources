# System.Xaml.XamlXmlReader::Initialize

- ea: `0x6260`
- end: `0x642c`
- name: `System.Xaml.XamlXmlReader::Initialize`
- size: `460`
- prototype: ``
- caller_count: `16`
- callee_count: `22`
- tags: `registry_config`

## callers

- `0x5e90`
- `0x5eb0`
- `0x5ed0`
- `0x5f00`
- `0x5f30`
- `0x5f60`
- `0x5f90`
- `0x5fd0`
- `0x6040`
- `0x6070`
- `0x60a0`
- `0x60e0`
- `0x6150`
- `0x6180`
- `0x61b0`
- `0x61f0`

## callees

- `0x2120`
- `0x23a0`
- `0x23f0`
- `0x2400`
- `0x6260`
- `0x6610`
- `0x6630`
- `0x6640`
- `0x6680`
- `0x6690`
- `0x69a0`
- `0xb4b0`
- `0x104e0`
- `0x10750`
- `0x10e00`
- `0x1d440`
- `0x1d850`
- `0x22c80`
- `0x22ca0`
- `0x22cb0`
- `0x25720`
- `0x25f90`

## string_xrefs

- `0x63ab`: `http://www.w3.org/XML/1998/namespace`

## pseudocode

```c

```

## disassembly

```asm
0x6260  ldarg.0
0x6261  ldarg.3
0x6262  brfalse.s loc_626C
0x6264  ldarg.3
0x6265  newobj   instance void System.Xaml.XamlXmlReaderSettings::.ctor(class System.Xaml.XamlXmlReaderSettings settings)
0x626a  br.s     loc_6271
0x626c  newobj   instance void System.Xaml.XamlXmlReaderSettings::.ctor()
0x6271  stfld    class System.Xaml.XamlXmlReaderSettings System.Xaml.XamlXmlReader::_mergedSettings
0x6276  ldarg.0
0x6277  ldfld    class System.Xaml.XamlXmlReaderSettings System.Xaml.XamlXmlReader::_mergedSettings
0x627c  callvirt instance bool System.Xaml.XamlXmlReaderSettings::get_SkipXmlCompatibilityProcessing()
0x6281  brtrue.s loc_62A4
0x6283  ldarg.1
0x6284  ldarg.0
0x6285  ldftn    instance bool System.Xaml.XamlXmlReader::IsXmlNamespaceSupported(string xmlNamespace, [out] string& newXmlNamespace)
0x628b  newobj   instance void System.Xaml.IsXmlNamespaceSupportedCallback::.ctor(object object, native int method)
0x6290  newobj   instance void System.Xaml.XmlCompatibilityReader::.ctor(class [System.Xml]System.Xml.XmlReader baseReader, class System.Xaml.IsXmlNamespaceSupportedCallback isXmlNamespaceSupported)
0x6295  stloc.s  6
0x6297  ldloc.s  6
0x6299  ldc.i4.1
0x629a  callvirt instance void System.Xaml.XmlCompatibilityReader::set_Normalization(bool value)
0x629f  ldloc.s  6
0x62a1  stloc.0
0x62a2  br.s     loc_62A6
0x62a4  ldarg.1
0x62a5  stloc.0
0x62a6  ldloc.0
0x62a7  callvirt instance string [System.Xml]System.Xml.XmlReader::get_BaseURI()
0x62ac  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x62b1  brtrue.s loc_62C9
0x62b3  ldarg.0
0x62b4  ldfld    class System.Xaml.XamlXmlReaderSettings System.Xaml.XamlXmlReader::_mergedSettings
0x62b9  ldloc.0
0x62ba  callvirt instance string [System.Xml]System.Xml.XmlReader::get_BaseURI()
0x62bf  newobj   instance void [System]System.Uri::.ctor(string)
0x62c4  callvirt instance void System.Xaml.XamlReaderSettings::set_BaseUri(class [System]System.Uri value)
0x62c9  ldloc.0
0x62ca  callvirt instance valuetype [System.Xml]System.Xml.XmlSpace [System.Xml]System.Xml.XmlReader::get_XmlSpace()
0x62cf  ldc.i4.2
0x62d0  bne.un.s loc_62DE
0x62d2  ldarg.0
0x62d3  ldfld    class System.Xaml.XamlXmlReaderSettings System.Xaml.XamlXmlReader::_mergedSettings
0x62d8  ldc.i4.1
0x62d9  callvirt instance void System.Xaml.XamlXmlReaderSettings::set_XmlSpacePreserve(bool value)
0x62de  ldloc.0
0x62df  callvirt instance string [System.Xml]System.Xml.XmlReader::get_XmlLang()
0x62e4  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x62e9  brtrue.s loc_62FC
0x62eb  ldarg.0
0x62ec  ldfld    class System.Xaml.XamlXmlReaderSettings System.Xaml.XamlXmlReader::_mergedSettings
0x62f1  ldloc.0
0x62f2  callvirt instance string [System.Xml]System.Xml.XmlReader::get_XmlLang()
0x62f7  callvirt instance void System.Xaml.XamlXmlReaderSettings::set_XmlLang(string value)
0x62fc  ldloc.0
0x62fd  isinst   [System.Xml]System.Xml.IXmlNamespaceResolver
0x6302  stloc.1
0x6303  ldnull
0x6304  stloc.2
0x6305  ldloc.1
0x6306  brfalse.s loc_635D
0x6308  ldloc.1
0x6309  ldc.i4.2
0x630a  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> [System.Xml]System.Xml.IXmlNamespaceResolver::GetNamespacesInScope(valuetype [System.Xml]System.Xml.XmlNamespaceScope)
0x630f  stloc.s  7
0x6311  ldloc.s  7
0x6313  brfalse.s loc_635D
0x6315  ldloc.s  7
0x6317  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::GetEnumerator()
0x631c  stloc.s  8
0x631e  br.s     loc_6346
0x6320  ldloc.s  8
0x6322  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::get_Current()
0x6327  stloc.s  9
0x6329  ldloc.2
0x632a  brtrue.s loc_6332
0x632c  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x6331  stloc.2
0x6332  ldloc.2
0x6333  ldloca.s 9
0x6335  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x633a  ldloca.s 9
0x633c  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x6341  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x6346  ldloc.s  8
0x6348  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x634d  brtrue.s loc_6320
0x634f  leave.s  loc_635D
0x6351  ldloc.s  8
0x6353  brfalse.s loc_635C
0x6355  ldloc.s  8
0x6357  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x635c  endfinally
0x635d  ldarg.2
0x635e  brtrue.s loc_6367
0x6360  newobj   instance void System.Xaml.XamlSchemaContext::.ctor()
0x6365  starg.s  2
0x6367  ldarg.0
0x6368  ldc.i4.2
0x6369  newobj   instance void System.Xaml.XamlNode::.ctor(valuetype InternalNodeType internalNodeType)
0x636e  stfld    valuetype System.Xaml.XamlNode System.Xaml.XamlXmlReader::_endOfStreamNode
0x6373  ldarg.0
0x6374  ldarg.2
0x6375  ldarg.0
0x6376  ldfld    class System.Xaml.XamlXmlReaderSettings System.Xaml.XamlXmlReader::_mergedSettings
0x637b  callvirt instance class [mscorlib]System.Reflection.Assembly System.Xaml.XamlReaderSettings::get_LocalAssembly()
0x6380  newobj   instance void MS.Internal.Xaml.Context.XamlParserContext::.ctor(class System.Xaml.XamlSchemaContext schemaContext, class [mscorlib]System.Reflection.Assembly localAssembly)
0x6385  stfld    class MS.Internal.Xaml.Context.XamlParserContext System.Xaml.XamlXmlReader::_context
0x638a  ldarg.0
0x638b  ldfld    class MS.Internal.Xaml.Context.XamlParserContext System.Xaml.XamlXmlReader::_context
0x6390  ldarg.0
0x6391  ldfld    class System.Xaml.XamlXmlReaderSettings System.Xaml.XamlXmlReader::_mergedSettings
0x6396  callvirt instance bool System.Xaml.XamlReaderSettings::get_AllowProtectedMembersOnRoot()
0x639b  callvirt instance void MS.Internal.Xaml.Context.XamlParserContext::set_AllowProtectedMembersOnRoot(bool value)
0x63a0  ldarg.0
0x63a1  ldfld    class MS.Internal.Xaml.Context.XamlParserContext System.Xaml.XamlXmlReader::_context
0x63a6  ldstr    aXml// "xml"
0x63ab  ldstr    aHttpWwwW3OrgXm// "http://www.w3.org/XML/1998/namespace"
0x63b0  callvirt instance void MS.Internal.Xaml.XamlContext::AddNamespacePrefix(string prefix, string xamlNamespace)
0x63b5  ldloc.0
0x63b6  dup
0x63b7  ldvirtftn instance string [System.Xml]System.Xml.XmlReader::LookupNamespace(string)
0x63bd  newobj   instance void class [mscorlib]System.Func`2<string, string>::.ctor(object, native int)
0x63c2  stloc.3
0x63c3  ldarg.0
0x63c4  ldfld    class MS.Internal.Xaml.Context.XamlParserContext System.Xaml.XamlXmlReader::_context
0x63c9  ldloc.3
0x63ca  callvirt instance void MS.Internal.Xaml.Context.XamlParserContext::set_XmlNamespaceResolver(class [mscorlib]System.Func`2<string, string> value)
0x63cf  ldarg.0
0x63d0  ldfld    class MS.Internal.Xaml.Context.XamlParserContext System.Xaml.XamlXmlReader::_context
0x63d5  ldloc.0
0x63d6  ldarg.0
0x63d7  ldfld    class System.Xaml.XamlXmlReaderSettings System.Xaml.XamlXmlReader::_mergedSettings
0x63dc  newobj   instance void MS.Internal.Xaml.Parser.XamlScanner::.ctor(class MS.Internal.Xaml.Context.XamlParserContext context, class [System.Xml]System.Xml.XmlReader xmlReader, class System.Xaml.XamlXmlReaderSettings settings)
0x63e1  stloc.s  4
0x63e3  ldarg.0
0x63e4  ldfld    class MS.Internal.Xaml.Context.XamlParserContext System.Xaml.XamlXmlReader::_context
0x63e9  ldloc.s  4
0x63eb  ldarg.0
0x63ec  ldfld    class System.Xaml.XamlXmlReaderSettings System.Xaml.XamlXmlReader::_mergedSettings
0x63f1  newobj   instance void MS.Internal.Xaml.Parser.XamlPullParser::.ctor(class MS.Internal.Xaml.Context.XamlParserContext context, class MS.Internal.Xaml.Parser.XamlScanner scanner, class System.Xaml.XamlXmlReaderSettings settings)
0x63f6  stloc.s  5
0x63f8  ldarg.0
0x63f9  ldarg.0
0x63fa  ldfld    class MS.Internal.Xaml.Context.XamlParserContext System.Xaml.XamlXmlReader::_context
0x63ff  ldloc.s  5
0x6401  ldarg.0
0x6402  ldfld    class System.Xaml.XamlXmlReaderSettings System.Xaml.XamlXmlReader::_mergedSettings
0x6407  ldloc.2
0x6408  newobj   instance void MS.Internal.Xaml.NodeStreamSorter::.ctor(class MS.Internal.Xaml.Context.XamlParserContext context, class MS.Internal.Xaml.Parser.XamlPullParser parser, class System.Xaml.XamlXmlReaderSettings settings, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> xmlnsDictionary)
0x640d  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> System.Xaml.XamlXmlReader::_nodeStream
0x6412  ldarg.0
0x6413  ldc.i4.1
0x6414  newobj   instance void System.Xaml.XamlNode::.ctor(valuetype InternalNodeType internalNodeType)
0x6419  stfld    valuetype System.Xaml.XamlNode System.Xaml.XamlXmlReader::_current
0x641e  ldarg.0
0x641f  ldc.i4.0
0x6420  ldc.i4.0
0x6421  newobj   instance void System.Xaml.LineInfo::.ctor(int32 lineNumber, int32 linePosition)
0x6426  stfld    class System.Xaml.LineInfo System.Xaml.XamlXmlReader::_currentLineInfo
0x642b  ret
```
