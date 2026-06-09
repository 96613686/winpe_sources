# System.Xml.Xsl.Xslt.XsltLoader::.ctor

- ea: `0x25610`
- end: `0x263bd`
- name: `System.Xml.Xsl.Xslt.XsltLoader::.ctor`
- size: `3501`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x13750`

## callees

- `0x56c40`

## string_xrefs

- `0x2581b`: `omit-xml-declaration`
- `0x2579d`: `escape-uri-attributes`
- `0x25c9a`: `copy-namespaces`
- `0x25d36`: `copy-namespaces`

## pseudocode

```c

```

## disassembly

```asm
0x25610  ldarg.0
0x25611  newobj   instance void [System]System.Collections.Specialized.HybridDictionary::.ctor()
0x25616  stfld    class [System]System.Collections.Specialized.HybridDictionary System.Xml.Xsl.Xslt.XsltLoader::documentUriInUse
0x2561b  ldarg.0
0x2561c  ldc.i4.4
0x2561d  newarr   XsltAttribute
0x25622  dup
0x25623  ldc.i4.0
0x25624  ldstr    aVersion// "version"
0x25629  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V1Req
0x2562e  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V2Req
0x25633  or
0x25634  newobj   instance void XsltAttribute::.ctor(string name, int32 flags)
0x25639  stelem   XsltAttribute
0x2563e  dup
0x2563f  ldc.i4.1
0x25640  ldstr    aId// "id"
0x25645  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V1Opt
0x2564a  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V2Opt
0x2564f  or
0x25650  newobj   instance void XsltAttribute::.ctor(string name, int32 flags)
0x25655  stelem   XsltAttribute
0x2565a  dup
0x2565b  ldc.i4.2
0x2565c  ldstr    aDefaultValidat// "default-validation"
0x25661  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V2Opt
0x25666  newobj   instance void XsltAttribute::.ctor(string name, int32 flags)
0x2566b  stelem   XsltAttribute
0x25670  dup
0x25671  ldc.i4.3
0x25672  ldstr    aInputTypeAnnot// "input-type-annotations"
0x25677  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V2Opt
0x2567c  newobj   instance void XsltAttribute::.ctor(string name, int32 flags)
0x25681  stelem   XsltAttribute
0x25686  stfld    valuetype XsltAttribute[] System.Xml.Xsl.Xslt.XsltLoader::stylesheetAttributes
0x2568b  ldarg.0
0x2568c  ldc.i4.1
0x2568d  newarr   XsltAttribute
0x25692  dup
0x25693  ldc.i4.0
0x25694  ldstr    aHref// "href"
0x25699  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V1Req
0x2569e  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V2Req
0x256a3  or
0x256a4  newobj   instance void XsltAttribute::.ctor(string name, int32 flags)
0x256a9  stelem   XsltAttribute
0x256ae  stfld    valuetype XsltAttribute[] System.Xml.Xsl.Xslt.XsltLoader::importIncludeAttributes
0x256b3  ldarg.0
0x256b4  ldc.i4.1
0x256b5  newarr   XsltAttribute
0x256ba  dup
0x256bb  ldc.i4.0
0x256bc  ldstr    aElements// "elements"
0x256c1  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V1Req
0x256c6  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V2Req
0x256cb  or
0x256cc  newobj   instance void XsltAttribute::.ctor(string name, int32 flags)
0x256d1  stelem   XsltAttribute
0x256d6  stfld    valuetype XsltAttribute[] System.Xml.Xsl.Xslt.XsltLoader::loadStripSpaceAttributes
0x256db  ldarg.0
0x256dc  ldc.i4.s 0x11
0x256de  newarr   XsltAttribute
0x256e3  dup
0x256e4  ldc.i4.0
0x256e5  ldstr    aName// "name"
0x256ea  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V2Opt
0x256ef  newobj   instance void XsltAttribute::.ctor(string name, int32 flags)
0x256f4  stelem   XsltAttribute
0x256f9  dup
0x256fa  ldc.i4.1
0x256fb  ldstr    aMethod// "method"
0x25700  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V1Opt
0x25705  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V2Opt
0x2570a  or
0x2570b  newobj   instance void XsltAttribute::.ctor(string name, int32 flags)
0x25710  stelem   XsltAttribute
0x25715  dup
0x25716  ldc.i4.2
0x25717  ldstr    aByteOrderMark// "byte-order-mark"
0x2571c  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V2Opt
0x25721  newobj   instance void XsltAttribute::.ctor(string name, int32 flags)
0x25726  stelem   XsltAttribute
0x2572b  dup
0x2572c  ldc.i4.3
0x2572d  ldstr    aCdataSectionEl// "cdata-section-elements"
0x25732  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V1Opt
0x25737  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V2Opt
0x2573c  or
0x2573d  newobj   instance void XsltAttribute::.ctor(string name, int32 flags)
0x25742  stelem   XsltAttribute
0x25747  dup
0x25748  ldc.i4.4
0x25749  ldstr    aDoctypePublic// "doctype-public"
0x2574e  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V1Opt
0x25753  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V2Opt
0x25758  or
0x25759  newobj   instance void XsltAttribute::.ctor(string name, int32 flags)
0x2575e  stelem   XsltAttribute
0x25763  dup
0x25764  ldc.i4.5
0x25765  ldstr    aDoctypeSystem// "doctype-system"
0x2576a  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V1Opt
0x2576f  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V2Opt
0x25774  or
0x25775  newobj   instance void XsltAttribute::.ctor(string name, int32 flags)
0x2577a  stelem   XsltAttribute
0x2577f  dup
0x25780  ldc.i4.6
0x25781  ldstr    aEncoding_0// "encoding"
0x25786  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V1Opt
0x2578b  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V2Opt
0x25790  or
0x25791  newobj   instance void XsltAttribute::.ctor(string name, int32 flags)
0x25796  stelem   XsltAttribute
0x2579b  dup
0x2579c  ldc.i4.7
0x2579d  ldstr    aEscapeUriAttri// "escape-uri-attributes"
0x257a2  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V2Opt
0x257a7  newobj   instance void XsltAttribute::.ctor(string name, int32 flags)
0x257ac  stelem   XsltAttribute
0x257b1  dup
0x257b2  ldc.i4.8
0x257b3  ldstr    aIncludeContent// "include-content-type"
0x257b8  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V2Opt
0x257bd  newobj   instance void XsltAttribute::.ctor(string name, int32 flags)
0x257c2  stelem   XsltAttribute
0x257c7  dup
0x257c8  ldc.i4.s 9
0x257ca  ldstr    aIndent// "indent"
0x257cf  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V1Opt
0x257d4  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V2Opt
0x257d9  or
0x257da  newobj   instance void XsltAttribute::.ctor(string name, int32 flags)
0x257df  stelem   XsltAttribute
0x257e4  dup
0x257e5  ldc.i4.s 0xA
0x257e7  ldstr    aMediaType// "media-type"
0x257ec  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V1Opt
0x257f1  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V2Opt
0x257f6  or
0x257f7  newobj   instance void XsltAttribute::.ctor(string name, int32 flags)
0x257fc  stelem   XsltAttribute
0x25801  dup
0x25802  ldc.i4.s 0xB
0x25804  ldstr    aNormalizationF// "normalization-form"
0x25809  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V2Opt
0x2580e  newobj   instance void XsltAttribute::.ctor(string name, int32 flags)
0x25813  stelem   XsltAttribute
0x25818  dup
0x25819  ldc.i4.s 0xC
0x2581b  ldstr    aOmitXmlDeclara// "omit-xml-declaration"
0x25820  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V1Opt
0x25825  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V2Opt
0x2582a  or
0x2582b  newobj   instance void XsltAttribute::.ctor(string name, int32 flags)
0x25830  stelem   XsltAttribute
0x25835  dup
0x25836  ldc.i4.s 0xD
0x25838  ldstr    aStandalone_0// "standalone"
0x2583d  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V1Opt
0x25842  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V2Opt
0x25847  or
0x25848  newobj   instance void XsltAttribute::.ctor(string name, int32 flags)
0x2584d  stelem   XsltAttribute
0x25852  dup
0x25853  ldc.i4.s 0xE
0x25855  ldstr    aUndeclarePrefi// "undeclare-prefixes"
0x2585a  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V2Opt
0x2585f  newobj   instance void XsltAttribute::.ctor(string name, int32 flags)
0x25864  stelem   XsltAttribute
0x25869  dup
0x2586a  ldc.i4.s 0xF
0x2586c  ldstr    aUseCharacterMa// "use-character-maps"
0x25871  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V2Opt
0x25876  newobj   instance void XsltAttribute::.ctor(string name, int32 flags)
0x2587b  stelem   XsltAttribute
0x25880  dup
0x25881  ldc.i4.s 0x10
0x25883  ldstr    aVersion// "version"
0x25888  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V1Opt
0x2588d  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V2Opt
0x25892  or
0x25893  newobj   instance void XsltAttribute::.ctor(string name, int32 flags)
0x25898  stelem   XsltAttribute
0x2589d  stfld    valuetype XsltAttribute[] System.Xml.Xsl.Xslt.XsltLoader::outputAttributes
0x258a2  ldarg.0
0x258a3  ldc.i4.4
0x258a4  newarr   XsltAttribute
0x258a9  dup
0x258aa  ldc.i4.0
0x258ab  ldstr    aName// "name"
0x258b0  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V1Req
0x258b5  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V2Req
0x258ba  or
0x258bb  newobj   instance void XsltAttribute::.ctor(string name, int32 flags)
0x258c0  stelem   XsltAttribute
0x258c5  dup
0x258c6  ldc.i4.1
0x258c7  ldstr    aMatch// "match"
0x258cc  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V1Req
0x258d1  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V2Req
0x258d6  or
0x258d7  newobj   instance void XsltAttribute::.ctor(string name, int32 flags)
0x258dc  stelem   XsltAttribute
0x258e1  dup
0x258e2  ldc.i4.2
0x258e3  ldstr    aUse// "use"
0x258e8  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V1Req
0x258ed  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V2Opt
0x258f2  or
0x258f3  newobj   instance void XsltAttribute::.ctor(string name, int32 flags)
0x258f8  stelem   XsltAttribute
0x258fd  dup
0x258fe  ldc.i4.3
0x258ff  ldstr    aCollation// "collation"
0x25904  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V2Opt
0x25909  newobj   instance void XsltAttribute::.ctor(string name, int32 flags)
0x2590e  stelem   XsltAttribute
0x25913  stfld    valuetype XsltAttribute[] System.Xml.Xsl.Xslt.XsltLoader::keyAttributes
0x25918  ldarg.0
0x25919  ldc.i4.s 0xB
0x2591b  newarr   XsltAttribute
0x25920  dup
0x25921  ldc.i4.0
0x25922  ldstr    aName// "name"
0x25927  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V1Opt
0x2592c  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V2Opt
0x25931  or
0x25932  newobj   instance void XsltAttribute::.ctor(string name, int32 flags)
0x25937  stelem   XsltAttribute
0x2593c  dup
0x2593d  ldc.i4.1
0x2593e  ldstr    aInfinity_1// "infinity"
0x25943  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V1Opt
0x25948  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V2Opt
0x2594d  or
0x2594e  newobj   instance void XsltAttribute::.ctor(string name, int32 flags)
0x25953  stelem   XsltAttribute
0x25958  dup
0x25959  ldc.i4.2
0x2595a  ldstr    aNan// "NaN"
0x2595f  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V1Opt
0x25964  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V2Opt
0x25969  or
0x2596a  newobj   instance void XsltAttribute::.ctor(string name, int32 flags)
0x2596f  stelem   XsltAttribute
0x25974  dup
0x25975  ldc.i4.3
0x25976  ldstr    aDecimalSeparat// "decimal-separator"
0x2597b  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V1Opt
0x25980  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V2Opt
0x25985  or
0x25986  newobj   instance void XsltAttribute::.ctor(string name, int32 flags)
0x2598b  stelem   XsltAttribute
0x25990  dup
0x25991  ldc.i4.4
0x25992  ldstr    aGroupingSepara// "grouping-separator"
0x25997  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V1Opt
0x2599c  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V2Opt
0x259a1  or
0x259a2  newobj   instance void XsltAttribute::.ctor(string name, int32 flags)
0x259a7  stelem   XsltAttribute
0x259ac  dup
0x259ad  ldc.i4.5
0x259ae  ldstr    aPercent// "percent"
0x259b3  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V1Opt
0x259b8  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V2Opt
0x259bd  or
0x259be  newobj   instance void XsltAttribute::.ctor(string name, int32 flags)
0x259c3  stelem   XsltAttribute
0x259c8  dup
0x259c9  ldc.i4.6
0x259ca  ldstr    aPerMille// "per-mille"
0x259cf  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V1Opt
0x259d4  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V2Opt
0x259d9  or
0x259da  newobj   instance void XsltAttribute::.ctor(string name, int32 flags)
0x259df  stelem   XsltAttribute
0x259e4  dup
0x259e5  ldc.i4.7
0x259e6  ldstr    aZeroDigit// "zero-digit"
0x259eb  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V1Opt
0x259f0  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V2Opt
0x259f5  or
0x259f6  newobj   instance void XsltAttribute::.ctor(string name, int32 flags)
0x259fb  stelem   XsltAttribute
0x25a00  dup
0x25a01  ldc.i4.8
0x25a02  ldstr    aDigit// "digit"
0x25a07  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V1Opt
0x25a0c  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V2Opt
0x25a11  or
0x25a12  newobj   instance void XsltAttribute::.ctor(string name, int32 flags)
0x25a17  stelem   XsltAttribute
0x25a1c  dup
0x25a1d  ldc.i4.s 9
0x25a1f  ldstr    aPatternSeparat// "pattern-separator"
0x25a24  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V1Opt
0x25a29  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V2Opt
0x25a2e  or
  ... truncated ...
```
