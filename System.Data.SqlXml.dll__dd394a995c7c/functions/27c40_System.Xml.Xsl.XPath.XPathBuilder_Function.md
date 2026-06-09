# System.Xml.Xsl.XPath.XPathBuilder::Function

- ea: `0x27c40`
- end: `0x28027`
- name: `System.Xml.Xsl.XPath.XPathBuilder::Function`
- size: `999`
- prototype: ``
- caller_count: `0`
- callee_count: `37`
- tags: `registry_config`

## callees

- `0x26e80`
- `0x270b0`
- `0x270d0`
- `0x270f0`
- `0x27c40`
- `0x28030`
- `0x28080`
- `0x280d0`
- `0x281a0`
- `0x281f0`
- `0x297d0`
- `0x298a0`
- `0x299c0`
- `0x29b80`
- `0x29bc0`
- `0x29bf0`
- `0x29c20`
- `0x29c50`
- `0x29c80`
- `0x29cb0`
- `0x29ce0`
- `0x29d10`
- `0x29d40`
- `0x29d70`
- `0x29da0`
- `0x29dd0`
- `0x37c90`
- `0x37ca0`
- `0x37d80`
- `0x37eb0`
- `0x37fe0`
- `0x38030`
- `0x381a0`
- `0x38370`
- `0x38380`
- `0x383d0`
- `0x384a0`

## pseudocode

```c

```

## disassembly

```asm
0x27c40  ldarg.1
0x27c41  callvirt instance int32 [mscorlib]System.String::get_Length()
0x27c46  brtrue   loc_28017
0x27c4b  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class FunctionInfo`1<valuetype FuncId>> System.Xml.Xsl.XPath.XPathBuilder::FunctionTable
0x27c50  ldarg.2
0x27c51  ldloca.s 0
0x27c53  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class FunctionInfo`1<valuetype FuncId>>::TryGetValue(var<u1>, !!T0)
0x27c58  brfalse  loc_28017
0x27c5d  ldloc.0
0x27c5e  ldarg.3
0x27c5f  ldarg.2
0x27c60  ldarg.0
0x27c61  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.XPath.XPathBuilder::f
0x27c66  callvirt instance void class FunctionInfo`1<valuetype FuncId>::CastArguments(class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode>, string, class System.Xml.Xsl.XPath.XPathQilFactory)
0x27c6b  ldloc.0
0x27c6c  ldfld    var<u1> class FunctionInfo`1<valuetype FuncId>::id
0x27c71  stloc.1
0x27c72  ldloc.1
0x27c73  switch   loc_27CFC, loc_27D03, loc_27D0A, loc_27D38, loc_27D60, loc_27D88, loc_27DAB, loc_27DD8, loc_27E15, loc_27E28, loc_27E34, loc_27CE9, loc_27E40, loc_27E64, loc_27E71, loc_27E8B, loc_27EA5, loc_27EBF, loc_27ED9, loc_27F1D, loc_27F5B, loc_27F89, loc_27FAA, loc_27FC3, loc_27FDC, loc_27FEF, loc_28002
0x27ce4  br       loc_28015
0x27ce9  ldarg.0
0x27cea  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.XPath.XPathBuilder::f
0x27cef  ldarg.3
0x27cf0  ldc.i4.0
0x27cf1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode>::get_Item(!!T0)
0x27cf6  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::Not(class System.Xml.Xsl.Qil.QilNode child)
0x27cfb  ret
0x27cfc  ldarg.0
0x27cfd  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.XPath.XPathBuilder::GetLastPosition()
0x27d02  ret
0x27d03  ldarg.0
0x27d04  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.XPath.XPathBuilder::GetCurrentPosition()
0x27d09  ret
0x27d0a  ldarg.0
0x27d0b  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.XPath.XPathBuilder::f
0x27d10  ldarg.0
0x27d11  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.XPath.XPathBuilder::f
0x27d16  ldarg.0
0x27d17  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.XPath.XPathBuilder::f
0x27d1c  ldarg.3
0x27d1d  ldc.i4.0
0x27d1e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode>::get_Item(!!T0)
0x27d23  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::DocOrderDistinct(class System.Xml.Xsl.Qil.QilNode collection)
0x27d28  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::Length(class System.Xml.Xsl.Qil.QilNode child)
0x27d2d  ldsfld   class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryTypeFactory::DoubleX
0x27d32  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::XsltConvert(class System.Xml.Xsl.Qil.QilNode expr, class System.Xml.Xsl.XmlQueryType t)
0x27d37  ret
0x27d38  ldarg.3
0x27d39  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class System.Xml.Xsl.Qil.QilNode>::get_Count()
0x27d3e  brfalse.s loc_27D4E
0x27d40  ldarg.0
0x27d41  ldarg.3
0x27d42  ldc.i4.0
0x27d43  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode>::get_Item(!!T0)
0x27d48  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.XPath.XPathBuilder::LocalNameOfFirstNode(class System.Xml.Xsl.Qil.QilNode arg)
0x27d4d  ret
0x27d4e  ldarg.0
0x27d4f  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.XPath.XPathBuilder::f
0x27d54  ldarg.0
0x27d55  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.XPath.XPathBuilder::GetCurrentNode()
0x27d5a  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::LocalNameOf(class System.Xml.Xsl.Qil.QilNode expr)
0x27d5f  ret
0x27d60  ldarg.3
0x27d61  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class System.Xml.Xsl.Qil.QilNode>::get_Count()
0x27d66  brfalse.s loc_27D76
0x27d68  ldarg.0
0x27d69  ldarg.3
0x27d6a  ldc.i4.0
0x27d6b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode>::get_Item(!!T0)
0x27d70  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.XPath.XPathBuilder::NamespaceOfFirstNode(class System.Xml.Xsl.Qil.QilNode arg)
0x27d75  ret
0x27d76  ldarg.0
0x27d77  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.XPath.XPathBuilder::f
0x27d7c  ldarg.0
0x27d7d  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.XPath.XPathBuilder::GetCurrentNode()
0x27d82  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::NamespaceUriOf(class System.Xml.Xsl.Qil.QilNode expr)
0x27d87  ret
0x27d88  ldarg.3
0x27d89  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class System.Xml.Xsl.Qil.QilNode>::get_Count()
0x27d8e  brfalse.s loc_27D9E
0x27d90  ldarg.0
0x27d91  ldarg.3
0x27d92  ldc.i4.0
0x27d93  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode>::get_Item(!!T0)
0x27d98  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.XPath.XPathBuilder::NameOfFirstNode(class System.Xml.Xsl.Qil.QilNode arg)
0x27d9d  ret
0x27d9e  ldarg.0
0x27d9f  ldarg.0
0x27da0  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.XPath.XPathBuilder::GetCurrentNode()
0x27da5  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.XPath.XPathBuilder::NameOf(class System.Xml.Xsl.Qil.QilNode arg)
0x27daa  ret
0x27dab  ldarg.3
0x27dac  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class System.Xml.Xsl.Qil.QilNode>::get_Count()
0x27db1  brfalse.s loc_27DC6
0x27db3  ldarg.0
0x27db4  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.XPath.XPathBuilder::f
0x27db9  ldarg.3
0x27dba  ldc.i4.0
0x27dbb  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode>::get_Item(!!T0)
0x27dc0  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.XPath.XPathQilFactory::ConvertToString(class System.Xml.Xsl.Qil.QilNode n)
0x27dc5  ret
0x27dc6  ldarg.0
0x27dc7  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.XPath.XPathBuilder::f
0x27dcc  ldarg.0
0x27dcd  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.XPath.XPathBuilder::GetCurrentNode()
0x27dd2  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::XPathNodeValue(class System.Xml.Xsl.Qil.QilNode expr)
0x27dd7  ret
0x27dd8  ldarg.3
0x27dd9  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class System.Xml.Xsl.Qil.QilNode>::get_Count()
0x27dde  brfalse.s loc_27DF3
0x27de0  ldarg.0
0x27de1  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.XPath.XPathBuilder::f
0x27de6  ldarg.3
0x27de7  ldc.i4.0
0x27de8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode>::get_Item(!!T0)
0x27ded  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.XPath.XPathQilFactory::ConvertToNumber(class System.Xml.Xsl.Qil.QilNode n)
0x27df2  ret
0x27df3  ldarg.0
0x27df4  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.XPath.XPathBuilder::f
0x27df9  ldarg.0
0x27dfa  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.XPath.XPathBuilder::f
0x27dff  ldarg.0
0x27e00  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.XPath.XPathBuilder::GetCurrentNode()
0x27e05  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::XPathNodeValue(class System.Xml.Xsl.Qil.QilNode expr)
0x27e0a  ldsfld   class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryTypeFactory::DoubleX
0x27e0f  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::XsltConvert(class System.Xml.Xsl.Qil.QilNode expr, class System.Xml.Xsl.XmlQueryType t)
0x27e14  ret
0x27e15  ldarg.0
0x27e16  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.XPath.XPathBuilder::f
0x27e1b  ldarg.3
0x27e1c  ldc.i4.0
0x27e1d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode>::get_Item(!!T0)
0x27e22  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.XPath.XPathQilFactory::ConvertToBoolean(class System.Xml.Xsl.Qil.QilNode n)
0x27e27  ret
0x27e28  ldarg.0
0x27e29  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.XPath.XPathBuilder::f
0x27e2e  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::True()
0x27e33  ret
0x27e34  ldarg.0
0x27e35  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.XPath.XPathBuilder::f
0x27e3a  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::False()
0x27e3f  ret
0x27e40  ldarg.0
0x27e41  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.XPath.XPathBuilder::f
0x27e46  ldarg.0
0x27e47  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.XPath.XPathBuilder::f
0x27e4c  ldarg.0
0x27e4d  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.XPath.XPathBuilder::GetCurrentNode()
0x27e52  ldarg.3
0x27e53  ldc.i4.0
0x27e54  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode>::get_Item(!!T0)
0x27e59  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.XPath.XPathQilFactory::Id(class System.Xml.Xsl.Qil.QilNode context, class System.Xml.Xsl.Qil.QilNode id)
0x27e5e  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::DocOrderDistinct(class System.Xml.Xsl.Qil.QilNode collection)
0x27e63  ret
0x27e64  ldarg.0
0x27e65  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.XPath.XPathBuilder::f
0x27e6a  ldarg.3
0x27e6b  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::StrConcat(class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode> args)
0x27e70  ret
0x27e71  ldarg.0
0x27e72  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.XPath.XPathBuilder::f
0x27e77  ldarg.3
0x27e78  ldc.i4.0
0x27e79  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode>::get_Item(!!T0)
0x27e7e  ldarg.3
0x27e7f  ldc.i4.1
0x27e80  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode>::get_Item(!!T0)
0x27e85  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.XPath.XPathQilFactory::InvokeStartsWith(class System.Xml.Xsl.Qil.QilNode str1, class System.Xml.Xsl.Qil.QilNode str2)
0x27e8a  ret
0x27e8b  ldarg.0
0x27e8c  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.XPath.XPathBuilder::f
0x27e91  ldarg.3
0x27e92  ldc.i4.0
0x27e93  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode>::get_Item(!!T0)
0x27e98  ldarg.3
0x27e99  ldc.i4.1
0x27e9a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode>::get_Item(!!T0)
0x27e9f  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.XPath.XPathQilFactory::InvokeContains(class System.Xml.Xsl.Qil.QilNode str1, class System.Xml.Xsl.Qil.QilNode str2)
0x27ea4  ret
0x27ea5  ldarg.0
0x27ea6  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.XPath.XPathBuilder::f
0x27eab  ldarg.3
0x27eac  ldc.i4.0
0x27ead  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode>::get_Item(!!T0)
0x27eb2  ldarg.3
0x27eb3  ldc.i4.1
0x27eb4  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode>::get_Item(!!T0)
0x27eb9  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.XPath.XPathQilFactory::InvokeSubstringBefore(class System.Xml.Xsl.Qil.QilNode str1, class System.Xml.Xsl.Qil.QilNode str2)
0x27ebe  ret
0x27ebf  ldarg.0
0x27ec0  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.XPath.XPathBuilder::f
0x27ec5  ldarg.3
0x27ec6  ldc.i4.0
0x27ec7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode>::get_Item(!!T0)
0x27ecc  ldarg.3
0x27ecd  ldc.i4.1
0x27ece  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode>::get_Item(!!T0)
0x27ed3  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.XPath.XPathQilFactory::InvokeSubstringAfter(class System.Xml.Xsl.Qil.QilNode str1, class System.Xml.Xsl.Qil.QilNode str2)
0x27ed8  ret
0x27ed9  ldarg.3
0x27eda  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class System.Xml.Xsl.Qil.QilNode>::get_Count()
0x27edf  ldc.i4.2
0x27ee0  beq.s    loc_27F03
0x27ee2  ldarg.0
0x27ee3  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.XPath.XPathBuilder::f
0x27ee8  ldarg.3
0x27ee9  ldc.i4.0
0x27eea  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode>::get_Item(!!T0)
0x27eef  ldarg.3
0x27ef0  ldc.i4.1
0x27ef1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode>::get_Item(!!T0)
0x27ef6  ldarg.3
0x27ef7  ldc.i4.2
0x27ef8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode>::get_Item(!!T0)
0x27efd  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.XPath.XPathQilFactory::InvokeSubstring(class System.Xml.Xsl.Qil.QilNode str, class System.Xml.Xsl.Qil.QilNode start, class System.Xml.Xsl.Qil.QilNode length)
0x27f02  ret
0x27f03  ldarg.0
0x27f04  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.XPath.XPathBuilder::f
0x27f09  ldarg.3
0x27f0a  ldc.i4.0
0x27f0b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode>::get_Item(!!T0)
0x27f10  ldarg.3
0x27f11  ldc.i4.1
0x27f12  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode>::get_Item(!!T0)
0x27f17  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.XPath.XPathQilFactory::InvokeSubstring(class System.Xml.Xsl.Qil.QilNode str, class System.Xml.Xsl.Qil.QilNode start)
0x27f1c  ret
0x27f1d  ldarg.0
0x27f1e  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.XPath.XPathBuilder::f
0x27f23  ldarg.0
0x27f24  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.XPath.XPathBuilder::f
0x27f29  ldarg.3
0x27f2a  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class System.Xml.Xsl.Qil.QilNode>::get_Count()
0x27f2f  brfalse.s loc_27F3A
0x27f31  ldarg.3
0x27f32  ldc.i4.0
0x27f33  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode>::get_Item(!!T0)
0x27f38  br.s     loc_27F4B
0x27f3a  ldarg.0
0x27f3b  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.XPath.XPathBuilder::f
0x27f40  ldarg.0
0x27f41  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.XPath.XPathBuilder::GetCurrentNode()
0x27f46  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::XPathNodeValue(class System.Xml.Xsl.Qil.QilNode expr)
0x27f4b  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::StrLength(class System.Xml.Xsl.Qil.QilNode str)
0x27f50  ldsfld   class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryTypeFactory::DoubleX
0x27f55  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::XsltConvert(class System.Xml.Xsl.Qil.QilNode expr, class System.Xml.Xsl.XmlQueryType t)
0x27f5a  ret
0x27f5b  ldarg.0
0x27f5c  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.XPath.XPathBuilder::f
0x27f61  ldarg.3
0x27f62  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class System.Xml.Xsl.Qil.QilNode>::get_Count()
0x27f67  brfalse.s loc_27F72
0x27f69  ldarg.3
0x27f6a  ldc.i4.0
0x27f6b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode>::get_Item(!!T0)
0x27f70  br.s     loc_27F83
0x27f72  ldarg.0
0x27f73  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.XPath.XPathBuilder::f
0x27f78  ldarg.0
0x27f79  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.XPath.XPathBuilder::GetCurrentNode()
0x27f7e  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::XPathNodeValue(class System.Xml.Xsl.Qil.QilNode expr)
0x27f83  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.XPath.XPathQilFactory::InvokeNormalizeSpace(class System.Xml.Xsl.Qil.QilNode str)
0x27f88  ret
0x27f89  ldarg.0
0x27f8a  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.XPath.XPathBuilder::f
0x27f8f  ldarg.3
0x27f90  ldc.i4.0
0x27f91  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode>::get_Item(!!T0)
0x27f96  ldarg.3
0x27f97  ldc.i4.1
0x27f98  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode>::get_Item(!!T0)
0x27f9d  ldarg.3
0x27f9e  ldc.i4.2
0x27f9f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode>::get_Item(!!T0)
0x27fa4  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.XPath.XPathQilFactory::InvokeTranslate(class System.Xml.Xsl.Qil.QilNode str1, class System.Xml.Xsl.Qil.QilNode str2, class System.Xml.Xsl.Qil.QilNode str3)
0x27fa9  ret
0x27faa  ldarg.0
0x27fab  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.XPath.XPathBuilder::f
0x27fb0  ldarg.3
0x27fb1  ldc.i4.0
0x27fb2  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode>::get_Item(!!T0)
0x27fb7  ldarg.0
0x27fb8  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.XPath.XPathBuilder::GetCurrentNode()
0x27fbd  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.XPath.XPathQilFactory::InvokeLang(class System.Xml.Xsl.Qil.QilNode lang, class System.Xml.Xsl.Qil.QilNode context)
0x27fc2  ret
0x27fc3  ldarg.0
0x27fc4  ldarg.0
0x27fc5  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.XPath.XPathBuilder::f
0x27fca  ldarg.3
0x27fcb  ldc.i4.0
0x27fcc  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode>::get_Item(!!T0)
0x27fd1  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::DocOrderDistinct(class System.Xml.Xsl.Qil.QilNode collection)
0x27fd6  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.XPath.XPathBuilder::Sum(class System.Xml.Xsl.Qil.QilNode arg)
0x27fdb  ret
0x27fdc  ldarg.0
0x27fdd  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.XPath.XPathBuilder::f
0x27fe2  ldarg.3
0x27fe3  ldc.i4.0
0x27fe4  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode>::get_Item(!!T0)
0x27fe9  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.XPath.XPathQilFactory::InvokeFloor(class System.Xml.Xsl.Qil.QilNode value)
0x27fee  ret
  ... truncated ...
```
