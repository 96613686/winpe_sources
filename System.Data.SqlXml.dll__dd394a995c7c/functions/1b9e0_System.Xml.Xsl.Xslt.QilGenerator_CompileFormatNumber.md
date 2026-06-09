# System.Xml.Xsl.Xslt.QilGenerator::CompileFormatNumber

- ea: `0x1b9e0`
- end: `0x1bb67`
- name: `System.Xml.Xsl.Xslt.QilGenerator::CompileFormatNumber`
- size: `391`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1a9a0`

## callees

- `0x3a50`
- `0x1a0a0`
- `0x1b9e0`
- `0x1bbf0`
- `0x266c0`
- `0x26720`
- `0x26750`
- `0x373b0`
- `0x376a0`
- `0x377c0`
- `0x37a20`
- `0x37a60`
- `0x37c50`
- `0x38120`
- `0x38ce0`

## string_xrefs

- `0x1bacb`: `urn:schemas-microsoft-com:xslt-debug`

## pseudocode

```c

```

## disassembly

```asm
0x1b9e0  ldarg.3
0x1b9e1  brtrue.s loc_1B9FD
0x1b9e3  newobj   instance void [System.Xml]System.Xml.XmlQualifiedName::.ctor()
0x1b9e8  stloc.0
0x1b9e9  ldarg.0
0x1b9ea  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1b9ef  ldsfld   string [mscorlib]System.String::Empty
0x1b9f4  callvirt instance class System.Xml.Xsl.Qil.QilLiteral System.Xml.Xsl.Qil.QilPatternFactory::String(string val)
0x1b9f9  starg.s  3
0x1b9fb  br.s     loc_1BA14
0x1b9fd  ldarg.3
0x1b9fe  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x1ba03  ldc.i4.s 0x14
0x1ba05  bne.un.s loc_1BA12
0x1ba07  ldarg.0
0x1ba08  ldc.i4.1
0x1ba09  ldarg.3
0x1ba0a  call     instance class [System.Xml]System.Xml.XmlQualifiedName System.Xml.Xsl.Xslt.QilGenerator::ResolveQNameThrow(bool ignoreDefaultNs, class System.Xml.Xsl.Qil.QilNode qilName)
0x1ba0f  stloc.0
0x1ba10  br.s     loc_1BA14
0x1ba12  ldnull
0x1ba13  stloc.0
0x1ba14  ldloc.0
0x1ba15  ldnull
0x1ba16  call     bool [System.Xml]System.Xml.XmlQualifiedName::op_Inequality(class [System.Xml]System.Xml.XmlQualifiedName, class [System.Xml]System.Xml.XmlQualifiedName)
0x1ba1b  brfalse  loc_1BB28
0x1ba20  ldarg.0
0x1ba21  ldfld    class System.Xml.Xsl.Xslt.Compiler System.Xml.Xsl.Xslt.QilGenerator::compiler
0x1ba26  ldfld    class System.Xml.Xsl.Xslt.DecimalFormats System.Xml.Xsl.Xslt.Compiler::DecimalFormats
0x1ba2b  ldloc.0
0x1ba2c  callvirt instance bool class [mscorlib]System.Collections.ObjectModel.KeyedCollection`2<class [System.Xml]System.Xml.XmlQualifiedName, class System.Xml.Xsl.Xslt.DecimalFormatDecl>::Contains(var<u1>)
0x1ba31  brfalse.s loc_1BA47
0x1ba33  ldarg.0
0x1ba34  ldfld    class System.Xml.Xsl.Xslt.Compiler System.Xml.Xsl.Xslt.QilGenerator::compiler
0x1ba39  ldfld    class System.Xml.Xsl.Xslt.DecimalFormats System.Xml.Xsl.Xslt.Compiler::DecimalFormats
0x1ba3e  ldloc.0
0x1ba3f  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.KeyedCollection`2<class [System.Xml]System.Xml.XmlQualifiedName, class System.Xml.Xsl.Xslt.DecimalFormatDecl>::get_Item(void)
0x1ba44  stloc.1
0x1ba45  br.s     loc_1BA7E
0x1ba47  ldloc.0
0x1ba48  ldsfld   class System.Xml.Xsl.Xslt.DecimalFormatDecl System.Xml.Xsl.Xslt.DecimalFormatDecl::Default
0x1ba4d  ldfld    class [System.Xml]System.Xml.XmlQualifiedName System.Xml.Xsl.Xslt.DecimalFormatDecl::Name
0x1ba52  call     bool [System.Xml]System.Xml.XmlQualifiedName::op_Inequality(class [System.Xml]System.Xml.XmlQualifiedName, class [System.Xml]System.Xml.XmlQualifiedName)
0x1ba57  brfalse.s loc_1BA78
0x1ba59  ldstr    aXsltNodecimalf// "Xslt_NoDecimalFormat"
0x1ba5e  ldc.i4.1
0x1ba5f  newarr   [mscorlib]System.String
0x1ba64  dup
0x1ba65  ldc.i4.0
0x1ba66  ldarg.3
0x1ba67  castclass System.Xml.Xsl.Qil.QilLiteral
0x1ba6c  call     string System.Xml.Xsl.Qil.QilLiteral::op_Implicit(class System.Xml.Xsl.Qil.QilLiteral literal)
0x1ba71  stelem.ref
0x1ba72  newobj   instance void System.Xml.Xsl.XslLoadException::.ctor(string res, string[] args)
0x1ba77  throw
0x1ba78  ldsfld   class System.Xml.Xsl.Xslt.DecimalFormatDecl System.Xml.Xsl.Xslt.DecimalFormatDecl::Default
0x1ba7d  stloc.1
0x1ba7e  ldarg.2
0x1ba7f  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x1ba84  ldc.i4.s 0x14
0x1ba86  bne.un.s loc_1BAF9
0x1ba88  ldarg.0
0x1ba89  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1ba8e  ldarg.0
0x1ba8f  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1ba94  ldarg.2
0x1ba95  ldloc.1
0x1ba96  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.XsltQilFactory::InvokeRegisterDecimalFormatter(class System.Xml.Xsl.Qil.QilNode formatPicture, class System.Xml.Xsl.Xslt.DecimalFormatDecl format)
0x1ba9b  callvirt instance class System.Xml.Xsl.Qil.QilIterator System.Xml.Xsl.Qil.QilPatternFactory::Let(class System.Xml.Xsl.Qil.QilNode binding)
0x1baa0  stloc.3
0x1baa1  ldloc.3
0x1baa2  ldarg.0
0x1baa3  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1baa8  ldstr    aFormatter// "formatter"
0x1baad  ldarg.0
0x1baae  ldarg.0
0x1baaf  ldfld    int32 System.Xml.Xsl.Xslt.QilGenerator::formatterCnt
0x1bab4  stloc.s  4
0x1bab6  ldloc.s  4
0x1bab8  ldc.i4.1
0x1bab9  add
0x1baba  stfld    int32 System.Xml.Xsl.Xslt.QilGenerator::formatterCnt
0x1babf  ldloca.s 4
0x1bac1  call     instance string [mscorlib]System.Int32::ToString()
0x1bac6  call     string [mscorlib]System.String::Concat(string, string)
0x1bacb  ldstr    aUrnSchemasMicr_0// "urn:schemas-microsoft-com:xslt-debug"
0x1bad0  callvirt instance class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Qil.QilPatternFactory::QName(string local, string uri)
0x1bad5  callvirt instance string [mscorlib]System.Object::ToString()
0x1bada  callvirt instance void System.Xml.Xsl.Qil.QilReference::set_DebugName(string value)
0x1badf  ldarg.0
0x1bae0  ldfld    class System.Xml.Xsl.Qil.QilList System.Xml.Xsl.Xslt.QilGenerator::gloVars
0x1bae5  ldloc.3
0x1bae6  callvirt instance void System.Xml.Xsl.Qil.QilNode::Add(class System.Xml.Xsl.Qil.QilNode node)
0x1baeb  ldarg.0
0x1baec  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1baf1  ldarg.1
0x1baf2  ldloc.3
0x1baf3  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.XsltQilFactory::InvokeFormatNumberStatic(class System.Xml.Xsl.Qil.QilNode value, class System.Xml.Xsl.Qil.QilNode decimalFormatIndex)
0x1baf8  ret
0x1baf9  ldarg.0
0x1bafa  ldc.i4.1
0x1bafb  stfld    bool System.Xml.Xsl.Xslt.QilGenerator::formatNumberDynamicUsed
0x1bb00  ldarg.0
0x1bb01  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1bb06  ldloc.0
0x1bb07  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Name()
0x1bb0c  ldloc.0
0x1bb0d  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Namespace()
0x1bb12  callvirt instance class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Qil.QilPatternFactory::QName(string local, string uri)
0x1bb17  stloc.2
0x1bb18  ldarg.0
0x1bb19  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1bb1e  ldarg.1
0x1bb1f  ldarg.2
0x1bb20  ldloc.2
0x1bb21  ldarg.3
0x1bb22  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.XsltQilFactory::InvokeFormatNumberDynamic(class System.Xml.Xsl.Qil.QilNode value, class System.Xml.Xsl.Qil.QilNode formatPicture, class System.Xml.Xsl.Qil.QilNode decimalFormatName, class System.Xml.Xsl.Qil.QilNode errorMessageName)
0x1bb27  ret
0x1bb28  ldarg.0
0x1bb29  ldc.i4.1
0x1bb2a  stfld    bool System.Xml.Xsl.Xslt.QilGenerator::formatNumberDynamicUsed
0x1bb2f  ldarg.0
0x1bb30  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1bb35  ldarg.3
0x1bb36  callvirt instance class System.Xml.Xsl.Qil.QilIterator System.Xml.Xsl.Qil.QilPatternFactory::Let(class System.Xml.Xsl.Qil.QilNode binding)
0x1bb3b  stloc.s  5
0x1bb3d  ldarg.0
0x1bb3e  ldc.i4.1
0x1bb3f  ldloc.s  5
0x1bb41  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::ResolveQNameDynamic(bool ignoreDefaultNs, class System.Xml.Xsl.Qil.QilNode qilName)
0x1bb46  stloc.s  6
0x1bb48  ldarg.0
0x1bb49  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1bb4e  ldloc.s  5
0x1bb50  ldarg.0
0x1bb51  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1bb56  ldarg.1
0x1bb57  ldarg.2
0x1bb58  ldloc.s  6
0x1bb5a  ldloc.s  5
0x1bb5c  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.XsltQilFactory::InvokeFormatNumberDynamic(class System.Xml.Xsl.Qil.QilNode value, class System.Xml.Xsl.Qil.QilNode formatPicture, class System.Xml.Xsl.Qil.QilNode decimalFormatName, class System.Xml.Xsl.Qil.QilNode errorMessageName)
0x1bb61  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::Loop(class System.Xml.Xsl.Qil.QilIterator variable, class System.Xml.Xsl.Qil.QilNode body)
0x1bb66  ret
```
