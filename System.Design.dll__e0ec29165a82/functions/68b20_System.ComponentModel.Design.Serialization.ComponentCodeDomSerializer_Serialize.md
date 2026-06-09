# System.ComponentModel.Design.Serialization.ComponentCodeDomSerializer::Serialize

- ea: `0x68b20`
- end: `0x69233`
- name: `System.ComponentModel.Design.Serialization.ComponentCodeDomSerializer::Serialize`
- size: `1811`
- prototype: ``
- caller_count: `0`
- callee_count: `33`
- tags: `broker_com_uri`

## callees

- `0x63c40`
- `0x63ca0`
- `0x65c70`
- `0x661e0`
- `0x66250`
- `0x66570`
- `0x66830`
- `0x668f0`
- `0x66b00`
- `0x66d30`
- `0x66f00`
- `0x68540`
- `0x68620`
- `0x68630`
- `0x68670`
- `0x686c0`
- `0x689c0`
- `0x68a20`
- `0x68b20`
- `0x69240`
- `0x692a0`
- `0x69a10`
- `0x6a3d0`
- `0x6aa50`
- `0x6bea0`
- `0x10afa0`
- `0x10afc0`
- `0x10afd0`
- `0x10afe0`
- `0x10b010`
- `0x10b020`
- `0x10b030`
- `0x10b060`

## string_xrefs

- `0x68b29`: `ComponentCodeDomSerializer::Serialize`

## pseudocode

```c

```

## disassembly

```asm
0x68b20  ldnull
0x68b21  stloc.0
0x68b22  ldarg.2
0x68b23  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0x68b28  stloc.1
0x68b29  ldstr    aComponentcoded_1// "ComponentCodeDomSerializer::Serialize"
0x68b2e  call     class [mscorlib]System.IDisposable System.ComponentModel.Design.Serialization.CodeDomSerializerBase::TraceScope(string name)
0x68b33  stloc.2
0x68b34  ldarg.1
0x68b35  brfalse.s loc_68B3A
0x68b37  ldarg.2
0x68b38  brtrue.s loc_68B4F
0x68b3a  ldarg.1
0x68b3b  brfalse.s loc_68B44
0x68b3d  ldstr    aValue// "value"
0x68b42  br.s     loc_68B49
0x68b44  ldstr    aManager// "manager"
0x68b49  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x68b4e  throw
0x68b4f  ldarg.0
0x68b50  ldarg.1
0x68b51  ldarg.2
0x68b52  call     instance bool System.ComponentModel.Design.Serialization.CodeDomSerializerBase::IsSerialized(class [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager manager, object value)
0x68b57  brfalse.s loc_68B68
0x68b59  ldarg.0
0x68b5a  ldarg.1
0x68b5b  ldarg.2
0x68b5c  call     instance class [System]System.CodeDom.CodeExpression System.ComponentModel.Design.Serialization.CodeDomSerializerBase::GetExpression(class [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager manager, object value)
0x68b61  stloc.s  5
0x68b63  leave    loc_69230
0x68b68  ldc.i4.3
0x68b69  stloc.3
0x68b6a  ldarg.2
0x68b6b  call     class [System]System.ComponentModel.AttributeCollection [System]System.ComponentModel.TypeDescriptor::GetAttributes(object)
0x68b70  ldtoken  [System]System.ComponentModel.InheritanceAttribute
0x68b75  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x68b7a  callvirt instance class [mscorlib]System.Attribute [System]System.ComponentModel.AttributeCollection::get_Item(class [mscorlib]System.Type)
0x68b7f  castclass [System]System.ComponentModel.InheritanceAttribute
0x68b84  stloc.s  4
0x68b86  ldloc.s  4
0x68b88  brfalse.s loc_68B92
0x68b8a  ldloc.s  4
0x68b8c  callvirt instance valuetype [System]System.ComponentModel.InheritanceLevel [System]System.ComponentModel.InheritanceAttribute::get_InheritanceLevel()
0x68b91  stloc.3
0x68b92  ldloc.3
0x68b93  ldc.i4.2
0x68b94  beq      loc_69222
0x68b99  newobj   instance void [System]System.CodeDom.CodeStatementCollection::.ctor()
0x68b9e  stloc.0
0x68b9f  ldarg.1
0x68ba0  callvirt instance class [System]System.ComponentModel.Design.Serialization.ContextStack [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager::get_Context()
0x68ba5  ldtoken  [System]System.CodeDom.CodeTypeDeclaration
0x68baa  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x68baf  callvirt instance object [System]System.ComponentModel.Design.Serialization.ContextStack::get_Item(class [mscorlib]System.Type)
0x68bb4  isinst   [System]System.CodeDom.CodeTypeDeclaration
0x68bb9  stloc.s  6
0x68bbb  ldarg.1
0x68bbc  callvirt instance class [System]System.ComponentModel.Design.Serialization.ContextStack [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager::get_Context()
0x68bc1  ldtoken  System.ComponentModel.Design.Serialization.RootContext
0x68bc6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x68bcb  callvirt instance object [System]System.ComponentModel.Design.Serialization.ContextStack::get_Item(class [mscorlib]System.Type)
0x68bd0  isinst   System.ComponentModel.Design.Serialization.RootContext
0x68bd5  stloc.s  7
0x68bd7  ldnull
0x68bd8  stloc.s  8
0x68bda  ldc.i4.0
0x68bdb  stloc.s  0xA
0x68bdd  ldc.i4.1
0x68bde  stloc.s  0xB
0x68be0  ldc.i4.1
0x68be1  stloc.s  0xC
0x68be3  ldc.i4.0
0x68be4  stloc.s  0xD
0x68be6  ldarg.0
0x68be7  ldarg.1
0x68be8  ldarg.2
0x68be9  call     instance class [System]System.CodeDom.CodeExpression System.ComponentModel.Design.Serialization.CodeDomSerializerBase::GetExpression(class [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager manager, object value)
0x68bee  stloc.s  8
0x68bf0  ldloc.s  8
0x68bf2  brfalse.s loc_68C47
0x68bf4  ldc.i4.0
0x68bf5  stloc.s  0xA
0x68bf7  ldc.i4.0
0x68bf8  stloc.s  0xB
0x68bfa  ldc.i4.0
0x68bfb  stloc.s  0xC
0x68bfd  ldarg.2
0x68bfe  isinst   [System]System.ComponentModel.IComponent
0x68c03  stloc.s  0xE
0x68c05  ldloc.s  0xE
0x68c07  brfalse  loc_68C98
0x68c0c  ldloc.s  0xE
0x68c0e  callvirt instance class [System]System.ComponentModel.ISite [System]System.ComponentModel.IComponent::get_Site()
0x68c13  brtrue   loc_68C98
0x68c18  ldarg.1
0x68c19  callvirt instance class [System]System.ComponentModel.Design.Serialization.ContextStack [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager::get_Context()
0x68c1e  ldtoken  System.ComponentModel.Design.Serialization.ExpressionContext
0x68c23  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x68c28  callvirt instance object [System]System.ComponentModel.Design.Serialization.ContextStack::get_Item(class [mscorlib]System.Type)
0x68c2d  isinst   System.ComponentModel.Design.Serialization.ExpressionContext
0x68c32  stloc.s  0xF
0x68c34  ldloc.s  0xF
0x68c36  brfalse.s loc_68C42
0x68c38  ldloc.s  0xF
0x68c3a  callvirt instance object System.ComponentModel.Design.Serialization.ExpressionContext::get_PresetValue()
0x68c3f  ldarg.2
0x68c40  beq.s    loc_68C98
0x68c42  ldc.i4.1
0x68c43  stloc.s  0xD
0x68c45  br.s     loc_68C98
0x68c47  ldloc.3
0x68c48  ldc.i4.3
0x68c49  bne.un.s loc_68C8B
0x68c4b  ldloc.1
0x68c4c  ldstr    aGeneratemember// "GenerateMember"
0x68c51  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0x68c56  stloc.s  0x10
0x68c58  ldloc.s  0x10
0x68c5a  brfalse.s loc_68C8E
0x68c5c  ldloc.s  0x10
0x68c5e  callvirt instance class [mscorlib]System.Type [System]System.ComponentModel.PropertyDescriptor::get_PropertyType()
0x68c63  ldtoken  [mscorlib]System.Boolean
0x68c68  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x68c6d  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x68c72  brfalse.s loc_68C8E
0x68c74  ldloc.s  0x10
0x68c76  ldarg.2
0x68c77  callvirt instance object [System]System.ComponentModel.PropertyDescriptor::GetValue(object)
0x68c7c  unbox.any [mscorlib]System.Boolean
0x68c81  brtrue.s loc_68C8E
0x68c83  ldc.i4.1
0x68c84  stloc.s  0xA
0x68c86  ldc.i4.0
0x68c87  stloc.s  0xB
0x68c89  br.s     loc_68C8E
0x68c8b  ldc.i4.0
0x68c8c  stloc.s  0xC
0x68c8e  ldloc.s  7
0x68c90  brtrue.s loc_68C98
0x68c92  ldc.i4.1
0x68c93  stloc.s  0xA
0x68c95  ldc.i4.0
0x68c96  stloc.s  0xB
0x68c98  ldarg.1
0x68c99  callvirt instance class [System]System.ComponentModel.Design.Serialization.ContextStack [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager::get_Context()
0x68c9e  ldarg.2
0x68c9f  callvirt instance void [System]System.ComponentModel.Design.Serialization.ContextStack::Push(object)
0x68ca4  ldarg.1
0x68ca5  callvirt instance class [System]System.ComponentModel.Design.Serialization.ContextStack [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager::get_Context()
0x68caa  ldloc.0
0x68cab  callvirt instance void [System]System.ComponentModel.Design.Serialization.ContextStack::Push(object)
0x68cb0  ldarg.1
0x68cb1  ldarg.2
0x68cb2  callvirt instance string [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager::GetName(object)
0x68cb7  stloc.s  0x11
0x68cb9  ldarg.2
0x68cba  call     string [System]System.ComponentModel.TypeDescriptor::GetClassName(object)
0x68cbf  stloc.s  0x12
0x68cc1  ldloc.s  0xB
0x68cc3  ldloc.s  0xA
0x68cc5  or
0x68cc6  brfalse  loc_68D85
0x68ccb  ldloc.s  0x11
0x68ccd  brfalse  loc_68D85
0x68cd2  ldloc.s  0xB
0x68cd4  brfalse  loc_68D64
0x68cd9  ldloc.3
0x68cda  ldc.i4.3
0x68cdb  bne.un.s loc_68D52
0x68cdd  ldloc.s  0x12
0x68cdf  ldloc.s  0x11
0x68ce1  newobj   instance void [System]System.CodeDom.CodeMemberField::.ctor(string, string)
0x68ce6  stloc.s  0x13
0x68ce8  ldloc.1
0x68ce9  ldstr    aModifiers// "Modifiers"
0x68cee  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0x68cf3  stloc.s  0x14
0x68cf5  ldloc.s  0x14
0x68cf7  brtrue.s loc_68D06
0x68cf9  ldloc.1
0x68cfa  ldstr    aDefaultmodifie// "DefaultModifiers"
0x68cff  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0x68d04  stloc.s  0x14
0x68d06  ldloc.s  0x14
0x68d08  brfalse.s loc_68D33
0x68d0a  ldloc.s  0x14
0x68d0c  callvirt instance class [mscorlib]System.Type [System]System.ComponentModel.PropertyDescriptor::get_PropertyType()
0x68d11  ldtoken  [System]System.CodeDom.MemberAttributes
0x68d16  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x68d1b  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x68d20  brfalse.s loc_68D33
0x68d22  ldloc.s  0x14
0x68d24  ldarg.2
0x68d25  callvirt instance object [System]System.ComponentModel.PropertyDescriptor::GetValue(object)
0x68d2a  unbox.any [System]System.CodeDom.MemberAttributes
0x68d2f  stloc.s  0x15
0x68d31  br.s     loc_68D3A
0x68d33  ldc.i4   0x5000
0x68d38  stloc.s  0x15
0x68d3a  ldloc.s  0x13
0x68d3c  ldloc.s  0x15
0x68d3e  callvirt instance void [System]System.CodeDom.CodeTypeMember::set_Attributes(valuetype [System]System.CodeDom.MemberAttributes)
0x68d43  ldloc.s  6
0x68d45  callvirt instance class [System]System.CodeDom.CodeTypeMemberCollection [System]System.CodeDom.CodeTypeDeclaration::get_Members()
0x68d4a  ldloc.s  0x13
0x68d4c  callvirt instance int32 [System]System.CodeDom.CodeTypeMemberCollection::Add(class [System]System.CodeDom.CodeTypeMember)
0x68d51  pop
0x68d52  ldloc.s  7
0x68d54  callvirt instance class [System]System.CodeDom.CodeExpression System.ComponentModel.Design.Serialization.RootContext::get_Expression()
0x68d59  ldloc.s  0x11
0x68d5b  newobj   instance void [System]System.CodeDom.CodeFieldReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0x68d60  stloc.s  8
0x68d62  br.s     loc_68D85
0x68d64  ldloc.3
0x68d65  ldc.i4.3
0x68d66  bne.un.s loc_68D7C
0x68d68  ldloc.s  0x12
0x68d6a  ldloc.s  0x11
0x68d6c  newobj   instance void [System]System.CodeDom.CodeVariableDeclarationStatement::.ctor(string, string)
0x68d71  stloc.s  0x16
0x68d73  ldloc.0
0x68d74  ldloc.s  0x16
0x68d76  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x68d7b  pop
0x68d7c  ldloc.s  0x11
0x68d7e  newobj   instance void [System]System.CodeDom.CodeVariableReferenceExpression::.ctor(string)
0x68d83  stloc.s  8
0x68d85  ldloc.s  0xC
0x68d87  brfalse  loc_68E1F
0x68d8c  ldarg.1
0x68d8d  ldtoken  [System]System.ComponentModel.IContainer
0x68d92  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x68d97  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x68d9c  isinst   [System]System.ComponentModel.IContainer
0x68da1  stloc.s  0x17
0x68da3  ldnull
0x68da4  stloc.s  0x18
0x68da6  ldloc.s  0x17
0x68da8  brfalse.s loc_68DC6
0x68daa  ldarg.1
0x68dab  ldarg.2
0x68dac  call     class [mscorlib]System.Type System.ComponentModel.Design.Serialization.CodeDomSerializerBase::GetReflectionTypeHelper(class [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager manager, object instance)
0x68db1  ldc.i4   0x10016
0x68db6  ldnull
0x68db7  ldarg.0
0x68db8  ldarg.1
0x68db9  call     instance class [mscorlib]System.Type[] System.ComponentModel.Design.Serialization.ComponentCodeDomSerializer::GetContainerConstructor(class [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager manager)
0x68dbe  ldnull
0x68dbf  callvirt instance class [mscorlib]System.Reflection.ConstructorInfo [mscorlib]System.Type::GetConstructor(valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x68dc4  stloc.s  0x18
0x68dc6  ldloc.s  0x18
0x68dc8  ldnull
0x68dc9  call     bool [mscorlib]System.Reflection.ConstructorInfo::op_Inequality(class [mscorlib]System.Reflection.ConstructorInfo, class [mscorlib]System.Reflection.ConstructorInfo)
0x68dce  brfalse.s loc_68DED
0x68dd0  ldloc.s  0x12
0x68dd2  ldc.i4.1
0x68dd3  newarr   [System]System.CodeDom.CodeExpression
0x68dd8  dup
0x68dd9  ldc.i4.0
0x68dda  ldarg.0
0x68ddb  ldarg.1
0x68ddc  ldloc.s  0x17
0x68dde  call     instance class [System]System.CodeDom.CodeExpression System.ComponentModel.Design.Serialization.CodeDomSerializerBase::SerializeToExpression(class [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager manager, object value)
0x68de3  stelem.ref
0x68de4  newobj   instance void [System]System.CodeDom.CodeObjectCreateExpression::.ctor(string, class [System]System.CodeDom.CodeExpression[])
0x68de9  stloc.s  9
0x68deb  br.s     loc_68DF9
0x68ded  ldarg.0
0x68dee  ldarg.1
0x68def  ldarg.2
0x68df0  ldloca.s 0x19
0x68df2  call     instance class [System]System.CodeDom.CodeExpression System.ComponentModel.Design.Serialization.CodeDomSerializerBase::SerializeCreationExpression(class [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager manager, object value, [out] bool& isComplete)
0x68df7  stloc.s  9
0x68df9  ldloc.s  9
0x68dfb  brfalse.s loc_68E1F
0x68dfd  ldloc.s  8
0x68dff  brtrue.s loc_68E0B
0x68e01  ldloc.s  0xD
0x68e03  brfalse.s loc_68E1F
0x68e05  ldloc.s  9
0x68e07  stloc.s  8
0x68e09  br.s     loc_68E1F
0x68e0b  ldloc.s  8
0x68e0d  ldloc.s  9
0x68e0f  newobj   instance void [System]System.CodeDom.CodeAssignStatement::.ctor(class [System]System.CodeDom.CodeExpression, class [System]System.CodeDom.CodeExpression)
0x68e14  stloc.s  0x1A
0x68e16  ldloc.0
0x68e17  ldloc.s  0x1A
0x68e19  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x68e1e  pop
0x68e1f  ldloc.s  8
0x68e21  brfalse.s loc_68E2D
0x68e23  ldarg.0
0x68e24  ldarg.1
0x68e25  ldarg.2
0x68e26  ldloc.s  8
0x68e28  call     instance void System.ComponentModel.Design.Serialization.CodeDomSerializerBase::SetExpression(class [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager manager, object value, class [System]System.CodeDom.CodeExpression expression)
0x68e2d  ldloc.s  8
0x68e2f  brfalse  loc_691F8
0x68e34  ldloc.s  0xD
  ... truncated ...
```
