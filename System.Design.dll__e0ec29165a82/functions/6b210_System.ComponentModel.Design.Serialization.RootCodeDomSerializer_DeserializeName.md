# System.ComponentModel.Design.Serialization.RootCodeDomSerializer::DeserializeName

- ea: `0x6b210`
- end: `0x6b440`
- name: `System.ComponentModel.Design.Serialization.RootCodeDomSerializer::DeserializeName`
- size: `560`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x6ac00`
- `0x6b720`

## callees

- `0x63480`
- `0x63bb0`
- `0x66f00`
- `0x6ab70`
- `0x6b210`
- `0x8eec0`

## string_xrefs

- `0x6b395`: `SerializerNoSerializerForComponent`
- `0x6b221`: `RootCodeDomSerializer::DeserializeName`

## pseudocode

```c

```

## disassembly

```asm
0x6b210  ldnull
0x6b211  stloc.0
0x6b212  ldnull
0x6b213  stloc.1
0x6b214  ldarg.0
0x6b215  ldfld    class [mscorlib]System.Collections.IDictionary System.ComponentModel.Design.Serialization.RootCodeDomSerializer::nameTable
0x6b21a  ldarg.2
0x6b21b  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x6b220  stloc.2
0x6b221  ldstr    aRootcodedomser_0// "RootCodeDomSerializer::DeserializeName"
0x6b226  call     class [mscorlib]System.IDisposable System.ComponentModel.Design.Serialization.CodeDomSerializerBase::TraceScope(string name)
0x6b22b  stloc.3
0x6b22c  ldnull
0x6b22d  stloc.s  4
0x6b22f  ldloc.2
0x6b230  isinst   [System]System.CodeDom.CodeObject
0x6b235  stloc.s  5
0x6b237  ldloc.s  5
0x6b239  brfalse.s loc_6B28E
0x6b23b  ldnull
0x6b23c  stloc.2
0x6b23d  ldarg.0
0x6b23e  ldfld    class [mscorlib]System.Collections.IDictionary System.ComponentModel.Design.Serialization.RootCodeDomSerializer::nameTable
0x6b243  ldarg.2
0x6b244  ldnull
0x6b245  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x6b24a  ldloc.s  5
0x6b24c  isinst   [System]System.CodeDom.CodeVariableDeclarationStatement
0x6b251  brfalse.s loc_6B26C
0x6b253  ldloc.s  5
0x6b255  castclass [System]System.CodeDom.CodeVariableDeclarationStatement
0x6b25a  stloc.s  6
0x6b25c  ldarg.1
0x6b25d  ldloc.s  6
0x6b25f  callvirt instance class [System]System.CodeDom.CodeTypeReference [System]System.CodeDom.CodeVariableDeclarationStatement::get_Type()
0x6b264  call     string System.ComponentModel.Design.Serialization.CodeDomSerializerBase::GetTypeNameFromCodeTypeReference(class [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager manager, class [System]System.CodeDom.CodeTypeReference typeref)
0x6b269  stloc.0
0x6b26a  br.s     loc_6B2E2
0x6b26c  ldloc.s  5
0x6b26e  isinst   [System]System.CodeDom.CodeMemberField
0x6b273  brfalse.s loc_6B2E2
0x6b275  ldloc.s  5
0x6b277  castclass [System]System.CodeDom.CodeMemberField
0x6b27c  stloc.s  4
0x6b27e  ldarg.1
0x6b27f  ldloc.s  4
0x6b281  callvirt instance class [System]System.CodeDom.CodeTypeReference [System]System.CodeDom.CodeMemberField::get_Type()
0x6b286  call     string System.ComponentModel.Design.Serialization.CodeDomSerializerBase::GetTypeNameFromCodeTypeReference(class [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager manager, class [System]System.CodeDom.CodeTypeReference typeref)
0x6b28b  stloc.0
0x6b28c  br.s     loc_6B2E2
0x6b28e  ldloc.2
0x6b28f  brfalse.s loc_6B299
0x6b291  ldloc.2
0x6b292  stloc.s  7
0x6b294  leave    loc_6B43D
0x6b299  ldarg.1
0x6b29a  ldtoken  [System]System.ComponentModel.IContainer
0x6b29f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6b2a4  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x6b2a9  castclass [System]System.ComponentModel.IContainer
0x6b2ae  stloc.s  8
0x6b2b0  ldloc.s  8
0x6b2b2  brfalse.s loc_6B2E2
0x6b2b4  ldloc.s  8
0x6b2b6  callvirt instance class [System]System.ComponentModel.ComponentCollection [System]System.ComponentModel.IContainer::get_Components()
0x6b2bb  ldarg.2
0x6b2bc  callvirt instance class [System]System.ComponentModel.IComponent [System]System.ComponentModel.ComponentCollection::get_Item(string)
0x6b2c1  stloc.s  9
0x6b2c3  ldloc.s  9
0x6b2c5  brfalse.s loc_6B2E2
0x6b2c7  ldloc.s  9
0x6b2c9  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x6b2ce  callvirt instance string [mscorlib]System.Type::get_FullName()
0x6b2d3  stloc.0
0x6b2d4  ldarg.0
0x6b2d5  ldfld    class [mscorlib]System.Collections.IDictionary System.ComponentModel.Design.Serialization.RootCodeDomSerializer::nameTable
0x6b2da  ldarg.2
0x6b2db  ldloc.s  9
0x6b2dd  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x6b2e2  ldarg.2
0x6b2e3  ldarg.0
0x6b2e4  call     instance string System.ComponentModel.Design.Serialization.RootCodeDomSerializer::get_ContainerName()
0x6b2e9  callvirt instance bool [mscorlib]System.String::Equals(string)
0x6b2ee  brfalse.s loc_6B316
0x6b2f0  ldarg.1
0x6b2f1  ldtoken  [System]System.ComponentModel.IContainer
0x6b2f6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6b2fb  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x6b300  castclass [System]System.ComponentModel.IContainer
0x6b305  stloc.s  0xA
0x6b307  ldloc.s  0xA
0x6b309  brfalse  loc_6B422
0x6b30e  ldloc.s  0xA
0x6b310  stloc.2
0x6b311  br       loc_6B422
0x6b316  ldloc.0
0x6b317  brfalse  loc_6B422
0x6b31c  ldarg.1
0x6b31d  ldloc.0
0x6b31e  callvirt instance class [mscorlib]System.Type [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager::GetType(string)
0x6b323  stloc.1
0x6b324  ldloc.1
0x6b325  ldnull
0x6b326  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x6b32b  brfalse.s loc_6B351
0x6b32d  ldarg.1
0x6b32e  ldstr    aSerializertype// "SerializerTypeNotFound"
0x6b333  ldc.i4.1
0x6b334  newarr   [mscorlib]System.Object
0x6b339  dup
0x6b33a  ldc.i4.0
0x6b33b  ldloc.0
0x6b33c  stelem.ref
0x6b33d  call     string System.Design.SR::GetString(string name, object[] args)
0x6b342  newobj   instance void [mscorlib]System.Runtime.Serialization.SerializationException::.ctor(string)
0x6b347  callvirt instance void [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager::ReportError(object)
0x6b34c  br       loc_6B422
0x6b351  ldarg.0
0x6b352  ldfld    class [mscorlib]System.Collections.IDictionary System.ComponentModel.Design.Serialization.RootCodeDomSerializer::statementTable
0x6b357  ldarg.2
0x6b358  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x6b35d  castclass [System]System.CodeDom.CodeStatementCollection
0x6b362  stloc.s  0xB
0x6b364  ldloc.s  0xB
0x6b366  brfalse  loc_6B422
0x6b36b  ldloc.s  0xB
0x6b36d  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x6b372  ldc.i4.0
0x6b373  ble      loc_6B422
0x6b378  ldarg.1
0x6b379  ldloc.1
0x6b37a  ldtoken  System.ComponentModel.Design.Serialization.CodeDomSerializer
0x6b37f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6b384  callvirt instance object [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager::GetSerializer(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x6b389  castclass System.ComponentModel.Design.Serialization.CodeDomSerializer
0x6b38e  stloc.s  0xC
0x6b390  ldloc.s  0xC
0x6b392  brtrue.s loc_6B3B5
0x6b394  ldarg.1
0x6b395  ldstr    aSerializernose// "SerializerNoSerializerForComponent"
0x6b39a  ldc.i4.1
0x6b39b  newarr   [mscorlib]System.Object
0x6b3a0  dup
0x6b3a1  ldc.i4.0
0x6b3a2  ldloc.1
0x6b3a3  callvirt instance string [mscorlib]System.Type::get_FullName()
0x6b3a8  stelem.ref
0x6b3a9  call     string System.Design.SR::GetString(string name, object[] args)
0x6b3ae  callvirt instance void [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager::ReportError(object)
0x6b3b3  br.s     loc_6B422
0x6b3b5  nop
0x6b3b6  ldloc.s  0xC
0x6b3b8  ldarg.1
0x6b3b9  ldloc.s  0xB
0x6b3bb  callvirt instance object System.ComponentModel.Design.Serialization.CodeDomSerializer::Deserialize(class [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager manager, object codeObject)
0x6b3c0  stloc.2
0x6b3c1  ldloc.2
0x6b3c2  brfalse.s loc_6B414
0x6b3c4  ldloc.s  4
0x6b3c6  brfalse.s loc_6B414
0x6b3c8  ldloc.2
0x6b3c9  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0x6b3ce  ldstr    aModifiers// "Modifiers"
0x6b3d3  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0x6b3d8  stloc.s  0xD
0x6b3da  ldloc.s  0xD
0x6b3dc  brfalse.s loc_6B414
0x6b3de  ldloc.s  0xD
0x6b3e0  callvirt instance class [mscorlib]System.Type [System]System.ComponentModel.PropertyDescriptor::get_PropertyType()
0x6b3e5  ldtoken  [System]System.CodeDom.MemberAttributes
0x6b3ea  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6b3ef  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x6b3f4  brfalse.s loc_6B414
0x6b3f6  ldloc.s  4
0x6b3f8  callvirt instance valuetype [System]System.CodeDom.MemberAttributes [System]System.CodeDom.CodeTypeMember::get_Attributes()
0x6b3fd  ldc.i4   0xF000
0x6b402  and
0x6b403  stloc.s  0xE
0x6b405  ldloc.s  0xD
0x6b407  ldloc.2
0x6b408  ldloc.s  0xE
0x6b40a  box      [System]System.CodeDom.MemberAttributes
0x6b40f  callvirt instance void [System]System.ComponentModel.PropertyDescriptor::SetValue(object, object)
0x6b414  leave.s  loc_6B422
0x6b416  stloc.s  0xF
0x6b418  ldarg.1
0x6b419  ldloc.s  0xF
0x6b41b  callvirt instance void [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager::ReportError(object)
0x6b420  leave.s  loc_6B422
0x6b422  ldarg.0
0x6b423  ldfld    class [mscorlib]System.Collections.IDictionary System.ComponentModel.Design.Serialization.RootCodeDomSerializer::nameTable
0x6b428  ldarg.2
0x6b429  ldloc.2
0x6b42a  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x6b42f  leave.s  loc_6B43B
0x6b431  ldloc.3
0x6b432  brfalse.s loc_6B43A
0x6b434  ldloc.3
0x6b435  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6b43a  endfinally
0x6b43b  ldloc.2
0x6b43c  ret
0x6b43d  ldloc.s  7
0x6b43f  ret
```
