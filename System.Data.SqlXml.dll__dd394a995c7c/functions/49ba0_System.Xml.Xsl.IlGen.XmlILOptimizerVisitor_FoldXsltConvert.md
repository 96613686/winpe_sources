# System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::FoldXsltConvert

- ea: `0x49ba0`
- end: `0x49ccb`
- name: `System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::FoldXsltConvert`
- size: `299`
- prototype: ``
- caller_count: `9`
- callee_count: `15`
- tags: `registry_config`

## callers

- `0x44b30`
- `0x44e60`
- `0x455f0`
- `0x45890`
- `0x45ac0`
- `0x45cf0`
- `0x49620`
- `0x49b30`
- `0x49b50`

## callees

- `0x1fa0`
- `0x2320`
- `0x23f0`
- `0x33d10`
- `0x36000`
- `0x36270`
- `0x36290`
- `0x362b0`
- `0x362d0`
- `0x36300`
- `0x36330`
- `0x36360`
- `0x376c0`
- `0x499f0`
- `0x49ba0`

## pseudocode

```c

```

## disassembly

```asm
0x49ba0  ldarg.2
0x49ba1  callvirt instance bool System.Xml.Xsl.XmlQueryType::get_IsAtomicValue()
0x49ba6  brfalse  loc_49CB3
0x49bab  ldarg.1
0x49bac  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x49bb1  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaType System.Xml.Xsl.XmlQueryType::get_SchemaType()
0x49bb6  ldarg.0
0x49bb7  ldarg.1
0x49bb8  call     instance object System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::ExtractLiteralValue(class System.Xml.Xsl.Qil.QilNode nd)
0x49bbd  newobj   instance void [System.Xml]System.Xml.Schema.XmlAtomicValue::.ctor(class [System.Xml]System.Xml.Schema.XmlSchemaType, object)
0x49bc2  stloc.0
0x49bc3  ldloc.0
0x49bc4  ldarg.2
0x49bc5  call     class [System.Xml]System.Xml.Schema.XmlAtomicValue System.Xml.Xsl.Runtime.XsltConvert::ConvertToType(class [System.Xml]System.Xml.Schema.XmlAtomicValue value, class System.Xml.Xsl.XmlQueryType destinationType)
0x49bca  stloc.0
0x49bcb  ldarg.2
0x49bcc  ldsfld   class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryTypeFactory::StringX
0x49bd1  call     bool System.Xml.Xsl.XmlQueryType::op_Equality(class System.Xml.Xsl.XmlQueryType left, class System.Xml.Xsl.XmlQueryType right)
0x49bd6  brfalse.s loc_49BEF
0x49bd8  ldarg.0
0x49bd9  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x49bde  ldloc.0
0x49bdf  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x49be4  callvirt instance class System.Xml.Xsl.Qil.QilLiteral System.Xml.Xsl.Qil.QilFactory::LiteralString(string value)
0x49be9  stloc.1
0x49bea  leave    loc_49CC9
0x49bef  ldarg.2
0x49bf0  ldsfld   class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryTypeFactory::IntX
0x49bf5  call     bool System.Xml.Xsl.XmlQueryType::op_Equality(class System.Xml.Xsl.XmlQueryType left, class System.Xml.Xsl.XmlQueryType right)
0x49bfa  brfalse.s loc_49C13
0x49bfc  ldarg.0
0x49bfd  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x49c02  ldloc.0
0x49c03  callvirt instance int32 [System.Xml]System.Xml.XPath.XPathItem::get_ValueAsInt()
0x49c08  callvirt instance class System.Xml.Xsl.Qil.QilLiteral System.Xml.Xsl.Qil.QilFactory::LiteralInt32(int32 value)
0x49c0d  stloc.1
0x49c0e  leave    loc_49CC9
0x49c13  ldarg.2
0x49c14  ldsfld   class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryTypeFactory::IntegerX
0x49c19  call     bool System.Xml.Xsl.XmlQueryType::op_Equality(class System.Xml.Xsl.XmlQueryType left, class System.Xml.Xsl.XmlQueryType right)
0x49c1e  brfalse.s loc_49C37
0x49c20  ldarg.0
0x49c21  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x49c26  ldloc.0
0x49c27  callvirt instance int64 [System.Xml]System.Xml.XPath.XPathItem::get_ValueAsLong()
0x49c2c  callvirt instance class System.Xml.Xsl.Qil.QilLiteral System.Xml.Xsl.Qil.QilFactory::LiteralInt64(int64 value)
0x49c31  stloc.1
0x49c32  leave    loc_49CC9
0x49c37  ldarg.2
0x49c38  ldsfld   class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryTypeFactory::DecimalX
0x49c3d  call     bool System.Xml.Xsl.XmlQueryType::op_Equality(class System.Xml.Xsl.XmlQueryType left, class System.Xml.Xsl.XmlQueryType right)
0x49c42  brfalse.s loc_49C62
0x49c44  ldarg.0
0x49c45  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x49c4a  ldloc.0
0x49c4b  ldsfld   class [mscorlib]System.Type System.Xml.Xsl.Runtime.XsltConvert::DecimalType
0x49c50  callvirt instance object [System.Xml]System.Xml.XPath.XPathItem::ValueAs(class [mscorlib]System.Type)
0x49c55  unbox.any [mscorlib]System.Decimal
0x49c5a  callvirt instance class System.Xml.Xsl.Qil.QilLiteral System.Xml.Xsl.Qil.QilFactory::LiteralDecimal(valuetype [mscorlib]System.Decimal value)
0x49c5f  stloc.1
0x49c60  leave.s  loc_49CC9
0x49c62  ldarg.2
0x49c63  ldsfld   class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryTypeFactory::DoubleX
0x49c68  call     bool System.Xml.Xsl.XmlQueryType::op_Equality(class System.Xml.Xsl.XmlQueryType left, class System.Xml.Xsl.XmlQueryType right)
0x49c6d  brfalse.s loc_49C83
0x49c6f  ldarg.0
0x49c70  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x49c75  ldloc.0
0x49c76  callvirt instance float64 [System.Xml]System.Xml.XPath.XPathItem::get_ValueAsDouble()
0x49c7b  callvirt instance class System.Xml.Xsl.Qil.QilLiteral System.Xml.Xsl.Qil.QilFactory::LiteralDouble(float64 value)
0x49c80  stloc.1
0x49c81  leave.s  loc_49CC9
0x49c83  ldarg.2
0x49c84  ldsfld   class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryTypeFactory::BooleanX
0x49c89  call     bool System.Xml.Xsl.XmlQueryType::op_Equality(class System.Xml.Xsl.XmlQueryType left, class System.Xml.Xsl.XmlQueryType right)
0x49c8e  brfalse.s loc_49CB3
0x49c90  ldloc.0
0x49c91  callvirt instance bool [System.Xml]System.Xml.XPath.XPathItem::get_ValueAsBoolean()
0x49c96  brtrue.s loc_49CA5
0x49c98  ldarg.0
0x49c99  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x49c9e  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilFactory::False()
0x49ca3  br.s     loc_49CB0
0x49ca5  ldarg.0
0x49ca6  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x49cab  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilFactory::True()
0x49cb0  stloc.1
0x49cb1  leave.s  loc_49CC9
0x49cb3  leave.s  loc_49CBB
0x49cb5  pop
0x49cb6  leave.s  loc_49CBB
0x49cb8  pop
0x49cb9  leave.s  loc_49CBB
0x49cbb  ldarg.0
0x49cbc  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x49cc1  ldarg.1
0x49cc2  ldarg.2
0x49cc3  callvirt instance class System.Xml.Xsl.Qil.QilTargetType System.Xml.Xsl.Qil.QilFactory::XsltConvert(class System.Xml.Xsl.Qil.QilNode expr, class System.Xml.Xsl.XmlQueryType xmlType)
0x49cc8  ret
0x49cc9  ldloc.1
0x49cca  ret
```
