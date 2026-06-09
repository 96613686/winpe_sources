# System.Xml.Xsl.Xslt.QilGenerator::System.Xml.Xsl.XPath.IXPathEnvironment.ResolveFunction

- ea: `0x1a9a0`
- end: `0x1aeda`
- name: `System.Xml.Xsl.Xslt.QilGenerator::System.Xml.Xsl.XPath.IXPathEnvironment.ResolveFunction`
- size: `1338`
- prototype: ``
- caller_count: `0`
- callee_count: `32`
- tags: `registry_config, broker_com_uri`

## callees

- `0x3a50`
- `0x139d0`
- `0x1a6a0`
- `0x1a9a0`
- `0x1aee0`
- `0x1afe0`
- `0x1b310`
- `0x1b7d0`
- `0x1b9e0`
- `0x1bb70`
- `0x1bba0`
- `0x1bc30`
- `0x1bcc0`
- `0x1bd20`
- `0x1bdb0`
- `0x1bde0`
- `0x1c180`
- `0x1c190`
- `0x267c0`
- `0x26800`
- `0x26840`
- `0x26870`
- `0x268a0`
- `0x268d0`
- `0x26e20`
- `0x294a0`
- `0x295c0`
- `0x297d0`
- `0x37a20`
- `0x37a50`
- `0x37cb0`
- `0x38450`

## string_xrefs

- `0x1ab19`: `urn:schemas-microsoft-com:xslt`
- `0x1ad2f`: `namespace-uri`
- `0x1ab52`: `string-compare`
- `0x1ad9d`: `http://exslt.org/common`

## pseudocode

```c

```

## disassembly

```asm
0x1a9a0  ldarg.1
0x1a9a1  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1a9a6  brtrue   loc_1AB0F
0x1a9ab  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class FunctionInfo`1<valuetype FuncId>> System.Xml.Xsl.Xslt.QilGenerator::FunctionTable
0x1a9b0  ldarg.2
0x1a9b1  ldloca.s 0
0x1a9b3  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class FunctionInfo`1<valuetype FuncId>>::TryGetValue(var<u1>, !!T0)
0x1a9b8  brfalse  loc_1AAF4
0x1a9bd  ldloc.0
0x1a9be  ldarg.3
0x1a9bf  ldarg.2
0x1a9c0  ldarg.0
0x1a9c1  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1a9c6  callvirt instance void class FunctionInfo`1<valuetype FuncId>::CastArguments(class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode>, string, class System.Xml.Xsl.XPath.XPathQilFactory)
0x1a9cb  ldloc.0
0x1a9cc  ldfld    var<u1> class FunctionInfo`1<valuetype FuncId>::id
0x1a9d1  stloc.1
0x1a9d2  ldloc.1
0x1a9d3  switch   loc_1AA01, loc_1AA51, loc_1AA21, loc_1AA72, loc_1AA9A, loc_1AAA8, loc_1AAC8, loc_1AAD6, loc_1AAE4
0x1a9fc  br       loc_1AAF2
0x1aa01  ldarg.0
0x1aa02  ldfld    bool System.Xml.Xsl.Xslt.QilGenerator::allowCurrent
0x1aa07  brtrue.s loc_1AA1A
0x1aa09  ldstr    aXsltCurrentnot// "Xslt_CurrentNotAllowed"
0x1aa0e  ldc.i4.0
0x1aa0f  newarr   [mscorlib]System.String
0x1aa14  newobj   instance void System.Xml.Xsl.XslLoadException::.ctor(string res, string[] args)
0x1aa19  throw
0x1aa1a  ldarg.0
0x1aa1b  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.XPath.IFocus::GetCurrent()
0x1aa20  ret
0x1aa21  ldarg.0
0x1aa22  ldfld    bool System.Xml.Xsl.Xslt.QilGenerator::allowKey
0x1aa27  brtrue.s loc_1AA3A
0x1aa29  ldstr    aXsltKeynotallo// "Xslt_KeyNotAllowed"
0x1aa2e  ldc.i4.0
0x1aa2f  newarr   [mscorlib]System.String
0x1aa34  newobj   instance void System.Xml.Xsl.XslLoadException::.ctor(string res, string[] args)
0x1aa39  throw
0x1aa3a  ldarg.0
0x1aa3b  ldarg.3
0x1aa3c  ldc.i4.0
0x1aa3d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode>::get_Item(!!T0)
0x1aa42  ldarg.3
0x1aa43  ldc.i4.1
0x1aa44  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode>::get_Item(!!T0)
0x1aa49  ldarg.s  4
0x1aa4b  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::CompileFnKey(class System.Xml.Xsl.Qil.QilNode name, class System.Xml.Xsl.Qil.QilNode keys, class System.Xml.Xsl.XPath.IFocus env)
0x1aa50  ret
0x1aa51  ldarg.0
0x1aa52  ldarg.3
0x1aa53  ldc.i4.0
0x1aa54  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode>::get_Item(!!T0)
0x1aa59  ldarg.3
0x1aa5a  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class System.Xml.Xsl.Qil.QilNode>::get_Count()
0x1aa5f  ldc.i4.1
0x1aa60  bgt.s    loc_1AA65
0x1aa62  ldnull
0x1aa63  br.s     loc_1AA6C
0x1aa65  ldarg.3
0x1aa66  ldc.i4.1
0x1aa67  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode>::get_Item(!!T0)
0x1aa6c  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::CompileFnDocument(class System.Xml.Xsl.Qil.QilNode uris, class System.Xml.Xsl.Qil.QilNode baseNode)
0x1aa71  ret
0x1aa72  ldarg.0
0x1aa73  ldarg.3
0x1aa74  ldc.i4.0
0x1aa75  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode>::get_Item(!!T0)
0x1aa7a  ldarg.3
0x1aa7b  ldc.i4.1
0x1aa7c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode>::get_Item(!!T0)
0x1aa81  ldarg.3
0x1aa82  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class System.Xml.Xsl.Qil.QilNode>::get_Count()
0x1aa87  ldc.i4.2
0x1aa88  bgt.s    loc_1AA8D
0x1aa8a  ldnull
0x1aa8b  br.s     loc_1AA94
0x1aa8d  ldarg.3
0x1aa8e  ldc.i4.2
0x1aa8f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode>::get_Item(!!T0)
0x1aa94  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::CompileFormatNumber(class System.Xml.Xsl.Qil.QilNode value, class System.Xml.Xsl.Qil.QilNode formatPicture, class System.Xml.Xsl.Qil.QilNode formatName)
0x1aa99  ret
0x1aa9a  ldarg.0
0x1aa9b  ldarg.3
0x1aa9c  ldc.i4.0
0x1aa9d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode>::get_Item(!!T0)
0x1aaa2  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::CompileUnparsedEntityUri(class System.Xml.Xsl.Qil.QilNode n)
0x1aaa7  ret
0x1aaa8  ldarg.0
0x1aaa9  ldarg.3
0x1aaaa  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class System.Xml.Xsl.Qil.QilNode>::get_Count()
0x1aaaf  ldc.i4.0
0x1aab0  bgt.s    loc_1AABB
0x1aab2  ldarg.s  4
0x1aab4  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.XPath.IFocus::GetCurrent()
0x1aab9  br.s     loc_1AAC2
0x1aabb  ldarg.3
0x1aabc  ldc.i4.0
0x1aabd  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode>::get_Item(!!T0)
0x1aac2  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::CompileGenerateId(class System.Xml.Xsl.Qil.QilNode n)
0x1aac7  ret
0x1aac8  ldarg.0
0x1aac9  ldarg.3
0x1aaca  ldc.i4.0
0x1aacb  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode>::get_Item(!!T0)
0x1aad0  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::CompileSystemProperty(class System.Xml.Xsl.Qil.QilNode name)
0x1aad5  ret
0x1aad6  ldarg.0
0x1aad7  ldarg.3
0x1aad8  ldc.i4.0
0x1aad9  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode>::get_Item(!!T0)
0x1aade  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::CompileElementAvailable(class System.Xml.Xsl.Qil.QilNode name)
0x1aae3  ret
0x1aae4  ldarg.0
0x1aae5  ldarg.3
0x1aae6  ldc.i4.0
0x1aae7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode>::get_Item(!!T0)
0x1aaec  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::CompileFunctionAvailable(class System.Xml.Xsl.Qil.QilNode name)
0x1aaf1  ret
0x1aaf2  ldnull
0x1aaf3  ret
0x1aaf4  ldstr    aXsltUnknownxsl// "Xslt_UnknownXsltFunction"
0x1aaf9  ldc.i4.1
0x1aafa  newarr   [mscorlib]System.String
0x1aaff  dup
0x1ab00  ldc.i4.0
0x1ab01  ldarg.1
0x1ab02  ldarg.2
0x1ab03  call     string System.Xml.Xsl.Xslt.Compiler::ConstructQName(string prefix, string localName)
0x1ab08  stelem.ref
0x1ab09  newobj   instance void System.Xml.Xsl.XslLoadException::.ctor(string res, string[] args)
0x1ab0e  throw
0x1ab0f  ldarg.0
0x1ab10  ldc.i4.1
0x1ab11  ldarg.1
0x1ab12  call     instance string System.Xml.Xsl.Xslt.QilGenerator::ResolvePrefixThrow(bool ignoreDefaultNs, string prefix)
0x1ab17  stloc.2
0x1ab18  ldloc.2
0x1ab19  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:xslt"
0x1ab1e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1ab23  brfalse  loc_1AD9C
0x1ab28  ldarg.2
0x1ab29  ldstr    aNodeSet// "node-set"
0x1ab2e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1ab33  brfalse.s loc_1AB51
0x1ab35  ldc.i4.1
0x1ab36  ldc.i4.1
0x1ab37  ldarg.2
0x1ab38  ldarg.3
0x1ab39  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class System.Xml.Xsl.Qil.QilNode>::get_Count()
0x1ab3e  call     void class FunctionInfo`1<valuetype FuncId>::CheckArity(int32, int32, string, int32)
0x1ab43  ldarg.0
0x1ab44  ldarg.3
0x1ab45  ldc.i4.0
0x1ab46  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode>::get_Item(!!T0)
0x1ab4b  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::CompileMsNodeSet(class System.Xml.Xsl.Qil.QilNode n)
0x1ab50  ret
0x1ab51  ldarg.2
0x1ab52  ldstr    aStringCompare// "string-compare"
0x1ab57  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1ab5c  brfalse  loc_1ABF9
0x1ab61  ldc.i4.2
0x1ab62  ldc.i4.4
0x1ab63  ldarg.2
0x1ab64  ldarg.3
0x1ab65  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class System.Xml.Xsl.Qil.QilNode>::get_Count()
0x1ab6a  call     void class FunctionInfo`1<valuetype FuncId>::CheckArity(int32, int32, string, int32)
0x1ab6f  ldarg.0
0x1ab70  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1ab75  ldarg.0
0x1ab76  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1ab7b  ldarg.3
0x1ab7c  ldc.i4.0
0x1ab7d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode>::get_Item(!!T0)
0x1ab82  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.XPath.XPathQilFactory::ConvertToString(class System.Xml.Xsl.Qil.QilNode n)
0x1ab87  ldarg.0
0x1ab88  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1ab8d  ldarg.3
0x1ab8e  ldc.i4.1
0x1ab8f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode>::get_Item(!!T0)
0x1ab94  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.XPath.XPathQilFactory::ConvertToString(class System.Xml.Xsl.Qil.QilNode n)
0x1ab99  ldc.i4.2
0x1ab9a  ldarg.3
0x1ab9b  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class System.Xml.Xsl.Qil.QilNode>::get_Count()
0x1aba0  blt.s    loc_1ABB4
0x1aba2  ldarg.0
0x1aba3  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1aba8  ldsfld   string [mscorlib]System.String::Empty
0x1abad  callvirt instance class System.Xml.Xsl.Qil.QilLiteral System.Xml.Xsl.Qil.QilPatternFactory::String(string val)
0x1abb2  br.s     loc_1ABC6
0x1abb4  ldarg.0
0x1abb5  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1abba  ldarg.3
0x1abbb  ldc.i4.2
0x1abbc  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode>::get_Item(!!T0)
0x1abc1  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.XPath.XPathQilFactory::ConvertToString(class System.Xml.Xsl.Qil.QilNode n)
0x1abc6  ldc.i4.3
0x1abc7  ldarg.3
0x1abc8  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class System.Xml.Xsl.Qil.QilNode>::get_Count()
0x1abcd  blt.s    loc_1ABE1
0x1abcf  ldarg.0
0x1abd0  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1abd5  ldsfld   string [mscorlib]System.String::Empty
0x1abda  callvirt instance class System.Xml.Xsl.Qil.QilLiteral System.Xml.Xsl.Qil.QilPatternFactory::String(string val)
0x1abdf  br.s     loc_1ABF3
0x1abe1  ldarg.0
0x1abe2  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1abe7  ldarg.3
0x1abe8  ldc.i4.3
0x1abe9  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode>::get_Item(!!T0)
0x1abee  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.XPath.XPathQilFactory::ConvertToString(class System.Xml.Xsl.Qil.QilNode n)
0x1abf3  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.XsltQilFactory::InvokeMsStringCompare(class System.Xml.Xsl.Qil.QilNode x, class System.Xml.Xsl.Qil.QilNode y, class System.Xml.Xsl.Qil.QilNode lang, class System.Xml.Xsl.Qil.QilNode options)
0x1abf8  ret
0x1abf9  ldarg.2
0x1abfa  ldstr    aUtc// "utc"
0x1abff  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1ac04  brfalse.s loc_1AC32
0x1ac06  ldc.i4.1
0x1ac07  ldc.i4.1
0x1ac08  ldarg.2
0x1ac09  ldarg.3
0x1ac0a  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class System.Xml.Xsl.Qil.QilNode>::get_Count()
0x1ac0f  call     void class FunctionInfo`1<valuetype FuncId>::CheckArity(int32, int32, string, int32)
0x1ac14  ldarg.0
0x1ac15  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1ac1a  ldarg.0
0x1ac1b  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1ac20  ldarg.3
0x1ac21  ldc.i4.0
0x1ac22  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode>::get_Item(!!T0)
0x1ac27  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.XPath.XPathQilFactory::ConvertToString(class System.Xml.Xsl.Qil.QilNode n)
0x1ac2c  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.XsltQilFactory::InvokeMsUtc(class System.Xml.Xsl.Qil.QilNode n)
0x1ac31  ret
0x1ac32  ldarg.2
0x1ac33  ldstr    aFormatDate// "format-date"
0x1ac38  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1ac3d  brtrue.s loc_1AC4F
0x1ac3f  ldarg.2
0x1ac40  ldstr    aFormatTime// "format-time"
0x1ac45  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1ac4a  brfalse  loc_1ACF5
0x1ac4f  ldc.i4.1
0x1ac50  ldc.i4.3
0x1ac51  ldarg.2
0x1ac52  ldarg.3
0x1ac53  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class System.Xml.Xsl.Qil.QilNode>::get_Count()
0x1ac58  call     void class FunctionInfo`1<valuetype FuncId>::CheckArity(int32, int32, string, int32)
0x1ac5d  ldarg.0
0x1ac5e  ldfld    valuetype System.Xml.Xsl.Xslt.XslVersion System.Xml.Xsl.Xslt.QilGenerator::xslVersion
0x1ac63  ldc.i4.1
0x1ac64  ceq
0x1ac66  stloc.3
0x1ac67  ldarg.0
0x1ac68  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1ac6d  ldarg.0
0x1ac6e  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1ac73  ldarg.3
0x1ac74  ldc.i4.0
0x1ac75  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode>::get_Item(!!T0)
0x1ac7a  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.XPath.XPathQilFactory::ConvertToString(class System.Xml.Xsl.Qil.QilNode n)
0x1ac7f  ldc.i4.1
0x1ac80  ldarg.3
0x1ac81  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class System.Xml.Xsl.Qil.QilNode>::get_Count()
0x1ac86  blt.s    loc_1AC9A
0x1ac88  ldarg.0
0x1ac89  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1ac8e  ldsfld   string [mscorlib]System.String::Empty
0x1ac93  callvirt instance class System.Xml.Xsl.Qil.QilLiteral System.Xml.Xsl.Qil.QilPatternFactory::String(string val)
0x1ac98  br.s     loc_1ACAC
0x1ac9a  ldarg.0
0x1ac9b  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1aca0  ldarg.3
0x1aca1  ldc.i4.1
0x1aca2  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode>::get_Item(!!T0)
0x1aca7  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.XPath.XPathQilFactory::ConvertToString(class System.Xml.Xsl.Qil.QilNode n)
0x1acac  ldc.i4.2
0x1acad  ldarg.3
0x1acae  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class System.Xml.Xsl.Qil.QilNode>::get_Count()
0x1acb3  blt.s    loc_1ACC7
0x1acb5  ldarg.0
0x1acb6  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1acbb  ldsfld   string [mscorlib]System.String::Empty
0x1acc0  callvirt instance class System.Xml.Xsl.Qil.QilLiteral System.Xml.Xsl.Qil.QilPatternFactory::String(string val)
0x1acc5  br.s     loc_1ACD9
0x1acc7  ldarg.0
0x1acc8  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1accd  ldarg.3
0x1acce  ldc.i4.2
0x1accf  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode>::get_Item(!!T0)
0x1acd4  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.XPath.XPathQilFactory::ConvertToString(class System.Xml.Xsl.Qil.QilNode n)
0x1acd9  ldarg.0
0x1acda  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1acdf  ldarg.2
0x1ace0  ldstr    aFormatDate// "format-date"
0x1ace5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1acea  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::Boolean(bool b)
0x1acef  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.XsltQilFactory::InvokeMsFormatDateTime(class System.Xml.Xsl.Qil.QilNode datetime, class System.Xml.Xsl.Qil.QilNode format, class System.Xml.Xsl.Qil.QilNode lang, class System.Xml.Xsl.Qil.QilNode isDate)
0x1acf4  ret
0x1acf5  ldarg.2
0x1acf6  ldstr    aLocalName// "local-name"
  ... truncated ...
```
