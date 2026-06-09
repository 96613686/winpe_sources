# System.ComponentModel.Design.Serialization.RootCodeDomSerializer::Serialize

- ea: `0x6b760`
- end: `0x6ba37`
- name: `System.ComponentModel.Design.Serialization.RootCodeDomSerializer::Serialize`
- size: `727`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x63410`
- `0x66000`
- `0x661e0`
- `0x66b00`
- `0x66f00`
- `0x6ab80`
- `0x6aba0`
- `0x6b760`
- `0x6ba40`
- `0x6bae0`
- `0x6be60`
- `0x6bf30`
- `0x6bf50`
- `0x6c010`
- `0x6c120`
- `0x8eec0`

## string_xrefs

- `0x6b880`: `SerializerNoSerializerForComponent`
- `0x6b8f4`: `SerializerNoSerializerForComponent`

## pseudocode

```c

```

## disassembly

```asm
0x6b760  ldarg.1
0x6b761  brfalse.s loc_6B766
0x6b763  ldarg.2
0x6b764  brtrue.s loc_6B77B
0x6b766  ldarg.1
0x6b767  brfalse.s loc_6B770
0x6b769  ldstr    aValue// "value"
0x6b76e  br.s     loc_6B775
0x6b770  ldstr    aManager// "manager"
0x6b775  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x6b77a  throw
0x6b77b  ldarg.1
0x6b77c  ldarg.2
0x6b77d  callvirt instance string [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager::GetName(object)
0x6b782  newobj   instance void [System]System.CodeDom.CodeTypeDeclaration::.ctor(string)
0x6b787  stloc.0
0x6b788  newobj   instance void [System]System.CodeDom.CodeThisReferenceExpression::.ctor()
0x6b78d  ldarg.2
0x6b78e  newobj   instance void System.ComponentModel.Design.Serialization.RootContext::.ctor(class [System]System.CodeDom.CodeExpression expression, object value)
0x6b793  stloc.1
0x6b794  ldstr    aRootcodedomser_3// "RootCodeDomSerializer::Serialize"
0x6b799  call     class [mscorlib]System.IDisposable System.ComponentModel.Design.Serialization.CodeDomSerializerBase::TraceScope(string name)
0x6b79e  stloc.2
0x6b79f  ldloc.0
0x6b7a0  callvirt instance class [System]System.CodeDom.CodeTypeReferenceCollection [System]System.CodeDom.CodeTypeDeclaration::get_BaseTypes()
0x6b7a5  ldarg.2
0x6b7a6  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x6b7ab  callvirt instance void [System]System.CodeDom.CodeTypeReferenceCollection::Add(class [mscorlib]System.Type)
0x6b7b0  ldarg.0
0x6b7b1  ldc.i4.0
0x6b7b2  stfld    bool System.ComponentModel.Design.Serialization.RootCodeDomSerializer::containerRequired
0x6b7b7  ldarg.1
0x6b7b8  callvirt instance class [System]System.ComponentModel.Design.Serialization.ContextStack [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager::get_Context()
0x6b7bd  ldloc.1
0x6b7be  callvirt instance void [System]System.ComponentModel.Design.Serialization.ContextStack::Push(object)
0x6b7c3  ldarg.1
0x6b7c4  callvirt instance class [System]System.ComponentModel.Design.Serialization.ContextStack [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager::get_Context()
0x6b7c9  ldarg.0
0x6b7ca  callvirt instance void [System]System.ComponentModel.Design.Serialization.ContextStack::Push(object)
0x6b7cf  ldarg.1
0x6b7d0  callvirt instance class [System]System.ComponentModel.Design.Serialization.ContextStack [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager::get_Context()
0x6b7d5  ldloc.0
0x6b7d6  callvirt instance void [System]System.ComponentModel.Design.Serialization.ContextStack::Push(object)
0x6b7db  ldarg.1
0x6b7dc  isinst   System.ComponentModel.Design.Serialization.DesignerSerializationManager
0x6b7e1  brtrue.s loc_6B7EE
0x6b7e3  ldarg.1
0x6b7e4  newobj   instance void System.ComponentModel.Design.Serialization.CodeDomSerializationProvider::.ctor()
0x6b7e9  callvirt instance void [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager::AddSerializationProvider(class [System]System.ComponentModel.Design.Serialization.IDesignerSerializationProvider)
0x6b7ee  nop
0x6b7ef  ldarg.2
0x6b7f0  isinst   [System]System.ComponentModel.IComponent
0x6b7f5  brfalse  loc_6BA04
0x6b7fa  ldarg.2
0x6b7fb  castclass [System]System.ComponentModel.IComponent
0x6b800  callvirt instance class [System]System.ComponentModel.ISite [System]System.ComponentModel.IComponent::get_Site()
0x6b805  stloc.3
0x6b806  ldloc.3
0x6b807  brfalse  loc_6BA04
0x6b80c  ldloc.3
0x6b80d  callvirt instance class [System]System.ComponentModel.IContainer [System]System.ComponentModel.ISite::get_Container()
0x6b812  callvirt instance class [System]System.ComponentModel.ComponentCollection [System]System.ComponentModel.IContainer::get_Components()
0x6b817  stloc.s  4
0x6b819  newobj   instance void System.ComponentModel.Design.Serialization.StatementContext::.ctor()
0x6b81e  stloc.s  5
0x6b820  ldloc.s  5
0x6b822  callvirt instance class System.ComponentModel.Design.Serialization.ObjectStatementCollection System.ComponentModel.Design.Serialization.StatementContext::get_StatementCollection()
0x6b827  ldloc.s  4
0x6b829  callvirt instance void System.ComponentModel.Design.Serialization.ObjectStatementCollection::Populate(class [mscorlib]System.Collections.ICollection statementOwners)
0x6b82e  ldarg.1
0x6b82f  callvirt instance class [System]System.ComponentModel.Design.Serialization.ContextStack [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager::get_Context()
0x6b834  ldloc.s  5
0x6b836  callvirt instance void [System]System.ComponentModel.Design.Serialization.ContextStack::Push(object)
0x6b83b  ldloc.s  4
0x6b83d  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x6b842  stloc.s  9
0x6b844  br.s     loc_6B8A4
0x6b846  ldloc.s  9
0x6b848  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x6b84d  castclass [System]System.ComponentModel.IComponent
0x6b852  stloc.s  0xA
0x6b854  ldloc.s  0xA
0x6b856  ldarg.2
0x6b857  beq.s    loc_6B8A4
0x6b859  ldarg.0
0x6b85a  ldarg.1
0x6b85b  ldloc.s  0xA
0x6b85d  call     instance bool System.ComponentModel.Design.Serialization.CodeDomSerializerBase::IsSerialized(class [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager manager, object value)
0x6b862  brtrue.s loc_6B8A4
0x6b864  ldarg.0
0x6b865  ldarg.1
0x6b866  ldloc.s  0xA
0x6b868  call     instance class System.ComponentModel.Design.Serialization.CodeDomSerializer System.ComponentModel.Design.Serialization.CodeDomSerializerBase::GetSerializer(class [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager manager, object value)
0x6b86d  stloc.s  0xB
0x6b86f  ldloc.s  0xB
0x6b871  brfalse.s loc_6B87F
0x6b873  ldarg.0
0x6b874  ldarg.1
0x6b875  ldloc.s  0xA
0x6b877  call     instance class [System]System.CodeDom.CodeExpression System.ComponentModel.Design.Serialization.CodeDomSerializerBase::SerializeToExpression(class [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager manager, object value)
0x6b87c  pop
0x6b87d  br.s     loc_6B8A4
0x6b87f  ldarg.1
0x6b880  ldstr    aSerializernose// "SerializerNoSerializerForComponent"
0x6b885  ldc.i4.1
0x6b886  newarr   [mscorlib]System.Object
0x6b88b  dup
0x6b88c  ldc.i4.0
0x6b88d  ldloc.s  0xA
0x6b88f  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x6b894  callvirt instance string [mscorlib]System.Type::get_FullName()
0x6b899  stelem.ref
0x6b89a  call     string System.Design.SR::GetString(string name, object[] args)
0x6b89f  callvirt instance void [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager::ReportError(object)
0x6b8a4  ldloc.s  9
0x6b8a6  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6b8ab  brtrue.s loc_6B846
0x6b8ad  leave.s  loc_6B8C4
0x6b8af  ldloc.s  9
0x6b8b1  isinst   [mscorlib]System.IDisposable
0x6b8b6  stloc.s  0xC
0x6b8b8  ldloc.s  0xC
0x6b8ba  brfalse.s loc_6B8C3
0x6b8bc  ldloc.s  0xC
0x6b8be  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6b8c3  endfinally
0x6b8c4  ldarg.1
0x6b8c5  callvirt instance class [System]System.ComponentModel.Design.Serialization.ContextStack [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager::get_Context()
0x6b8ca  ldarg.2
0x6b8cb  callvirt instance void [System]System.ComponentModel.Design.Serialization.ContextStack::Push(object)
0x6b8d0  ldarg.0
0x6b8d1  ldarg.1
0x6b8d2  ldarg.2
0x6b8d3  call     instance class System.ComponentModel.Design.Serialization.CodeDomSerializer System.ComponentModel.Design.Serialization.CodeDomSerializerBase::GetSerializer(class [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager manager, object value)
0x6b8d8  stloc.s  0xD
0x6b8da  ldloc.s  0xD
0x6b8dc  brfalse.s loc_6B8F3
0x6b8de  ldarg.0
0x6b8df  ldarg.1
0x6b8e0  ldarg.2
0x6b8e1  call     instance bool System.ComponentModel.Design.Serialization.CodeDomSerializerBase::IsSerialized(class [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager manager, object value)
0x6b8e6  brtrue.s loc_6B8F3
0x6b8e8  ldarg.0
0x6b8e9  ldarg.1
0x6b8ea  ldarg.2
0x6b8eb  call     instance class [System]System.CodeDom.CodeExpression System.ComponentModel.Design.Serialization.CodeDomSerializerBase::SerializeToExpression(class [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager manager, object value)
0x6b8f0  pop
0x6b8f1  leave.s  loc_6B933
0x6b8f3  ldarg.1
0x6b8f4  ldstr    aSerializernose// "SerializerNoSerializerForComponent"
0x6b8f9  ldc.i4.1
0x6b8fa  newarr   [mscorlib]System.Object
0x6b8ff  dup
0x6b900  ldc.i4.0
0x6b901  ldarg.2
0x6b902  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x6b907  callvirt instance string [mscorlib]System.Type::get_FullName()
0x6b90c  stelem.ref
0x6b90d  call     string System.Design.SR::GetString(string name, object[] args)
0x6b912  callvirt instance void [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager::ReportError(object)
0x6b917  leave.s  loc_6B933
0x6b919  ldarg.1
0x6b91a  callvirt instance class [System]System.ComponentModel.Design.Serialization.ContextStack [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager::get_Context()
0x6b91f  callvirt instance object [System]System.ComponentModel.Design.Serialization.ContextStack::Pop()
0x6b924  pop
0x6b925  endfinally
0x6b926  ldarg.1
0x6b927  callvirt instance class [System]System.ComponentModel.Design.Serialization.ContextStack [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager::get_Context()
0x6b92c  callvirt instance object [System]System.ComponentModel.Design.Serialization.ContextStack::Pop()
0x6b931  pop
0x6b932  endfinally
0x6b933  newobj   instance void [System]System.CodeDom.CodeMemberMethod::.ctor()
0x6b938  stloc.s  6
0x6b93a  ldloc.s  6
0x6b93c  ldarg.0
0x6b93d  call     instance string System.ComponentModel.Design.Serialization.RootCodeDomSerializer::get_InitMethodName()
0x6b942  callvirt instance void [System]System.CodeDom.CodeTypeMember::set_Name(string)
0x6b947  ldloc.s  6
0x6b949  ldc.i4   0x5000
0x6b94e  callvirt instance void [System]System.CodeDom.CodeTypeMember::set_Attributes(valuetype [System]System.CodeDom.MemberAttributes)
0x6b953  ldloc.0
0x6b954  callvirt instance class [System]System.CodeDom.CodeTypeMemberCollection [System]System.CodeDom.CodeTypeDeclaration::get_Members()
0x6b959  ldloc.s  6
0x6b95b  callvirt instance int32 [System]System.CodeDom.CodeTypeMemberCollection::Add(class [System]System.CodeDom.CodeTypeMember)
0x6b960  pop
0x6b961  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x6b966  stloc.s  7
0x6b968  ldloc.s  4
0x6b96a  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x6b96f  stloc.s  0xE
0x6b971  br.s     loc_6B997
0x6b973  ldloc.s  0xE
0x6b975  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x6b97a  stloc.s  0xF
0x6b97c  ldloc.s  0xF
0x6b97e  ldarg.2
0x6b97f  beq.s    loc_6B997
0x6b981  ldloc.s  7
0x6b983  ldloc.s  5
0x6b985  callvirt instance class System.ComponentModel.Design.Serialization.ObjectStatementCollection System.ComponentModel.Design.Serialization.StatementContext::get_StatementCollection()
0x6b98a  ldloc.s  0xF
0x6b98c  callvirt instance class [System]System.CodeDom.CodeStatementCollection System.ComponentModel.Design.Serialization.ObjectStatementCollection::get_Item(object statementOwner)
0x6b991  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x6b996  pop
0x6b997  ldloc.s  0xE
0x6b999  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6b99e  brtrue.s loc_6B973
0x6b9a0  leave.s  loc_6B9B7
0x6b9a2  ldloc.s  0xE
0x6b9a4  isinst   [mscorlib]System.IDisposable
0x6b9a9  stloc.s  0xC
0x6b9ab  ldloc.s  0xC
0x6b9ad  brfalse.s loc_6B9B6
0x6b9af  ldloc.s  0xC
0x6b9b1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6b9b6  endfinally
0x6b9b7  ldloc.s  5
0x6b9b9  callvirt instance class System.ComponentModel.Design.Serialization.ObjectStatementCollection System.ComponentModel.Design.Serialization.StatementContext::get_StatementCollection()
0x6b9be  ldarg.2
0x6b9bf  callvirt instance class [System]System.CodeDom.CodeStatementCollection System.ComponentModel.Design.Serialization.ObjectStatementCollection::get_Item(object statementOwner)
0x6b9c4  stloc.s  8
0x6b9c6  ldloc.s  8
0x6b9c8  brfalse.s loc_6B9DF
0x6b9ca  ldloc.s  7
0x6b9cc  ldloc.s  5
0x6b9ce  callvirt instance class System.ComponentModel.Design.Serialization.ObjectStatementCollection System.ComponentModel.Design.Serialization.StatementContext::get_StatementCollection()
0x6b9d3  ldarg.2
0x6b9d4  callvirt instance class [System]System.CodeDom.CodeStatementCollection System.ComponentModel.Design.Serialization.ObjectStatementCollection::get_Item(object statementOwner)
0x6b9d9  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x6b9de  pop
0x6b9df  ldarg.0
0x6b9e0  call     instance bool System.ComponentModel.Design.Serialization.RootCodeDomSerializer::get_ContainerRequired()
0x6b9e5  brfalse.s loc_6B9F5
0x6b9e7  ldarg.0
0x6b9e8  ldarg.1
0x6b9e9  ldloc.s  6
0x6b9eb  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x6b9f0  call     instance void System.ComponentModel.Design.Serialization.RootCodeDomSerializer::SerializeContainerDeclaration(class [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager manager, class [System]System.CodeDom.CodeStatementCollection statements)
0x6b9f5  ldarg.0
0x6b9f6  ldloc.s  7
0x6b9f8  ldloc.s  6
0x6b9fa  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x6b9ff  call     instance void System.ComponentModel.Design.Serialization.RootCodeDomSerializer::SerializeElementsToStatements(class [mscorlib]System.Collections.ArrayList elements, class [System]System.CodeDom.CodeStatementCollection statements)
0x6ba04  leave.s  loc_6BA35
0x6ba06  ldarg.1
0x6ba07  callvirt instance class [System]System.ComponentModel.Design.Serialization.ContextStack [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager::get_Context()
0x6ba0c  callvirt instance object [System]System.ComponentModel.Design.Serialization.ContextStack::Pop()
0x6ba11  pop
0x6ba12  ldarg.1
0x6ba13  callvirt instance class [System]System.ComponentModel.Design.Serialization.ContextStack [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager::get_Context()
0x6ba18  callvirt instance object [System]System.ComponentModel.Design.Serialization.ContextStack::Pop()
0x6ba1d  pop
0x6ba1e  ldarg.1
0x6ba1f  callvirt instance class [System]System.ComponentModel.Design.Serialization.ContextStack [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager::get_Context()
0x6ba24  callvirt instance object [System]System.ComponentModel.Design.Serialization.ContextStack::Pop()
0x6ba29  pop
0x6ba2a  endfinally
0x6ba2b  ldloc.2
0x6ba2c  brfalse.s loc_6BA34
0x6ba2e  ldloc.2
0x6ba2f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6ba34  endfinally
0x6ba35  ldloc.0
0x6ba36  ret
```
