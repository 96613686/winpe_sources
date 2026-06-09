# System.Xml.Xsl.Xslt.QilGenerator::CreateFunctionTable

- ea: `0x1b030`
- end: `0x1b10e`
- name: `System.Xml.Xsl.Xslt.QilGenerator::CreateFunctionTable`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1be90`

## string_xrefs

- `0x1b095`: `unparsed-entity-uri`

## pseudocode

```c

```

## disassembly

```asm
0x1b030  ldc.i4.s 0x10
0x1b032  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class FunctionInfo`1<valuetype FuncId>>::.ctor(int32)
0x1b037  stloc.0
0x1b038  ldloc.0
0x1b039  ldstr    aCurrent// "current"
0x1b03e  ldc.i4.0
0x1b03f  ldc.i4.0
0x1b040  ldc.i4.0
0x1b041  ldnull
0x1b042  newobj   instance void class FunctionInfo`1<valuetype FuncId>::.ctor(var<u1>, !!T0, int32, int32)
0x1b047  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class FunctionInfo`1<valuetype FuncId>>::Add(var<u1>, !!T0)
0x1b04c  ldloc.0
0x1b04d  ldstr    aDocument// "document"
0x1b052  ldc.i4.1
0x1b053  ldc.i4.1
0x1b054  ldc.i4.2
0x1b055  ldsfld   valuetype [System.Xml]System.Xml.Schema.XmlTypeCode[] System.Xml.Xsl.Xslt.QilGenerator::argFnDocument
0x1b05a  newobj   instance void class FunctionInfo`1<valuetype FuncId>::.ctor(var<u1>, !!T0, int32, int32)
0x1b05f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class FunctionInfo`1<valuetype FuncId>>::Add(var<u1>, !!T0)
0x1b064  ldloc.0
0x1b065  ldstr    aKey// "key"
0x1b06a  ldc.i4.2
0x1b06b  ldc.i4.2
0x1b06c  ldc.i4.2
0x1b06d  ldsfld   valuetype [System.Xml]System.Xml.Schema.XmlTypeCode[] System.Xml.Xsl.Xslt.QilGenerator::argFnKey
0x1b072  newobj   instance void class FunctionInfo`1<valuetype FuncId>::.ctor(var<u1>, !!T0, int32, int32)
0x1b077  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class FunctionInfo`1<valuetype FuncId>>::Add(var<u1>, !!T0)
0x1b07c  ldloc.0
0x1b07d  ldstr    aFormatNumber// "format-number"
0x1b082  ldc.i4.3
0x1b083  ldc.i4.2
0x1b084  ldc.i4.3
0x1b085  ldsfld   valuetype [System.Xml]System.Xml.Schema.XmlTypeCode[] System.Xml.Xsl.Xslt.QilGenerator::argFnFormatNumber
0x1b08a  newobj   instance void class FunctionInfo`1<valuetype FuncId>::.ctor(var<u1>, !!T0, int32, int32)
0x1b08f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class FunctionInfo`1<valuetype FuncId>>::Add(var<u1>, !!T0)
0x1b094  ldloc.0
0x1b095  ldstr    aUnparsedEntity// "unparsed-entity-uri"
0x1b09a  ldc.i4.4
0x1b09b  ldc.i4.1
0x1b09c  ldc.i4.1
0x1b09d  ldsfld   valuetype [System.Xml]System.Xml.Schema.XmlTypeCode[] System.Xml.Xsl.XPath.XPathBuilder::argString
0x1b0a2  newobj   instance void class FunctionInfo`1<valuetype FuncId>::.ctor(var<u1>, !!T0, int32, int32)
0x1b0a7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class FunctionInfo`1<valuetype FuncId>>::Add(var<u1>, !!T0)
0x1b0ac  ldloc.0
0x1b0ad  ldstr    aGenerateId// "generate-id"
0x1b0b2  ldc.i4.5
0x1b0b3  ldc.i4.0
0x1b0b4  ldc.i4.1
0x1b0b5  ldsfld   valuetype [System.Xml]System.Xml.Schema.XmlTypeCode[] System.Xml.Xsl.XPath.XPathBuilder::argNodeSet
0x1b0ba  newobj   instance void class FunctionInfo`1<valuetype FuncId>::.ctor(var<u1>, !!T0, int32, int32)
0x1b0bf  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class FunctionInfo`1<valuetype FuncId>>::Add(var<u1>, !!T0)
0x1b0c4  ldloc.0
0x1b0c5  ldstr    aSystemProperty// "system-property"
0x1b0ca  ldc.i4.6
0x1b0cb  ldc.i4.1
0x1b0cc  ldc.i4.1
0x1b0cd  ldsfld   valuetype [System.Xml]System.Xml.Schema.XmlTypeCode[] System.Xml.Xsl.XPath.XPathBuilder::argString
0x1b0d2  newobj   instance void class FunctionInfo`1<valuetype FuncId>::.ctor(var<u1>, !!T0, int32, int32)
0x1b0d7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class FunctionInfo`1<valuetype FuncId>>::Add(var<u1>, !!T0)
0x1b0dc  ldloc.0
0x1b0dd  ldstr    aElementAvailab// "element-available"
0x1b0e2  ldc.i4.7
0x1b0e3  ldc.i4.1
0x1b0e4  ldc.i4.1
0x1b0e5  ldsfld   valuetype [System.Xml]System.Xml.Schema.XmlTypeCode[] System.Xml.Xsl.XPath.XPathBuilder::argString
0x1b0ea  newobj   instance void class FunctionInfo`1<valuetype FuncId>::.ctor(var<u1>, !!T0, int32, int32)
0x1b0ef  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class FunctionInfo`1<valuetype FuncId>>::Add(var<u1>, !!T0)
0x1b0f4  ldloc.0
0x1b0f5  ldstr    aFunctionAvaila// "function-available"
0x1b0fa  ldc.i4.8
0x1b0fb  ldc.i4.1
0x1b0fc  ldc.i4.1
0x1b0fd  ldsfld   valuetype [System.Xml]System.Xml.Schema.XmlTypeCode[] System.Xml.Xsl.XPath.XPathBuilder::argString
0x1b102  newobj   instance void class FunctionInfo`1<valuetype FuncId>::.ctor(var<u1>, !!T0, int32, int32)
0x1b107  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class FunctionInfo`1<valuetype FuncId>>::Add(var<u1>, !!T0)
0x1b10c  ldloc.0
0x1b10d  ret
```
