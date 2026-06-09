# System.ComponentModel.Design.Serialization.TypeCodeDomSerializer::DeserializeName

- ea: `0x6c710`
- end: `0x6c94d`
- name: `System.ComponentModel.Design.Serialization.TypeCodeDomSerializer::DeserializeName`
- size: `573`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x6c1d0`
- `0x6ca40`

## callees

- `0x63480`
- `0x63bb0`
- `0x661c0`
- `0x66f00`
- `0x67440`
- `0x6bea0`
- `0x6beb0`
- `0x6c710`
- `0x8eec0`

## string_xrefs

- `0x6c89c`: `SerializerNoSerializerForComponent`
- `0x6c712`: `RootCodeDomSerializer::DeserializeName`

## pseudocode

```c

```

## disassembly

```asm
0x6c710  ldnull
0x6c711  stloc.0
0x6c712  ldstr    aRootcodedomser_0// "RootCodeDomSerializer::DeserializeName"
0x6c717  call     class [mscorlib]System.IDisposable System.ComponentModel.Design.Serialization.CodeDomSerializerBase::TraceScope(string name)
0x6c71c  stloc.1
0x6c71d  ldarg.0
0x6c71e  ldfld    class [mscorlib]System.Collections.IDictionary System.ComponentModel.Design.Serialization.TypeCodeDomSerializer::_nameTable
0x6c723  ldarg.2
0x6c724  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x6c729  stloc.0
0x6c72a  ldloc.0
0x6c72b  isinst   [System]System.CodeDom.CodeObject
0x6c730  stloc.2
0x6c731  ldnull
0x6c732  stloc.3
0x6c733  ldnull
0x6c734  stloc.s  4
0x6c736  ldloc.2
0x6c737  brfalse  loc_6C7D1
0x6c73c  ldnull
0x6c73d  stloc.0
0x6c73e  ldarg.0
0x6c73f  ldfld    class [mscorlib]System.Collections.IDictionary System.ComponentModel.Design.Serialization.TypeCodeDomSerializer::_nameTable
0x6c744  ldarg.2
0x6c745  ldnull
0x6c746  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x6c74b  ldloc.2
0x6c74c  isinst   [System]System.CodeDom.CodeVariableDeclarationStatement
0x6c751  stloc.s  5
0x6c753  ldloc.s  5
0x6c755  brfalse.s loc_6C76A
0x6c757  ldarg.1
0x6c758  ldloc.s  5
0x6c75a  callvirt instance class [System]System.CodeDom.CodeTypeReference [System]System.CodeDom.CodeVariableDeclarationStatement::get_Type()
0x6c75f  call     string System.ComponentModel.Design.Serialization.CodeDomSerializerBase::GetTypeNameFromCodeTypeReference(class [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager manager, class [System]System.CodeDom.CodeTypeReference typeref)
0x6c764  stloc.3
0x6c765  br       loc_6C81D
0x6c76a  ldloc.2
0x6c76b  isinst   [System]System.CodeDom.CodeMemberField
0x6c770  stloc.s  4
0x6c772  ldloc.s  4
0x6c774  brfalse.s loc_6C789
0x6c776  ldarg.1
0x6c777  ldloc.s  4
0x6c779  callvirt instance class [System]System.CodeDom.CodeTypeReference [System]System.CodeDom.CodeMemberField::get_Type()
0x6c77e  call     string System.ComponentModel.Design.Serialization.CodeDomSerializerBase::GetTypeNameFromCodeTypeReference(class [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager manager, class [System]System.CodeDom.CodeTypeReference typeref)
0x6c783  stloc.3
0x6c784  br       loc_6C81D
0x6c789  ldloc.2
0x6c78a  isinst   [System]System.CodeDom.CodeExpression
0x6c78f  stloc.s  6
0x6c791  ldarg.1
0x6c792  callvirt instance class [System]System.ComponentModel.Design.Serialization.ContextStack [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager::get_Context()
0x6c797  ldtoken  System.ComponentModel.Design.Serialization.RootContext
0x6c79c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6c7a1  callvirt instance object [System]System.ComponentModel.Design.Serialization.ContextStack::get_Item(class [mscorlib]System.Type)
0x6c7a6  isinst   System.ComponentModel.Design.Serialization.RootContext
0x6c7ab  stloc.s  7
0x6c7ad  ldloc.s  7
0x6c7af  brfalse.s loc_6C81D
0x6c7b1  ldloc.s  6
0x6c7b3  brfalse.s loc_6C81D
0x6c7b5  ldloc.s  7
0x6c7b7  callvirt instance class [System]System.CodeDom.CodeExpression System.ComponentModel.Design.Serialization.RootContext::get_Expression()
0x6c7bc  ldloc.s  6
0x6c7be  bne.un.s loc_6C81D
0x6c7c0  ldloc.s  7
0x6c7c2  callvirt instance object System.ComponentModel.Design.Serialization.RootContext::get_Value()
0x6c7c7  stloc.0
0x6c7c8  ldloc.0
0x6c7c9  call     string [System]System.ComponentModel.TypeDescriptor::GetClassName(object)
0x6c7ce  stloc.3
0x6c7cf  br.s     loc_6C81D
0x6c7d1  ldloc.0
0x6c7d2  brtrue.s loc_6C81D
0x6c7d4  ldarg.1
0x6c7d5  ldtoken  [System]System.ComponentModel.IContainer
0x6c7da  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6c7df  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x6c7e4  castclass [System]System.ComponentModel.IContainer
0x6c7e9  stloc.s  8
0x6c7eb  ldloc.s  8
0x6c7ed  brfalse.s loc_6C81D
0x6c7ef  ldloc.s  8
0x6c7f1  callvirt instance class [System]System.ComponentModel.ComponentCollection [System]System.ComponentModel.IContainer::get_Components()
0x6c7f6  ldarg.2
0x6c7f7  callvirt instance class [System]System.ComponentModel.IComponent [System]System.ComponentModel.ComponentCollection::get_Item(string)
0x6c7fc  stloc.s  9
0x6c7fe  ldloc.s  9
0x6c800  brfalse.s loc_6C81D
0x6c802  ldloc.s  9
0x6c804  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x6c809  callvirt instance string [mscorlib]System.Type::get_FullName()
0x6c80e  stloc.3
0x6c80f  ldarg.0
0x6c810  ldfld    class [mscorlib]System.Collections.IDictionary System.ComponentModel.Design.Serialization.TypeCodeDomSerializer::_nameTable
0x6c815  ldarg.2
0x6c816  ldloc.s  9
0x6c818  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x6c81d  ldloc.3
0x6c81e  brfalse  loc_6C93F
0x6c823  ldarg.1
0x6c824  ldloc.3
0x6c825  callvirt instance class [mscorlib]System.Type [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager::GetType(string)
0x6c82a  stloc.s  0xA
0x6c82c  ldloc.s  0xA
0x6c82e  ldnull
0x6c82f  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x6c834  brfalse.s loc_6C85B
0x6c836  ldarg.1
0x6c837  ldstr    aSerializertype// "SerializerTypeNotFound"
0x6c83c  ldc.i4.1
0x6c83d  newarr   [mscorlib]System.Object
0x6c842  dup
0x6c843  ldc.i4.0
0x6c844  ldloc.3
0x6c845  stelem.ref
0x6c846  call     string System.Design.SR::GetString(string name, object[] args)
0x6c84b  ldarg.1
0x6c84c  newobj   instance void System.ComponentModel.Design.Serialization.CodeDomSerializerException::.ctor(string message, class [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager manager)
0x6c851  callvirt instance void [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager::ReportError(object)
0x6c856  leave    loc_6C94B
0x6c85b  ldarg.3
0x6c85c  brtrue.s loc_6C87A
0x6c85e  ldarg.0
0x6c85f  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class OrderedCodeStatementCollection> System.ComponentModel.Design.Serialization.TypeCodeDomSerializer::_statementTable
0x6c864  ldarg.2
0x6c865  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class OrderedCodeStatementCollection>::ContainsKey(var<u1>)
0x6c86a  brfalse.s loc_6C87A
0x6c86c  ldarg.0
0x6c86d  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class OrderedCodeStatementCollection> System.ComponentModel.Design.Serialization.TypeCodeDomSerializer::_statementTable
0x6c872  ldarg.2
0x6c873  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class OrderedCodeStatementCollection>::get_Item(void)
0x6c878  starg.s  3
0x6c87a  ldarg.3
0x6c87b  brfalse  loc_6C93F
0x6c880  ldarg.3
0x6c881  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x6c886  ldc.i4.0
0x6c887  ble      loc_6C93F
0x6c88c  ldarg.0
0x6c88d  ldarg.1
0x6c88e  ldloc.s  0xA
0x6c890  call     instance class System.ComponentModel.Design.Serialization.CodeDomSerializer System.ComponentModel.Design.Serialization.CodeDomSerializerBase::GetSerializer(class [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager manager, class [mscorlib]System.Type valueType)
0x6c895  stloc.s  0xB
0x6c897  ldloc.s  0xB
0x6c899  brtrue.s loc_6C8C6
0x6c89b  ldarg.1
0x6c89c  ldstr    aSerializernose// "SerializerNoSerializerForComponent"
0x6c8a1  ldc.i4.1
0x6c8a2  newarr   [mscorlib]System.Object
0x6c8a7  dup
0x6c8a8  ldc.i4.0
0x6c8a9  ldloc.s  0xA
0x6c8ab  callvirt instance string [mscorlib]System.Type::get_FullName()
0x6c8b0  stelem.ref
0x6c8b1  call     string System.Design.SR::GetString(string name, object[] args)
0x6c8b6  ldarg.1
0x6c8b7  newobj   instance void System.ComponentModel.Design.Serialization.CodeDomSerializerException::.ctor(string message, class [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager manager)
0x6c8bc  callvirt instance void [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager::ReportError(object)
0x6c8c1  leave    loc_6C94B
0x6c8c6  nop
0x6c8c7  ldloc.s  0xB
0x6c8c9  ldarg.1
0x6c8ca  ldarg.3
0x6c8cb  callvirt instance object System.ComponentModel.Design.Serialization.CodeDomSerializer::Deserialize(class [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager manager, object codeObject)
0x6c8d0  stloc.0
0x6c8d1  ldloc.0
0x6c8d2  brfalse.s loc_6C924
0x6c8d4  ldloc.s  4
0x6c8d6  brfalse.s loc_6C924
0x6c8d8  ldloc.0
0x6c8d9  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0x6c8de  ldstr    aModifiers// "Modifiers"
0x6c8e3  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0x6c8e8  stloc.s  0xC
0x6c8ea  ldloc.s  0xC
0x6c8ec  brfalse.s loc_6C924
0x6c8ee  ldloc.s  0xC
0x6c8f0  callvirt instance class [mscorlib]System.Type [System]System.ComponentModel.PropertyDescriptor::get_PropertyType()
0x6c8f5  ldtoken  [System]System.CodeDom.MemberAttributes
0x6c8fa  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6c8ff  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x6c904  brfalse.s loc_6C924
0x6c906  ldloc.s  4
0x6c908  callvirt instance valuetype [System]System.CodeDom.MemberAttributes [System]System.CodeDom.CodeTypeMember::get_Attributes()
0x6c90d  ldc.i4   0xF000
0x6c912  and
0x6c913  stloc.s  0xD
0x6c915  ldloc.s  0xC
0x6c917  ldloc.0
0x6c918  ldloc.s  0xD
0x6c91a  box      [System]System.CodeDom.MemberAttributes
0x6c91f  callvirt instance void [System]System.ComponentModel.PropertyDescriptor::SetValue(object, object)
0x6c924  ldarg.0
0x6c925  ldfld    class [mscorlib]System.Collections.IDictionary System.ComponentModel.Design.Serialization.TypeCodeDomSerializer::_nameTable
0x6c92a  ldarg.2
0x6c92b  ldloc.0
0x6c92c  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x6c931  leave.s  loc_6C94B
0x6c933  stloc.s  0xE
0x6c935  ldarg.1
0x6c936  ldloc.s  0xE
0x6c938  callvirt instance void [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager::ReportError(object)
0x6c93d  leave.s  loc_6C94B
0x6c93f  leave.s  loc_6C94B
0x6c941  ldloc.1
0x6c942  brfalse.s loc_6C94A
0x6c944  ldloc.1
0x6c945  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6c94a  endfinally
0x6c94b  ldloc.0
0x6c94c  ret
```
