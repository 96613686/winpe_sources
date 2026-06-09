# System.Xml.Xsl.XmlILGenerator::Generate

- ea: `0x940`
- end: `0xb83`
- name: `System.Xml.Xsl.XmlILGenerator::Generate`
- size: `579`
- prototype: ``
- caller_count: `0`
- callee_count: `31`
- tags: `registry_config`

## callees

- `0x7c0`
- `0x940`
- `0xb90`
- `0xcd0`
- `0xd50`
- `0xdb0`
- `0xf50`
- `0x2b5f0`
- `0x2b600`
- `0x32040`
- `0x35d30`
- `0x35d70`
- `0x35db0`
- `0x35df0`
- `0x35e10`
- `0x35e30`
- `0x35e70`
- `0x35e90`
- `0x376e0`
- `0x3ef50`
- `0x3f060`
- `0x40f50`
- `0x423c0`
- `0x42430`
- `0x42510`
- `0x42780`
- `0x42840`
- `0x42a80`
- `0x42af0`
- `0x4a930`
- `0x50ac0`

## pseudocode

```c

```

## disassembly

```asm
0x940  ldarg.0
0x941  ldarg.1
0x942  stfld    class System.Xml.Xsl.Qil.QilExpression System.Xml.Xsl.XmlILGenerator::qil
0x947  ldarg.0
0x948  ldfld    class System.Xml.Xsl.Qil.QilExpression System.Xml.Xsl.XmlILGenerator::qil
0x94d  callvirt instance bool System.Xml.Xsl.Qil.QilExpression::get_IsDebug()
0x952  brtrue.s loc_95D
0x954  ldarg.2
0x955  ldnull
0x956  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x95b  br.s     loc_95E
0x95d  ldc.i4.0
0x95e  stloc.0
0x95f  ldarg.0
0x960  ldfld    class System.Xml.Xsl.Qil.QilExpression System.Xml.Xsl.XmlILGenerator::qil
0x965  callvirt instance bool System.Xml.Xsl.Qil.QilExpression::get_IsDebug()
0x96a  stloc.1
0x96b  ldarg.0
0x96c  ldarg.0
0x96d  ldfld    class System.Xml.Xsl.Qil.QilExpression System.Xml.Xsl.XmlILGenerator::qil
0x972  ldarg.0
0x973  ldfld    class System.Xml.Xsl.Qil.QilExpression System.Xml.Xsl.XmlILGenerator::qil
0x978  callvirt instance bool System.Xml.Xsl.Qil.QilExpression::get_IsDebug()
0x97d  ldc.i4.0
0x97e  ceq
0x980  newobj   instance void System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::.ctor(class System.Xml.Xsl.Qil.QilExpression qil, bool optimize)
0x985  stfld    class System.Xml.Xsl.IlGen.XmlILOptimizerVisitor System.Xml.Xsl.XmlILGenerator::optVisitor
0x98a  ldarg.0
0x98b  ldarg.0
0x98c  ldfld    class System.Xml.Xsl.IlGen.XmlILOptimizerVisitor System.Xml.Xsl.XmlILGenerator::optVisitor
0x991  callvirt instance class System.Xml.Xsl.Qil.QilExpression System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Optimize()
0x996  stfld    class System.Xml.Xsl.Qil.QilExpression System.Xml.Xsl.XmlILGenerator::qil
0x99b  ldsfld   class [mscorlib]System.Security.PermissionSet System.Xml.Xsl.IlGen.XmlILModule::CreateModulePermissionSet
0x9a0  callvirt instance void [mscorlib]System.Security.PermissionSet::Assert()
0x9a5  ldarg.2
0x9a6  ldnull
0x9a7  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x9ac  brfalse.s loc_9BC
0x9ae  ldarg.0
0x9af  ldarg.2
0x9b0  newobj   instance void System.Xml.Xsl.IlGen.XmlILModule::.ctor(class [mscorlib]System.Reflection.Emit.TypeBuilder typeBldr)
0x9b5  stfld    class System.Xml.Xsl.IlGen.XmlILModule System.Xml.Xsl.XmlILGenerator::module
0x9ba  br.s     loc_9C9
0x9bc  ldarg.0
0x9bd  ldloc.0
0x9be  ldloc.1
0x9bf  newobj   instance void System.Xml.Xsl.IlGen.XmlILModule::.ctor(bool useLRE, bool emitSymbols)
0x9c4  stfld    class System.Xml.Xsl.IlGen.XmlILModule System.Xml.Xsl.XmlILGenerator::module
0x9c9  ldarg.0
0x9ca  ldarg.0
0x9cb  ldfld    class System.Xml.Xsl.IlGen.XmlILModule System.Xml.Xsl.XmlILGenerator::module
0x9d0  ldarg.0
0x9d1  ldfld    class System.Xml.Xsl.Qil.QilExpression System.Xml.Xsl.XmlILGenerator::qil
0x9d6  callvirt instance bool System.Xml.Xsl.Qil.QilExpression::get_IsDebug()
0x9db  newobj   instance void System.Xml.Xsl.IlGen.GenerateHelper::.ctor(class System.Xml.Xsl.IlGen.XmlILModule module, bool isDebug)
0x9e0  stfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.XmlILGenerator::helper
0x9e5  ldarg.0
0x9e6  call     instance void System.Xml.Xsl.XmlILGenerator::CreateHelperFunctions()
0x9eb  ldarg.0
0x9ec  ldfld    class System.Xml.Xsl.IlGen.XmlILModule System.Xml.Xsl.XmlILGenerator::module
0x9f1  ldstr    aExecute// "Execute"
0x9f6  ldtoken  [mscorlib]System.Void
0x9fb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa00  ldc.i4.0
0xa01  newarr   [mscorlib]System.Type
0xa06  ldc.i4.0
0xa07  newarr   [mscorlib]System.String
0xa0c  ldc.i4.1
0xa0d  callvirt instance class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILModule::DefineMethod(string name, class [mscorlib]System.Type returnType, class [mscorlib]System.Type[] paramTypes, string[] paramNames, valuetype System.Xml.Xsl.IlGen.XmlILMethodAttributes xmlAttrs)
0xa12  stloc.2
0xa13  ldarg.0
0xa14  ldfld    class System.Xml.Xsl.Qil.QilExpression System.Xml.Xsl.XmlILGenerator::qil
0xa19  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilExpression::get_Root()
0xa1e  callvirt instance class System.Xml.Xsl.ISourceLineInfo System.Xml.Xsl.Qil.QilNode::get_SourceLine()
0xa23  brfalse.s loc_A28
0xa25  ldc.i4.0
0xa26  br.s     loc_A29
0xa28  ldc.i4.1
0xa29  stloc.3
0xa2a  ldarg.0
0xa2b  ldfld    class System.Xml.Xsl.IlGen.XmlILModule System.Xml.Xsl.XmlILGenerator::module
0xa30  ldstr    aRoot// "Root"
0xa35  ldtoken  [mscorlib]System.Void
0xa3a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa3f  ldc.i4.0
0xa40  newarr   [mscorlib]System.Type
0xa45  ldc.i4.0
0xa46  newarr   [mscorlib]System.String
0xa4b  ldloc.3
0xa4c  callvirt instance class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILModule::DefineMethod(string name, class [mscorlib]System.Type returnType, class [mscorlib]System.Type[] paramTypes, string[] paramNames, valuetype System.Xml.Xsl.IlGen.XmlILMethodAttributes xmlAttrs)
0xa51  stloc.s  4
0xa53  ldarg.0
0xa54  ldfld    class System.Xml.Xsl.Qil.QilExpression System.Xml.Xsl.XmlILGenerator::qil
0xa59  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Runtime.EarlyBoundInfo> System.Xml.Xsl.Qil.QilExpression::get_EarlyBoundTypes()
0xa5e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class System.Xml.Xsl.Runtime.EarlyBoundInfo>::GetEnumerator()
0xa63  stloc.s  6
0xa65  br.s     loc_A8F
0xa67  ldloc.s  6
0xa69  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class System.Xml.Xsl.Runtime.EarlyBoundInfo>::get_Current()
0xa6e  stloc.s  7
0xa70  ldarg.0
0xa71  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.XmlILGenerator::helper
0xa76  callvirt instance class System.Xml.Xsl.IlGen.StaticDataManager System.Xml.Xsl.IlGen.GenerateHelper::get_StaticData()
0xa7b  ldloc.s  7
0xa7d  callvirt instance string System.Xml.Xsl.Runtime.EarlyBoundInfo::get_NamespaceUri()
0xa82  ldloc.s  7
0xa84  callvirt instance class [mscorlib]System.Type System.Xml.Xsl.Runtime.EarlyBoundInfo::get_EarlyBoundType()
0xa89  callvirt instance int32 System.Xml.Xsl.IlGen.StaticDataManager::DeclareEarlyBound(string namespaceUri, class [mscorlib]System.Type ebType)
0xa8e  pop
0xa8f  ldloc.s  6
0xa91  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xa96  brtrue.s loc_A67
0xa98  leave.s  loc_AA6
0xa9a  ldloc.s  6
0xa9c  brfalse.s loc_AA5
0xa9e  ldloc.s  6
0xaa0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xaa5  endfinally
0xaa6  ldarg.0
0xaa7  ldarg.0
0xaa8  ldfld    class System.Xml.Xsl.Qil.QilExpression System.Xml.Xsl.XmlILGenerator::qil
0xaad  callvirt instance class System.Xml.Xsl.Qil.QilList System.Xml.Xsl.Qil.QilExpression::get_FunctionList()
0xab2  call     instance void System.Xml.Xsl.XmlILGenerator::CreateFunctionMetadata(class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode> funcList)
0xab7  ldarg.0
0xab8  ldarg.0
0xab9  ldfld    class System.Xml.Xsl.Qil.QilExpression System.Xml.Xsl.XmlILGenerator::qil
0xabe  callvirt instance class System.Xml.Xsl.Qil.QilList System.Xml.Xsl.Qil.QilExpression::get_GlobalVariableList()
0xac3  call     instance void System.Xml.Xsl.XmlILGenerator::CreateGlobalValueMetadata(class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode> globalList)
0xac8  ldarg.0
0xac9  ldarg.0
0xaca  ldfld    class System.Xml.Xsl.Qil.QilExpression System.Xml.Xsl.XmlILGenerator::qil
0xacf  callvirt instance class System.Xml.Xsl.Qil.QilList System.Xml.Xsl.Qil.QilExpression::get_GlobalParameterList()
0xad4  call     instance void System.Xml.Xsl.XmlILGenerator::CreateGlobalValueMetadata(class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode> globalList)
0xad9  ldarg.0
0xada  ldloc.2
0xadb  ldloc.s  4
0xadd  call     instance class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.XmlILGenerator::GenerateExecuteFunction(class [mscorlib]System.Reflection.MethodInfo methExec, class [mscorlib]System.Reflection.MethodInfo methRoot)
0xae2  pop
0xae3  ldarg.0
0xae4  newobj   instance void System.Xml.Xsl.IlGen.XmlILVisitor::.ctor()
0xae9  stfld    class System.Xml.Xsl.IlGen.XmlILVisitor System.Xml.Xsl.XmlILGenerator::xmlIlVisitor
0xaee  ldarg.0
0xaef  ldfld    class System.Xml.Xsl.IlGen.XmlILVisitor System.Xml.Xsl.XmlILGenerator::xmlIlVisitor
0xaf4  ldarg.0
0xaf5  ldfld    class System.Xml.Xsl.Qil.QilExpression System.Xml.Xsl.XmlILGenerator::qil
0xafa  ldarg.0
0xafb  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.XmlILGenerator::helper
0xb00  ldloc.s  4
0xb02  callvirt instance void System.Xml.Xsl.IlGen.XmlILVisitor::Visit(class System.Xml.Xsl.Qil.QilExpression qil, class System.Xml.Xsl.IlGen.GenerateHelper helper, class [mscorlib]System.Reflection.MethodInfo methRoot)
0xb07  ldarg.0
0xb08  ldfld    class System.Xml.Xsl.Qil.QilExpression System.Xml.Xsl.XmlILGenerator::qil
0xb0d  callvirt instance class [System.Xml]System.Xml.XmlWriterSettings System.Xml.Xsl.Qil.QilExpression::get_DefaultWriterSettings()
0xb12  ldarg.0
0xb13  ldfld    class System.Xml.Xsl.Qil.QilExpression System.Xml.Xsl.XmlILGenerator::qil
0xb18  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.WhitespaceRule> System.Xml.Xsl.Qil.QilExpression::get_WhitespaceRules()
0xb1d  ldarg.0
0xb1e  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.XmlILGenerator::helper
0xb23  callvirt instance class System.Xml.Xsl.IlGen.StaticDataManager System.Xml.Xsl.IlGen.GenerateHelper::get_StaticData()
0xb28  newobj   instance void System.Xml.Xsl.Runtime.XmlQueryStaticData::.ctor(class [System.Xml]System.Xml.XmlWriterSettings defaultWriterSettings, class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.WhitespaceRule> whitespaceRules, class System.Xml.Xsl.IlGen.StaticDataManager staticData)
0xb2d  stloc.s  5
0xb2f  ldarg.2
0xb30  ldnull
0xb31  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xb36  brfalse.s loc_B4D
0xb38  ldarg.0
0xb39  ldloc.s  5
0xb3b  call     instance void System.Xml.Xsl.XmlILGenerator::CreateTypeInitializer(class System.Xml.Xsl.Runtime.XmlQueryStaticData staticData)
0xb40  ldarg.0
0xb41  ldfld    class System.Xml.Xsl.IlGen.XmlILModule System.Xml.Xsl.XmlILGenerator::module
0xb46  callvirt instance void System.Xml.Xsl.IlGen.XmlILModule::BakeMethods()
0xb4b  ldnull
0xb4c  ret
0xb4d  ldarg.0
0xb4e  ldfld    class System.Xml.Xsl.IlGen.XmlILModule System.Xml.Xsl.XmlILGenerator::module
0xb53  callvirt instance void System.Xml.Xsl.IlGen.XmlILModule::BakeMethods()
0xb58  ldarg.0
0xb59  ldfld    class System.Xml.Xsl.IlGen.XmlILModule System.Xml.Xsl.XmlILGenerator::module
0xb5e  ldstr    aExecute// "Execute"
0xb63  ldtoken  System.Xml.Xsl.ExecuteDelegate
0xb68  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xb6d  callvirt instance class [mscorlib]System.Delegate System.Xml.Xsl.IlGen.XmlILModule::CreateDelegate(string name, class [mscorlib]System.Type typDelegate)
0xb72  castclass System.Xml.Xsl.ExecuteDelegate
0xb77  stloc.s  8
0xb79  ldloc.s  8
0xb7b  ldloc.s  5
0xb7d  newobj   instance void System.Xml.Xsl.XmlILCommand::.ctor(class System.Xml.Xsl.ExecuteDelegate delExec, class System.Xml.Xsl.Runtime.XmlQueryStaticData staticData)
0xb82  ret
```
