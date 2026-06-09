# System.ComponentModel.Design.Serialization.ContainerCodeDomSerializer::Serialize

- ea: `0x69570`
- end: `0x6966a`
- name: `System.ComponentModel.Design.Serialization.ContainerCodeDomSerializer::Serialize`
- size: `250`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x66d30`
- `0x69570`
- `0x6bea0`

## string_xrefs

- `0x695bc`: `components`
- `0x695e8`: `components`
- `0x695ff`: `components`
- `0x69614`: `components`

## pseudocode

```c

```

## disassembly

```asm
0x69570  ldarg.1
0x69571  callvirt instance class [System]System.ComponentModel.Design.Serialization.ContextStack [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager::get_Context()
0x69576  ldtoken  [System]System.CodeDom.CodeTypeDeclaration
0x6957b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x69580  callvirt instance object [System]System.ComponentModel.Design.Serialization.ContextStack::get_Item(class [mscorlib]System.Type)
0x69585  isinst   [System]System.CodeDom.CodeTypeDeclaration
0x6958a  stloc.0
0x6958b  ldarg.1
0x6958c  callvirt instance class [System]System.ComponentModel.Design.Serialization.ContextStack [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager::get_Context()
0x69591  ldtoken  System.ComponentModel.Design.Serialization.RootContext
0x69596  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6959b  callvirt instance object [System]System.ComponentModel.Design.Serialization.ContextStack::get_Item(class [mscorlib]System.Type)
0x695a0  isinst   System.ComponentModel.Design.Serialization.RootContext
0x695a5  stloc.1
0x695a6  newobj   instance void [System]System.CodeDom.CodeStatementCollection::.ctor()
0x695ab  stloc.2
0x695ac  ldloc.0
0x695ad  brfalse.s loc_695F5
0x695af  ldloc.1
0x695b0  brfalse.s loc_695F5
0x695b2  ldtoken  [System]System.ComponentModel.IContainer
0x695b7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x695bc  ldstr    aComponents// "components"
0x695c1  newobj   instance void [System]System.CodeDom.CodeMemberField::.ctor(class [mscorlib]System.Type, string)
0x695c6  stloc.s  6
0x695c8  ldloc.s  6
0x695ca  ldc.i4   0x5000
0x695cf  callvirt instance void [System]System.CodeDom.CodeTypeMember::set_Attributes(valuetype [System]System.CodeDom.MemberAttributes)
0x695d4  ldloc.0
0x695d5  callvirt instance class [System]System.CodeDom.CodeTypeMemberCollection [System]System.CodeDom.CodeTypeDeclaration::get_Members()
0x695da  ldloc.s  6
0x695dc  callvirt instance int32 [System]System.CodeDom.CodeTypeMemberCollection::Add(class [System]System.CodeDom.CodeTypeMember)
0x695e1  pop
0x695e2  ldloc.1
0x695e3  callvirt instance class [System]System.CodeDom.CodeExpression System.ComponentModel.Design.Serialization.RootContext::get_Expression()
0x695e8  ldstr    aComponents// "components"
0x695ed  newobj   instance void [System]System.CodeDom.CodeFieldReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0x695f2  stloc.3
0x695f3  br.s     loc_6961F
0x695f5  ldtoken  [System]System.ComponentModel.IContainer
0x695fa  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x695ff  ldstr    aComponents// "components"
0x69604  newobj   instance void [System]System.CodeDom.CodeVariableDeclarationStatement::.ctor(class [mscorlib]System.Type, string)
0x69609  stloc.s  7
0x6960b  ldloc.2
0x6960c  ldloc.s  7
0x6960e  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x69613  pop
0x69614  ldstr    aComponents// "components"
0x69619  newobj   instance void [System]System.CodeDom.CodeVariableReferenceExpression::.ctor(string)
0x6961e  stloc.3
0x6961f  ldarg.0
0x69620  ldarg.1
0x69621  ldarg.2
0x69622  ldloc.3
0x69623  call     instance void System.ComponentModel.Design.Serialization.CodeDomSerializerBase::SetExpression(class [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager manager, object value, class [System]System.CodeDom.CodeExpression expression)
0x69628  ldtoken  [System]System.ComponentModel.Container
0x6962d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x69632  ldc.i4.0
0x69633  newarr   [System]System.CodeDom.CodeExpression
0x69638  newobj   instance void [System]System.CodeDom.CodeObjectCreateExpression::.ctor(class [mscorlib]System.Type, class [System]System.CodeDom.CodeExpression[])
0x6963d  stloc.s  4
0x6963f  ldloc.3
0x69640  ldloc.s  4
0x69642  newobj   instance void [System]System.CodeDom.CodeAssignStatement::.ctor(class [System]System.CodeDom.CodeExpression, class [System]System.CodeDom.CodeExpression)
0x69647  stloc.s  5
0x69649  ldloc.s  5
0x6964b  callvirt instance class [mscorlib]System.Collections.IDictionary [System]System.CodeDom.CodeObject::get_UserData()
0x69650  ldstr    aIcontainer// "IContainer"
0x69655  ldstr    aIcontainer// "IContainer"
0x6965a  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x6965f  ldloc.2
0x69660  ldloc.s  5
0x69662  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x69667  pop
0x69668  ldloc.2
0x69669  ret
```
