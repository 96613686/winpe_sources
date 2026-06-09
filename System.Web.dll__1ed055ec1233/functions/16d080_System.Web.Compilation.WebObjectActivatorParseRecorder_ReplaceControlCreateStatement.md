# System.Web.Compilation.WebObjectActivatorParseRecorder::ReplaceControlCreateStatement

- ea: `0x16d080`
- end: `0x16d1a5`
- name: `System.Web.Compilation.WebObjectActivatorParseRecorder::ReplaceControlCreateStatement`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x16cf90`

## callees

- `0x34f20`
- `0x16d080`
- `0x16d1b0`

## string_xrefs

- `0x16d12a`: `Could_not_create_type_instance`
- `0x16d0a1`: `GetService`

## pseudocode

```c

```

## disassembly

```asm
0x16d080  ldstr    aSystemWebHttpr_0// "System.Web.HttpRuntime"
0x16d085  newobj   instance void [System]System.CodeDom.CodeTypeReferenceExpression::.ctor(string)
0x16d08a  ldstr    aWebobjectactiv// "WebObjectActivator"
0x16d08f  newobj   instance void [System]System.CodeDom.CodePropertyReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0x16d094  stloc.0
0x16d095  ldstr    aActivator// "__activator"
0x16d09a  newobj   instance void [System]System.CodeDom.CodeVariableReferenceExpression::.ctor(string)
0x16d09f  stloc.1
0x16d0a0  ldloc.0
0x16d0a1  ldstr    aGetservice// "GetService"
0x16d0a6  ldc.i4.1
0x16d0a7  newarr   [System]System.CodeDom.CodeExpression
0x16d0ac  dup
0x16d0ad  ldc.i4.0
0x16d0ae  ldarg.0
0x16d0af  newobj   instance void [System]System.CodeDom.CodeTypeOfExpression::.ctor(class [mscorlib]System.Type)
0x16d0b4  stelem.ref
0x16d0b5  newobj   instance void [System]System.CodeDom.CodeMethodInvokeExpression::.ctor(class [System]System.CodeDom.CodeExpression, string, class [System]System.CodeDom.CodeExpression[])
0x16d0ba  stloc.2
0x16d0bb  ldarg.0
0x16d0bc  newobj   instance void [System]System.CodeDom.CodeTypeReference::.ctor(class [mscorlib]System.Type)
0x16d0c1  ldloc.2
0x16d0c2  newobj   instance void [System]System.CodeDom.CodeCastExpression::.ctor(class [System]System.CodeDom.CodeTypeReference, class [System]System.CodeDom.CodeExpression)
0x16d0c7  stloc.3
0x16d0c8  newobj   instance void [System]System.CodeDom.CodeConditionStatement::.ctor()
0x16d0cd  dup
0x16d0ce  ldloc.1
0x16d0cf  ldc.i4.6
0x16d0d0  ldnull
0x16d0d1  newobj   instance void [System]System.CodeDom.CodePrimitiveExpression::.ctor(object)
0x16d0d6  newobj   instance void [System]System.CodeDom.CodeBinaryOperatorExpression::.ctor(class [System]System.CodeDom.CodeExpression, valuetype [System]System.CodeDom.CodeBinaryOperatorType, class [System]System.CodeDom.CodeExpression)
0x16d0db  callvirt instance void [System]System.CodeDom.CodeConditionStatement::set_Condition(class [System]System.CodeDom.CodeExpression)
0x16d0e0  stloc.s  4
0x16d0e2  ldloc.s  4
0x16d0e4  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeConditionStatement::get_TrueStatements()
0x16d0e9  ldarg.1
0x16d0ea  callvirt instance class [System]System.CodeDom.CodeExpression [System]System.CodeDom.CodeAssignStatement::get_Left()
0x16d0ef  ldloc.3
0x16d0f0  newobj   instance void [System]System.CodeDom.CodeAssignStatement::.ctor(class [System]System.CodeDom.CodeExpression, class [System]System.CodeDom.CodeExpression)
0x16d0f5  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x16d0fa  pop
0x16d0fb  ldarg.0
0x16d0fc  call     bool System.Web.Compilation.WebObjectActivatorParseRecorder::DoesTypeHaveDefaultCtor(class [mscorlib]System.Type type)
0x16d101  brfalse.s loc_16D113
0x16d103  ldloc.s  4
0x16d105  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeConditionStatement::get_FalseStatements()
0x16d10a  ldarg.1
0x16d10b  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x16d110  pop
0x16d111  br.s     loc_16D15F
0x16d113  ldtoken  [mscorlib]System.InvalidOperationException
0x16d118  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16d11d  newobj   instance void [System]System.CodeDom.CodeTypeReference::.ctor(class [mscorlib]System.Type)
0x16d122  ldc.i4.1
0x16d123  newarr   [System]System.CodeDom.CodeExpression
0x16d128  dup
0x16d129  ldc.i4.0
0x16d12a  ldstr    aCouldNotCreate_3// "Could_not_create_type_instance"
0x16d12f  ldc.i4.1
0x16d130  newarr   [mscorlib]System.Object
0x16d135  dup
0x16d136  ldc.i4.0
0x16d137  ldarg.0
0x16d138  stelem.ref
0x16d139  call     string System.Web.SR::GetString(string name, object[] args)
0x16d13e  newobj   instance void [System]System.CodeDom.CodePrimitiveExpression::.ctor(object)
0x16d143  stelem.ref
0x16d144  newobj   instance void [System]System.CodeDom.CodeObjectCreateExpression::.ctor(class [System]System.CodeDom.CodeTypeReference, class [System]System.CodeDom.CodeExpression[])
0x16d149  newobj   instance void [System]System.CodeDom.CodeThrowExceptionStatement::.ctor(class [System]System.CodeDom.CodeExpression)
0x16d14e  stloc.s  6
0x16d150  ldloc.s  4
0x16d152  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeConditionStatement::get_FalseStatements()
0x16d157  ldloc.s  6
0x16d159  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x16d15e  pop
0x16d15f  ldarg.2
0x16d160  ldarg.1
0x16d161  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::IndexOf(class [System]System.CodeDom.CodeStatement)
0x16d166  stloc.s  5
0x16d168  ldarg.2
0x16d169  ldloc.s  5
0x16d16b  ldloc.s  4
0x16d16d  callvirt instance void [System]System.CodeDom.CodeStatementCollection::Insert(int32, class [System]System.CodeDom.CodeStatement)
0x16d172  ldarg.2
0x16d173  ldloc.s  5
0x16d175  ldloc.1
0x16d176  ldloc.0
0x16d177  newobj   instance void [System]System.CodeDom.CodeAssignStatement::.ctor(class [System]System.CodeDom.CodeExpression, class [System]System.CodeDom.CodeExpression)
0x16d17c  callvirt instance void [System]System.CodeDom.CodeStatementCollection::Insert(int32, class [System]System.CodeDom.CodeStatement)
0x16d181  ldarg.2
0x16d182  ldloc.s  5
0x16d184  ldtoken  [mscorlib]System.IServiceProvider
0x16d189  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16d18e  ldstr    aActivator// "__activator"
0x16d193  newobj   instance void [System]System.CodeDom.CodeVariableDeclarationStatement::.ctor(class [mscorlib]System.Type, string)
0x16d198  callvirt instance void [System]System.CodeDom.CodeStatementCollection::Insert(int32, class [System]System.CodeDom.CodeStatement)
0x16d19d  ldarg.2
0x16d19e  ldarg.1
0x16d19f  callvirt instance void [System]System.CodeDom.CodeStatementCollection::Remove(class [System]System.CodeDom.CodeStatement)
0x16d1a4  ret
```
