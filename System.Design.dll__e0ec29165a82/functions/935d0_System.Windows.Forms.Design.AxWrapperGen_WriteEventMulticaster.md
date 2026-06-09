# System.Windows.Forms.Design.AxWrapperGen::WriteEventMulticaster

- ea: `0x935d0`
- end: `0x93b62`
- name: `System.Windows.Forms.Design.AxWrapperGen::WriteEventMulticaster`
- size: `1426`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `service_task`

## callers

- `0x93b70`

## callees

- `0x919c0`
- `0x919e0`
- `0x91a00`
- `0x91a10`
- `0x91a20`
- `0x91a90`
- `0x91b60`
- `0x91ea0`
- `0x91fb0`
- `0x92280`
- `0x925a0`
- `0x92c40`
- `0x935d0`

## string_xrefs

- `0x93611`: `System.Runtime.InteropServices.ClassInterface`
- `0x9361f`: `System.Runtime.InteropServices.ClassInterfaceType`

## pseudocode

```c

```

## disassembly

```asm
0x935d0  ldarg.0
0x935d1  ldfld    string System.Windows.Forms.Design.AxWrapperGen::axctl
0x935d6  ldstr    aEventmulticast// "EventMulticaster"
0x935db  call     string [mscorlib]System.String::Concat(string, string)
0x935e0  stloc.0
0x935e1  ldarg.0
0x935e2  ldarg.1
0x935e3  ldloc.0
0x935e4  call     instance bool System.Windows.Forms.Design.AxWrapperGen::ClassAlreadyExistsInNamespace(class [System]System.CodeDom.CodeNamespace ns, string clsName)
0x935e9  brfalse.s loc_935ED
0x935eb  ldloc.0
0x935ec  ret
0x935ed  newobj   instance void [System]System.CodeDom.CodeTypeDeclaration::.ctor()
0x935f2  stloc.1
0x935f3  ldloc.1
0x935f4  ldloc.0
0x935f5  callvirt instance void [System]System.CodeDom.CodeTypeMember::set_Name(string)
0x935fa  ldloc.1
0x935fb  callvirt instance class [System]System.CodeDom.CodeTypeReferenceCollection [System]System.CodeDom.CodeTypeDeclaration::get_BaseTypes()
0x93600  ldarg.0
0x93601  ldfld    string System.Windows.Forms.Design.AxWrapperGen::axctlEvents
0x93606  callvirt instance void [System]System.CodeDom.CodeTypeReferenceCollection::Add(string)
0x9360b  newobj   instance void [System]System.CodeDom.CodeAttributeDeclarationCollection::.ctor()
0x93610  stloc.2
0x93611  ldstr    aSystemRuntimeI_0// "System.Runtime.InteropServices.ClassInt"...
0x93616  ldc.i4.1
0x93617  newarr   [System]System.CodeDom.CodeAttributeArgument
0x9361c  dup
0x9361d  ldc.i4.0
0x9361e  ldnull
0x9361f  ldstr    aSystemRuntimeI_1// "System.Runtime.InteropServices.ClassInt"...
0x93624  newobj   instance void [System]System.CodeDom.CodeFieldReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0x93629  ldstr    aNone_0// "None"
0x9362e  newobj   instance void [System]System.CodeDom.CodeFieldReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0x93633  newobj   instance void [System]System.CodeDom.CodeAttributeArgument::.ctor(class [System]System.CodeDom.CodeExpression)
0x93638  stelem.ref
0x93639  newobj   instance void [System]System.CodeDom.CodeAttributeDeclaration::.ctor(string, class [System]System.CodeDom.CodeAttributeArgument[])
0x9363e  stloc.3
0x9363f  ldloc.2
0x93640  ldloc.3
0x93641  callvirt instance int32 [System]System.CodeDom.CodeAttributeDeclarationCollection::Add(class [System]System.CodeDom.CodeAttributeDeclaration)
0x93646  pop
0x93647  ldloc.1
0x93648  ldloc.2
0x93649  callvirt instance void [System]System.CodeDom.CodeTypeMember::set_CustomAttributes(class [System]System.CodeDom.CodeAttributeDeclarationCollection)
0x9364e  ldarg.0
0x9364f  ldfld    string System.Windows.Forms.Design.AxWrapperGen::axctl
0x93654  ldstr    aParent_0// "parent"
0x93659  newobj   instance void [System]System.CodeDom.CodeMemberField::.ctor(string, string)
0x9365e  stloc.s  4
0x93660  ldloc.s  4
0x93662  ldc.i4   0x5002
0x93667  callvirt instance void [System]System.CodeDom.CodeTypeMember::set_Attributes(valuetype [System]System.CodeDom.MemberAttributes)
0x9366c  ldloc.1
0x9366d  callvirt instance class [System]System.CodeDom.CodeTypeMemberCollection [System]System.CodeDom.CodeTypeDeclaration::get_Members()
0x93672  ldloc.s  4
0x93674  callvirt instance int32 [System]System.CodeDom.CodeTypeMemberCollection::Add(class [System]System.CodeDom.CodeTypeMember)
0x93679  pop
0x9367a  newobj   instance void [System]System.CodeDom.CodeConstructor::.ctor()
0x9367f  stloc.s  5
0x93681  ldloc.s  5
0x93683  ldc.i4   0x6000
0x93688  callvirt instance void [System]System.CodeDom.CodeTypeMember::set_Attributes(valuetype [System]System.CodeDom.MemberAttributes)
0x9368d  ldloc.s  5
0x9368f  callvirt instance class [System]System.CodeDom.CodeParameterDeclarationExpressionCollection [System]System.CodeDom.CodeMemberMethod::get_Parameters()
0x93694  ldarg.0
0x93695  ldarg.0
0x93696  ldfld    string System.Windows.Forms.Design.AxWrapperGen::axctl
0x9369b  ldstr    aParent_0// "parent"
0x936a0  ldc.i4.0
0x936a1  call     instance class [System]System.CodeDom.CodeParameterDeclarationExpression System.Windows.Forms.Design.AxWrapperGen::CreateParamDecl(string type, string name, bool isOptional)
0x936a6  callvirt instance int32 [System]System.CodeDom.CodeParameterDeclarationExpressionCollection::Add(class [System]System.CodeDom.CodeParameterDeclarationExpression)
0x936ab  pop
0x936ac  newobj   instance void [System]System.CodeDom.CodeThisReferenceExpression::.ctor()
0x936b1  ldstr    aParent_0// "parent"
0x936b6  newobj   instance void [System]System.CodeDom.CodeFieldReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0x936bb  stloc.s  6
0x936bd  ldnull
0x936be  ldstr    aParent_0// "parent"
0x936c3  newobj   instance void [System]System.CodeDom.CodeFieldReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0x936c8  stloc.s  7
0x936ca  ldloc.s  5
0x936cc  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x936d1  ldloc.s  6
0x936d3  ldloc.s  7
0x936d5  newobj   instance void [System]System.CodeDom.CodeAssignStatement::.ctor(class [System]System.CodeDom.CodeExpression, class [System]System.CodeDom.CodeExpression)
0x936da  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x936df  pop
0x936e0  ldloc.1
0x936e1  callvirt instance class [System]System.CodeDom.CodeTypeMemberCollection [System]System.CodeDom.CodeTypeDeclaration::get_Members()
0x936e6  ldloc.s  5
0x936e8  callvirt instance int32 [System]System.CodeDom.CodeTypeMemberCollection::Add(class [System]System.CodeDom.CodeTypeMember)
0x936ed  pop
0x936ee  ldarg.0
0x936ef  ldfld    class [mscorlib]System.Type System.Windows.Forms.Design.AxWrapperGen::axctlEventsType
0x936f4  ldc.i4.s 0x16
0x936f6  callvirt instance class [mscorlib]System.Reflection.MethodInfo[] [mscorlib]System.Type::GetMethods(valuetype [mscorlib]System.Reflection.BindingFlags)
0x936fb  stloc.s  8
0x936fd  ldc.i4.0
0x936fe  stloc.s  9
0x93700  ldc.i4.0
0x93701  stloc.s  0xA
0x93703  br       loc_93B4D
0x93708  ldloc.s  8
0x9370a  ldloc.s  0xA
0x9370c  ldelem.ref
0x9370d  callvirt instance class [mscorlib]System.Reflection.ParameterInfo[] [mscorlib]System.Reflection.MethodBase::GetParameters()
0x93712  call     class System.Windows.Forms.Design.AxParameterData[] System.Windows.Forms.Design.AxParameterData::Convert(class [mscorlib]System.Reflection.ParameterInfo[] infos)
0x93717  stloc.s  0xB
0x93719  newobj   instance void [System]System.CodeDom.CodeMemberMethod::.ctor()
0x9371e  stloc.s  0xC
0x93720  ldloc.s  0xC
0x93722  ldloc.s  8
0x93724  ldloc.s  0xA
0x93726  ldelem.ref
0x93727  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x9372c  callvirt instance void [System]System.CodeDom.CodeTypeMember::set_Name(string)
0x93731  ldloc.s  0xC
0x93733  ldc.i4   0x6000
0x93738  callvirt instance void [System]System.CodeDom.CodeTypeMember::set_Attributes(valuetype [System]System.CodeDom.MemberAttributes)
0x9373d  ldloc.s  0xC
0x9373f  ldloc.s  8
0x93741  ldloc.s  0xA
0x93743  ldelem.ref
0x93744  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.MethodInfo::get_ReturnType()
0x93749  call     string System.Windows.Forms.Design.AxWrapperGen::MapTypeName(class [mscorlib]System.Type type)
0x9374e  newobj   instance void [System]System.CodeDom.CodeTypeReference::.ctor(string)
0x93753  callvirt instance void [System]System.CodeDom.CodeMemberMethod::set_ReturnType(class [System]System.CodeDom.CodeTypeReference)
0x93758  ldc.i4.0
0x93759  stloc.s  0xE
0x9375b  br.s     loc_937AE
0x9375d  ldarg.0
0x9375e  ldloc.s  0xB
0x93760  ldloc.s  0xE
0x93762  ldelem.ref
0x93763  callvirt instance class [mscorlib]System.Type System.Windows.Forms.Design.AxParameterData::get_ParameterType()
0x93768  call     string System.Windows.Forms.Design.AxWrapperGen::MapTypeName(class [mscorlib]System.Type type)
0x9376d  ldloc.s  0xB
0x9376f  ldloc.s  0xE
0x93771  ldelem.ref
0x93772  callvirt instance string System.Windows.Forms.Design.AxParameterData::get_Name()
0x93777  ldloc.s  0xB
0x93779  ldloc.s  0xE
0x9377b  ldelem.ref
0x9377c  callvirt instance bool System.Windows.Forms.Design.AxParameterData::get_IsOptional()
0x93781  call     instance class [System]System.CodeDom.CodeParameterDeclarationExpression System.Windows.Forms.Design.AxWrapperGen::CreateParamDecl(string type, string name, bool isOptional)
0x93786  stloc.s  0xF
0x93788  ldloc.s  0xF
0x9378a  ldloc.s  0xB
0x9378c  ldloc.s  0xE
0x9378e  ldelem.ref
0x9378f  callvirt instance valuetype [System]System.CodeDom.FieldDirection System.Windows.Forms.Design.AxParameterData::get_Direction()
0x93794  callvirt instance void [System]System.CodeDom.CodeParameterDeclarationExpression::set_Direction(valuetype [System]System.CodeDom.FieldDirection)
0x93799  ldloc.s  0xC
0x9379b  callvirt instance class [System]System.CodeDom.CodeParameterDeclarationExpressionCollection [System]System.CodeDom.CodeMemberMethod::get_Parameters()
0x937a0  ldloc.s  0xF
0x937a2  callvirt instance int32 [System]System.CodeDom.CodeParameterDeclarationExpressionCollection::Add(class [System]System.CodeDom.CodeParameterDeclarationExpression)
0x937a7  pop
0x937a8  ldloc.s  0xE
0x937aa  ldc.i4.1
0x937ab  add
0x937ac  stloc.s  0xE
0x937ae  ldloc.s  0xE
0x937b0  ldloc.s  0xB
0x937b2  ldlen
0x937b3  conv.i4
0x937b4  blt.s    loc_9375D
0x937b6  newobj   instance void [System]System.CodeDom.CodeThisReferenceExpression::.ctor()
0x937bb  ldstr    aParent_0// "parent"
0x937c0  newobj   instance void [System]System.CodeDom.CodeFieldReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0x937c5  stloc.s  0xD
0x937c7  ldarg.0
0x937c8  ldloc.s  8
0x937ca  ldloc.s  0xA
0x937cc  ldelem.ref
0x937cd  call     instance bool System.Windows.Forms.Design.AxWrapperGen::IsEventPresent(class [mscorlib]System.Reflection.MethodInfo mievent)
0x937d2  brtrue   loc_93A8B
0x937d7  ldarg.0
0x937d8  ldfld    class [mscorlib]System.Collections.ArrayList System.Windows.Forms.Design.AxWrapperGen::events
0x937dd  ldloc.s  9
0x937df  dup
0x937e0  ldc.i4.1
0x937e1  add
0x937e2  stloc.s  9
0x937e4  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x937e9  castclass EventEntry
0x937ee  stloc.s  0x10
0x937f0  newobj   instance void [System]System.CodeDom.CodeExpressionCollection::.ctor()
0x937f5  stloc.s  0x11
0x937f7  ldloc.s  0x11
0x937f9  ldloc.s  0xD
0x937fb  callvirt instance int32 [System]System.CodeDom.CodeExpressionCollection::Add(class [System]System.CodeDom.CodeExpression)
0x93800  pop
0x93801  ldloc.s  0x10
0x93803  ldfld    string EventEntry::eventCls
0x93808  ldstr    aEventargs// "EventArgs"
0x9380d  callvirt instance bool [mscorlib]System.String::Equals(string)
0x93812  brfalse  loc_938AB
0x93817  ldloc.s  0x11
0x93819  ldnull
0x9381a  ldstr    aEventargs// "EventArgs"
0x9381f  newobj   instance void [System]System.CodeDom.CodeFieldReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0x93824  ldstr    aEmpty_0// "Empty"
0x93829  newobj   instance void [System]System.CodeDom.CodeFieldReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0x9382e  callvirt instance int32 [System]System.CodeDom.CodeExpressionCollection::Add(class [System]System.CodeDom.CodeExpression)
0x93833  pop
0x93834  ldloc.s  0x11
0x93836  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x9383b  newarr   [System]System.CodeDom.CodeExpression
0x93840  stloc.s  0x12
0x93842  ldloc.s  0x11
0x93844  ldloc.s  0x12
0x93846  ldc.i4.0
0x93847  callvirt instance void [mscorlib]System.Collections.ICollection::CopyTo(class [mscorlib]System.Array, int32)
0x9384c  ldloc.s  0xD
0x9384e  ldloc.s  0x10
0x93850  ldfld    string EventEntry::invokeMethodName
0x93855  ldloc.s  0x12
0x93857  newobj   instance void [System]System.CodeDom.CodeMethodInvokeExpression::.ctor(class [System]System.CodeDom.CodeExpression, string, class [System]System.CodeDom.CodeExpression[])
0x9385c  stloc.s  0x13
0x9385e  ldloc.s  8
0x93860  ldloc.s  0xA
0x93862  ldelem.ref
0x93863  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.MethodInfo::get_ReturnType()
0x93868  ldtoken  [mscorlib]System.Void
0x9386d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x93872  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x93877  brfalse.s loc_93892
0x93879  ldloc.s  0xC
0x9387b  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x93880  ldloc.s  0x13
0x93882  newobj   instance void [System]System.CodeDom.CodeExpressionStatement::.ctor(class [System]System.CodeDom.CodeExpression)
0x93887  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x9388c  pop
0x9388d  br       loc_93B39
0x93892  ldloc.s  0xC
0x93894  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x93899  ldloc.s  0x13
0x9389b  newobj   instance void [System]System.CodeDom.CodeMethodReturnStatement::.ctor(class [System]System.CodeDom.CodeExpression)
0x938a0  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x938a5  pop
0x938a6  br       loc_93B39
0x938ab  ldloc.s  0x10
0x938ad  ldfld    string EventEntry::eventCls
0x938b2  ldc.i4.0
0x938b3  newarr   [System]System.CodeDom.CodeExpression
0x938b8  newobj   instance void [System]System.CodeDom.CodeObjectCreateExpression::.ctor(string, class [System]System.CodeDom.CodeExpression[])
0x938bd  stloc.s  0x14
0x938bf  ldc.i4.0
0x938c0  stloc.s  0x18
0x938c2  br.s     loc_938FD
0x938c4  ldloc.s  0x10
0x938c6  ldfld    class System.Windows.Forms.Design.AxParameterData[] EventEntry::parameters
0x938cb  ldloc.s  0x18
0x938cd  ldelem.ref
0x938ce  callvirt instance bool System.Windows.Forms.Design.AxParameterData::get_IsOut()
0x938d3  brtrue.s loc_938F7
0x938d5  ldloc.s  0x14
0x938d7  callvirt instance class [System]System.CodeDom.CodeExpressionCollection [System]System.CodeDom.CodeObjectCreateExpression::get_Parameters()
0x938dc  ldnull
0x938dd  ldloc.s  0x10
0x938df  ldfld    class System.Windows.Forms.Design.AxParameterData[] EventEntry::parameters
0x938e4  ldloc.s  0x18
0x938e6  ldelem.ref
0x938e7  callvirt instance string System.Windows.Forms.Design.AxParameterData::get_Name()
0x938ec  newobj   instance void [System]System.CodeDom.CodeFieldReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0x938f1  callvirt instance int32 [System]System.CodeDom.CodeExpressionCollection::Add(class [System]System.CodeDom.CodeExpression)
0x938f6  pop
0x938f7  ldloc.s  0x18
0x938f9  ldc.i4.1
0x938fa  add
0x938fb  stloc.s  0x18
0x938fd  ldloc.s  0x18
0x938ff  ldloc.s  0x10
0x93901  ldfld    class System.Windows.Forms.Design.AxParameterData[] EventEntry::parameters
0x93906  ldlen
0x93907  conv.i4
0x93908  blt.s    loc_938C4
0x9390a  ldloc.s  0x10
0x9390c  ldfld    string EventEntry::eventCls
0x93911  ldloc.s  0x10
0x93913  ldfld    string EventEntry::eventParam
0x93918  newobj   instance void [System]System.CodeDom.CodeVariableDeclarationStatement::.ctor(string, string)
0x9391d  stloc.s  0x15
0x9391f  ldloc.s  0x15
0x93921  ldloc.s  0x14
0x93923  callvirt instance void [System]System.CodeDom.CodeVariableDeclarationStatement::set_InitExpression(class [System]System.CodeDom.CodeExpression)
0x93928  ldloc.s  0xC
0x9392a  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x9392f  ldloc.s  0x15
0x93931  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x93936  pop
0x93937  ldloc.s  0x11
0x93939  ldnull
0x9393a  ldloc.s  0x10
0x9393c  ldfld    string EventEntry::eventParam
0x93941  newobj   instance void [System]System.CodeDom.CodeFieldReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0x93946  callvirt instance int32 [System]System.CodeDom.CodeExpressionCollection::Add(class [System]System.CodeDom.CodeExpression)
0x9394b  pop
0x9394c  ldloc.s  0x11
  ... truncated ...
```
