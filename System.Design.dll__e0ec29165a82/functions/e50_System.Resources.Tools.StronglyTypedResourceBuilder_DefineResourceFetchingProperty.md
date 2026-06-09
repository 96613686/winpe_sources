# System.Resources.Tools.StronglyTypedResourceBuilder::DefineResourceFetchingProperty

- ea: `0xe50`
- end: `0x10c5`
- name: `System.Resources.Tools.StronglyTypedResourceBuilder::DefineResourceFetchingProperty`
- size: `629`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x470`

## callees

- `0xe10`
- `0xe50`
- `0x8eec0`
- `0xef3e0`
- `0xef3f0`

## string_xrefs

- `0xf9c`: `StringPropertyComment`
- `0xfc4`: `NonStringPropertyComment`
- `0xfdd`: `NonStringPropertyDetailedComment`

## pseudocode

```c

```

## disassembly

```asm
0xe50  newobj   instance void [System]System.CodeDom.CodeMemberProperty::.ctor()
0xe55  stloc.0
0xe56  ldloc.0
0xe57  ldarg.0
0xe58  callvirt instance void [System]System.CodeDom.CodeTypeMember::set_Name(string)
0xe5d  ldloc.0
0xe5e  ldc.i4.1
0xe5f  callvirt instance void [System]System.CodeDom.CodeMemberProperty::set_HasGet(bool)
0xe64  ldloc.0
0xe65  ldc.i4.0
0xe66  callvirt instance void [System]System.CodeDom.CodeMemberProperty::set_HasSet(bool)
0xe6b  ldarg.2
0xe6c  callvirt instance class [mscorlib]System.Type ResourceData::get_Type()
0xe71  stloc.1
0xe72  ldloc.1
0xe73  ldnull
0xe74  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xe79  brfalse.s loc_E7D
0xe7b  ldc.i4.0
0xe7c  ret
0xe7d  ldloc.1
0xe7e  ldtoken  [mscorlib]System.IO.MemoryStream
0xe83  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe88  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xe8d  brfalse.s loc_EA3
0xe8f  ldtoken  [mscorlib]System.IO.UnmanagedMemoryStream
0xe94  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe99  stloc.1
0xe9a  br.s     loc_EA3
0xe9c  ldloc.1
0xe9d  callvirt instance class [mscorlib]System.Type [mscorlib]System.Type::get_BaseType()
0xea2  stloc.1
0xea3  ldloc.1
0xea4  callvirt instance bool [mscorlib]System.Type::get_IsPublic()
0xea9  brfalse.s loc_E9C
0xeab  ldloc.1
0xeac  newobj   instance void [System]System.CodeDom.CodeTypeReference::.ctor(class [mscorlib]System.Type)
0xeb1  stloc.2
0xeb2  ldloc.0
0xeb3  ldloc.2
0xeb4  callvirt instance void [System]System.CodeDom.CodeMemberProperty::set_Type(class [System]System.CodeDom.CodeTypeReference)
0xeb9  ldarg.s  4
0xebb  brfalse.s loc_ECA
0xebd  ldloc.0
0xebe  ldc.i4   0x1000
0xec3  callvirt instance void [System]System.CodeDom.CodeTypeMember::set_Attributes(valuetype [System]System.CodeDom.MemberAttributes)
0xec8  br.s     loc_ED5
0xeca  ldloc.0
0xecb  ldc.i4   0x6000
0xed0  callvirt instance void [System]System.CodeDom.CodeTypeMember::set_Attributes(valuetype [System]System.CodeDom.MemberAttributes)
0xed5  ldarg.s  5
0xed7  brfalse.s loc_EE7
0xed9  ldloc.0
0xeda  dup
0xedb  callvirt instance valuetype [System]System.CodeDom.MemberAttributes [System]System.CodeDom.CodeTypeMember::get_Attributes()
0xee0  ldc.i4.3
0xee1  or
0xee2  callvirt instance void [System]System.CodeDom.CodeTypeMember::set_Attributes(valuetype [System]System.CodeDom.MemberAttributes)
0xee7  ldnull
0xee8  ldstr    aResourcemanage// "ResourceManager"
0xeed  newobj   instance void [System]System.CodeDom.CodePropertyReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0xef2  stloc.3
0xef3  ldarg.s  5
0xef5  brtrue.s loc_EFE
0xef7  newobj   instance void [System]System.CodeDom.CodeThisReferenceExpression::.ctor()
0xefc  br.s     loc_EFF
0xefe  ldnull
0xeff  ldstr    aResourcecultur// "resourceCulture"
0xf04  newobj   instance void [System]System.CodeDom.CodeFieldReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0xf09  stloc.s  4
0xf0b  ldloc.1
0xf0c  ldtoken  [mscorlib]System.String
0xf11  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xf16  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xf1b  stloc.s  5
0xf1d  ldloc.1
0xf1e  ldtoken  [mscorlib]System.IO.UnmanagedMemoryStream
0xf23  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xf28  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xf2d  brtrue.s loc_F41
0xf2f  ldloc.1
0xf30  ldtoken  [mscorlib]System.IO.MemoryStream
0xf35  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xf3a  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xf3f  br.s     loc_F42
0xf41  ldc.i4.1
0xf42  stloc.s  6
0xf44  ldsfld   string [mscorlib]System.String::Empty
0xf49  stloc.s  7
0xf4b  ldsfld   string [mscorlib]System.String::Empty
0xf50  stloc.s  8
0xf52  ldarg.2
0xf53  callvirt instance string ResourceData::get_ValueAsString()
0xf58  call     string System.Resources.Tools.StronglyTypedResourceBuilder::TruncateAndFormatCommentStringForOutput(string commentString)
0xf5d  stloc.s  9
0xf5f  ldsfld   string [mscorlib]System.String::Empty
0xf64  stloc.s  0xA
0xf66  ldloc.s  5
0xf68  brtrue.s loc_F77
0xf6a  ldloc.1
0xf6b  callvirt instance string [mscorlib]System.Object::ToString()
0xf70  call     string System.Resources.Tools.StronglyTypedResourceBuilder::TruncateAndFormatCommentStringForOutput(string commentString)
0xf75  stloc.s  0xA
0xf77  ldloc.s  5
0xf79  brfalse.s loc_F84
0xf7b  ldstr    aGetstring// "GetString"
0xf80  stloc.s  7
0xf82  br.s     loc_F98
0xf84  ldloc.s  6
0xf86  brfalse.s loc_F91
0xf88  ldstr    aGetstream// "GetStream"
0xf8d  stloc.s  7
0xf8f  br.s     loc_F98
0xf91  ldstr    aGetobject// "GetObject"
0xf96  stloc.s  7
0xf98  ldloc.s  5
0xf9a  brfalse.s loc_FB5
0xf9c  ldstr    aStringproperty_0// "StringPropertyComment"
0xfa1  ldc.i4.1
0xfa2  newarr   [mscorlib]System.Object
0xfa7  dup
0xfa8  ldc.i4.0
0xfa9  ldloc.s  9
0xfab  stelem.ref
0xfac  call     string System.Design.SR::GetString(string name, object[] args)
0xfb1  stloc.s  8
0xfb3  br.s     loc_FF9
0xfb5  ldloc.s  9
0xfb7  brfalse.s loc_FC4
0xfb9  ldloc.s  0xA
0xfbb  ldloc.s  9
0xfbd  call     bool [mscorlib]System.String::Equals(string, string)
0xfc2  brfalse.s loc_FDD
0xfc4  ldstr    aNonstringprope// "NonStringPropertyComment"
0xfc9  ldc.i4.1
0xfca  newarr   [mscorlib]System.Object
0xfcf  dup
0xfd0  ldc.i4.0
0xfd1  ldloc.s  0xA
0xfd3  stelem.ref
0xfd4  call     string System.Design.SR::GetString(string name, object[] args)
0xfd9  stloc.s  8
0xfdb  br.s     loc_FF9
0xfdd  ldstr    aNonstringprope_0// "NonStringPropertyDetailedComment"
0xfe2  ldc.i4.2
0xfe3  newarr   [mscorlib]System.Object
0xfe8  dup
0xfe9  ldc.i4.0
0xfea  ldloc.s  0xA
0xfec  stelem.ref
0xfed  dup
0xfee  ldc.i4.1
0xfef  ldloc.s  9
0xff1  stelem.ref
0xff2  call     string System.Design.SR::GetString(string name, object[] args)
0xff7  stloc.s  8
0xff9  ldloc.0
0xffa  callvirt instance class [System]System.CodeDom.CodeCommentStatementCollection [System]System.CodeDom.CodeTypeMember::get_Comments()
0xfff  ldstr    aSummary// "<summary>"
0x1004  ldc.i4.1
0x1005  newobj   instance void [System]System.CodeDom.CodeCommentStatement::.ctor(string, bool)
0x100a  callvirt instance int32 [System]System.CodeDom.CodeCommentStatementCollection::Add(class [System]System.CodeDom.CodeCommentStatement)
0x100f  pop
0x1010  ldloc.0
0x1011  callvirt instance class [System]System.CodeDom.CodeCommentStatementCollection [System]System.CodeDom.CodeTypeMember::get_Comments()
0x1016  ldloc.s  8
0x1018  ldc.i4.1
0x1019  newobj   instance void [System]System.CodeDom.CodeCommentStatement::.ctor(string, bool)
0x101e  callvirt instance int32 [System]System.CodeDom.CodeCommentStatementCollection::Add(class [System]System.CodeDom.CodeCommentStatement)
0x1023  pop
0x1024  ldloc.0
0x1025  callvirt instance class [System]System.CodeDom.CodeCommentStatementCollection [System]System.CodeDom.CodeTypeMember::get_Comments()
0x102a  ldstr    aSummary_0// "</summary>"
0x102f  ldc.i4.1
0x1030  newobj   instance void [System]System.CodeDom.CodeCommentStatement::.ctor(string, bool)
0x1035  callvirt instance int32 [System]System.CodeDom.CodeCommentStatementCollection::Add(class [System]System.CodeDom.CodeCommentStatement)
0x103a  pop
0x103b  ldloc.3
0x103c  ldloc.s  7
0x103e  ldc.i4.2
0x103f  newarr   [System]System.CodeDom.CodeExpression
0x1044  dup
0x1045  ldc.i4.0
0x1046  ldarg.1
0x1047  newobj   instance void [System]System.CodeDom.CodePrimitiveExpression::.ctor(object)
0x104c  stelem.ref
0x104d  dup
0x104e  ldc.i4.1
0x104f  ldloc.s  4
0x1051  stelem.ref
0x1052  newobj   instance void [System]System.CodeDom.CodeMethodInvokeExpression::.ctor(class [System]System.CodeDom.CodeExpression, string, class [System]System.CodeDom.CodeExpression[])
0x1057  stloc.s  0xB
0x1059  ldloc.s  5
0x105b  ldloc.s  6
0x105d  or
0x105e  brfalse.s loc_106B
0x1060  ldloc.s  0xB
0x1062  newobj   instance void [System]System.CodeDom.CodeMethodReturnStatement::.ctor(class [System]System.CodeDom.CodeExpression)
0x1067  stloc.s  0xC
0x1069  br.s     loc_10A8
0x106b  ldtoken  [mscorlib]System.Object
0x1070  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1075  ldstr    aObj// "obj"
0x107a  ldloc.s  0xB
0x107c  newobj   instance void [System]System.CodeDom.CodeVariableDeclarationStatement::.ctor(class [mscorlib]System.Type, string, class [System]System.CodeDom.CodeExpression)
0x1081  stloc.s  0xD
0x1083  ldloc.0
0x1084  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberProperty::get_GetStatements()
0x1089  ldloc.s  0xD
0x108b  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x1090  pop
0x1091  ldloc.2
0x1092  ldstr    aObj// "obj"
0x1097  newobj   instance void [System]System.CodeDom.CodeVariableReferenceExpression::.ctor(string)
0x109c  newobj   instance void [System]System.CodeDom.CodeCastExpression::.ctor(class [System]System.CodeDom.CodeTypeReference, class [System]System.CodeDom.CodeExpression)
0x10a1  newobj   instance void [System]System.CodeDom.CodeMethodReturnStatement::.ctor(class [System]System.CodeDom.CodeExpression)
0x10a6  stloc.s  0xC
0x10a8  ldloc.0
0x10a9  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberProperty::get_GetStatements()
0x10ae  ldloc.s  0xC
0x10b0  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x10b5  pop
0x10b6  ldarg.3
0x10b7  callvirt instance class [System]System.CodeDom.CodeTypeMemberCollection [System]System.CodeDom.CodeTypeDeclaration::get_Members()
0x10bc  ldloc.0
0x10bd  callvirt instance int32 [System]System.CodeDom.CodeTypeMemberCollection::Add(class [System]System.CodeDom.CodeTypeMember)
0x10c2  pop
0x10c3  ldc.i4.1
0x10c4  ret
```
