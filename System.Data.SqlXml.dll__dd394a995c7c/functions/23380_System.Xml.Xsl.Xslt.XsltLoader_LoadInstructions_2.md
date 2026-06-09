# System.Xml.Xsl.Xslt.XsltLoader::LoadInstructions_2

- ea: `0x23380`
- end: `0x23794`
- name: `System.Xml.Xsl.Xslt.XsltLoader::LoadInstructions_2`
- size: `1044`
- prototype: ``
- caller_count: `3`
- callee_count: `37`
- tags: `registry_config, broker_com_uri`

## callers

- `0x23350`
- `0x23360`
- `0x23370`

## callees

- `0x1e290`
- `0x1f8a0`
- `0x1f8c0`
- `0x1f8e0`
- `0x1f920`
- `0x1f960`
- `0x20190`
- `0x201b0`
- `0x201e0`
- `0x205f0`
- `0x20fd0`
- `0x23380`
- `0x238d0`
- `0x239e0`
- `0x23a40`
- `0x23a80`
- `0x23b20`
- `0x23b90`
- `0x23bb0`
- `0x23bf0`
- `0x23db0`
- `0x23e10`
- `0x23e80`
- `0x24010`
- `0x24140`
- `0x24330`
- `0x243d0`
- `0x24430`
- `0x24500`
- `0x245c0`
- `0x24690`
- `0x24780`
- `0x24940`
- `0x24990`
- `0x254b0`
- `0x25580`
- `0x56c00`

## string_xrefs

- `0x2339f`: `Xslt_InputTooComplex`

## pseudocode

```c

```

## disassembly

```asm
0x23380  ldarg.0
0x23381  ldarg.0
0x23382  ldfld    int32 System.Xml.Xsl.Xslt.XsltLoader::loadInstructionsDepth
0x23387  ldc.i4.1
0x23388  add
0x23389  stloc.1
0x2338a  ldloc.1
0x2338b  stfld    int32 System.Xml.Xsl.Xslt.XsltLoader::loadInstructionsDepth
0x23390  ldloc.1
0x23391  ldc.i4   0x400
0x23396  ble.s    loc_233B0
0x23398  call     bool [System.Xml]System.Xml.XmlConfiguration.XsltConfigSection::get_LimitXPathComplexity()
0x2339d  brfalse.s loc_233B0
0x2339f  ldstr    aXsltInputtooco// "Xslt_InputTooComplex"
0x233a4  ldc.i4.0
0x233a5  newarr   [mscorlib]System.String
0x233aa  call     class [System.Xml]System.Xml.Xsl.XsltException [System.Xml]System.Xml.Xsl.XsltException::Create(string, string[])
0x233af  throw
0x233b0  ldarg.0
0x233b1  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x233b6  callvirt instance valuetype DelayedQName System.Xml.Xsl.Xslt.XsltInput::get_ElementName()
0x233bb  stloc.0
0x233bc  ldarg.0
0x233bd  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x233c2  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::MoveToFirstChild()
0x233c7  brfalse  loc_23784
0x233cc  ldc.i4.1
0x233cd  stloc.2
0x233ce  ldc.i4.0
0x233cf  stloc.3
0x233d0  ldarg.0
0x233d1  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x233d6  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType System.Xml.Xsl.Xslt.XsltInput::get_NodeType()
0x233db  stloc.s  7
0x233dd  ldloc.s  7
0x233df  ldc.i4.1
0x233e0  beq.s    loc_233F9
0x233e2  ldloc.s  7
0x233e4  ldc.i4.s 0xD
0x233e6  beq      loc_23774
0x233eb  ldloc.s  7
0x233ed  ldc.i4.s 0xE
0x233ef  beq      loc_23744
0x233f4  br       loc_23768
0x233f9  ldarg.0
0x233fa  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x233ff  callvirt instance string System.Xml.Xsl.Xslt.XsltInput::get_NamespaceUri()
0x23404  stloc.s  5
0x23406  ldarg.0
0x23407  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x2340c  callvirt instance string System.Xml.Xsl.Xslt.XsltInput::get_LocalName()
0x23411  stloc.s  6
0x23413  ldloc.s  5
0x23415  ldarg.0
0x23416  ldfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.Xslt.XsltLoader::atoms
0x2341b  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::UriXsl
0x23420  call     bool [mscorlib]System.String::op_Equality(string, string)
0x23425  brfalse  loc_23737
0x2342a  ldloc.s  6
0x2342c  ldarg.0
0x2342d  ldfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.Xslt.XsltLoader::atoms
0x23432  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::Param
0x23437  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x2343c  brtrue.s loc_23458
0x2343e  ldloc.s  6
0x23440  ldarg.0
0x23441  ldfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.Xslt.XsltLoader::atoms
0x23446  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::Sort
0x2344b  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x23450  brtrue.s loc_23455
0x23452  ldc.i4.0
0x23453  br.s     loc_23459
0x23455  ldc.i4.2
0x23456  br.s     loc_23459
0x23458  ldc.i4.1
0x23459  stloc.s  8
0x2345b  ldloc.s  8
0x2345d  brfalse.s loc_234B4
0x2345f  ldarg.2
0x23460  ldloc.s  8
0x23462  and
0x23463  brfalse.s loc_23472
0x23465  ldloc.2
0x23466  brfalse.s loc_2346B
0x23468  ldnull
0x23469  br.s     loc_23477
0x2346b  ldstr    aXsltNotattop// "Xslt_NotAtTop"
0x23470  br.s     loc_23477
0x23472  ldstr    aXsltUnexpected_0// "Xslt_UnexpectedElement"
0x23477  stloc.s  9
0x23479  ldloc.s  9
0x2347b  brfalse.s loc_234B6
0x2347d  ldarg.0
0x2347e  ldloc.s  9
0x23480  ldc.i4.2
0x23481  newarr   [mscorlib]System.String
0x23486  dup
0x23487  ldc.i4.0
0x23488  ldarg.0
0x23489  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x2348e  callvirt instance string System.Xml.Xsl.Xslt.XsltInput::get_QualifiedName()
0x23493  stelem.ref
0x23494  dup
0x23495  ldc.i4.1
0x23496  ldloc.0
0x23497  call     string DelayedQName::op_Implicit(valuetype DelayedQName qn)
0x2349c  stelem.ref
0x2349d  call     instance void System.Xml.Xsl.Xslt.XsltLoader::ReportError(string res, string[] args)
0x234a2  ldc.i4.0
0x234a3  stloc.2
0x234a4  ldarg.0
0x234a5  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x234aa  callvirt instance void System.Xml.Xsl.Xslt.XsltInput::SkipNode()
0x234af  br       loc_23774
0x234b4  ldc.i4.0
0x234b5  stloc.2
0x234b6  ldloc.s  6
0x234b8  ldarg.0
0x234b9  ldfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.Xslt.XsltLoader::atoms
0x234be  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::ApplyImports
0x234c3  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x234c8  brtrue   loc_2372D
0x234cd  ldloc.s  6
0x234cf  ldarg.0
0x234d0  ldfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.Xslt.XsltLoader::atoms
0x234d5  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::ApplyTemplates
0x234da  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x234df  brtrue   loc_23725
0x234e4  ldloc.s  6
0x234e6  ldarg.0
0x234e7  ldfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.Xslt.XsltLoader::atoms
0x234ec  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::CallTemplate
0x234f1  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x234f6  brtrue   loc_2371D
0x234fb  ldloc.s  6
0x234fd  ldarg.0
0x234fe  ldfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.Xslt.XsltLoader::atoms
0x23503  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::Copy
0x23508  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x2350d  brtrue   loc_23715
0x23512  ldloc.s  6
0x23514  ldarg.0
0x23515  ldfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.Xslt.XsltLoader::atoms
0x2351a  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::CopyOf
0x2351f  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x23524  brtrue   loc_2370D
0x23529  ldloc.s  6
0x2352b  ldarg.0
0x2352c  ldfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.Xslt.XsltLoader::atoms
0x23531  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::Fallback
0x23536  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x2353b  brtrue   loc_23705
0x23540  ldloc.s  6
0x23542  ldarg.0
0x23543  ldfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.Xslt.XsltLoader::atoms
0x23548  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::If
0x2354d  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x23552  brtrue   loc_236FD
0x23557  ldloc.s  6
0x23559  ldarg.0
0x2355a  ldfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.Xslt.XsltLoader::atoms
0x2355f  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::Choose
0x23564  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x23569  brtrue   loc_236F5
0x2356e  ldloc.s  6
0x23570  ldarg.0
0x23571  ldfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.Xslt.XsltLoader::atoms
0x23576  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::ForEach
0x2357b  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x23580  brtrue   loc_236ED
0x23585  ldloc.s  6
0x23587  ldarg.0
0x23588  ldfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.Xslt.XsltLoader::atoms
0x2358d  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::Message
0x23592  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x23597  brtrue   loc_236E5
0x2359c  ldloc.s  6
0x2359e  ldarg.0
0x2359f  ldfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.Xslt.XsltLoader::atoms
0x235a4  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::Number
0x235a9  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x235ae  brtrue   loc_236DD
0x235b3  ldloc.s  6
0x235b5  ldarg.0
0x235b6  ldfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.Xslt.XsltLoader::atoms
0x235bb  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::ValueOf
0x235c0  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x235c5  brtrue   loc_236D5
0x235ca  ldloc.s  6
0x235cc  ldarg.0
0x235cd  ldfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.Xslt.XsltLoader::atoms
0x235d2  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::Comment
0x235d7  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x235dc  brtrue   loc_236CD
0x235e1  ldloc.s  6
0x235e3  ldarg.0
0x235e4  ldfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.Xslt.XsltLoader::atoms
0x235e9  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::ProcessingInstruction
0x235ee  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x235f3  brtrue   loc_236C5
0x235f8  ldloc.s  6
0x235fa  ldarg.0
0x235fb  ldfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.Xslt.XsltLoader::atoms
0x23600  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::Text
0x23605  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x2360a  brtrue   loc_236BD
0x2360f  ldloc.s  6
0x23611  ldarg.0
0x23612  ldfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.Xslt.XsltLoader::atoms
0x23617  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::Element
0x2361c  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x23621  brtrue   loc_236B5
0x23626  ldloc.s  6
0x23628  ldarg.0
0x23629  ldfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.Xslt.XsltLoader::atoms
0x2362e  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::Attribute
0x23633  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x23638  brtrue.s loc_236AD
0x2363a  ldloc.s  6
0x2363c  ldarg.0
0x2363d  ldfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.Xslt.XsltLoader::atoms
0x23642  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::Variable
0x23647  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x2364c  brtrue.s loc_236A2
0x2364e  ldloc.s  6
0x23650  ldarg.0
0x23651  ldfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.Xslt.XsltLoader::atoms
0x23656  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::Param
0x2365b  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x23660  brtrue.s loc_23697
0x23662  ldloc.s  6
0x23664  ldarg.0
0x23665  ldfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.Xslt.XsltLoader::atoms
0x2366a  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::Sort
0x2366f  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x23674  brtrue.s loc_23687
0x23676  ldarg.0
0x23677  ldloc.0
0x23678  call     string DelayedQName::op_Implicit(valuetype DelayedQName qn)
0x2367d  call     instance class System.Xml.Xsl.Xslt.XslNode System.Xml.Xsl.Xslt.XsltLoader::LoadUnknownXsltInstruction(string parentName)
0x23682  br       loc_23733
0x23687  ldarg.0
0x23688  ldloc.3
0x23689  dup
0x2368a  ldc.i4.1
0x2368b  add
0x2368c  stloc.3
0x2368d  call     instance class System.Xml.Xsl.Xslt.XslNode System.Xml.Xsl.Xslt.XsltLoader::XslSort(int32 sortNumber)
0x23692  br       loc_23733
0x23697  ldarg.0
0x23698  call     instance class System.Xml.Xsl.Xslt.VarPar System.Xml.Xsl.Xslt.XsltLoader::XslVarPar()
0x2369d  br       loc_23733
0x236a2  ldarg.0
0x236a3  call     instance class System.Xml.Xsl.Xslt.VarPar System.Xml.Xsl.Xslt.XsltLoader::XslVarPar()
0x236a8  br       loc_23733
0x236ad  ldarg.0
0x236ae  call     instance class System.Xml.Xsl.Xslt.XslNode System.Xml.Xsl.Xslt.XsltLoader::XslAttribute()
0x236b3  br.s     loc_23733
0x236b5  ldarg.0
0x236b6  call     instance class System.Xml.Xsl.Xslt.XslNode System.Xml.Xsl.Xslt.XsltLoader::XslElement()
0x236bb  br.s     loc_23733
0x236bd  ldarg.0
0x236be  call     instance class System.Xml.Xsl.Xslt.XslNode System.Xml.Xsl.Xslt.XsltLoader::XslText()
0x236c3  br.s     loc_23733
0x236c5  ldarg.0
0x236c6  call     instance class System.Xml.Xsl.Xslt.XslNode System.Xml.Xsl.Xslt.XsltLoader::XslProcessingInstruction()
0x236cb  br.s     loc_23733
0x236cd  ldarg.0
0x236ce  call     instance class System.Xml.Xsl.Xslt.XslNode System.Xml.Xsl.Xslt.XsltLoader::XslComment()
0x236d3  br.s     loc_23733
0x236d5  ldarg.0
0x236d6  call     instance class System.Xml.Xsl.Xslt.XslNode System.Xml.Xsl.Xslt.XsltLoader::XslValueOf()
0x236db  br.s     loc_23733
0x236dd  ldarg.0
0x236de  call     instance class System.Xml.Xsl.Xslt.XslNode System.Xml.Xsl.Xslt.XsltLoader::XslNumber()
0x236e3  br.s     loc_23733
0x236e5  ldarg.0
0x236e6  call     instance class System.Xml.Xsl.Xslt.XslNode System.Xml.Xsl.Xslt.XsltLoader::XslMessage()
0x236eb  br.s     loc_23733
0x236ed  ldarg.0
0x236ee  call     instance class System.Xml.Xsl.Xslt.XslNode System.Xml.Xsl.Xslt.XsltLoader::XslForEach()
0x236f3  br.s     loc_23733
0x236f5  ldarg.0
0x236f6  call     instance class System.Xml.Xsl.Xslt.XslNode System.Xml.Xsl.Xslt.XsltLoader::XslChoose()
0x236fb  br.s     loc_23733
0x236fd  ldarg.0
0x236fe  call     instance class System.Xml.Xsl.Xslt.XslNode System.Xml.Xsl.Xslt.XsltLoader::XslIf()
0x23703  br.s     loc_23733
0x23705  ldarg.0
0x23706  call     instance class System.Xml.Xsl.Xslt.XslNode System.Xml.Xsl.Xslt.XsltLoader::XslFallback()
0x2370b  br.s     loc_23733
0x2370d  ldarg.0
0x2370e  call     instance class System.Xml.Xsl.Xslt.XslNode System.Xml.Xsl.Xslt.XsltLoader::XslCopyOf()
0x23713  br.s     loc_23733
0x23715  ldarg.0
0x23716  call     instance class System.Xml.Xsl.Xslt.XslNode System.Xml.Xsl.Xslt.XsltLoader::XslCopy()
0x2371b  br.s     loc_23733
0x2371d  ldarg.0
0x2371e  call     instance class System.Xml.Xsl.Xslt.XslNode System.Xml.Xsl.Xslt.XsltLoader::XslCallTemplate()
0x23723  br.s     loc_23733
  ... truncated ...
```
