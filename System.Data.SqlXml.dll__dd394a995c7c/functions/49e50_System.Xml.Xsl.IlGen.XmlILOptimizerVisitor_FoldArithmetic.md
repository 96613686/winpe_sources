# System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::FoldArithmetic

- ea: `0x49e50`
- end: `0x4a168`
- name: `System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::FoldArithmetic`
- size: `792`
- prototype: ``
- caller_count: `7`
- callee_count: `15`
- tags: `registry_config`

## callers

- `0x44310`
- `0x44450`
- `0x44540`
- `0x44680`
- `0x44770`
- `0x44e60`
- `0x49e30`

## callees

- `0x362d0`
- `0x36300`
- `0x36330`
- `0x36360`
- `0x365d0`
- `0x365f0`
- `0x36610`
- `0x36630`
- `0x36650`
- `0x373c0`
- `0x373d0`
- `0x373e0`
- `0x373f0`
- `0x376a0`
- `0x49e50`

## pseudocode

```c

```

## disassembly

```asm
0x49e50  ldarg.2
0x49e51  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x49e56  stloc.0
0x49e57  ldloc.0
0x49e58  ldc.i4.s 0x15
0x49e5a  sub
0x49e5b  switch   loc_49E75, loc_49F09, loc_4A05D, loc_49FA9
0x49e70  br       loc_4A0F7
0x49e75  ldarg.2
0x49e76  call     int32 System.Xml.Xsl.Qil.QilLiteral::op_Implicit(class System.Xml.Xsl.Qil.QilLiteral literal)
0x49e7b  stloc.1
0x49e7c  ldarg.3
0x49e7d  call     int32 System.Xml.Xsl.Qil.QilLiteral::op_Implicit(class System.Xml.Xsl.Qil.QilLiteral literal)
0x49e82  stloc.2
0x49e83  ldarg.1
0x49e84  ldc.i4.s 0x2B
0x49e86  sub
0x49e87  switch   loc_49EA5, loc_49EB9, loc_49ECD, loc_49EE1, loc_49EF5
0x49ea0  br       loc_4A0F7
0x49ea5  ldarg.0
0x49ea6  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x49eab  ldloc.1
0x49eac  ldloc.2
0x49ead  add.ovf
0x49eae  callvirt instance class System.Xml.Xsl.Qil.QilLiteral System.Xml.Xsl.Qil.QilFactory::LiteralInt32(int32 value)
0x49eb3  stloc.3
0x49eb4  leave    loc_4A166
0x49eb9  ldarg.0
0x49eba  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x49ebf  ldloc.1
0x49ec0  ldloc.2
0x49ec1  sub.ovf
0x49ec2  callvirt instance class System.Xml.Xsl.Qil.QilLiteral System.Xml.Xsl.Qil.QilFactory::LiteralInt32(int32 value)
0x49ec7  stloc.3
0x49ec8  leave    loc_4A166
0x49ecd  ldarg.0
0x49ece  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x49ed3  ldloc.1
0x49ed4  ldloc.2
0x49ed5  mul.ovf
0x49ed6  callvirt instance class System.Xml.Xsl.Qil.QilLiteral System.Xml.Xsl.Qil.QilFactory::LiteralInt32(int32 value)
0x49edb  stloc.3
0x49edc  leave    loc_4A166
0x49ee1  ldarg.0
0x49ee2  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x49ee7  ldloc.1
0x49ee8  ldloc.2
0x49ee9  div
0x49eea  callvirt instance class System.Xml.Xsl.Qil.QilLiteral System.Xml.Xsl.Qil.QilFactory::LiteralInt32(int32 value)
0x49eef  stloc.3
0x49ef0  leave    loc_4A166
0x49ef5  ldarg.0
0x49ef6  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x49efb  ldloc.1
0x49efc  ldloc.2
0x49efd  rem
0x49efe  callvirt instance class System.Xml.Xsl.Qil.QilLiteral System.Xml.Xsl.Qil.QilFactory::LiteralInt32(int32 value)
0x49f03  stloc.3
0x49f04  leave    loc_4A166
0x49f09  ldarg.2
0x49f0a  call     int64 System.Xml.Xsl.Qil.QilLiteral::op_Implicit(class System.Xml.Xsl.Qil.QilLiteral literal)
0x49f0f  stloc.s  4
0x49f11  ldarg.3
0x49f12  call     int64 System.Xml.Xsl.Qil.QilLiteral::op_Implicit(class System.Xml.Xsl.Qil.QilLiteral literal)
0x49f17  stloc.s  5
0x49f19  ldarg.1
0x49f1a  ldc.i4.s 0x2B
0x49f1c  sub
0x49f1d  switch   loc_49F3B, loc_49F51, loc_49F67, loc_49F7D, loc_49F93
0x49f36  br       loc_4A0F7
0x49f3b  ldarg.0
0x49f3c  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x49f41  ldloc.s  4
0x49f43  ldloc.s  5
0x49f45  add.ovf
0x49f46  callvirt instance class System.Xml.Xsl.Qil.QilLiteral System.Xml.Xsl.Qil.QilFactory::LiteralInt64(int64 value)
0x49f4b  stloc.3
0x49f4c  leave    loc_4A166
0x49f51  ldarg.0
0x49f52  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x49f57  ldloc.s  4
0x49f59  ldloc.s  5
0x49f5b  sub.ovf
0x49f5c  callvirt instance class System.Xml.Xsl.Qil.QilLiteral System.Xml.Xsl.Qil.QilFactory::LiteralInt64(int64 value)
0x49f61  stloc.3
0x49f62  leave    loc_4A166
0x49f67  ldarg.0
0x49f68  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x49f6d  ldloc.s  4
0x49f6f  ldloc.s  5
0x49f71  mul.ovf
0x49f72  callvirt instance class System.Xml.Xsl.Qil.QilLiteral System.Xml.Xsl.Qil.QilFactory::LiteralInt64(int64 value)
0x49f77  stloc.3
0x49f78  leave    loc_4A166
0x49f7d  ldarg.0
0x49f7e  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x49f83  ldloc.s  4
0x49f85  ldloc.s  5
0x49f87  div
0x49f88  callvirt instance class System.Xml.Xsl.Qil.QilLiteral System.Xml.Xsl.Qil.QilFactory::LiteralInt64(int64 value)
0x49f8d  stloc.3
0x49f8e  leave    loc_4A166
0x49f93  ldarg.0
0x49f94  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x49f99  ldloc.s  4
0x49f9b  ldloc.s  5
0x49f9d  rem
0x49f9e  callvirt instance class System.Xml.Xsl.Qil.QilLiteral System.Xml.Xsl.Qil.QilFactory::LiteralInt64(int64 value)
0x49fa3  stloc.3
0x49fa4  leave    loc_4A166
0x49fa9  ldarg.2
0x49faa  call     valuetype [mscorlib]System.Decimal System.Xml.Xsl.Qil.QilLiteral::op_Implicit(class System.Xml.Xsl.Qil.QilLiteral literal)
0x49faf  stloc.s  6
0x49fb1  ldarg.3
0x49fb2  call     valuetype [mscorlib]System.Decimal System.Xml.Xsl.Qil.QilLiteral::op_Implicit(class System.Xml.Xsl.Qil.QilLiteral literal)
0x49fb7  stloc.s  7
0x49fb9  ldarg.1
0x49fba  ldc.i4.s 0x2B
0x49fbc  sub
0x49fbd  switch   loc_49FDB, loc_49FF5, loc_4A00F, loc_4A029, loc_4A043
0x49fd6  br       loc_4A0F7
0x49fdb  ldarg.0
0x49fdc  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x49fe1  ldloc.s  6
0x49fe3  ldloc.s  7
0x49fe5  call     valuetype [mscorlib]System.Decimal [mscorlib]System.Decimal::op_Addition(valuetype [mscorlib]System.Decimal, valuetype [mscorlib]System.Decimal)
0x49fea  callvirt instance class System.Xml.Xsl.Qil.QilLiteral System.Xml.Xsl.Qil.QilFactory::LiteralDecimal(valuetype [mscorlib]System.Decimal value)
0x49fef  stloc.3
0x49ff0  leave    loc_4A166
0x49ff5  ldarg.0
0x49ff6  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x49ffb  ldloc.s  6
0x49ffd  ldloc.s  7
0x49fff  call     valuetype [mscorlib]System.Decimal [mscorlib]System.Decimal::op_Subtraction(valuetype [mscorlib]System.Decimal, valuetype [mscorlib]System.Decimal)
0x4a004  callvirt instance class System.Xml.Xsl.Qil.QilLiteral System.Xml.Xsl.Qil.QilFactory::LiteralDecimal(valuetype [mscorlib]System.Decimal value)
0x4a009  stloc.3
0x4a00a  leave    loc_4A166
0x4a00f  ldarg.0
0x4a010  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x4a015  ldloc.s  6
0x4a017  ldloc.s  7
0x4a019  call     valuetype [mscorlib]System.Decimal [mscorlib]System.Decimal::op_Multiply(valuetype [mscorlib]System.Decimal, valuetype [mscorlib]System.Decimal)
0x4a01e  callvirt instance class System.Xml.Xsl.Qil.QilLiteral System.Xml.Xsl.Qil.QilFactory::LiteralDecimal(valuetype [mscorlib]System.Decimal value)
0x4a023  stloc.3
0x4a024  leave    loc_4A166
0x4a029  ldarg.0
0x4a02a  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x4a02f  ldloc.s  6
0x4a031  ldloc.s  7
0x4a033  call     valuetype [mscorlib]System.Decimal [mscorlib]System.Decimal::op_Division(valuetype [mscorlib]System.Decimal, valuetype [mscorlib]System.Decimal)
0x4a038  callvirt instance class System.Xml.Xsl.Qil.QilLiteral System.Xml.Xsl.Qil.QilFactory::LiteralDecimal(valuetype [mscorlib]System.Decimal value)
0x4a03d  stloc.3
0x4a03e  leave    loc_4A166
0x4a043  ldarg.0
0x4a044  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x4a049  ldloc.s  6
0x4a04b  ldloc.s  7
0x4a04d  call     valuetype [mscorlib]System.Decimal [mscorlib]System.Decimal::op_Modulus(valuetype [mscorlib]System.Decimal, valuetype [mscorlib]System.Decimal)
0x4a052  callvirt instance class System.Xml.Xsl.Qil.QilLiteral System.Xml.Xsl.Qil.QilFactory::LiteralDecimal(valuetype [mscorlib]System.Decimal value)
0x4a057  stloc.3
0x4a058  leave    loc_4A166
0x4a05d  ldarg.2
0x4a05e  call     float64 System.Xml.Xsl.Qil.QilLiteral::op_Implicit(class System.Xml.Xsl.Qil.QilLiteral literal)
0x4a063  stloc.s  8
0x4a065  ldarg.3
0x4a066  call     float64 System.Xml.Xsl.Qil.QilLiteral::op_Implicit(class System.Xml.Xsl.Qil.QilLiteral literal)
0x4a06b  stloc.s  9
0x4a06d  ldarg.1
0x4a06e  ldc.i4.s 0x2B
0x4a070  sub
0x4a071  switch   loc_4A08C, loc_4A0A2, loc_4A0B8, loc_4A0CE, loc_4A0E4
0x4a08a  br.s     loc_4A0F7
0x4a08c  ldarg.0
0x4a08d  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x4a092  ldloc.s  8
0x4a094  ldloc.s  9
0x4a096  add
0x4a097  callvirt instance class System.Xml.Xsl.Qil.QilLiteral System.Xml.Xsl.Qil.QilFactory::LiteralDouble(float64 value)
0x4a09c  stloc.3
0x4a09d  leave    loc_4A166
0x4a0a2  ldarg.0
0x4a0a3  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x4a0a8  ldloc.s  8
0x4a0aa  ldloc.s  9
0x4a0ac  sub
0x4a0ad  callvirt instance class System.Xml.Xsl.Qil.QilLiteral System.Xml.Xsl.Qil.QilFactory::LiteralDouble(float64 value)
0x4a0b2  stloc.3
0x4a0b3  leave    loc_4A166
0x4a0b8  ldarg.0
0x4a0b9  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x4a0be  ldloc.s  8
0x4a0c0  ldloc.s  9
0x4a0c2  mul
0x4a0c3  callvirt instance class System.Xml.Xsl.Qil.QilLiteral System.Xml.Xsl.Qil.QilFactory::LiteralDouble(float64 value)
0x4a0c8  stloc.3
0x4a0c9  leave    loc_4A166
0x4a0ce  ldarg.0
0x4a0cf  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x4a0d4  ldloc.s  8
0x4a0d6  ldloc.s  9
0x4a0d8  div
0x4a0d9  callvirt instance class System.Xml.Xsl.Qil.QilLiteral System.Xml.Xsl.Qil.QilFactory::LiteralDouble(float64 value)
0x4a0de  stloc.3
0x4a0df  leave    loc_4A166
0x4a0e4  ldarg.0
0x4a0e5  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x4a0ea  ldloc.s  8
0x4a0ec  ldloc.s  9
0x4a0ee  rem
0x4a0ef  callvirt instance class System.Xml.Xsl.Qil.QilLiteral System.Xml.Xsl.Qil.QilFactory::LiteralDouble(float64 value)
0x4a0f4  stloc.3
0x4a0f5  leave.s  loc_4A166
0x4a0f7  leave.s  loc_4A0FF
0x4a0f9  pop
0x4a0fa  leave.s  loc_4A0FF
0x4a0fc  pop
0x4a0fd  leave.s  loc_4A0FF
0x4a0ff  ldarg.1
0x4a100  ldc.i4.s 0x2B
0x4a102  sub
0x4a103  switch   loc_4A11E, loc_4A12C, loc_4A13A, loc_4A148, loc_4A156
0x4a11c  br.s     loc_4A164
0x4a11e  ldarg.0
0x4a11f  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x4a124  ldarg.2
0x4a125  ldarg.3
0x4a126  callvirt instance class System.Xml.Xsl.Qil.QilBinary System.Xml.Xsl.Qil.QilFactory::Add(class System.Xml.Xsl.Qil.QilNode left, class System.Xml.Xsl.Qil.QilNode right)
0x4a12b  ret
0x4a12c  ldarg.0
0x4a12d  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x4a132  ldarg.2
0x4a133  ldarg.3
0x4a134  callvirt instance class System.Xml.Xsl.Qil.QilBinary System.Xml.Xsl.Qil.QilFactory::Subtract(class System.Xml.Xsl.Qil.QilNode left, class System.Xml.Xsl.Qil.QilNode right)
0x4a139  ret
0x4a13a  ldarg.0
0x4a13b  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x4a140  ldarg.2
0x4a141  ldarg.3
0x4a142  callvirt instance class System.Xml.Xsl.Qil.QilBinary System.Xml.Xsl.Qil.QilFactory::Multiply(class System.Xml.Xsl.Qil.QilNode left, class System.Xml.Xsl.Qil.QilNode right)
0x4a147  ret
0x4a148  ldarg.0
0x4a149  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x4a14e  ldarg.2
0x4a14f  ldarg.3
0x4a150  callvirt instance class System.Xml.Xsl.Qil.QilBinary System.Xml.Xsl.Qil.QilFactory::Divide(class System.Xml.Xsl.Qil.QilNode left, class System.Xml.Xsl.Qil.QilNode right)
0x4a155  ret
0x4a156  ldarg.0
0x4a157  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x4a15c  ldarg.2
0x4a15d  ldarg.3
0x4a15e  callvirt instance class System.Xml.Xsl.Qil.QilBinary System.Xml.Xsl.Qil.QilFactory::Modulo(class System.Xml.Xsl.Qil.QilNode left, class System.Xml.Xsl.Qil.QilNode right)
0x4a163  ret
0x4a164  ldnull
0x4a165  ret
0x4a166  ldloc.3
0x4a167  ret
```
