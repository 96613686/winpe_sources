# System.Xml.Xsl.IlGen.XmlILNamespaceAnalyzer::CheckNamespaceInScope

- ea: `0x42150`
- end: `0x42290`
- name: `System.Xml.Xsl.IlGen.XmlILNamespaceAnalyzer::CheckNamespaceInScope`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x41fc0`

## callees

- `0x35920`
- `0x35940`
- `0x373b0`
- `0x374d0`
- `0x374f0`
- `0x375d0`
- `0x376a0`
- `0x413a0`
- `0x415b0`
- `0x42150`

## string_xrefs

- `0x421dc`: `http://www.w3.org/XML/1998/namespace`

## pseudocode

```c

```

## disassembly

```asm
0x42150  ldarg.1
0x42151  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x42156  stloc.s  6
0x42158  ldloc.s  6
0x4215a  ldc.i4.s 0x51
0x4215c  sub
0x4215d  ldc.i4.1
0x4215e  bgt.un.s loc_42197
0x42160  ldarg.1
0x42161  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilBinary::get_Left()
0x42166  isinst   System.Xml.Xsl.Qil.QilName
0x4216b  stloc.0
0x4216c  ldloc.0
0x4216d  ldnull
0x4216e  call     bool System.Xml.Xsl.Qil.QilName::op_Inequality(class System.Xml.Xsl.Qil.QilName a, class System.Xml.Xsl.Qil.QilName b)
0x42173  brfalse.s loc_42195
0x42175  ldloc.0
0x42176  callvirt instance string System.Xml.Xsl.Qil.QilName::get_Prefix()
0x4217b  stloc.1
0x4217c  ldloc.0
0x4217d  callvirt instance string System.Xml.Xsl.Qil.QilName::get_NamespaceUri()
0x42182  stloc.2
0x42183  ldarg.1
0x42184  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x42189  ldc.i4.s 0x51
0x4218b  beq.s    loc_42190
0x4218d  ldc.i4.2
0x4218e  br.s     loc_42191
0x42190  ldc.i4.1
0x42191  stloc.s  5
0x42193  br.s     loc_421BC
0x42195  ldc.i4.0
0x42196  ret
0x42197  ldarg.1
0x42198  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilBinary::get_Left()
0x4219d  castclass System.Xml.Xsl.Qil.QilLiteral
0x421a2  call     string System.Xml.Xsl.Qil.QilLiteral::op_Implicit(class System.Xml.Xsl.Qil.QilLiteral literal)
0x421a7  stloc.1
0x421a8  ldarg.1
0x421a9  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilBinary::get_Right()
0x421ae  castclass System.Xml.Xsl.Qil.QilLiteral
0x421b3  call     string System.Xml.Xsl.Qil.QilLiteral::op_Implicit(class System.Xml.Xsl.Qil.QilLiteral literal)
0x421b8  stloc.2
0x421b9  ldc.i4.3
0x421ba  stloc.s  5
0x421bc  ldarg.1
0x421bd  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x421c2  ldc.i4.s 0x52
0x421c4  bne.un.s loc_421CE
0x421c6  ldloc.2
0x421c7  callvirt instance int32 [mscorlib]System.String::get_Length()
0x421cc  brfalse.s loc_421E8
0x421ce  ldloc.1
0x421cf  ldstr    aXml// "xml"
0x421d4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x421d9  brfalse.s loc_421F6
0x421db  ldloc.2
0x421dc  ldstr    aHttpWwwW3OrgXm// "http://www.w3.org/XML/1998/namespace"
0x421e1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x421e6  brfalse.s loc_421F6
0x421e8  ldarg.1
0x421e9  call     class System.Xml.Xsl.IlGen.XmlILConstructInfo System.Xml.Xsl.IlGen.XmlILConstructInfo::Write(class System.Xml.Xsl.Qil.QilNode nd)
0x421ee  ldc.i4.1
0x421ef  callvirt instance void System.Xml.Xsl.IlGen.XmlILConstructInfo::set_IsNamespaceInScope(bool value)
0x421f4  ldc.i4.1
0x421f5  ret
0x421f6  ldloc.1
0x421f7  ldsfld   string [mscorlib]System.String::Empty
0x421fc  ldloc.2
0x421fd  ldloc.s  5
0x421ff  ldc.i4.4
0x42200  call     bool [System.Xml]System.Xml.ValidateNames::ValidateName(string, string, string, valuetype [System.Xml]System.Xml.XPath.XPathNodeType, valuetype [System.Xml]System.Xml.ValidateNames/Flags)
0x42205  brtrue.s loc_42209
0x42207  ldc.i4.0
0x42208  ret
0x42209  ldarg.0
0x4220a  ldfld    class [System.Xml]System.Xml.XmlNamespaceManager System.Xml.Xsl.IlGen.XmlILNamespaceAnalyzer::nsmgr
0x4220f  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlNamespaceManager::get_NameTable()
0x42214  ldloc.1
0x42215  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x4221a  stloc.1
0x4221b  ldarg.0
0x4221c  ldfld    class [System.Xml]System.Xml.XmlNamespaceManager System.Xml.Xsl.IlGen.XmlILNamespaceAnalyzer::nsmgr
0x42221  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlNamespaceManager::get_NameTable()
0x42226  ldloc.2
0x42227  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x4222c  stloc.2
0x4222d  ldc.i4.0
0x4222e  stloc.s  7
0x42230  br.s     loc_42261
0x42232  ldarg.0
0x42233  ldfld    class [System.Xml]System.Xml.XmlNamespaceManager System.Xml.Xsl.IlGen.XmlILNamespaceAnalyzer::nsmgr
0x42238  ldloc.s  7
0x4223a  ldloca.s 3
0x4223c  ldloca.s 4
0x4223e  callvirt instance bool [System.Xml]System.Xml.XmlNamespaceManager::GetNamespaceDeclaration(int32, string&, string&)
0x42243  pop
0x42244  ldloc.1
0x42245  ldloc.3
0x42246  bne.un.s loc_4225B
0x42248  ldloc.2
0x42249  ldloc.s  4
0x4224b  bne.un.s loc_4226B
0x4224d  ldarg.1
0x4224e  call     class System.Xml.Xsl.IlGen.XmlILConstructInfo System.Xml.Xsl.IlGen.XmlILConstructInfo::Write(class System.Xml.Xsl.Qil.QilNode nd)
0x42253  ldc.i4.1
0x42254  callvirt instance void System.Xml.Xsl.IlGen.XmlILConstructInfo::set_IsNamespaceInScope(bool value)
0x42259  br.s     loc_4226B
0x4225b  ldloc.s  7
0x4225d  ldc.i4.1
0x4225e  add
0x4225f  stloc.s  7
0x42261  ldloc.s  7
0x42263  ldarg.0
0x42264  ldfld    int32 System.Xml.Xsl.IlGen.XmlILNamespaceAnalyzer::cntNmsp
0x42269  blt.s    loc_42232
0x4226b  ldarg.0
0x4226c  ldfld    bool System.Xml.Xsl.IlGen.XmlILNamespaceAnalyzer::addInScopeNmsp
0x42271  brfalse.s loc_4228E
0x42273  ldarg.0
0x42274  ldfld    class [System.Xml]System.Xml.XmlNamespaceManager System.Xml.Xsl.IlGen.XmlILNamespaceAnalyzer::nsmgr
0x42279  ldloc.1
0x4227a  ldloc.2
0x4227b  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x42280  ldarg.0
0x42281  ldarg.0
0x42282  ldfld    int32 System.Xml.Xsl.IlGen.XmlILNamespaceAnalyzer::cntNmsp
0x42287  ldc.i4.1
0x42288  add
0x42289  stfld    int32 System.Xml.Xsl.IlGen.XmlILNamespaceAnalyzer::cntNmsp
0x4228e  ldc.i4.1
0x4228f  ret
```
