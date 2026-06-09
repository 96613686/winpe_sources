# System.Xml.Xsl.XsltOld.XsltCompileContext::ResolveFunction

- ea: `0x12780`
- end: `0x12843`
- name: `System.Xml.Xsl.XsltOld.XsltCompileContext::ResolveFunction`
- size: `195`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x126e0`
- `0x12780`

## string_xrefs

- `0x127a6`: `urn:schemas-microsoft-com:xslt`

## pseudocode

```c

```

## disassembly

```asm
0x12780  ldnull
0x12781  stloc.0
0x12782  ldarg.1
0x12783  callvirt instance int32 [mscorlib]System.String::get_Length()
0x12788  brtrue.s loc_1279D
0x1278a  ldsfld   class [mscorlib]System.Collections.Hashtable System.Xml.Xsl.XsltOld.XsltCompileContext::s_FunctionTable
0x1278f  ldarg.2
0x12790  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x12795  isinst   [System.Xml]System.Xml.Xsl.IXsltContextFunction
0x1279a  stloc.0
0x1279b  br.s     loc_127EB
0x1279d  ldarg.0
0x1279e  ldarg.1
0x1279f  callvirt instance string [System.Xml]System.Xml.XmlNamespaceManager::LookupNamespace(string)
0x127a4  stloc.1
0x127a5  ldloc.1
0x127a6  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:xslt"
0x127ab  call     bool [mscorlib]System.String::op_Equality(string, string)
0x127b0  brfalse.s loc_127C7
0x127b2  ldarg.2
0x127b3  ldstr    aNodeSet// "node-set"
0x127b8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x127bd  brfalse.s loc_127C7
0x127bf  ldsfld   class [System.Xml]System.Xml.Xsl.IXsltContextFunction System.Xml.Xsl.XsltOld.XsltCompileContext::s_FuncNodeSet
0x127c4  stloc.0
0x127c5  br.s     loc_127EB
0x127c7  ldarg.0
0x127c8  ldloc.1
0x127c9  ldarg.2
0x127ca  ldarg.3
0x127cb  ldloca.s 2
0x127cd  call     instance class [System.Xml]System.Xml.Xsl.IXsltContextFunction System.Xml.Xsl.XsltOld.XsltCompileContext::GetExtentionMethod(string ns, string name, valuetype [System.Xml]System.Xml.XPath.XPathResultType[] argTypes, [out] object& extension)
0x127d2  stloc.0
0x127d3  ldloc.2
0x127d4  brtrue.s loc_127EB
0x127d6  ldstr    aXsltScriptinva_0// "Xslt_ScriptInvalidPrefix"
0x127db  ldc.i4.1
0x127dc  newarr   [mscorlib]System.String
0x127e1  dup
0x127e2  ldc.i4.0
0x127e3  ldarg.1
0x127e4  stelem.ref
0x127e5  call     class [System.Xml]System.Xml.Xsl.XsltException [System.Xml]System.Xml.Xsl.XsltException::Create(string, string[])
0x127ea  throw
0x127eb  ldloc.0
0x127ec  brtrue.s loc_12803
0x127ee  ldstr    aXsltUnknownxsl// "Xslt_UnknownXsltFunction"
0x127f3  ldc.i4.1
0x127f4  newarr   [mscorlib]System.String
0x127f9  dup
0x127fa  ldc.i4.0
0x127fb  ldarg.2
0x127fc  stelem.ref
0x127fd  call     class [System.Xml]System.Xml.Xsl.XsltException [System.Xml]System.Xml.Xsl.XsltException::Create(string, string[])
0x12802  throw
0x12803  ldarg.3
0x12804  ldlen
0x12805  conv.i4
0x12806  ldloc.0
0x12807  callvirt instance int32 [System.Xml]System.Xml.Xsl.IXsltContextFunction::get_Minargs()
0x1280c  blt.s    loc_12819
0x1280e  ldloc.0
0x1280f  callvirt instance int32 [System.Xml]System.Xml.Xsl.IXsltContextFunction::get_Maxargs()
0x12814  ldarg.3
0x12815  ldlen
0x12816  conv.i4
0x12817  bge.s    loc_12841
0x12819  ldstr    aXsltWrongnumbe// "Xslt_WrongNumberArgs"
0x1281e  ldc.i4.2
0x1281f  newarr   [mscorlib]System.String
0x12824  dup
0x12825  ldc.i4.0
0x12826  ldarg.2
0x12827  stelem.ref
0x12828  dup
0x12829  ldc.i4.1
0x1282a  ldarg.3
0x1282b  ldlen
0x1282c  conv.i4
0x1282d  stloc.3
0x1282e  ldloca.s 3
0x12830  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x12835  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1283a  stelem.ref
0x1283b  call     class [System.Xml]System.Xml.Xsl.XsltException [System.Xml]System.Xml.Xsl.XsltException::Create(string, string[])
0x12840  throw
0x12841  ldloc.0
0x12842  ret
```
