# System.Web.Compilation.PageCodeDomTreeGenerator::BuildFrameworkInitializeMethodContents

- ea: `0x1810d0`
- end: `0x181350`
- name: `System.Web.Compilation.PageCodeDomTreeGenerator::BuildFrameworkInitializeMethodContents`
- size: `640`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callees

- `0x71070`
- `0x710a0`
- `0x71220`
- `0x77d30`
- `0x77d40`
- `0x77d90`
- `0x77dd0`
- `0x80440`
- `0x17ffd0`
- `0x1807d0`
- `0x1810d0`
- `0x183ea0`

## string_xrefs

- `0x1811e6`: `__outputCacheSettings`
- `0x1811cf`: `InitOutputCache`

## pseudocode

```c

```

## disassembly

```asm
0x1810d0  ldarg.0
0x1810d1  call     instance class System.Web.UI.PageParser System.Web.Compilation.PageCodeDomTreeGenerator::get_Parser()
0x1810d6  callvirt instance string System.Web.UI.PageParser::get_StyleSheetTheme()
0x1810db  brfalse.s loc_181113
0x1810dd  ldarg.0
0x1810de  call     instance class System.Web.UI.PageParser System.Web.Compilation.PageCodeDomTreeGenerator::get_Parser()
0x1810e3  callvirt instance string System.Web.UI.PageParser::get_StyleSheetTheme()
0x1810e8  newobj   instance void [System]System.CodeDom.CodePrimitiveExpression::.ctor(object)
0x1810ed  stloc.1
0x1810ee  newobj   instance void [System]System.CodeDom.CodeThisReferenceExpression::.ctor()
0x1810f3  ldstr    aStylesheetthem_1// "StyleSheetTheme"
0x1810f8  newobj   instance void [System]System.CodeDom.CodePropertyReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0x1810fd  stloc.2
0x1810fe  ldloc.2
0x1810ff  ldloc.1
0x181100  newobj   instance void [System]System.CodeDom.CodeAssignStatement::.ctor(class [System]System.CodeDom.CodeExpression, class [System]System.CodeDom.CodeExpression)
0x181105  stloc.3
0x181106  ldarg.1
0x181107  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x18110c  ldloc.3
0x18110d  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x181112  pop
0x181113  ldarg.0
0x181114  ldarg.1
0x181115  call     instance void System.Web.Compilation.TemplateControlCodeDomTreeGenerator::BuildFrameworkInitializeMethodContents(class [System]System.CodeDom.CodeMemberMethod method)
0x18111a  newobj   instance void [System]System.CodeDom.CodeMethodInvokeExpression::.ctor()
0x18111f  stloc.0
0x181120  ldloc.0
0x181121  callvirt instance class [System]System.CodeDom.CodeMethodReferenceExpression [System]System.CodeDom.CodeMethodInvokeExpression::get_Method()
0x181126  newobj   instance void [System]System.CodeDom.CodeThisReferenceExpression::.ctor()
0x18112b  callvirt instance void [System]System.CodeDom.CodeMethodReferenceExpression::set_TargetObject(class [System]System.CodeDom.CodeExpression)
0x181130  ldloc.0
0x181131  callvirt instance class [System]System.CodeDom.CodeMethodReferenceExpression [System]System.CodeDom.CodeMethodInvokeExpression::get_Method()
0x181136  ldstr    aAddwrappedfile// "AddWrappedFileDependencies"
0x18113b  callvirt instance void [System]System.CodeDom.CodeMethodReferenceExpression::set_MethodName(string)
0x181140  ldloc.0
0x181141  callvirt instance class [System]System.CodeDom.CodeExpressionCollection [System]System.CodeDom.CodeMethodInvokeExpression::get_Parameters()
0x181146  ldarg.0
0x181147  ldfld    class [System]System.CodeDom.CodeTypeReferenceExpression System.Web.Compilation.BaseCodeDomTreeGenerator::_classTypeExpr
0x18114c  ldstr    aFiledependenci// "__fileDependencies"
0x181151  newobj   instance void [System]System.CodeDom.CodeFieldReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0x181156  callvirt instance int32 [System]System.CodeDom.CodeExpressionCollection::Add(class [System]System.CodeDom.CodeExpression)
0x18115b  pop
0x18115c  ldarg.1
0x18115d  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x181162  ldloc.0
0x181163  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeExpression)
0x181168  pop
0x181169  ldarg.0
0x18116a  call     instance class System.Web.UI.PageParser System.Web.Compilation.PageCodeDomTreeGenerator::get_Parser()
0x18116f  callvirt instance class System.Web.UI.OutputCacheParameters System.Web.UI.TemplateControlParser::get_OutputCacheParameters()
0x181174  brfalse  loc_181204
0x181179  ldarg.0
0x18117a  call     instance class System.Web.UI.PageParser System.Web.Compilation.PageCodeDomTreeGenerator::get_Parser()
0x18117f  callvirt instance class System.Web.UI.OutputCacheParameters System.Web.UI.TemplateControlParser::get_OutputCacheParameters()
0x181184  stloc.s  4
0x181186  ldloc.s  4
0x181188  callvirt instance string System.Web.UI.OutputCacheParameters::get_CacheProfile()
0x18118d  brfalse.s loc_18119D
0x18118f  ldloc.s  4
0x181191  callvirt instance string System.Web.UI.OutputCacheParameters::get_CacheProfile()
0x181196  callvirt instance int32 [mscorlib]System.String::get_Length()
0x18119b  brtrue.s loc_1811B0
0x18119d  ldloc.s  4
0x18119f  callvirt instance int32 System.Web.UI.OutputCacheParameters::get_Duration()
0x1811a4  brtrue.s loc_1811B0
0x1811a6  ldloc.s  4
0x1811a8  callvirt instance valuetype System.Web.UI.OutputCacheLocation System.Web.UI.OutputCacheParameters::get_Location()
0x1811ad  ldc.i4.4
0x1811ae  bne.un.s loc_181204
0x1811b0  newobj   instance void [System]System.CodeDom.CodeMethodInvokeExpression::.ctor()
0x1811b5  stloc.s  5
0x1811b7  ldloc.s  5
0x1811b9  callvirt instance class [System]System.CodeDom.CodeMethodReferenceExpression [System]System.CodeDom.CodeMethodInvokeExpression::get_Method()
0x1811be  newobj   instance void [System]System.CodeDom.CodeThisReferenceExpression::.ctor()
0x1811c3  callvirt instance void [System]System.CodeDom.CodeMethodReferenceExpression::set_TargetObject(class [System]System.CodeDom.CodeExpression)
0x1811c8  ldloc.s  5
0x1811ca  callvirt instance class [System]System.CodeDom.CodeMethodReferenceExpression [System]System.CodeDom.CodeMethodInvokeExpression::get_Method()
0x1811cf  ldstr    aInitoutputcach// "InitOutputCache"
0x1811d4  callvirt instance void [System]System.CodeDom.CodeMethodReferenceExpression::set_MethodName(string)
0x1811d9  ldloc.s  5
0x1811db  callvirt instance class [System]System.CodeDom.CodeExpressionCollection [System]System.CodeDom.CodeMethodInvokeExpression::get_Parameters()
0x1811e0  ldarg.0
0x1811e1  ldfld    class [System]System.CodeDom.CodeTypeReferenceExpression System.Web.Compilation.BaseCodeDomTreeGenerator::_classTypeExpr
0x1811e6  ldstr    aOutputcacheset_0// "__outputCacheSettings"
0x1811eb  newobj   instance void [System]System.CodeDom.CodeFieldReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0x1811f0  callvirt instance int32 [System]System.CodeDom.CodeExpressionCollection::Add(class [System]System.CodeDom.CodeExpression)
0x1811f5  pop
0x1811f6  ldarg.1
0x1811f7  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x1811fc  ldloc.s  5
0x1811fe  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeExpression)
0x181203  pop
0x181204  ldarg.0
0x181205  call     instance class System.Web.UI.PageParser System.Web.Compilation.PageCodeDomTreeGenerator::get_Parser()
0x18120a  callvirt instance valuetype System.Web.TraceEnable System.Web.UI.PageParser::get_TraceEnabled()
0x18120f  brfalse.s loc_181249
0x181211  ldarg.1
0x181212  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x181217  newobj   instance void [System]System.CodeDom.CodeThisReferenceExpression::.ctor()
0x18121c  ldstr    aTraceenabled// "TraceEnabled"
0x181221  newobj   instance void [System]System.CodeDom.CodePropertyReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0x181226  ldarg.0
0x181227  call     instance class System.Web.UI.PageParser System.Web.Compilation.PageCodeDomTreeGenerator::get_Parser()
0x18122c  callvirt instance valuetype System.Web.TraceEnable System.Web.UI.PageParser::get_TraceEnabled()
0x181231  ldc.i4.1
0x181232  ceq
0x181234  box      [mscorlib]System.Boolean
0x181239  newobj   instance void [System]System.CodeDom.CodePrimitiveExpression::.ctor(object)
0x18123e  newobj   instance void [System]System.CodeDom.CodeAssignStatement::.ctor(class [System]System.CodeDom.CodeExpression, class [System]System.CodeDom.CodeExpression)
0x181243  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x181248  pop
0x181249  ldarg.0
0x18124a  call     instance class System.Web.UI.PageParser System.Web.Compilation.PageCodeDomTreeGenerator::get_Parser()
0x18124f  callvirt instance valuetype System.Web.TraceMode System.Web.UI.PageParser::get_TraceMode()
0x181254  ldc.i4.2
0x181255  beq.s    loc_1812A5
0x181257  ldarg.1
0x181258  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x18125d  newobj   instance void [System]System.CodeDom.CodeThisReferenceExpression::.ctor()
0x181262  ldstr    aTracemodevalue// "TraceModeValue"
0x181267  newobj   instance void [System]System.CodeDom.CodePropertyReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0x18126c  ldtoken  System.Web.TraceMode
0x181271  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x181276  newobj   instance void [System]System.CodeDom.CodeTypeReferenceExpression::.ctor(class [mscorlib]System.Type)
0x18127b  ldarg.0
0x18127c  call     instance class System.Web.UI.PageParser System.Web.Compilation.PageCodeDomTreeGenerator::get_Parser()
0x181281  callvirt instance valuetype System.Web.TraceMode System.Web.UI.PageParser::get_TraceMode()
0x181286  stloc.s  6
0x181288  ldloca.s 6
0x18128a  constrained. System.Web.TraceMode
0x181290  callvirt instance string [mscorlib]System.Object::ToString()
0x181295  newobj   instance void [System]System.CodeDom.CodeFieldReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0x18129a  newobj   instance void [System]System.CodeDom.CodeAssignStatement::.ctor(class [System]System.CodeDom.CodeExpression, class [System]System.CodeDom.CodeExpression)
0x18129f  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x1812a4  pop
0x1812a5  ldarg.0
0x1812a6  call     instance class System.Web.UI.PageParser System.Web.Compilation.PageCodeDomTreeGenerator::get_Parser()
0x1812ab  callvirt instance bool System.Web.UI.PageParser::get_ValidateRequest()
0x1812b0  brfalse.s loc_1812F9
0x1812b2  newobj   instance void [System]System.CodeDom.CodeMethodInvokeExpression::.ctor()
0x1812b7  stloc.s  7
0x1812b9  ldloc.s  7
0x1812bb  callvirt instance class [System]System.CodeDom.CodeMethodReferenceExpression [System]System.CodeDom.CodeMethodInvokeExpression::get_Method()
0x1812c0  newobj   instance void [System]System.CodeDom.CodeThisReferenceExpression::.ctor()
0x1812c5  ldstr    aRequest_1// "Request"
0x1812ca  newobj   instance void [System]System.CodeDom.CodePropertyReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0x1812cf  callvirt instance void [System]System.CodeDom.CodeMethodReferenceExpression::set_TargetObject(class [System]System.CodeDom.CodeExpression)
0x1812d4  ldloc.s  7
0x1812d6  callvirt instance class [System]System.CodeDom.CodeMethodReferenceExpression [System]System.CodeDom.CodeMethodInvokeExpression::get_Method()
0x1812db  ldstr    aValidateinput// "ValidateInput"
0x1812e0  callvirt instance void [System]System.CodeDom.CodeMethodReferenceExpression::set_MethodName(string)
0x1812e5  ldarg.1
0x1812e6  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x1812eb  ldloc.s  7
0x1812ed  newobj   instance void [System]System.CodeDom.CodeExpressionStatement::.ctor(class [System]System.CodeDom.CodeExpression)
0x1812f2  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x1812f7  pop
0x1812f8  ret
0x1812f9  call     class [mscorlib]System.Version System.Web.Compilation.MultiTargetingUtil::get_TargetFrameworkVersion()
0x1812fe  ldsfld   class [mscorlib]System.Version System.Web.Util.VersionUtil::Framework45
0x181303  call     bool [mscorlib]System.Version::op_GreaterThanOrEqual(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x181308  brfalse.s loc_18134F
0x18130a  newobj   instance void [System]System.CodeDom.CodeThisReferenceExpression::.ctor()
0x18130f  ldstr    aValidatereques// "ValidateRequestMode"
0x181314  newobj   instance void [System]System.CodeDom.CodePropertyReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0x181319  stloc.s  8
0x18131b  ldtoken  System.Web.UI.ValidateRequestMode
0x181320  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x181325  newobj   instance void [System]System.CodeDom.CodeTypeReferenceExpression::.ctor(class [mscorlib]System.Type)
0x18132a  ldstr    aDisabled_0// "Disabled"
0x18132f  newobj   instance void [System]System.CodeDom.CodeFieldReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0x181334  stloc.s  9
0x181336  ldloc.s  8
0x181338  ldloc.s  9
0x18133a  newobj   instance void [System]System.CodeDom.CodeAssignStatement::.ctor(class [System]System.CodeDom.CodeExpression, class [System]System.CodeDom.CodeExpression)
0x18133f  stloc.s  0xA
0x181341  ldarg.1
0x181342  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x181347  ldloc.s  0xA
0x181349  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x18134e  pop
0x18134f  ret
```
