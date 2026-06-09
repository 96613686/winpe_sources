# System.Xml.Xsl.IlGen.XmlILStateAnalyzer::Analyze

- ea: `0x417a0`
- end: `0x41998`
- name: `System.Xml.Xsl.IlGen.XmlILStateAnalyzer::Analyze`
- size: `504`
- prototype: ``
- caller_count: `14`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x41d40`
- `0x42d10`
- `0x43610`
- `0x485b0`
- `0x48670`
- `0x48730`
- `0x487b0`
- `0x48870`
- `0x488e0`
- `0x48950`
- `0x489d0`
- `0x48ad0`
- `0x494f0`
- `0x495b0`

## callees

- `0x376a0`
- `0x413a0`
- `0x41430`
- `0x41440`
- `0x41460`
- `0x414a0`
- `0x414d0`
- `0x41640`
- `0x417a0`
- `0x419a0`
- `0x41b80`

## pseudocode

```c

```

## disassembly

```asm
0x417a0  ldarg.1
0x417a1  brtrue.s loc_417C6
0x417a3  ldarg.0
0x417a4  ldnull
0x417a5  stfld    class System.Xml.Xsl.IlGen.XmlILConstructInfo System.Xml.Xsl.IlGen.XmlILStateAnalyzer::parentInfo
0x417aa  ldarg.0
0x417ab  ldc.i4.1
0x417ac  stfld    valuetype System.Xml.Xsl.IlGen.PossibleXmlStates System.Xml.Xsl.IlGen.XmlILStateAnalyzer::xstates
0x417b1  ldarg.0
0x417b2  ldc.i4.0
0x417b3  stfld    bool System.Xml.Xsl.IlGen.XmlILStateAnalyzer::withinElem
0x417b8  ldarg.0
0x417b9  ldarg.2
0x417ba  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILStateAnalyzer::AnalyzeContent(class System.Xml.Xsl.Qil.QilNode nd)
0x417bf  starg.s  2
0x417c1  br       loc_41996
0x417c6  ldarg.0
0x417c7  ldarg.1
0x417c8  call     class System.Xml.Xsl.IlGen.XmlILConstructInfo System.Xml.Xsl.IlGen.XmlILConstructInfo::Write(class System.Xml.Xsl.Qil.QilNode nd)
0x417cd  stfld    class System.Xml.Xsl.IlGen.XmlILConstructInfo System.Xml.Xsl.IlGen.XmlILStateAnalyzer::parentInfo
0x417d2  ldarg.1
0x417d3  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x417d8  ldc.i4.s 0x41
0x417da  bne.un.s loc_41850
0x417dc  ldarg.0
0x417dd  ldfld    class System.Xml.Xsl.IlGen.XmlILConstructInfo System.Xml.Xsl.IlGen.XmlILStateAnalyzer::parentInfo
0x417e2  ldc.i4.1
0x417e3  callvirt instance void System.Xml.Xsl.IlGen.XmlILConstructInfo::set_ConstructMethod(valuetype System.Xml.Xsl.IlGen.XmlILConstructMethod value)
0x417e8  ldc.i4.0
0x417e9  stloc.0
0x417ea  ldarg.0
0x417eb  ldfld    class System.Xml.Xsl.IlGen.XmlILConstructInfo System.Xml.Xsl.IlGen.XmlILStateAnalyzer::parentInfo
0x417f0  callvirt instance class [mscorlib]System.Collections.ArrayList System.Xml.Xsl.IlGen.XmlILConstructInfo::get_CallersInfo()
0x417f5  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x417fa  stloc.1
0x417fb  br.s     loc_41827
0x417fd  ldloc.1
0x417fe  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x41803  castclass System.Xml.Xsl.IlGen.XmlILConstructInfo
0x41808  stloc.2
0x41809  ldloc.0
0x4180a  brtrue.s loc_41815
0x4180c  ldloc.2
0x4180d  callvirt instance valuetype System.Xml.Xsl.IlGen.PossibleXmlStates System.Xml.Xsl.IlGen.XmlILConstructInfo::get_InitialStates()
0x41812  stloc.0
0x41813  br.s     loc_41820
0x41815  ldloc.0
0x41816  ldloc.2
0x41817  callvirt instance valuetype System.Xml.Xsl.IlGen.PossibleXmlStates System.Xml.Xsl.IlGen.XmlILConstructInfo::get_InitialStates()
0x4181c  beq.s    loc_41820
0x4181e  ldc.i4.7
0x4181f  stloc.0
0x41820  ldloc.2
0x41821  ldc.i4.1
0x41822  callvirt instance void System.Xml.Xsl.IlGen.XmlILConstructInfo::set_PushToWriterFirst(bool value)
0x41827  ldloc.1
0x41828  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4182d  brtrue.s loc_417FD
0x4182f  leave.s  loc_41842
0x41831  ldloc.1
0x41832  isinst   [mscorlib]System.IDisposable
0x41837  stloc.3
0x41838  ldloc.3
0x41839  brfalse.s loc_41841
0x4183b  ldloc.3
0x4183c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x41841  endfinally
0x41842  ldarg.0
0x41843  ldfld    class System.Xml.Xsl.IlGen.XmlILConstructInfo System.Xml.Xsl.IlGen.XmlILStateAnalyzer::parentInfo
0x41848  ldloc.0
0x41849  callvirt instance void System.Xml.Xsl.IlGen.XmlILConstructInfo::set_InitialStates(valuetype System.Xml.Xsl.IlGen.PossibleXmlStates value)
0x4184e  br.s     loc_4188C
0x41850  ldarg.1
0x41851  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x41856  ldc.i4.s 0x20
0x41858  beq.s    loc_41876
0x4185a  ldarg.0
0x4185b  ldfld    class System.Xml.Xsl.IlGen.XmlILConstructInfo System.Xml.Xsl.IlGen.XmlILStateAnalyzer::parentInfo
0x41860  ldarg.0
0x41861  ldfld    class System.Xml.Xsl.IlGen.XmlILConstructInfo System.Xml.Xsl.IlGen.XmlILStateAnalyzer::parentInfo
0x41866  ldc.i4.1
0x41867  dup
0x41868  stloc.s  4
0x4186a  callvirt instance void System.Xml.Xsl.IlGen.XmlILConstructInfo::set_FinalStates(valuetype System.Xml.Xsl.IlGen.PossibleXmlStates value)
0x4186f  ldloc.s  4
0x41871  callvirt instance void System.Xml.Xsl.IlGen.XmlILConstructInfo::set_InitialStates(valuetype System.Xml.Xsl.IlGen.PossibleXmlStates value)
0x41876  ldarg.1
0x41877  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x4187c  ldc.i4.s 0x59
0x4187e  beq.s    loc_4188C
0x41880  ldarg.0
0x41881  ldfld    class System.Xml.Xsl.IlGen.XmlILConstructInfo System.Xml.Xsl.IlGen.XmlILStateAnalyzer::parentInfo
0x41886  ldc.i4.2
0x41887  callvirt instance void System.Xml.Xsl.IlGen.XmlILConstructInfo::set_ConstructMethod(valuetype System.Xml.Xsl.IlGen.XmlILConstructMethod value)
0x4188c  ldarg.0
0x4188d  ldarg.1
0x4188e  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x41893  ldc.i4.s 0x51
0x41895  ceq
0x41897  stfld    bool System.Xml.Xsl.IlGen.XmlILStateAnalyzer::withinElem
0x4189c  ldarg.1
0x4189d  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x418a2  stloc.s  5
0x418a4  ldloc.s  5
0x418a6  ldc.i4.s 0x41
0x418a8  bgt.s    loc_418BE
0x418aa  ldloc.s  5
0x418ac  ldc.i4.s 0x20
0x418ae  beq      loc_4194C
0x418b3  ldloc.s  5
0x418b5  ldc.i4.s 0x41
0x418b7  beq.s    loc_41930
0x418b9  br       loc_41953
0x418be  ldloc.s  5
0x418c0  ldc.i4.s 0x51
0x418c2  sub
0x418c3  switch   loc_41903, loc_4190C, loc_41915, loc_4191E, loc_41953, loc_41953, loc_418FA, loc_41953, loc_41943
0x418ec  ldloc.s  5
0x418ee  ldc.i4.s 0x68
0x418f0  beq.s    loc_41927
0x418f2  ldloc.s  5
0x418f4  ldc.i4.s 0x69
0x418f6  beq.s    loc_41953
0x418f8  br.s     loc_41953
0x418fa  ldarg.0
0x418fb  ldc.i4.3
0x418fc  stfld    valuetype System.Xml.Xsl.IlGen.PossibleXmlStates System.Xml.Xsl.IlGen.XmlILStateAnalyzer::xstates
0x41901  br.s     loc_41953
0x41903  ldarg.0
0x41904  ldc.i4.2
0x41905  stfld    valuetype System.Xml.Xsl.IlGen.PossibleXmlStates System.Xml.Xsl.IlGen.XmlILStateAnalyzer::xstates
0x4190a  br.s     loc_41953
0x4190c  ldarg.0
0x4190d  ldc.i4.4
0x4190e  stfld    valuetype System.Xml.Xsl.IlGen.PossibleXmlStates System.Xml.Xsl.IlGen.XmlILStateAnalyzer::xstates
0x41913  br.s     loc_41953
0x41915  ldarg.0
0x41916  ldc.i4.5
0x41917  stfld    valuetype System.Xml.Xsl.IlGen.PossibleXmlStates System.Xml.Xsl.IlGen.XmlILStateAnalyzer::xstates
0x4191c  br.s     loc_41953
0x4191e  ldarg.0
0x4191f  ldc.i4.6
0x41920  stfld    valuetype System.Xml.Xsl.IlGen.PossibleXmlStates System.Xml.Xsl.IlGen.XmlILStateAnalyzer::xstates
0x41925  br.s     loc_41953
0x41927  ldarg.0
0x41928  ldc.i4.7
0x41929  stfld    valuetype System.Xml.Xsl.IlGen.PossibleXmlStates System.Xml.Xsl.IlGen.XmlILStateAnalyzer::xstates
0x4192e  br.s     loc_41953
0x41930  ldarg.0
0x41931  ldarg.0
0x41932  ldfld    class System.Xml.Xsl.IlGen.XmlILConstructInfo System.Xml.Xsl.IlGen.XmlILStateAnalyzer::parentInfo
0x41937  callvirt instance valuetype System.Xml.Xsl.IlGen.PossibleXmlStates System.Xml.Xsl.IlGen.XmlILConstructInfo::get_InitialStates()
0x4193c  stfld    valuetype System.Xml.Xsl.IlGen.PossibleXmlStates System.Xml.Xsl.IlGen.XmlILStateAnalyzer::xstates
0x41941  br.s     loc_41953
0x41943  ldarg.0
0x41944  ldc.i4.3
0x41945  stfld    valuetype System.Xml.Xsl.IlGen.PossibleXmlStates System.Xml.Xsl.IlGen.XmlILStateAnalyzer::xstates
0x4194a  br.s     loc_41953
0x4194c  ldarg.0
0x4194d  ldc.i4.7
0x4194e  stfld    valuetype System.Xml.Xsl.IlGen.PossibleXmlStates System.Xml.Xsl.IlGen.XmlILStateAnalyzer::xstates
0x41953  ldarg.2
0x41954  brfalse.s loc_4195F
0x41956  ldarg.0
0x41957  ldarg.2
0x41958  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILStateAnalyzer::AnalyzeContent(class System.Xml.Xsl.Qil.QilNode nd)
0x4195d  starg.s  2
0x4195f  ldarg.1
0x41960  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x41965  ldc.i4.s 0x20
0x41967  bne.un.s loc_4197B
0x41969  ldarg.0
0x4196a  ldarg.1
0x4196b  isinst   System.Xml.Xsl.Qil.QilChoice
0x41970  ldarg.0
0x41971  ldfld    class System.Xml.Xsl.IlGen.XmlILConstructInfo System.Xml.Xsl.IlGen.XmlILStateAnalyzer::parentInfo
0x41976  callvirt instance void System.Xml.Xsl.IlGen.XmlILStateAnalyzer::AnalyzeChoice(class System.Xml.Xsl.Qil.QilChoice ndChoice, class System.Xml.Xsl.IlGen.XmlILConstructInfo info)
0x4197b  ldarg.1
0x4197c  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x41981  ldc.i4.s 0x41
0x41983  bne.un.s loc_41996
0x41985  ldarg.0
0x41986  ldfld    class System.Xml.Xsl.IlGen.XmlILConstructInfo System.Xml.Xsl.IlGen.XmlILStateAnalyzer::parentInfo
0x4198b  ldarg.0
0x4198c  ldfld    valuetype System.Xml.Xsl.IlGen.PossibleXmlStates System.Xml.Xsl.IlGen.XmlILStateAnalyzer::xstates
0x41991  callvirt instance void System.Xml.Xsl.IlGen.XmlILConstructInfo::set_FinalStates(valuetype System.Xml.Xsl.IlGen.PossibleXmlStates value)
0x41996  ldarg.2
0x41997  ret
```
