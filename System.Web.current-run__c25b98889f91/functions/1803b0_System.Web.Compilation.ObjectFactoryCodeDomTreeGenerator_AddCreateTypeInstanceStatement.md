# System.Web.Compilation.ObjectFactoryCodeDomTreeGenerator::AddCreateTypeInstanceStatement

- ea: `0x1803b0`
- end: `0x1804f1`
- name: `System.Web.Compilation.ObjectFactoryCodeDomTreeGenerator::AddCreateTypeInstanceStatement`
- size: `321`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180360`

## callees

- `0x34f20`
- `0x4ef20`
- `0x1803b0`
- `0x180500`

## string_xrefs

- `0x180497`: `Could_not_create_type_instance`
- `0x18040f`: `GetService`

## pseudocode

```c

```

## disassembly

```asm
0x1803b0  ldsfld   class System.Web.Util.BinaryCompatibility System.Web.Util.BinaryCompatibility::Current
0x1803b5  callvirt instance bool System.Web.Util.BinaryCompatibility::get_TargetsAtLeastFramework472()
0x1803ba  brfalse  loc_1804D4
0x1803bf  ldarg.1
0x1803c0  brfalse  loc_1804D4
0x1803c5  ldstr    aSystemWebHttpr_0// "System.Web.HttpRuntime"
0x1803ca  newobj   instance void [System]System.CodeDom.CodeTypeReferenceExpression::.ctor(string)
0x1803cf  ldstr    aWebobjectactiv// "WebObjectActivator"
0x1803d4  newobj   instance void [System]System.CodeDom.CodePropertyReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0x1803d9  stloc.0
0x1803da  ldarg.2
0x1803db  ldtoken  [mscorlib]System.IServiceProvider
0x1803e0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1803e5  ldstr    aActivator// "__activator"
0x1803ea  newobj   instance void [System]System.CodeDom.CodeVariableDeclarationStatement::.ctor(class [mscorlib]System.Type, string)
0x1803ef  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x1803f4  pop
0x1803f5  ldstr    aActivator// "__activator"
0x1803fa  newobj   instance void [System]System.CodeDom.CodeVariableReferenceExpression::.ctor(string)
0x1803ff  stloc.1
0x180400  ldarg.2
0x180401  ldloc.1
0x180402  ldloc.0
0x180403  newobj   instance void [System]System.CodeDom.CodeAssignStatement::.ctor(class [System]System.CodeDom.CodeExpression, class [System]System.CodeDom.CodeExpression)
0x180408  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x18040d  pop
0x18040e  ldloc.1
0x18040f  ldstr    aGetservice// "GetService"
0x180414  ldc.i4.1
0x180415  newarr   [System]System.CodeDom.CodeExpression
0x18041a  dup
0x18041b  ldc.i4.0
0x18041c  ldarg.0
0x18041d  newobj   instance void [System]System.CodeDom.CodeTypeOfExpression::.ctor(string)
0x180422  stelem.ref
0x180423  newobj   instance void [System]System.CodeDom.CodeMethodInvokeExpression::.ctor(class [System]System.CodeDom.CodeExpression, string, class [System]System.CodeDom.CodeExpression[])
0x180428  stloc.2
0x180429  newobj   instance void [System]System.CodeDom.CodeConditionStatement::.ctor()
0x18042e  dup
0x18042f  ldloc.1
0x180430  ldc.i4.6
0x180431  ldnull
0x180432  newobj   instance void [System]System.CodeDom.CodePrimitiveExpression::.ctor(object)
0x180437  newobj   instance void [System]System.CodeDom.CodeBinaryOperatorExpression::.ctor(class [System]System.CodeDom.CodeExpression, valuetype [System]System.CodeDom.CodeBinaryOperatorType, class [System]System.CodeDom.CodeExpression)
0x18043c  callvirt instance void [System]System.CodeDom.CodeConditionStatement::set_Condition(class [System]System.CodeDom.CodeExpression)
0x180441  stloc.3
0x180442  ldloc.3
0x180443  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeConditionStatement::get_TrueStatements()
0x180448  ldloc.2
0x180449  newobj   instance void [System]System.CodeDom.CodeMethodReturnStatement::.ctor(class [System]System.CodeDom.CodeExpression)
0x18044e  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x180453  pop
0x180454  ldarg.0
0x180455  ldarg.1
0x180456  call     bool System.Web.Compilation.ObjectFactoryCodeDomTreeGenerator::DoesGeneratedCodeHaveDefaultCtor(string typeToCreate, class [System]System.CodeDom.CodeCompileUnit ccu)
0x18045b  brfalse.s loc_180480
0x18045d  ldarg.0
0x18045e  ldc.i4.0
0x18045f  newarr   [System]System.CodeDom.CodeExpression
0x180464  newobj   instance void [System]System.CodeDom.CodeObjectCreateExpression::.ctor(string, class [System]System.CodeDom.CodeExpression[])
0x180469  stloc.s  4
0x18046b  ldloc.3
0x18046c  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeConditionStatement::get_FalseStatements()
0x180471  ldloc.s  4
0x180473  newobj   instance void [System]System.CodeDom.CodeMethodReturnStatement::.ctor(class [System]System.CodeDom.CodeExpression)
0x180478  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x18047d  pop
0x18047e  br.s     loc_1804CB
0x180480  ldtoken  [mscorlib]System.InvalidOperationException
0x180485  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18048a  newobj   instance void [System]System.CodeDom.CodeTypeReference::.ctor(class [mscorlib]System.Type)
0x18048f  ldc.i4.1
0x180490  newarr   [System]System.CodeDom.CodeExpression
0x180495  dup
0x180496  ldc.i4.0
0x180497  ldstr    aCouldNotCreate_3// "Could_not_create_type_instance"
0x18049c  ldc.i4.1
0x18049d  newarr   [mscorlib]System.Object
0x1804a2  dup
0x1804a3  ldc.i4.0
0x1804a4  ldarg.0
0x1804a5  stelem.ref
0x1804a6  call     string System.Web.SR::GetString(string name, object[] args)
0x1804ab  newobj   instance void [System]System.CodeDom.CodePrimitiveExpression::.ctor(object)
0x1804b0  stelem.ref
0x1804b1  newobj   instance void [System]System.CodeDom.CodeObjectCreateExpression::.ctor(class [System]System.CodeDom.CodeTypeReference, class [System]System.CodeDom.CodeExpression[])
0x1804b6  newobj   instance void [System]System.CodeDom.CodeThrowExceptionStatement::.ctor(class [System]System.CodeDom.CodeExpression)
0x1804bb  stloc.s  5
0x1804bd  ldloc.3
0x1804be  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeConditionStatement::get_FalseStatements()
0x1804c3  ldloc.s  5
0x1804c5  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x1804ca  pop
0x1804cb  ldarg.2
0x1804cc  ldloc.3
0x1804cd  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x1804d2  pop
0x1804d3  ret
0x1804d4  ldarg.0
0x1804d5  ldc.i4.0
0x1804d6  newarr   [System]System.CodeDom.CodeExpression
0x1804db  newobj   instance void [System]System.CodeDom.CodeObjectCreateExpression::.ctor(string, class [System]System.CodeDom.CodeExpression[])
0x1804e0  stloc.s  6
0x1804e2  ldarg.2
0x1804e3  ldloc.s  6
0x1804e5  newobj   instance void [System]System.CodeDom.CodeMethodReturnStatement::.ctor(class [System]System.CodeDom.CodeExpression)
0x1804ea  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x1804ef  pop
0x1804f0  ret
```
