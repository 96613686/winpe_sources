# System.Xml.Xsl.XsltOld.XsltCompileContext::FunctionAvailable

- ea: `0x12c30`
- end: `0x12e2a`
- name: `System.Xml.Xsl.XsltOld.XsltCompileContext::FunctionAvailable`
- size: `506`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x55770`

## callees

- `0xc100`
- `0x126e0`
- `0x12c30`

## string_xrefs

- `0x12c43`: `urn:schemas-microsoft-com:xslt`
- `0x12c97`: `namespace-uri`
- `0x12e0c`: `unparsed-entity-uri`

## pseudocode

```c

```

## disassembly

```asm
0x12c30  ldarg.1
0x12c31  ldloca.s 1
0x12c33  ldloca.s 0
0x12c35  call     void System.Xml.Xsl.XsltOld.PrefixQName::ParseQualifiedName(string qname, [out] string& prefix, [out] string& local)
0x12c3a  ldarg.0
0x12c3b  ldloc.1
0x12c3c  callvirt instance string [System.Xml]System.Xml.XmlNamespaceManager::LookupNamespace(string)
0x12c41  stloc.2
0x12c42  ldloc.2
0x12c43  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:xslt"
0x12c48  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12c4d  brfalse.s loc_12C5B
0x12c4f  ldloc.0
0x12c50  ldstr    aNodeSet// "node-set"
0x12c55  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12c5a  ret
0x12c5b  ldloc.2
0x12c5c  callvirt instance int32 [mscorlib]System.String::get_Length()
0x12c61  brtrue   loc_12E1B
0x12c66  ldloc.0
0x12c67  ldstr    aLast// "last"
0x12c6c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12c71  brtrue   loc_12E19
0x12c76  ldloc.0
0x12c77  ldstr    aPosition// "position"
0x12c7c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12c81  brtrue   loc_12E19
0x12c86  ldloc.0
0x12c87  ldstr    aName// "name"
0x12c8c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12c91  brtrue   loc_12E19
0x12c96  ldloc.0
0x12c97  ldstr    aNamespaceUri// "namespace-uri"
0x12c9c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12ca1  brtrue   loc_12E19
0x12ca6  ldloc.0
0x12ca7  ldstr    aLocalName// "local-name"
0x12cac  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12cb1  brtrue   loc_12E19
0x12cb6  ldloc.0
0x12cb7  ldstr    aCount// "count"
0x12cbc  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12cc1  brtrue   loc_12E19
0x12cc6  ldloc.0
0x12cc7  ldstr    aId// "id"
0x12ccc  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12cd1  brtrue   loc_12E19
0x12cd6  ldloc.0
0x12cd7  ldstr    aString_0// "string"
0x12cdc  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12ce1  brtrue   loc_12E19
0x12ce6  ldloc.0
0x12ce7  ldstr    aConcat// "concat"
0x12cec  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12cf1  brtrue   loc_12E19
0x12cf6  ldloc.0
0x12cf7  ldstr    aStartsWith// "starts-with"
0x12cfc  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12d01  brtrue   loc_12E19
0x12d06  ldloc.0
0x12d07  ldstr    aContains// "contains"
0x12d0c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12d11  brtrue   loc_12E19
0x12d16  ldloc.0
0x12d17  ldstr    aSubstringBefor// "substring-before"
0x12d1c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12d21  brtrue   loc_12E19
0x12d26  ldloc.0
0x12d27  ldstr    aSubstringAfter// "substring-after"
0x12d2c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12d31  brtrue   loc_12E19
0x12d36  ldloc.0
0x12d37  ldstr    aSubstring// "substring"
0x12d3c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12d41  brtrue   loc_12E19
0x12d46  ldloc.0
0x12d47  ldstr    aStringLength// "string-length"
0x12d4c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12d51  brtrue   loc_12E19
0x12d56  ldloc.0
0x12d57  ldstr    aNormalizeSpace// "normalize-space"
0x12d5c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12d61  brtrue   loc_12E19
0x12d66  ldloc.0
0x12d67  ldstr    aTranslate// "translate"
0x12d6c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12d71  brtrue   loc_12E19
0x12d76  ldloc.0
0x12d77  ldstr    aBoolean_0// "boolean"
0x12d7c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12d81  brtrue   loc_12E19
0x12d86  ldloc.0
0x12d87  ldstr    aNot// "not"
0x12d8c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12d91  brtrue   loc_12E19
0x12d96  ldloc.0
0x12d97  ldstr    aTrue// "true"
0x12d9c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12da1  brtrue.s loc_12E19
0x12da3  ldloc.0
0x12da4  ldstr    aFalse// "false"
0x12da9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12dae  brtrue.s loc_12E19
0x12db0  ldloc.0
0x12db1  ldstr    aLang// "lang"
0x12db6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12dbb  brtrue.s loc_12E19
0x12dbd  ldloc.0
0x12dbe  ldstr    aNumber// "number"
0x12dc3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12dc8  brtrue.s loc_12E19
0x12dca  ldloc.0
0x12dcb  ldstr    aSum// "sum"
0x12dd0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12dd5  brtrue.s loc_12E19
0x12dd7  ldloc.0
0x12dd8  ldstr    aFloor// "floor"
0x12ddd  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12de2  brtrue.s loc_12E19
0x12de4  ldloc.0
0x12de5  ldstr    aCeiling// "ceiling"
0x12dea  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12def  brtrue.s loc_12E19
0x12df1  ldloc.0
0x12df2  ldstr    aRound// "round"
0x12df7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12dfc  brtrue.s loc_12E19
0x12dfe  ldsfld   class [mscorlib]System.Collections.Hashtable System.Xml.Xsl.XsltOld.XsltCompileContext::s_FunctionTable
0x12e03  ldloc.0
0x12e04  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x12e09  brfalse.s loc_12E17
0x12e0b  ldloc.0
0x12e0c  ldstr    aUnparsedEntity// "unparsed-entity-uri"
0x12e11  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x12e16  ret
0x12e17  ldc.i4.0
0x12e18  ret
0x12e19  ldc.i4.1
0x12e1a  ret
0x12e1b  ldarg.0
0x12e1c  ldloc.2
0x12e1d  ldloc.0
0x12e1e  ldnull
0x12e1f  ldloca.s 3
0x12e21  call     instance class [System.Xml]System.Xml.Xsl.IXsltContextFunction System.Xml.Xsl.XsltOld.XsltCompileContext::GetExtentionMethod(string ns, string name, valuetype [System.Xml]System.Xml.XPath.XPathResultType[] argTypes, [out] object& extension)
0x12e26  ldnull
0x12e27  cgt.un
0x12e29  ret
```
