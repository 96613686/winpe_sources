# System.ComponentModel.Design.Serialization.ComponentTypeCodeDomSerializer::GetInitializeMethod

- ea: `0x69390`
- end: `0x69436`
- name: `System.ComponentModel.Design.Serialization.ComponentTypeCodeDomSerializer::GetInitializeMethod`
- size: `166`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x69390`

## string_xrefs

- `0x693da`: `InitializeComponent`
- `0x69411`: `InitializeComponent`

## pseudocode

```c

```

## disassembly

```asm
0x69390  ldarg.1
0x69391  brtrue.s loc_6939E
0x69393  ldstr    aManager// "manager"
0x69398  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x6939d  throw
0x6939e  ldarg.2
0x6939f  brtrue.s loc_693AC
0x693a1  ldstr    aTypedecl// "typeDecl"
0x693a6  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x693ab  throw
0x693ac  ldarg.3
0x693ad  brtrue.s loc_693BA
0x693af  ldstr    aValue// "value"
0x693b4  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x693b9  throw
0x693ba  ldarg.2
0x693bb  callvirt instance class [mscorlib]System.Collections.IDictionary [System]System.CodeDom.CodeObject::get_UserData()
0x693c0  ldsfld   object System.ComponentModel.Design.Serialization.ComponentTypeCodeDomSerializer::_initMethodKey
0x693c5  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x693ca  isinst   [System]System.CodeDom.CodeMemberMethod
0x693cf  stloc.0
0x693d0  ldloc.0
0x693d1  brtrue.s loc_69434
0x693d3  newobj   instance void [System]System.CodeDom.CodeMemberMethod::.ctor()
0x693d8  stloc.0
0x693d9  ldloc.0
0x693da  ldstr    aInitializecomp// "InitializeComponent"
0x693df  callvirt instance void [System]System.CodeDom.CodeTypeMember::set_Name(string)
0x693e4  ldloc.0
0x693e5  ldc.i4   0x5000
0x693ea  callvirt instance void [System]System.CodeDom.CodeTypeMember::set_Attributes(valuetype [System]System.CodeDom.MemberAttributes)
0x693ef  ldarg.2
0x693f0  callvirt instance class [mscorlib]System.Collections.IDictionary [System]System.CodeDom.CodeObject::get_UserData()
0x693f5  ldsfld   object System.ComponentModel.Design.Serialization.ComponentTypeCodeDomSerializer::_initMethodKey
0x693fa  ldloc.0
0x693fb  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x69400  newobj   instance void [System]System.CodeDom.CodeConstructor::.ctor()
0x69405  stloc.1
0x69406  ldloc.1
0x69407  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x6940c  newobj   instance void [System]System.CodeDom.CodeThisReferenceExpression::.ctor()
0x69411  ldstr    aInitializecomp// "InitializeComponent"
0x69416  ldc.i4.0
0x69417  newarr   [System]System.CodeDom.CodeExpression
0x6941c  newobj   instance void [System]System.CodeDom.CodeMethodInvokeExpression::.ctor(class [System]System.CodeDom.CodeExpression, string, class [System]System.CodeDom.CodeExpression[])
0x69421  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeExpression)
0x69426  pop
0x69427  ldarg.2
0x69428  callvirt instance class [System]System.CodeDom.CodeTypeMemberCollection [System]System.CodeDom.CodeTypeDeclaration::get_Members()
0x6942d  ldloc.1
0x6942e  callvirt instance int32 [System]System.CodeDom.CodeTypeMemberCollection::Add(class [System]System.CodeDom.CodeTypeMember)
0x69433  pop
0x69434  ldloc.0
0x69435  ret
```
