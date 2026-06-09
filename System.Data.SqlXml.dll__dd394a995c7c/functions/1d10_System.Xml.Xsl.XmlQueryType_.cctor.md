# System.Xml.Xsl.XmlQueryType::.cctor

- ea: `0x1d10`
- end: `0x1f77`
- name: `System.Xml.Xsl.XmlQueryType::.cctor`
- size: `615`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1d10`
- `0x50b40`
- `0x50b80`

## string_xrefs

- `0x1d87`: `comment`
- `0x1e3b`: `xs:anyUri`
- `0x1e5f`: `xs:token`
- `0x1e71`: `xs:NMTOKEN`

## pseudocode

```c

```

## disassembly

```asm
0x1d10  ldc.i4.s 0x37
0x1d12  newarr   TypeFlags
0x1d17  dup
0x1d18  ldtoken  valuetype __StaticArrayInitTypeSize=220 <PrivateImplementationDetails>::'7046613AF72F42CEDD96B1CB3A3C6227B6898D0E3C7249636D99561247639B7A'
0x1d1d  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::InitializeArray(class [mscorlib]System.Array, valuetype [mscorlib]System.RuntimeFieldHandle)
0x1d22  stsfld   valuetype TypeFlags[] System.Xml.Xsl.XmlQueryType::TypeCodeToFlags
0x1d27  ldc.i4.s 0x37
0x1d29  newarr   [System.Xml]System.Xml.Schema.XmlTypeCode
0x1d2e  dup
0x1d2f  ldtoken  valuetype __StaticArrayInitTypeSize=220 <PrivateImplementationDetails>::'84D6377D5BCC7596352F207CD6257687D56FA1AABBE6B2287F5EF0149221F847'
0x1d34  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::InitializeArray(class [mscorlib]System.Array, valuetype [mscorlib]System.RuntimeFieldHandle)
0x1d39  stsfld   valuetype [System.Xml]System.Xml.Schema.XmlTypeCode[] System.Xml.Xsl.XmlQueryType::BaseTypeCodes
0x1d3e  ldc.i4.s 0x37
0x1d40  newarr   [mscorlib]System.String
0x1d45  dup
0x1d46  ldc.i4.0
0x1d47  ldstr    aNone_0// "none"
0x1d4c  stelem.ref
0x1d4d  dup
0x1d4e  ldc.i4.1
0x1d4f  ldstr    aItem// "item"
0x1d54  stelem.ref
0x1d55  dup
0x1d56  ldc.i4.2
0x1d57  ldstr    aNode// "node"
0x1d5c  stelem.ref
0x1d5d  dup
0x1d5e  ldc.i4.3
0x1d5f  ldstr    aDocument// "document"
0x1d64  stelem.ref
0x1d65  dup
0x1d66  ldc.i4.4
0x1d67  ldstr    aElement// "element"
0x1d6c  stelem.ref
0x1d6d  dup
0x1d6e  ldc.i4.5
0x1d6f  ldstr    aAttribute// "attribute"
0x1d74  stelem.ref
0x1d75  dup
0x1d76  ldc.i4.6
0x1d77  ldstr    aNamespace// "namespace"
0x1d7c  stelem.ref
0x1d7d  dup
0x1d7e  ldc.i4.7
0x1d7f  ldstr    aProcessingInst// "processing-instruction"
0x1d84  stelem.ref
0x1d85  dup
0x1d86  ldc.i4.8
0x1d87  ldstr    aComment// "comment"
0x1d8c  stelem.ref
0x1d8d  dup
0x1d8e  ldc.i4.s 9
0x1d90  ldstr    aText// "text"
0x1d95  stelem.ref
0x1d96  dup
0x1d97  ldc.i4.s 0xA
0x1d99  ldstr    aXdtAnyatomicty// "xdt:anyAtomicType"
0x1d9e  stelem.ref
0x1d9f  dup
0x1da0  ldc.i4.s 0xB
0x1da2  ldstr    aXdtUntypedatom// "xdt:untypedAtomic"
0x1da7  stelem.ref
0x1da8  dup
0x1da9  ldc.i4.s 0xC
0x1dab  ldstr    aXsString// "xs:string"
0x1db0  stelem.ref
0x1db1  dup
0x1db2  ldc.i4.s 0xD
0x1db4  ldstr    aXsBoolean// "xs:boolean"
0x1db9  stelem.ref
0x1dba  dup
0x1dbb  ldc.i4.s 0xE
0x1dbd  ldstr    aXsDecimal// "xs:decimal"
0x1dc2  stelem.ref
0x1dc3  dup
0x1dc4  ldc.i4.s 0xF
0x1dc6  ldstr    aXsFloat// "xs:float"
0x1dcb  stelem.ref
0x1dcc  dup
0x1dcd  ldc.i4.s 0x10
0x1dcf  ldstr    aXsDouble// "xs:double"
0x1dd4  stelem.ref
0x1dd5  dup
0x1dd6  ldc.i4.s 0x11
0x1dd8  ldstr    aXsDuration// "xs:duration"
0x1ddd  stelem.ref
0x1dde  dup
0x1ddf  ldc.i4.s 0x12
0x1de1  ldstr    aXsDatetime// "xs:dateTime"
0x1de6  stelem.ref
0x1de7  dup
0x1de8  ldc.i4.s 0x13
0x1dea  ldstr    aXsTime// "xs:time"
0x1def  stelem.ref
0x1df0  dup
0x1df1  ldc.i4.s 0x14
0x1df3  ldstr    aXsDate// "xs:date"
0x1df8  stelem.ref
0x1df9  dup
0x1dfa  ldc.i4.s 0x15
0x1dfc  ldstr    aXsGyearmonth// "xs:gYearMonth"
0x1e01  stelem.ref
0x1e02  dup
0x1e03  ldc.i4.s 0x16
0x1e05  ldstr    aXsGyear// "xs:gYear"
0x1e0a  stelem.ref
0x1e0b  dup
0x1e0c  ldc.i4.s 0x17
0x1e0e  ldstr    aXsGmonthday// "xs:gMonthDay"
0x1e13  stelem.ref
0x1e14  dup
0x1e15  ldc.i4.s 0x18
0x1e17  ldstr    aXsGday// "xs:gDay"
0x1e1c  stelem.ref
0x1e1d  dup
0x1e1e  ldc.i4.s 0x19
0x1e20  ldstr    aXsGmonth// "xs:gMonth"
0x1e25  stelem.ref
0x1e26  dup
0x1e27  ldc.i4.s 0x1A
0x1e29  ldstr    aXsHexbinary// "xs:hexBinary"
0x1e2e  stelem.ref
0x1e2f  dup
0x1e30  ldc.i4.s 0x1B
0x1e32  ldstr    aXsBase64binary// "xs:base64Binary"
0x1e37  stelem.ref
0x1e38  dup
0x1e39  ldc.i4.s 0x1C
0x1e3b  ldstr    aXsAnyuri// "xs:anyUri"
0x1e40  stelem.ref
0x1e41  dup
0x1e42  ldc.i4.s 0x1D
0x1e44  ldstr    aXsQname// "xs:QName"
0x1e49  stelem.ref
0x1e4a  dup
0x1e4b  ldc.i4.s 0x1E
0x1e4d  ldstr    aXsNotation// "xs:NOTATION"
0x1e52  stelem.ref
0x1e53  dup
0x1e54  ldc.i4.s 0x1F
0x1e56  ldstr    aXsNormalizedst// "xs:normalizedString"
0x1e5b  stelem.ref
0x1e5c  dup
0x1e5d  ldc.i4.s 0x20
0x1e5f  ldstr    aXsToken// "xs:token"
0x1e64  stelem.ref
0x1e65  dup
0x1e66  ldc.i4.s 0x21
0x1e68  ldstr    aXsLanguage// "xs:language"
0x1e6d  stelem.ref
0x1e6e  dup
0x1e6f  ldc.i4.s 0x22
0x1e71  ldstr    aXsNmtoken// "xs:NMTOKEN"
0x1e76  stelem.ref
0x1e77  dup
0x1e78  ldc.i4.s 0x23
0x1e7a  ldstr    aXsName// "xs:Name"
0x1e7f  stelem.ref
0x1e80  dup
0x1e81  ldc.i4.s 0x24
0x1e83  ldstr    aXsNcname// "xs:NCName"
0x1e88  stelem.ref
0x1e89  dup
0x1e8a  ldc.i4.s 0x25
0x1e8c  ldstr    aXsId// "xs:ID"
0x1e91  stelem.ref
0x1e92  dup
0x1e93  ldc.i4.s 0x26
0x1e95  ldstr    aXsIdref// "xs:IDREF"
0x1e9a  stelem.ref
0x1e9b  dup
0x1e9c  ldc.i4.s 0x27
0x1e9e  ldstr    aXsEntity// "xs:ENTITY"
0x1ea3  stelem.ref
0x1ea4  dup
0x1ea5  ldc.i4.s 0x28
0x1ea7  ldstr    aXsInteger// "xs:integer"
0x1eac  stelem.ref
0x1ead  dup
0x1eae  ldc.i4.s 0x29
0x1eb0  ldstr    aXsNonpositivei// "xs:nonPositiveInteger"
0x1eb5  stelem.ref
0x1eb6  dup
0x1eb7  ldc.i4.s 0x2A
0x1eb9  ldstr    aXsNegativeinte// "xs:negativeInteger"
0x1ebe  stelem.ref
0x1ebf  dup
0x1ec0  ldc.i4.s 0x2B
0x1ec2  ldstr    aXsLong// "xs:long"
0x1ec7  stelem.ref
0x1ec8  dup
0x1ec9  ldc.i4.s 0x2C
0x1ecb  ldstr    aXsInt// "xs:int"
0x1ed0  stelem.ref
0x1ed1  dup
0x1ed2  ldc.i4.s 0x2D
0x1ed4  ldstr    aXsShort// "xs:short"
0x1ed9  stelem.ref
0x1eda  dup
0x1edb  ldc.i4.s 0x2E
0x1edd  ldstr    aXsByte// "xs:byte"
0x1ee2  stelem.ref
0x1ee3  dup
0x1ee4  ldc.i4.s 0x2F
0x1ee6  ldstr    aXsNonnegativei// "xs:nonNegativeInteger"
0x1eeb  stelem.ref
0x1eec  dup
0x1eed  ldc.i4.s 0x30
0x1eef  ldstr    aXsUnsignedlong// "xs:unsignedLong"
0x1ef4  stelem.ref
0x1ef5  dup
0x1ef6  ldc.i4.s 0x31
0x1ef8  ldstr    aXsUnsignedint// "xs:unsignedInt"
0x1efd  stelem.ref
0x1efe  dup
0x1eff  ldc.i4.s 0x32
0x1f01  ldstr    aXsUnsignedshor// "xs:unsignedShort"
0x1f06  stelem.ref
0x1f07  dup
0x1f08  ldc.i4.s 0x33
0x1f0a  ldstr    aXsUnsignedbyte// "xs:unsignedByte"
0x1f0f  stelem.ref
0x1f10  dup
0x1f11  ldc.i4.s 0x34
0x1f13  ldstr    aXsPositiveinte// "xs:positiveInteger"
0x1f18  stelem.ref
0x1f19  dup
0x1f1a  ldc.i4.s 0x35
0x1f1c  ldstr    aXdtYearmonthdu// "xdt:yearMonthDuration"
0x1f21  stelem.ref
0x1f22  dup
0x1f23  ldc.i4.s 0x36
0x1f25  ldstr    aXdtDaytimedura// "xdt:dayTimeDuration"
0x1f2a  stelem.ref
0x1f2b  stsfld   string[] System.Xml.Xsl.XmlQueryType::TypeNames
0x1f30  ldsfld   valuetype [System.Xml]System.Xml.Schema.XmlTypeCode[] System.Xml.Xsl.XmlQueryType::BaseTypeCodes
0x1f35  ldlen
0x1f36  conv.i4
0x1f37  newobj   instance void BitMatrix::.ctor(int32 count)
0x1f3c  stsfld   class BitMatrix System.Xml.Xsl.XmlQueryType::TypeCodeDerivation
0x1f41  ldc.i4.0
0x1f42  stloc.0
0x1f43  br.s     loc_1F6C
0x1f45  ldloc.0
0x1f46  stloc.1
0x1f47  ldsfld   class BitMatrix System.Xml.Xsl.XmlQueryType::TypeCodeDerivation
0x1f4c  ldloc.0
0x1f4d  ldloc.1
0x1f4e  ldc.i4.1
0x1f4f  callvirt instance void BitMatrix::set_Item(int32 index1, int32 index2, bool value)
0x1f54  ldsfld   valuetype [System.Xml]System.Xml.Schema.XmlTypeCode[] System.Xml.Xsl.XmlQueryType::BaseTypeCodes
0x1f59  ldloc.1
0x1f5a  ldelem.i4
0x1f5b  ldloc.1
0x1f5c  beq.s    loc_1F68
0x1f5e  ldsfld   valuetype [System.Xml]System.Xml.Schema.XmlTypeCode[] System.Xml.Xsl.XmlQueryType::BaseTypeCodes
0x1f63  ldloc.1
0x1f64  ldelem.i4
0x1f65  stloc.1
0x1f66  br.s     loc_1F47
0x1f68  ldloc.0
0x1f69  ldc.i4.1
0x1f6a  add
0x1f6b  stloc.0
0x1f6c  ldloc.0
0x1f6d  ldsfld   valuetype [System.Xml]System.Xml.Schema.XmlTypeCode[] System.Xml.Xsl.XmlQueryType::BaseTypeCodes
0x1f72  ldlen
0x1f73  conv.i4
0x1f74  blt.s    loc_1F45
0x1f76  ret
```
