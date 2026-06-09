# System.Xml.Xsl.Xslt.QilGenerator::IsFunctionAvailable

- ea: `0x1b110`
- end: `0x1b1de`
- name: `System.Xml.Xsl.Xslt.QilGenerator::IsFunctionAvailable`
- size: `206`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1bd20`
- `0x35210`

## callees

- `0x1b110`
- `0x284e0`

## string_xrefs

- `0x1b13f`: `urn:schemas-microsoft-com:xslt`
- `0x1b180`: `namespace-uri`
- `0x1b131`: `unparsed-entity-uri`
- `0x1b19a`: `string-compare`
- `0x1b1b5`: `http://exslt.org/common`

## pseudocode

```c

```

## disassembly

```asm
0x1b110  ldarg.0
0x1b111  ldarg.1
0x1b112  call     bool System.Xml.Xsl.XPath.XPathBuilder::IsFunctionAvailable(string localName, string nsUri)
0x1b117  brfalse.s loc_1B11B
0x1b119  ldc.i4.1
0x1b11a  ret
0x1b11b  ldarg.1
0x1b11c  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1b121  brtrue.s loc_1B13E
0x1b123  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class FunctionInfo`1<valuetype FuncId>> System.Xml.Xsl.Xslt.QilGenerator::FunctionTable
0x1b128  ldarg.0
0x1b129  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class FunctionInfo`1<valuetype FuncId>>::ContainsKey(var<u1>)
0x1b12e  brfalse.s loc_1B13C
0x1b130  ldarg.0
0x1b131  ldstr    aUnparsedEntity// "unparsed-entity-uri"
0x1b136  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x1b13b  ret
0x1b13c  ldc.i4.0
0x1b13d  ret
0x1b13e  ldarg.1
0x1b13f  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:xslt"
0x1b144  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b149  brfalse.s loc_1B1B4
0x1b14b  ldarg.0
0x1b14c  ldstr    aNodeSet// "node-set"
0x1b151  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b156  brtrue.s loc_1B1B2
0x1b158  ldarg.0
0x1b159  ldstr    aFormatDate// "format-date"
0x1b15e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b163  brtrue.s loc_1B1B2
0x1b165  ldarg.0
0x1b166  ldstr    aFormatTime// "format-time"
0x1b16b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b170  brtrue.s loc_1B1B2
0x1b172  ldarg.0
0x1b173  ldstr    aLocalName// "local-name"
0x1b178  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b17d  brtrue.s loc_1B1B2
0x1b17f  ldarg.0
0x1b180  ldstr    aNamespaceUri// "namespace-uri"
0x1b185  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b18a  brtrue.s loc_1B1B2
0x1b18c  ldarg.0
0x1b18d  ldstr    aNumber// "number"
0x1b192  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b197  brtrue.s loc_1B1B2
0x1b199  ldarg.0
0x1b19a  ldstr    aStringCompare// "string-compare"
0x1b19f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b1a4  brtrue.s loc_1B1B2
0x1b1a6  ldarg.0
0x1b1a7  ldstr    aUtc// "utc"
0x1b1ac  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b1b1  ret
0x1b1b2  ldc.i4.1
0x1b1b3  ret
0x1b1b4  ldarg.1
0x1b1b5  ldstr    aHttpExsltOrgCo// "http://exslt.org/common"
0x1b1ba  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b1bf  brfalse.s loc_1B1DC
0x1b1c1  ldarg.0
0x1b1c2  ldstr    aNodeSet// "node-set"
0x1b1c7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b1cc  brtrue.s loc_1B1DA
0x1b1ce  ldarg.0
0x1b1cf  ldstr    aObjectType// "object-type"
0x1b1d4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b1d9  ret
0x1b1da  ldc.i4.1
0x1b1db  ret
0x1b1dc  ldc.i4.0
0x1b1dd  ret
```
