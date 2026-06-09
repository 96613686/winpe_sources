# System.Xml.Xsl.Xslt.XsltLoader::XslVarPar

- ea: `0x24140`
- end: `0x24325`
- name: `System.Xml.Xsl.Xslt.XsltLoader::XslVarPar`
- size: `485`
- prototype: ``
- caller_count: `3`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x22c90`
- `0x23380`
- `0x237a0`

## callees

- `0x1e2c0`
- `0x1f8c0`
- `0x206d0`
- `0x206f0`
- `0x20800`
- `0x24140`
- `0x24380`
- `0x24e00`
- `0x25170`
- `0x25200`
- `0x254e0`
- `0x25580`
- `0x255c0`
- `0x255f0`

## string_xrefs

- `0x24293`: `Xslt_NonTemplateTunnel`

## pseudocode

```c

```

## disassembly

```asm
0x24140  ldarg.0
0x24141  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x24146  callvirt instance string System.Xml.Xsl.Xslt.XsltInput::get_LocalName()
0x2414b  stloc.0
0x2414c  ldloc.0
0x2414d  ldarg.0
0x2414e  ldfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.Xslt.XsltLoader::atoms
0x24153  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::Variable
0x24158  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x2415d  brtrue.s loc_24190
0x2415f  ldloc.0
0x24160  ldarg.0
0x24161  ldfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.Xslt.XsltLoader::atoms
0x24166  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::Param
0x2416b  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x24170  brtrue.s loc_2418C
0x24172  ldloc.0
0x24173  ldarg.0
0x24174  ldfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.Xslt.XsltLoader::atoms
0x24179  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::WithParam
0x2417e  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x24183  brtrue.s loc_24188
0x24185  ldc.i4.0
0x24186  br.s     loc_24192
0x24188  ldc.i4.s 0x1F
0x2418a  br.s     loc_24192
0x2418c  ldc.i4.s 0x16
0x2418e  br.s     loc_24192
0x24190  ldc.i4.s 0x1E
0x24192  stloc.1
0x24193  ldloc.0
0x24194  ldarg.0
0x24195  ldfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.Xslt.XsltLoader::atoms
0x2419a  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::Param
0x2419f  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x241a4  stloc.2
0x241a5  ldarg.0
0x241a6  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x241ab  ldloc.1
0x241ac  ldc.i4.s 0x1E
0x241ae  beq.s    loc_241C5
0x241b0  ldloc.1
0x241b1  ldc.i4.s 0x16
0x241b3  beq.s    loc_241BD
0x241b5  ldarg.0
0x241b6  ldfld    valuetype XsltAttribute[] System.Xml.Xsl.Xslt.XsltLoader::withParamAttributes
0x241bb  br.s     loc_241CB
0x241bd  ldarg.0
0x241be  ldfld    valuetype XsltAttribute[] System.Xml.Xsl.Xslt.XsltLoader::paramAttributes
0x241c3  br.s     loc_241CB
0x241c5  ldarg.0
0x241c6  ldfld    valuetype XsltAttribute[] System.Xml.Xsl.Xslt.XsltLoader::variableAttributes
0x241cb  callvirt instance class ContextInfo System.Xml.Xsl.Xslt.XsltInput::GetAttributes(valuetype XsltAttribute[] attributes)
0x241d0  stloc.3
0x241d1  ldarg.0
0x241d2  ldc.i4.0
0x241d3  call     instance class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.XsltLoader::ParseQNameAttribute(int32 attNum)
0x241d8  stloc.s  4
0x241da  ldarg.0
0x241db  ldc.i4.1
0x241dc  ldstr    aSelect// "select"
0x241e1  call     instance string System.Xml.Xsl.Xslt.XsltLoader::ParseStringAttribute(int32 attNum, string attName)
0x241e6  stloc.s  5
0x241e8  ldarg.0
0x241e9  ldc.i4.2
0x241ea  ldstr    aAs// "as"
0x241ef  call     instance string System.Xml.Xsl.Xslt.XsltLoader::ParseStringAttribute(int32 attNum, string attName)
0x241f4  stloc.s  6
0x241f6  ldarg.0
0x241f7  ldc.i4.3
0x241f8  ldstr    aRequired// "required"
0x241fd  call     instance valuetype [System.Xml]System.Xml.TriState System.Xml.Xsl.Xslt.XsltLoader::ParseYesNoAttribute(int32 attNum, string attName)
0x24202  stloc.s  7
0x24204  ldloc.1
0x24205  ldc.i4.s 0x16
0x24207  bne.un.s loc_24246
0x24209  ldarg.0
0x2420a  ldfld    object System.Xml.Xsl.Xslt.XsltLoader::curFunction
0x2420f  brfalse.s loc_24246
0x24211  ldarg.0
0x24212  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x24217  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::get_ForwardCompatibility()
0x2421c  brtrue.s loc_24241
0x2421e  ldarg.0
0x2421f  ldloc.s  7
0x24221  ldc.i4.m1
0x24222  ceq
0x24224  ldc.i4.0
0x24225  ceq
0x24227  ldstr    aXsltRequiredon// "Xslt_RequiredOnFunction"
0x2422c  ldc.i4.1
0x2422d  newarr   [mscorlib]System.String
0x24232  dup
0x24233  ldc.i4.0
0x24234  ldloc.s  4
0x24236  callvirt instance string [mscorlib]System.Object::ToString()
0x2423b  stelem.ref
0x2423c  call     instance void System.Xml.Xsl.Xslt.XsltLoader::CheckError(bool cond, string res, string[] args)
0x24241  ldc.i4.1
0x24242  stloc.s  7
0x24244  br.s     loc_24256
0x24246  ldloc.s  7
0x24248  ldc.i4.1
0x24249  bne.un.s loc_24256
0x2424b  ldarg.0
0x2424c  ldstr    aXslParamRequir// "xsl:param/@required == true()"
0x24251  call     instance void System.Xml.Xsl.Xslt.XsltLoader::ReportNYI(string arg)
0x24256  ldloc.s  6
0x24258  brfalse.s loc_24265
0x2425a  ldarg.0
0x2425b  ldstr    aXslParamAs// "xsl:param/@as"
0x24260  call     instance void System.Xml.Xsl.Xslt.XsltLoader::ReportNYI(string arg)
0x24265  ldarg.0
0x24266  ldc.i4.4
0x24267  ldstr    aTunnel// "tunnel"
0x2426c  call     instance valuetype [System.Xml]System.Xml.TriState System.Xml.Xsl.Xslt.XsltLoader::ParseYesNoAttribute(int32 attNum, string attName)
0x24271  stloc.s  8
0x24273  ldloc.s  8
0x24275  ldc.i4.m1
0x24276  beq.s    loc_242BF
0x24278  ldloc.1
0x24279  ldc.i4.s 0x16
0x2427b  bne.un.s loc_242AF
0x2427d  ldarg.0
0x2427e  ldfld    class System.Xml.Xsl.Xslt.Template System.Xml.Xsl.Xslt.XsltLoader::curTemplate
0x24283  brtrue.s loc_242AF
0x24285  ldarg.0
0x24286  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x2428b  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::get_ForwardCompatibility()
0x24290  brtrue.s loc_242BF
0x24292  ldarg.0
0x24293  ldstr    aXsltNontemplat// "Xslt_NonTemplateTunnel"
0x24298  ldc.i4.1
0x24299  newarr   [mscorlib]System.String
0x2429e  dup
0x2429f  ldc.i4.0
0x242a0  ldloc.s  4
0x242a2  callvirt instance string [mscorlib]System.Object::ToString()
0x242a7  stelem.ref
0x242a8  call     instance void System.Xml.Xsl.Xslt.XsltLoader::ReportError(string res, string[] args)
0x242ad  br.s     loc_242BF
0x242af  ldloc.s  8
0x242b1  ldc.i4.1
0x242b2  bne.un.s loc_242BF
0x242b4  ldarg.0
0x242b5  ldstr    aXslParamTunnel// "xsl:param/@tunnel == true()"
0x242ba  call     instance void System.Xml.Xsl.Xslt.XsltLoader::ReportNYI(string arg)
0x242bf  ldarg.0
0x242c0  ldloc.s  5
0x242c2  ldnull
0x242c3  cgt.un
0x242c5  call     instance class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode> System.Xml.Xsl.Xslt.XsltLoader::LoadContent(bool hasSelect)
0x242ca  stloc.s  9
0x242cc  ldarg.0
0x242cd  ldloc.s  7
0x242cf  ldc.i4.1
0x242d0  bne.un.s loc_242E5
0x242d2  ldloc.s  5
0x242d4  brtrue.s loc_242E2
0x242d6  ldloc.s  9
0x242d8  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode>::get_Count()
0x242dd  ldc.i4.0
0x242de  cgt.un
0x242e0  br.s     loc_242E6
0x242e2  ldc.i4.1
0x242e3  br.s     loc_242E6
0x242e5  ldc.i4.0
0x242e6  ldstr    aXsltRequiredan// "Xslt_RequiredAndSelect"
0x242eb  ldc.i4.1
0x242ec  newarr   [mscorlib]System.String
0x242f1  dup
0x242f2  ldc.i4.0
0x242f3  ldloc.s  4
0x242f5  callvirt instance string [mscorlib]System.Object::ToString()
0x242fa  stelem.ref
0x242fb  call     instance void System.Xml.Xsl.Xslt.XsltLoader::CheckError(bool cond, string res, string[] args)
0x24300  ldloc.1
0x24301  ldloc.s  4
0x24303  ldloc.s  5
0x24305  ldarg.0
0x24306  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x2430b  callvirt instance valuetype System.Xml.Xsl.Xslt.XslVersion System.Xml.Xsl.Xslt.XsltInput::get_XslVersion()
0x24310  call     class System.Xml.Xsl.Xslt.VarPar System.Xml.Xsl.Xslt.AstFactory::VarPar(valuetype System.Xml.Xsl.Xslt.XslNodeType nt, class System.Xml.Xsl.Qil.QilName name, string select, valuetype System.Xml.Xsl.Xslt.XslVersion xslVer)
0x24315  stloc.s  0xA
0x24317  ldloc.s  0xA
0x24319  ldloc.s  9
0x2431b  ldloc.3
0x2431c  call     class System.Xml.Xsl.Xslt.XslNode System.Xml.Xsl.Xslt.XsltLoader::SetInfo(class System.Xml.Xsl.Xslt.XslNode to, class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode> content, class ContextInfo info)
0x24321  pop
0x24322  ldloc.s  0xA
0x24324  ret
```
