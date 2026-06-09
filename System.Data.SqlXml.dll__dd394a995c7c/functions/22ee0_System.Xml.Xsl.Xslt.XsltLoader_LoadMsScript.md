# System.Xml.Xsl.Xslt.XsltLoader::LoadMsScript

- ea: `0x22ee0`
- end: `0x23218`
- name: `System.Xml.Xsl.Xslt.XsltLoader::LoadMsScript`
- size: `824`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `registry_config`

## callers

- `0x21890`

## callees

- `0x3b0`
- `0x13aa0`
- `0x1c0d0`
- `0x1c180`
- `0x1c1d0`
- `0x1f8a0`
- `0x1f920`
- `0x1f960`
- `0x1f990`
- `0x1f9b0`
- `0x1f9d0`
- `0x20190`
- `0x201b0`
- `0x201e0`
- `0x20590`
- `0x205f0`
- `0x20610`
- `0x20620`
- `0x20800`
- `0x210c0`
- `0x22ee0`
- `0x23220`
- `0x23300`
- `0x25170`
- `0x25510`
- `0x25580`
- `0x56c00`

## pseudocode

```c

```

## disassembly

```asm
0x22ee0  ldarg.0
0x22ee1  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x22ee6  ldarg.0
0x22ee7  ldfld    valuetype XsltAttribute[] System.Xml.Xsl.Xslt.XsltLoader::scriptAttributes
0x22eec  callvirt instance class ContextInfo System.Xml.Xsl.Xslt.XsltInput::GetAttributes(valuetype XsltAttribute[] attributes)
0x22ef1  stloc.0
0x22ef2  ldloc.0
0x22ef3  ldloc.0
0x22ef4  ldfld    class System.Xml.Xsl.Xslt.NsDecl ContextInfo::nsList
0x22ef9  ldarg.1
0x22efa  call     class System.Xml.Xsl.Xslt.NsDecl System.Xml.Xsl.Xslt.XsltLoader::MergeNamespaces(class System.Xml.Xsl.Xslt.NsDecl thisList, class System.Xml.Xsl.Xslt.NsDecl parentList)
0x22eff  stfld    class System.Xml.Xsl.Xslt.NsDecl ContextInfo::nsList
0x22f04  ldnull
0x22f05  stloc.1
0x22f06  ldarg.0
0x22f07  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x22f0c  ldc.i4.0
0x22f0d  ldstr    aImplementsPref// "implements-prefix"
0x22f12  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::MoveToXsltAttribute(int32 attNum, string attName)
0x22f17  brfalse.s loc_22F8B
0x22f19  ldarg.0
0x22f1a  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x22f1f  callvirt instance string System.Xml.Xsl.Xslt.XsltInput::get_Value()
0x22f24  callvirt instance int32 [mscorlib]System.String::get_Length()
0x22f29  brtrue.s loc_22F54
0x22f2b  ldarg.0
0x22f2c  ldstr    aXsltEmptyattrv// "Xslt_EmptyAttrValue"
0x22f31  ldc.i4.2
0x22f32  newarr   [mscorlib]System.String
0x22f37  dup
0x22f38  ldc.i4.0
0x22f39  ldstr    aImplementsPref// "implements-prefix"
0x22f3e  stelem.ref
0x22f3f  dup
0x22f40  ldc.i4.1
0x22f41  ldarg.0
0x22f42  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x22f47  callvirt instance string System.Xml.Xsl.Xslt.XsltInput::get_Value()
0x22f4c  stelem.ref
0x22f4d  call     instance void System.Xml.Xsl.Xslt.XsltLoader::ReportError(string res, string[] args)
0x22f52  br.s     loc_22F8B
0x22f54  ldarg.0
0x22f55  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x22f5a  ldarg.0
0x22f5b  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x22f60  callvirt instance string System.Xml.Xsl.Xslt.XsltInput::get_Value()
0x22f65  callvirt instance string System.Xml.Xsl.Xslt.XsltInput::LookupXmlNamespace(string prefix)
0x22f6a  stloc.1
0x22f6b  ldloc.1
0x22f6c  ldstr    aHttpWwwW3Org19// "http://www.w3.org/1999/XSL/Transform"
0x22f71  call     bool [mscorlib]System.String::op_Equality(string, string)
0x22f76  brfalse.s loc_22F8B
0x22f78  ldarg.0
0x22f79  ldstr    aXsltScriptxslt// "Xslt_ScriptXsltNamespace"
0x22f7e  ldc.i4.0
0x22f7f  newarr   [mscorlib]System.String
0x22f84  call     instance void System.Xml.Xsl.Xslt.XsltLoader::ReportError(string res, string[] args)
0x22f89  ldnull
0x22f8a  stloc.1
0x22f8b  ldloc.1
0x22f8c  brtrue.s loc_22F9A
0x22f8e  ldarg.0
0x22f8f  ldfld    class System.Xml.Xsl.Xslt.Compiler System.Xml.Xsl.Xslt.XsltLoader::compiler
0x22f94  callvirt instance string System.Xml.Xsl.Xslt.Compiler::CreatePhantomNamespace()
0x22f99  stloc.1
0x22f9a  ldarg.0
0x22f9b  ldc.i4.1
0x22f9c  ldstr    aLanguage// "language"
0x22fa1  call     instance string System.Xml.Xsl.Xslt.XsltLoader::ParseStringAttribute(int32 attNum, string attName)
0x22fa6  stloc.2
0x22fa7  ldloc.2
0x22fa8  brtrue.s loc_22FB0
0x22faa  ldstr    aJscript// "jscript"
0x22faf  stloc.2
0x22fb0  ldarg.0
0x22fb1  ldfld    class System.Xml.Xsl.Xslt.Compiler System.Xml.Xsl.Xslt.XsltLoader::compiler
0x22fb6  ldfld    class [System.Xml]System.Xml.Xsl.XsltSettings System.Xml.Xsl.Xslt.Compiler::Settings
0x22fbb  callvirt instance bool [System.Xml]System.Xml.Xsl.XsltSettings::get_EnableScript()
0x22fc0  brtrue.s loc_22FE5
0x22fc2  ldarg.0
0x22fc3  ldfld    class System.Xml.Xsl.Xslt.Compiler System.Xml.Xsl.Xslt.XsltLoader::compiler
0x22fc8  ldfld    class System.Xml.Xsl.Xslt.Scripts System.Xml.Xsl.Xslt.Compiler::Scripts
0x22fcd  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Type> System.Xml.Xsl.Xslt.Scripts::get_ScriptClasses()
0x22fd2  ldloc.1
0x22fd3  ldnull
0x22fd4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Type>::set_Item(var<u1>, !!T0)
0x22fd9  ldarg.0
0x22fda  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x22fdf  callvirt instance void System.Xml.Xsl.Xslt.XsltInput::SkipNode()
0x22fe4  ret
0x22fe5  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x22fea  stloc.s  4
0x22fec  ldarg.0
0x22fed  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x22ff2  callvirt instance string System.Xml.Xsl.Xslt.XsltInput::get_Uri()
0x22ff7  stloc.s  5
0x22ff9  ldc.i4.0
0x22ffa  stloc.s  6
0x22ffc  ldc.i4.0
0x22ffd  stloc.s  7
0x22fff  ldarg.0
0x23000  ldfld    class System.Xml.Xsl.Xslt.Compiler System.Xml.Xsl.Xslt.XsltLoader::compiler
0x23005  ldfld    class System.Xml.Xsl.Xslt.Scripts System.Xml.Xsl.Xslt.Compiler::Scripts
0x2300a  ldloc.1
0x2300b  ldloc.2
0x2300c  ldarg.0
0x2300d  callvirt instance class System.Xml.Xsl.Xslt.ScriptClass System.Xml.Xsl.Xslt.Scripts::GetScriptClass(string ns, string language, class System.Xml.Xsl.IErrorHelper errorHelper)
0x23012  stloc.3
0x23013  ldloc.3
0x23014  brtrue.s loc_23022
0x23016  ldarg.0
0x23017  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x2301c  callvirt instance void System.Xml.Xsl.Xslt.XsltInput::SkipNode()
0x23021  ret
0x23022  ldarg.0
0x23023  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x23028  callvirt instance valuetype DelayedQName System.Xml.Xsl.Xslt.XsltInput::get_ElementName()
0x2302d  stloc.s  8
0x2302f  ldarg.0
0x23030  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x23035  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::MoveToFirstChild()
0x2303a  brfalse  loc_231DC
0x2303f  ldarg.0
0x23040  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x23045  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType System.Xml.Xsl.Xslt.XsltInput::get_NodeType()
0x2304a  stloc.s  0xB
0x2304c  ldloc.s  0xB
0x2304e  ldc.i4.1
0x2304f  beq.s    loc_230C5
0x23051  ldloc.s  0xB
0x23053  ldc.i4.3
0x23054  bne.un   loc_231C0
0x23059  ldarg.0
0x2305a  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x2305f  callvirt instance valuetype System.Xml.Xsl.Location System.Xml.Xsl.Xslt.XsltInput::get_Start()
0x23064  stloc.s  0xC
0x23066  ldloca.s 0xC
0x23068  call     instance int32 System.Xml.Xsl.Location::get_Line()
0x2306d  stloc.s  9
0x2306f  ldarg.0
0x23070  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x23075  callvirt instance valuetype System.Xml.Xsl.Location System.Xml.Xsl.Xslt.XsltInput::get_End()
0x2307a  stloc.s  0xC
0x2307c  ldloca.s 0xC
0x2307e  call     instance int32 System.Xml.Xsl.Location::get_Line()
0x23083  stloc.s  0xA
0x23085  ldloc.s  4
0x23087  callvirt instance int32 [mscorlib]System.Text.StringBuilder::get_Length()
0x2308c  brtrue.s loc_23094
0x2308e  ldloc.s  9
0x23090  stloc.s  6
0x23092  br.s     loc_230A9
0x23094  ldloc.s  7
0x23096  ldloc.s  9
0x23098  bge.s    loc_230A9
0x2309a  ldloc.s  4
0x2309c  ldc.i4.s 0xA
0x2309e  ldloc.s  9
0x230a0  ldloc.s  7
0x230a2  sub
0x230a3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char, int32)
0x230a8  pop
0x230a9  ldloc.s  4
0x230ab  ldarg.0
0x230ac  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x230b1  callvirt instance string System.Xml.Xsl.Xslt.XsltInput::get_Value()
0x230b6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x230bb  pop
0x230bc  ldloc.s  0xA
0x230be  stloc.s  7
0x230c0  br       loc_231CC
0x230c5  ldarg.0
0x230c6  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x230cb  ldarg.0
0x230cc  ldfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.Xslt.XsltLoader::atoms
0x230d1  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::UrnMsxsl
0x230d6  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::IsNs(string ns)
0x230db  brfalse  loc_2318A
0x230e0  ldarg.0
0x230e1  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x230e6  ldarg.0
0x230e7  ldfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.Xslt.XsltLoader::atoms
0x230ec  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::Assembly
0x230f1  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::IsKeyword(string kwd)
0x230f6  brtrue.s loc_23110
0x230f8  ldarg.0
0x230f9  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x230fe  ldarg.0
0x230ff  ldfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.Xslt.XsltLoader::atoms
0x23104  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::Using
0x23109  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::IsKeyword(string kwd)
0x2310e  brfalse.s loc_2318A
0x23110  ldloc.s  4
0x23112  callvirt instance int32 [mscorlib]System.Text.StringBuilder::get_Length()
0x23117  brfalse.s loc_23148
0x23119  ldarg.0
0x2311a  ldstr    aXsltScriptnota// "Xslt_ScriptNotAtTop"
0x2311f  ldc.i4.1
0x23120  newarr   [mscorlib]System.String
0x23125  dup
0x23126  ldc.i4.0
0x23127  ldarg.0
0x23128  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x2312d  callvirt instance string System.Xml.Xsl.Xslt.XsltInput::get_QualifiedName()
0x23132  stelem.ref
0x23133  call     instance void System.Xml.Xsl.Xslt.XsltLoader::ReportError(string res, string[] args)
0x23138  ldarg.0
0x23139  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x2313e  callvirt instance void System.Xml.Xsl.Xslt.XsltInput::SkipNode()
0x23143  br       loc_231CC
0x23148  ldarg.0
0x23149  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x2314e  ldarg.0
0x2314f  ldfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.Xslt.XsltLoader::atoms
0x23154  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::Assembly
0x23159  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::IsKeyword(string kwd)
0x2315e  brfalse.s loc_23169
0x23160  ldarg.0
0x23161  ldloc.3
0x23162  call     instance void System.Xml.Xsl.Xslt.XsltLoader::LoadMsAssembly(class System.Xml.Xsl.Xslt.ScriptClass scriptClass)
0x23167  br.s     loc_231CC
0x23169  ldarg.0
0x2316a  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x2316f  ldarg.0
0x23170  ldfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.Xslt.XsltLoader::atoms
0x23175  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::Using
0x2317a  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::IsKeyword(string kwd)
0x2317f  brfalse.s loc_231CC
0x23181  ldarg.0
0x23182  ldloc.3
0x23183  call     instance void System.Xml.Xsl.Xslt.XsltLoader::LoadMsUsing(class System.Xml.Xsl.Xslt.ScriptClass scriptClass)
0x23188  br.s     loc_231CC
0x2318a  ldarg.0
0x2318b  ldstr    aXsltUnexpected_0// "Xslt_UnexpectedElement"
0x23190  ldc.i4.2
0x23191  newarr   [mscorlib]System.String
0x23196  dup
0x23197  ldc.i4.0
0x23198  ldarg.0
0x23199  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x2319e  callvirt instance string System.Xml.Xsl.Xslt.XsltInput::get_QualifiedName()
0x231a3  stelem.ref
0x231a4  dup
0x231a5  ldc.i4.1
0x231a6  ldloc.s  8
0x231a8  call     string DelayedQName::op_Implicit(valuetype DelayedQName qn)
0x231ad  stelem.ref
0x231ae  call     instance void System.Xml.Xsl.Xslt.XsltLoader::ReportError(string res, string[] args)
0x231b3  ldarg.0
0x231b4  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x231b9  callvirt instance void System.Xml.Xsl.Xslt.XsltInput::SkipNode()
0x231be  br.s     loc_231CC
0x231c0  ldloc.s  4
0x231c2  callvirt instance int32 [mscorlib]System.Text.StringBuilder::get_Length()
0x231c7  brtrue   loc_23059
0x231cc  ldarg.0
0x231cd  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x231d2  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::MoveToNextSibling()
0x231d7  brtrue   loc_2303F
0x231dc  ldloc.s  4
0x231de  callvirt instance int32 [mscorlib]System.Text.StringBuilder::get_Length()
0x231e3  brtrue.s loc_231FB
0x231e5  ldarg.0
0x231e6  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x231eb  callvirt instance valuetype System.Xml.Xsl.Location System.Xml.Xsl.Xslt.XsltInput::get_Start()
0x231f0  stloc.s  0xC
0x231f2  ldloca.s 0xC
0x231f4  call     instance int32 System.Xml.Xsl.Location::get_Line()
0x231f9  stloc.s  6
0x231fb  ldloc.3
0x231fc  ldloc.s  4
0x231fe  callvirt instance string [mscorlib]System.Object::ToString()
0x23203  ldloc.s  5
0x23205  ldloc.s  6
0x23207  ldarg.0
0x23208  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x2320d  callvirt instance valuetype System.Xml.Xsl.Location System.Xml.Xsl.Xslt.XsltInput::get_Start()
0x23212  callvirt instance void System.Xml.Xsl.Xslt.ScriptClass::AddScriptBlock(string source, string uriString, int32 lineNumber, valuetype System.Xml.Xsl.Location end)
0x23217  ret
```
