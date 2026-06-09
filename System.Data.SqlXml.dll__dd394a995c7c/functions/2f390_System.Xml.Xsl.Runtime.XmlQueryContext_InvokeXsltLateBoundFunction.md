# System.Xml.Xsl.Runtime.XmlQueryContext::InvokeXsltLateBoundFunction

- ea: `0x2f390`
- end: `0x2f52b`
- name: `System.Xml.Xsl.Runtime.XmlQueryContext::InvokeXsltLateBoundFunction`
- size: `411`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config`

## callees

- `0x1f80`
- `0x2370`
- `0x3780`
- `0x2e250`
- `0x2e270`
- `0x2e3b0`
- `0x2e3c0`
- `0x2e3d0`
- `0x2e730`
- `0x2f390`
- `0x30e90`
- `0x31010`
- `0x33a90`
- `0x33b30`
- `0x33ba0`
- `0x33be0`
- `0x33c50`

## string_xrefs

- `0x2f3ab`: `XmlIl_UnknownExtObj`

## pseudocode

```c

```

## disassembly

```asm
0x2f390  ldarg.0
0x2f391  ldfld    class [System.Xml]System.Xml.Xsl.XsltArgumentList System.Xml.Xsl.Runtime.XmlQueryContext::argList
0x2f396  brtrue.s loc_2F39B
0x2f398  ldnull
0x2f399  br.s     loc_2F3A7
0x2f39b  ldarg.0
0x2f39c  ldfld    class [System.Xml]System.Xml.Xsl.XsltArgumentList System.Xml.Xsl.Runtime.XmlQueryContext::argList
0x2f3a1  ldarg.2
0x2f3a2  callvirt instance object [System.Xml]System.Xml.Xsl.XsltArgumentList::GetExtensionObject(string)
0x2f3a7  stloc.0
0x2f3a8  ldloc.0
0x2f3a9  brtrue.s loc_2F3C0
0x2f3ab  ldstr    aXmlilUnknownex// "XmlIl_UnknownExtObj"
0x2f3b0  ldc.i4.1
0x2f3b1  newarr   [mscorlib]System.String
0x2f3b6  dup
0x2f3b7  ldc.i4.0
0x2f3b8  ldarg.2
0x2f3b9  stelem.ref
0x2f3ba  newobj   instance void System.Xml.Xsl.XslTransformException::.ctor(string res, string[] args)
0x2f3bf  throw
0x2f3c0  ldarg.0
0x2f3c1  ldfld    class System.Xml.Xsl.Runtime.XmlExtensionFunctionTable System.Xml.Xsl.Runtime.XmlQueryContext::extFuncsLate
0x2f3c6  brtrue.s loc_2F3D3
0x2f3c8  ldarg.0
0x2f3c9  newobj   instance void System.Xml.Xsl.Runtime.XmlExtensionFunctionTable::.ctor()
0x2f3ce  stfld    class System.Xml.Xsl.Runtime.XmlExtensionFunctionTable System.Xml.Xsl.Runtime.XmlQueryContext::extFuncsLate
0x2f3d3  ldarg.0
0x2f3d4  ldfld    class System.Xml.Xsl.Runtime.XmlExtensionFunctionTable System.Xml.Xsl.Runtime.XmlQueryContext::extFuncsLate
0x2f3d9  ldarg.1
0x2f3da  ldarg.2
0x2f3db  ldarg.3
0x2f3dc  ldlen
0x2f3dd  conv.i4
0x2f3de  ldloc.0
0x2f3df  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2f3e4  ldc.i4.s 0x1C
0x2f3e6  callvirt instance class System.Xml.Xsl.Runtime.XmlExtensionFunction System.Xml.Xsl.Runtime.XmlExtensionFunctionTable::Bind(string name, string namespaceUri, int32 numArgs, class [mscorlib]System.Type objectType, valuetype [mscorlib]System.Reflection.BindingFlags flags)
0x2f3eb  stloc.s  5
0x2f3ed  ldarg.3
0x2f3ee  ldlen
0x2f3ef  conv.i4
0x2f3f0  newarr   [mscorlib]System.Object
0x2f3f5  stloc.1
0x2f3f6  ldc.i4.0
0x2f3f7  stloc.s  6
0x2f3f9  br       loc_2F4E1
0x2f3fe  ldloc.s  5
0x2f400  ldloc.s  6
0x2f402  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Runtime.XmlExtensionFunction::GetXmlArgumentType(int32 index)
0x2f407  stloc.2
0x2f408  ldloc.2
0x2f409  callvirt instance valuetype [System.Xml]System.Xml.Schema.XmlTypeCode System.Xml.Xsl.XmlQueryType::get_TypeCode()
0x2f40e  stloc.s  7
0x2f410  ldloc.s  7
0x2f412  ldc.i4.1
0x2f413  beq      loc_2F49A
0x2f418  ldloc.s  7
0x2f41a  ldc.i4.2
0x2f41b  beq.s    loc_2F474
0x2f41d  ldloc.s  7
0x2f41f  ldc.i4.s 0xC
0x2f421  sub
0x2f422  switch   loc_2F465, loc_2F43D, loc_2F4A2, loc_2F4A2, loc_2F451
0x2f43b  br.s     loc_2F4A2
0x2f43d  ldloc.1
0x2f43e  ldloc.s  6
0x2f440  ldarg.3
0x2f441  ldloc.s  6
0x2f443  ldelem.ref
0x2f444  call     bool System.Xml.Xsl.Runtime.XsltConvert::ToBoolean(class [mscorlib]System.Collections.Generic.IList`1<class [System.Xml]System.Xml.XPath.XPathItem> listItems)
0x2f449  box      [mscorlib]System.Boolean
0x2f44e  stelem.ref
0x2f44f  br.s     loc_2F4A2
0x2f451  ldloc.1
0x2f452  ldloc.s  6
0x2f454  ldarg.3
0x2f455  ldloc.s  6
0x2f457  ldelem.ref
0x2f458  call     float64 System.Xml.Xsl.Runtime.XsltConvert::ToDouble(class [mscorlib]System.Collections.Generic.IList`1<class [System.Xml]System.Xml.XPath.XPathItem> listItems)
0x2f45d  box      [mscorlib]System.Double
0x2f462  stelem.ref
0x2f463  br.s     loc_2F4A2
0x2f465  ldloc.1
0x2f466  ldloc.s  6
0x2f468  ldarg.3
0x2f469  ldloc.s  6
0x2f46b  ldelem.ref
0x2f46c  call     string System.Xml.Xsl.Runtime.XsltConvert::ToString(class [mscorlib]System.Collections.Generic.IList`1<class [System.Xml]System.Xml.XPath.XPathItem> listItems)
0x2f471  stelem.ref
0x2f472  br.s     loc_2F4A2
0x2f474  ldloc.2
0x2f475  callvirt instance bool System.Xml.Xsl.XmlQueryType::get_IsSingleton()
0x2f47a  brfalse.s loc_2F48B
0x2f47c  ldloc.1
0x2f47d  ldloc.s  6
0x2f47f  ldarg.3
0x2f480  ldloc.s  6
0x2f482  ldelem.ref
0x2f483  call     class [System.Xml]System.Xml.XPath.XPathNavigator System.Xml.Xsl.Runtime.XsltConvert::ToNode(class [mscorlib]System.Collections.Generic.IList`1<class [System.Xml]System.Xml.XPath.XPathItem> listItems)
0x2f488  stelem.ref
0x2f489  br.s     loc_2F4A2
0x2f48b  ldloc.1
0x2f48c  ldloc.s  6
0x2f48e  ldarg.3
0x2f48f  ldloc.s  6
0x2f491  ldelem.ref
0x2f492  call     class [mscorlib]System.Collections.Generic.IList`1<class [System.Xml]System.Xml.XPath.XPathNavigator> System.Xml.Xsl.Runtime.XsltConvert::ToNodeSet(class [mscorlib]System.Collections.Generic.IList`1<class [System.Xml]System.Xml.XPath.XPathItem> listItems)
0x2f497  stelem.ref
0x2f498  br.s     loc_2F4A2
0x2f49a  ldloc.1
0x2f49b  ldloc.s  6
0x2f49d  ldarg.3
0x2f49e  ldloc.s  6
0x2f4a0  ldelem.ref
0x2f4a1  stelem.ref
0x2f4a2  ldloc.s  5
0x2f4a4  ldloc.s  6
0x2f4a6  callvirt instance class [mscorlib]System.Type System.Xml.Xsl.Runtime.XmlExtensionFunction::GetClrArgumentType(int32 index)
0x2f4ab  stloc.3
0x2f4ac  ldloc.2
0x2f4ad  callvirt instance valuetype [System.Xml]System.Xml.Schema.XmlTypeCode System.Xml.Xsl.XmlQueryType::get_TypeCode()
0x2f4b2  ldc.i4.1
0x2f4b3  beq.s    loc_2F4C6
0x2f4b5  ldloc.3
0x2f4b6  ldloc.1
0x2f4b7  ldloc.s  6
0x2f4b9  ldelem.ref
0x2f4ba  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2f4bf  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0x2f4c4  brtrue.s loc_2F4DB
0x2f4c6  ldloc.1
0x2f4c7  ldloc.s  6
0x2f4c9  ldarg.0
0x2f4ca  ldfld    class System.Xml.Xsl.Runtime.XmlQueryRuntime System.Xml.Xsl.Runtime.XmlQueryContext::runtime
0x2f4cf  ldloc.2
0x2f4d0  ldloc.1
0x2f4d1  ldloc.s  6
0x2f4d3  ldelem.ref
0x2f4d4  ldloc.3
0x2f4d5  callvirt instance object System.Xml.Xsl.Runtime.XmlQueryRuntime::ChangeTypeXsltArgument(class System.Xml.Xsl.XmlQueryType xmlType, object value, class [mscorlib]System.Type destinationType)
0x2f4da  stelem.ref
0x2f4db  ldloc.s  6
0x2f4dd  ldc.i4.1
0x2f4de  add
0x2f4df  stloc.s  6
0x2f4e1  ldloc.s  6
0x2f4e3  ldarg.3
0x2f4e4  ldlen
0x2f4e5  conv.i4
0x2f4e6  blt      loc_2F3FE
0x2f4eb  ldloc.s  5
0x2f4ed  ldloc.0
0x2f4ee  ldloc.1
0x2f4ef  callvirt instance object System.Xml.Xsl.Runtime.XmlExtensionFunction::Invoke(object extObj, object[] args)
0x2f4f4  stloc.s  4
0x2f4f6  ldloc.s  4
0x2f4f8  brtrue.s loc_2F513
0x2f4fa  ldloc.s  5
0x2f4fc  callvirt instance class [mscorlib]System.Type System.Xml.Xsl.Runtime.XmlExtensionFunction::get_ClrReturnType()
0x2f501  ldsfld   class [mscorlib]System.Type System.Xml.Xsl.Runtime.XsltConvert::VoidType
0x2f506  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2f50b  brfalse.s loc_2F513
0x2f50d  ldsfld   class System.Xml.Xsl.Runtime.XmlQueryNodeSequence System.Xml.Xsl.Runtime.XmlQueryNodeSequence::Empty
0x2f512  ret
0x2f513  ldarg.0
0x2f514  ldfld    class System.Xml.Xsl.Runtime.XmlQueryRuntime System.Xml.Xsl.Runtime.XmlQueryContext::runtime
0x2f519  ldsfld   class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryTypeFactory::ItemS
0x2f51e  ldloc.s  4
0x2f520  callvirt instance object System.Xml.Xsl.Runtime.XmlQueryRuntime::ChangeTypeXsltResult(class System.Xml.Xsl.XmlQueryType xmlType, object value)
0x2f525  castclass class [mscorlib]System.Collections.Generic.IList`1<class [System.Xml]System.Xml.XPath.XPathItem>
0x2f52a  ret
```
