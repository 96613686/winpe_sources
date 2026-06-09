# System.Resources.Tools.StronglyTypedResourceBuilder::EmitBasicClassMembers

- ea: `0x8e0`
- end: `0xe0c`
- name: `System.Resources.Tools.StronglyTypedResourceBuilder::EmitBasicClassMembers`
- size: `1324`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x470`

## callees

- `0x8e0`
- `0x8ef40`

## string_xrefs

- `0x91c`: `ClassComments1`
- `0x939`: `ClassComments2`
- `0x956`: `ClassComments3`
- `0x973`: `ClassComments4`
- `0xb5c`: `System.ComponentModel.EditorBrowsableAttribute`
- `0xd35`: `ResMgrPropertyComment`
- `0xdc0`: `CulturePropertyComment1`
- `0xddd`: `CulturePropertyComment2`

## pseudocode

```c

```

## disassembly

```asm
0x8e0  ldarg.3
0x8e1  brfalse.s loc_8FF
0x8e3  ldarg.3
0x8e4  callvirt instance int32 [mscorlib]System.String::get_Length()
0x8e9  ldc.i4.0
0x8ea  ble.s    loc_8FB
0x8ec  ldarg.3
0x8ed  ldstr    asc_12C1E8// "."
0x8f2  ldarg.2
0x8f3  call     string [mscorlib]System.String::Concat(string, string, string)
0x8f8  stloc.0
0x8f9  br.s     loc_91C
0x8fb  ldarg.2
0x8fc  stloc.0
0x8fd  br.s     loc_91C
0x8ff  ldarg.1
0x900  brfalse.s loc_91A
0x902  ldarg.1
0x903  callvirt instance int32 [mscorlib]System.String::get_Length()
0x908  ldc.i4.0
0x909  ble.s    loc_91A
0x90b  ldarg.1
0x90c  ldstr    asc_12C1E8// "."
0x911  ldarg.2
0x912  call     string [mscorlib]System.String::Concat(string, string, string)
0x917  stloc.0
0x918  br.s     loc_91C
0x91a  ldarg.2
0x91b  stloc.0
0x91c  ldstr    aClasscomments1// "ClassComments1"
0x921  call     string System.Design.SR::GetString(string name)
0x926  newobj   instance void [System]System.CodeDom.CodeCommentStatement::.ctor(string)
0x92b  stloc.1
0x92c  ldarg.0
0x92d  callvirt instance class [System]System.CodeDom.CodeCommentStatementCollection [System]System.CodeDom.CodeTypeMember::get_Comments()
0x932  ldloc.1
0x933  callvirt instance int32 [System]System.CodeDom.CodeCommentStatementCollection::Add(class [System]System.CodeDom.CodeCommentStatement)
0x938  pop
0x939  ldstr    aClasscomments2// "ClassComments2"
0x93e  call     string System.Design.SR::GetString(string name)
0x943  newobj   instance void [System]System.CodeDom.CodeCommentStatement::.ctor(string)
0x948  stloc.1
0x949  ldarg.0
0x94a  callvirt instance class [System]System.CodeDom.CodeCommentStatementCollection [System]System.CodeDom.CodeTypeMember::get_Comments()
0x94f  ldloc.1
0x950  callvirt instance int32 [System]System.CodeDom.CodeCommentStatementCollection::Add(class [System]System.CodeDom.CodeCommentStatement)
0x955  pop
0x956  ldstr    aClasscomments3// "ClassComments3"
0x95b  call     string System.Design.SR::GetString(string name)
0x960  newobj   instance void [System]System.CodeDom.CodeCommentStatement::.ctor(string)
0x965  stloc.1
0x966  ldarg.0
0x967  callvirt instance class [System]System.CodeDom.CodeCommentStatementCollection [System]System.CodeDom.CodeTypeMember::get_Comments()
0x96c  ldloc.1
0x96d  callvirt instance int32 [System]System.CodeDom.CodeCommentStatementCollection::Add(class [System]System.CodeDom.CodeCommentStatement)
0x972  pop
0x973  ldstr    aClasscomments4// "ClassComments4"
0x978  call     string System.Design.SR::GetString(string name)
0x97d  newobj   instance void [System]System.CodeDom.CodeCommentStatement::.ctor(string)
0x982  stloc.1
0x983  ldarg.0
0x984  callvirt instance class [System]System.CodeDom.CodeCommentStatementCollection [System]System.CodeDom.CodeTypeMember::get_Comments()
0x989  ldloc.1
0x98a  callvirt instance int32 [System]System.CodeDom.CodeCommentStatementCollection::Add(class [System]System.CodeDom.CodeCommentStatement)
0x98f  pop
0x990  ldtoken  [mscorlib]System.Diagnostics.CodeAnalysis.SuppressMessageAttribute
0x995  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x99a  newobj   instance void [System]System.CodeDom.CodeTypeReference::.ctor(class [mscorlib]System.Type)
0x99f  newobj   instance void [System]System.CodeDom.CodeAttributeDeclaration::.ctor(class [System]System.CodeDom.CodeTypeReference)
0x9a4  stloc.2
0x9a5  ldloc.2
0x9a6  callvirt instance class [System]System.CodeDom.CodeTypeReference [System]System.CodeDom.CodeAttributeDeclaration::get_AttributeType()
0x9ab  ldc.i4.1
0x9ac  callvirt instance void [System]System.CodeDom.CodeTypeReference::set_Options(valuetype [System]System.CodeDom.CodeTypeReferenceOptions)
0x9b1  ldloc.2
0x9b2  callvirt instance class [System]System.CodeDom.CodeAttributeArgumentCollection [System]System.CodeDom.CodeAttributeDeclaration::get_Arguments()
0x9b7  ldstr    aMicrosoftPerfo// "Microsoft.Performance"
0x9bc  newobj   instance void [System]System.CodeDom.CodePrimitiveExpression::.ctor(object)
0x9c1  newobj   instance void [System]System.CodeDom.CodeAttributeArgument::.ctor(class [System]System.CodeDom.CodeExpression)
0x9c6  callvirt instance int32 [System]System.CodeDom.CodeAttributeArgumentCollection::Add(class [System]System.CodeDom.CodeAttributeArgument)
0x9cb  pop
0x9cc  ldloc.2
0x9cd  callvirt instance class [System]System.CodeDom.CodeAttributeArgumentCollection [System]System.CodeDom.CodeAttributeDeclaration::get_Arguments()
0x9d2  ldstr    aCa1811Avoidunc// "CA1811:AvoidUncalledPrivateCode"
0x9d7  newobj   instance void [System]System.CodeDom.CodePrimitiveExpression::.ctor(object)
0x9dc  newobj   instance void [System]System.CodeDom.CodeAttributeArgument::.ctor(class [System]System.CodeDom.CodeExpression)
0x9e1  callvirt instance int32 [System]System.CodeDom.CodeAttributeArgumentCollection::Add(class [System]System.CodeDom.CodeAttributeArgument)
0x9e6  pop
0x9e7  newobj   instance void [System]System.CodeDom.CodeConstructor::.ctor()
0x9ec  stloc.3
0x9ed  ldloc.3
0x9ee  callvirt instance class [System]System.CodeDom.CodeAttributeDeclarationCollection [System]System.CodeDom.CodeTypeMember::get_CustomAttributes()
0x9f3  ldloc.2
0x9f4  callvirt instance int32 [System]System.CodeDom.CodeAttributeDeclarationCollection::Add(class [System]System.CodeDom.CodeAttributeDeclaration)
0x9f9  pop
0x9fa  ldarg.s  5
0x9fc  ldarg.s  4
0x9fe  or
0x9ff  brfalse.s loc_A0E
0xa01  ldloc.3
0xa02  ldc.i4   0x2000
0xa07  callvirt instance void [System]System.CodeDom.CodeTypeMember::set_Attributes(valuetype [System]System.CodeDom.MemberAttributes)
0xa0c  br.s     loc_A19
0xa0e  ldloc.3
0xa0f  ldc.i4   0x6000
0xa14  callvirt instance void [System]System.CodeDom.CodeTypeMember::set_Attributes(valuetype [System]System.CodeDom.MemberAttributes)
0xa19  ldarg.0
0xa1a  callvirt instance class [System]System.CodeDom.CodeTypeMemberCollection [System]System.CodeDom.CodeTypeDeclaration::get_Members()
0xa1f  ldloc.3
0xa20  callvirt instance int32 [System]System.CodeDom.CodeTypeMemberCollection::Add(class [System]System.CodeDom.CodeTypeMember)
0xa25  pop
0xa26  ldtoken  [mscorlib]System.Resources.ResourceManager
0xa2b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa30  ldc.i4.1
0xa31  newobj   instance void [System]System.CodeDom.CodeTypeReference::.ctor(class [mscorlib]System.Type, valuetype [System]System.CodeDom.CodeTypeReferenceOptions)
0xa36  stloc.s  4
0xa38  ldloc.s  4
0xa3a  ldstr    aResourceman// "resourceMan"
0xa3f  newobj   instance void [System]System.CodeDom.CodeMemberField::.ctor(class [System]System.CodeDom.CodeTypeReference, string)
0xa44  stloc.s  5
0xa46  ldloc.s  5
0xa48  ldc.i4   0x5000
0xa4d  callvirt instance void [System]System.CodeDom.CodeTypeMember::set_Attributes(valuetype [System]System.CodeDom.MemberAttributes)
0xa52  ldarg.s  5
0xa54  brfalse.s loc_A65
0xa56  ldloc.s  5
0xa58  dup
0xa59  callvirt instance valuetype [System]System.CodeDom.MemberAttributes [System]System.CodeDom.CodeTypeMember::get_Attributes()
0xa5e  ldc.i4.3
0xa5f  or
0xa60  callvirt instance void [System]System.CodeDom.CodeTypeMember::set_Attributes(valuetype [System]System.CodeDom.MemberAttributes)
0xa65  ldarg.0
0xa66  callvirt instance class [System]System.CodeDom.CodeTypeMemberCollection [System]System.CodeDom.CodeTypeDeclaration::get_Members()
0xa6b  ldloc.s  5
0xa6d  callvirt instance int32 [System]System.CodeDom.CodeTypeMemberCollection::Add(class [System]System.CodeDom.CodeTypeMember)
0xa72  pop
0xa73  ldtoken  [mscorlib]System.Globalization.CultureInfo
0xa78  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa7d  ldc.i4.1
0xa7e  newobj   instance void [System]System.CodeDom.CodeTypeReference::.ctor(class [mscorlib]System.Type, valuetype [System]System.CodeDom.CodeTypeReferenceOptions)
0xa83  stloc.s  6
0xa85  ldloc.s  6
0xa87  ldstr    aResourcecultur// "resourceCulture"
0xa8c  newobj   instance void [System]System.CodeDom.CodeMemberField::.ctor(class [System]System.CodeDom.CodeTypeReference, string)
0xa91  stloc.s  5
0xa93  ldloc.s  5
0xa95  ldc.i4   0x5000
0xa9a  callvirt instance void [System]System.CodeDom.CodeTypeMember::set_Attributes(valuetype [System]System.CodeDom.MemberAttributes)
0xa9f  ldarg.s  5
0xaa1  brfalse.s loc_AB2
0xaa3  ldloc.s  5
0xaa5  dup
0xaa6  callvirt instance valuetype [System]System.CodeDom.MemberAttributes [System]System.CodeDom.CodeTypeMember::get_Attributes()
0xaab  ldc.i4.3
0xaac  or
0xaad  callvirt instance void [System]System.CodeDom.CodeTypeMember::set_Attributes(valuetype [System]System.CodeDom.MemberAttributes)
0xab2  ldarg.0
0xab3  callvirt instance class [System]System.CodeDom.CodeTypeMemberCollection [System]System.CodeDom.CodeTypeDeclaration::get_Members()
0xab8  ldloc.s  5
0xaba  callvirt instance int32 [System]System.CodeDom.CodeTypeMemberCollection::Add(class [System]System.CodeDom.CodeTypeMember)
0xabf  pop
0xac0  newobj   instance void [System]System.CodeDom.CodeMemberProperty::.ctor()
0xac5  stloc.s  7
0xac7  ldarg.0
0xac8  callvirt instance class [System]System.CodeDom.CodeTypeMemberCollection [System]System.CodeDom.CodeTypeDeclaration::get_Members()
0xacd  ldloc.s  7
0xacf  callvirt instance int32 [System]System.CodeDom.CodeTypeMemberCollection::Add(class [System]System.CodeDom.CodeTypeMember)
0xad4  pop
0xad5  ldloc.s  7
0xad7  ldstr    aResourcemanage// "ResourceManager"
0xadc  callvirt instance void [System]System.CodeDom.CodeTypeMember::set_Name(string)
0xae1  ldloc.s  7
0xae3  ldc.i4.1
0xae4  callvirt instance void [System]System.CodeDom.CodeMemberProperty::set_HasGet(bool)
0xae9  ldloc.s  7
0xaeb  ldc.i4.0
0xaec  callvirt instance void [System]System.CodeDom.CodeMemberProperty::set_HasSet(bool)
0xaf1  ldloc.s  7
0xaf3  ldloc.s  4
0xaf5  callvirt instance void [System]System.CodeDom.CodeMemberProperty::set_Type(class [System]System.CodeDom.CodeTypeReference)
0xafa  ldarg.s  4
0xafc  brfalse.s loc_B0C
0xafe  ldloc.s  7
0xb00  ldc.i4   0x1000
0xb05  callvirt instance void [System]System.CodeDom.CodeTypeMember::set_Attributes(valuetype [System]System.CodeDom.MemberAttributes)
0xb0a  br.s     loc_B18
0xb0c  ldloc.s  7
0xb0e  ldc.i4   0x6000
0xb13  callvirt instance void [System]System.CodeDom.CodeTypeMember::set_Attributes(valuetype [System]System.CodeDom.MemberAttributes)
0xb18  ldarg.s  5
0xb1a  brfalse.s loc_B2B
0xb1c  ldloc.s  7
0xb1e  dup
0xb1f  callvirt instance valuetype [System]System.CodeDom.MemberAttributes [System]System.CodeDom.CodeTypeMember::get_Attributes()
0xb24  ldc.i4.3
0xb25  or
0xb26  callvirt instance void [System]System.CodeDom.CodeTypeMember::set_Attributes(valuetype [System]System.CodeDom.MemberAttributes)
0xb2b  ldtoken  [System]System.ComponentModel.EditorBrowsableState
0xb30  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xb35  newobj   instance void [System]System.CodeDom.CodeTypeReference::.ctor(class [mscorlib]System.Type)
0xb3a  stloc.s  8
0xb3c  ldloc.s  8
0xb3e  ldc.i4.1
0xb3f  callvirt instance void [System]System.CodeDom.CodeTypeReference::set_Options(valuetype [System]System.CodeDom.CodeTypeReferenceOptions)
0xb44  ldloc.s  8
0xb46  newobj   instance void [System]System.CodeDom.CodeTypeReferenceExpression::.ctor(class [System]System.CodeDom.CodeTypeReference)
0xb4b  ldstr    aAdvanced// "Advanced"
0xb50  newobj   instance void [System]System.CodeDom.CodeFieldReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0xb55  newobj   instance void [System]System.CodeDom.CodeAttributeArgument::.ctor(class [System]System.CodeDom.CodeExpression)
0xb5a  stloc.s  9
0xb5c  ldstr    aSystemComponen// "System.ComponentModel.EditorBrowsableAt"...
0xb61  ldc.i4.1
0xb62  newarr   [System]System.CodeDom.CodeAttributeArgument
0xb67  dup
0xb68  ldc.i4.0
0xb69  ldloc.s  9
0xb6b  stelem.ref
0xb6c  newobj   instance void [System]System.CodeDom.CodeAttributeDeclaration::.ctor(string, class [System]System.CodeDom.CodeAttributeArgument[])
0xb71  stloc.s  0xA
0xb73  ldloc.s  0xA
0xb75  callvirt instance class [System]System.CodeDom.CodeTypeReference [System]System.CodeDom.CodeAttributeDeclaration::get_AttributeType()
0xb7a  ldc.i4.1
0xb7b  callvirt instance void [System]System.CodeDom.CodeTypeReference::set_Options(valuetype [System]System.CodeDom.CodeTypeReferenceOptions)
0xb80  ldloc.s  7
0xb82  callvirt instance class [System]System.CodeDom.CodeAttributeDeclarationCollection [System]System.CodeDom.CodeTypeMember::get_CustomAttributes()
0xb87  ldloc.s  0xA
0xb89  callvirt instance int32 [System]System.CodeDom.CodeAttributeDeclarationCollection::Add(class [System]System.CodeDom.CodeAttributeDeclaration)
0xb8e  pop
0xb8f  newobj   instance void [System]System.CodeDom.CodeMemberProperty::.ctor()
0xb94  stloc.s  0xB
0xb96  ldarg.0
0xb97  callvirt instance class [System]System.CodeDom.CodeTypeMemberCollection [System]System.CodeDom.CodeTypeDeclaration::get_Members()
0xb9c  ldloc.s  0xB
0xb9e  callvirt instance int32 [System]System.CodeDom.CodeTypeMemberCollection::Add(class [System]System.CodeDom.CodeTypeMember)
0xba3  pop
0xba4  ldloc.s  0xB
0xba6  ldstr    aCulture// "Culture"
0xbab  callvirt instance void [System]System.CodeDom.CodeTypeMember::set_Name(string)
0xbb0  ldloc.s  0xB
0xbb2  ldc.i4.1
0xbb3  callvirt instance void [System]System.CodeDom.CodeMemberProperty::set_HasGet(bool)
0xbb8  ldloc.s  0xB
0xbba  ldc.i4.1
0xbbb  callvirt instance void [System]System.CodeDom.CodeMemberProperty::set_HasSet(bool)
0xbc0  ldloc.s  0xB
0xbc2  ldloc.s  6
0xbc4  callvirt instance void [System]System.CodeDom.CodeMemberProperty::set_Type(class [System]System.CodeDom.CodeTypeReference)
0xbc9  ldarg.s  4
0xbcb  brfalse.s loc_BDB
0xbcd  ldloc.s  0xB
0xbcf  ldc.i4   0x1000
0xbd4  callvirt instance void [System]System.CodeDom.CodeTypeMember::set_Attributes(valuetype [System]System.CodeDom.MemberAttributes)
0xbd9  br.s     loc_BE7
0xbdb  ldloc.s  0xB
0xbdd  ldc.i4   0x6000
0xbe2  callvirt instance void [System]System.CodeDom.CodeTypeMember::set_Attributes(valuetype [System]System.CodeDom.MemberAttributes)
0xbe7  ldarg.s  5
0xbe9  brfalse.s loc_BFA
0xbeb  ldloc.s  0xB
0xbed  dup
0xbee  callvirt instance valuetype [System]System.CodeDom.MemberAttributes [System]System.CodeDom.CodeTypeMember::get_Attributes()
0xbf3  ldc.i4.3
0xbf4  or
0xbf5  callvirt instance void [System]System.CodeDom.CodeTypeMember::set_Attributes(valuetype [System]System.CodeDom.MemberAttributes)
0xbfa  ldloc.s  0xB
0xbfc  callvirt instance class [System]System.CodeDom.CodeAttributeDeclarationCollection [System]System.CodeDom.CodeTypeMember::get_CustomAttributes()
0xc01  ldloc.s  0xA
0xc03  callvirt instance int32 [System]System.CodeDom.CodeAttributeDeclarationCollection::Add(class [System]System.CodeDom.CodeAttributeDeclaration)
0xc08  pop
0xc09  ldnull
0xc0a  ldstr    aResourceman// "resourceMan"
0xc0f  newobj   instance void [System]System.CodeDom.CodeFieldReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0xc14  stloc.s  0xC
0xc16  ldtoken  [mscorlib]System.Object
0xc1b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xc20  newobj   instance void [System]System.CodeDom.CodeTypeReferenceExpression::.ctor(class [mscorlib]System.Type)
0xc25  ldstr    aReferenceequal// "ReferenceEquals"
0xc2a  newobj   instance void [System]System.CodeDom.CodeMethodReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0xc2f  stloc.s  0xD
0xc31  ldloc.s  0xD
0xc33  ldc.i4.2
0xc34  newarr   [System]System.CodeDom.CodeExpression
0xc39  dup
0xc3a  ldc.i4.0
0xc3b  ldloc.s  0xC
0xc3d  stelem.ref
0xc3e  dup
0xc3f  ldc.i4.1
0xc40  ldnull
0xc41  newobj   instance void [System]System.CodeDom.CodePrimitiveExpression::.ctor(object)
0xc46  stelem.ref
0xc47  newobj   instance void [System]System.CodeDom.CodeMethodInvokeExpression::.ctor(class [System]System.CodeDom.CodeMethodReferenceExpression, class [System]System.CodeDom.CodeExpression[])
0xc4c  stloc.s  0xE
0xc4e  ldarg.s  7
0xc50  brfalse.s loc_C84
0xc52  ldarg.0
0xc53  callvirt instance string [System]System.CodeDom.CodeTypeMember::get_Name()
0xc58  newobj   instance void [System]System.CodeDom.CodeTypeReference::.ctor(string)
0xc5d  newobj   instance void [System]System.CodeDom.CodeTypeOfExpression::.ctor(class [System]System.CodeDom.CodeTypeReference)
0xc62  ldstr    aGettypeinfo// "GetTypeInfo"
  ... truncated ...
```
