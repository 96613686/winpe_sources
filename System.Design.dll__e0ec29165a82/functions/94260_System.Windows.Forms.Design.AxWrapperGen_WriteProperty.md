# System.Windows.Forms.Design.AxWrapperGen::WriteProperty

- ea: `0x94260`
- end: `0x947be`
- name: `System.Windows.Forms.Design.AxWrapperGen::WriteProperty`
- size: `1374`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callers

- `0x94de0`

## callees

- `0x919c0`
- `0x91a20`
- `0x91b10`
- `0x91b60`
- `0x92270`
- `0x92280`
- `0x925a0`
- `0x926c0`
- `0x92be0`
- `0x92c50`
- `0x92cc0`
- `0x92fa0`
- `0x94260`
- `0x947c0`
- `0x94880`
- `0x112c70`
- `0x112d00`

## string_xrefs

- `0x942a0`: `System.ComponentModel.Browsable`
- `0x942c8`: `System.ComponentModel.Browsable`
- `0x9426e`: `System.ComponentModel.DesignerSerializationVisibility`
- `0x9427c`: `System.ComponentModel.DesignerSerializationVisibility`
- `0x942f0`: `System.ComponentModel.Bindable`
- `0x94322`: `System.ComponentModel.Bindable`
- `0x942fe`: `System.ComponentModel.BindableSupport`
- `0x94330`: `System.ComponentModel.BindableSupport`
- `0x9471f`: `System.Runtime.CompilerServices.IndexerName`
- `0x9477b`: `System.ComponentModel.DefaultProperty`

## pseudocode

```c

```

## disassembly

```asm
0x94260  ldnull
0x94261  stloc.1
0x94262  ldnull
0x94263  stloc.2
0x94264  ldsfld   class [System]System.CodeDom.CodeAttributeDeclaration System.Windows.Forms.Design.AxWrapperGen::nopersist
0x94269  brtrue   loc_94354
0x9426e  ldstr    aSystemComponen_10// "System.ComponentModel.DesignerSerializa"...
0x94273  ldc.i4.1
0x94274  newarr   [System]System.CodeDom.CodeAttributeArgument
0x94279  dup
0x9427a  ldc.i4.0
0x9427b  ldnull
0x9427c  ldstr    aSystemComponen_10// "System.ComponentModel.DesignerSerializa"...
0x94281  newobj   instance void [System]System.CodeDom.CodeFieldReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0x94286  ldstr    aHidden// "Hidden"
0x9428b  newobj   instance void [System]System.CodeDom.CodeFieldReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0x94290  newobj   instance void [System]System.CodeDom.CodeAttributeArgument::.ctor(class [System]System.CodeDom.CodeExpression)
0x94295  stelem.ref
0x94296  newobj   instance void [System]System.CodeDom.CodeAttributeDeclaration::.ctor(string, class [System]System.CodeDom.CodeAttributeArgument[])
0x9429b  stsfld   class [System]System.CodeDom.CodeAttributeDeclaration System.Windows.Forms.Design.AxWrapperGen::nopersist
0x942a0  ldstr    aSystemComponen_9// "System.ComponentModel.Browsable"
0x942a5  ldc.i4.1
0x942a6  newarr   [System]System.CodeDom.CodeAttributeArgument
0x942ab  dup
0x942ac  ldc.i4.0
0x942ad  ldc.i4.0
0x942ae  box      [mscorlib]System.Boolean
0x942b3  newobj   instance void [System]System.CodeDom.CodePrimitiveExpression::.ctor(object)
0x942b8  newobj   instance void [System]System.CodeDom.CodeAttributeArgument::.ctor(class [System]System.CodeDom.CodeExpression)
0x942bd  stelem.ref
0x942be  newobj   instance void [System]System.CodeDom.CodeAttributeDeclaration::.ctor(string, class [System]System.CodeDom.CodeAttributeArgument[])
0x942c3  stsfld   class [System]System.CodeDom.CodeAttributeDeclaration System.Windows.Forms.Design.AxWrapperGen::nobrowse
0x942c8  ldstr    aSystemComponen_9// "System.ComponentModel.Browsable"
0x942cd  ldc.i4.1
0x942ce  newarr   [System]System.CodeDom.CodeAttributeArgument
0x942d3  dup
0x942d4  ldc.i4.0
0x942d5  ldc.i4.1
0x942d6  box      [mscorlib]System.Boolean
0x942db  newobj   instance void [System]System.CodeDom.CodePrimitiveExpression::.ctor(object)
0x942e0  newobj   instance void [System]System.CodeDom.CodeAttributeArgument::.ctor(class [System]System.CodeDom.CodeExpression)
0x942e5  stelem.ref
0x942e6  newobj   instance void [System]System.CodeDom.CodeAttributeDeclaration::.ctor(string, class [System]System.CodeDom.CodeAttributeArgument[])
0x942eb  stsfld   class [System]System.CodeDom.CodeAttributeDeclaration System.Windows.Forms.Design.AxWrapperGen::browse
0x942f0  ldstr    aSystemComponen_12// "System.ComponentModel.Bindable"
0x942f5  ldc.i4.1
0x942f6  newarr   [System]System.CodeDom.CodeAttributeArgument
0x942fb  dup
0x942fc  ldc.i4.0
0x942fd  ldnull
0x942fe  ldstr    aSystemComponen_13// "System.ComponentModel.BindableSupport"
0x94303  newobj   instance void [System]System.CodeDom.CodeFieldReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0x94308  ldstr    aYes// "Yes"
0x9430d  newobj   instance void [System]System.CodeDom.CodeFieldReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0x94312  newobj   instance void [System]System.CodeDom.CodeAttributeArgument::.ctor(class [System]System.CodeDom.CodeExpression)
0x94317  stelem.ref
0x94318  newobj   instance void [System]System.CodeDom.CodeAttributeDeclaration::.ctor(string, class [System]System.CodeDom.CodeAttributeArgument[])
0x9431d  stsfld   class [System]System.CodeDom.CodeAttributeDeclaration System.Windows.Forms.Design.AxWrapperGen::bindable
0x94322  ldstr    aSystemComponen_12// "System.ComponentModel.Bindable"
0x94327  ldc.i4.1
0x94328  newarr   [System]System.CodeDom.CodeAttributeArgument
0x9432d  dup
0x9432e  ldc.i4.0
0x9432f  ldnull
0x94330  ldstr    aSystemComponen_13// "System.ComponentModel.BindableSupport"
0x94335  newobj   instance void [System]System.CodeDom.CodeFieldReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0x9433a  ldstr    aDefault_0// "Default"
0x9433f  newobj   instance void [System]System.CodeDom.CodeFieldReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0x94344  newobj   instance void [System]System.CodeDom.CodeAttributeArgument::.ctor(class [System]System.CodeDom.CodeExpression)
0x94349  stelem.ref
0x9434a  newobj   instance void [System]System.CodeDom.CodeAttributeDeclaration::.ctor(string, class [System]System.CodeDom.CodeAttributeArgument[])
0x9434f  stsfld   class [System]System.CodeDom.CodeAttributeDeclaration System.Windows.Forms.Design.AxWrapperGen::defaultBind
0x94354  ldarg.2
0x94355  ldarg.2
0x94356  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.PropertyInfo::get_PropertyType()
0x9435b  ldarg.2
0x9435c  call     valuetype ComAliasEnum ComAliasConverter::GetComAliasEnum(class [mscorlib]System.Reflection.MemberInfo memberInfo, class [mscorlib]System.Type type, class [mscorlib]System.Reflection.ICustomAttributeProvider attrProvider)
0x94361  stloc.3
0x94362  ldarg.2
0x94363  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.PropertyInfo::get_PropertyType()
0x94368  stloc.s  4
0x9436a  ldloc.3
0x9436b  brfalse.s loc_94377
0x9436d  ldloc.s  4
0x9436f  ldloc.3
0x94370  call     class [mscorlib]System.Type ComAliasConverter::GetWFTypeFromComType(class [mscorlib]System.Type t, valuetype ComAliasEnum alias)
0x94375  stloc.s  4
0x94377  ldloc.s  4
0x94379  callvirt instance valuetype [mscorlib]System.Guid [mscorlib]System.Type::get_GUID()
0x9437e  stloc.s  0x10
0x94380  ldloca.s 0x10
0x94382  ldsfld   valuetype [mscorlib]System.Guid System.Windows.Forms.Design.AxWrapperGen::Guid_DataSource
0x94387  call     instance bool [mscorlib]System.Guid::Equals(valuetype [mscorlib]System.Guid)
0x9438c  stloc.s  5
0x9438e  ldloc.s  5
0x94390  brfalse.s loc_943D3
0x94392  ldloc.s  4
0x94394  callvirt instance string [mscorlib]System.Type::get_FullName()
0x94399  ldarg.0
0x9439a  ldarg.2
0x9439b  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x943a0  call     instance string System.Windows.Forms.Design.AxWrapperGen::CreateDataSourceFieldName(string propName)
0x943a5  newobj   instance void [System]System.CodeDom.CodeMemberField::.ctor(string, string)
0x943aa  stloc.s  0x11
0x943ac  ldloc.s  0x11
0x943ae  ldc.i4   0x5002
0x943b3  callvirt instance void [System]System.CodeDom.CodeTypeMember::set_Attributes(valuetype [System]System.CodeDom.MemberAttributes)
0x943b8  ldarg.1
0x943b9  callvirt instance class [System]System.CodeDom.CodeTypeMemberCollection [System]System.CodeDom.CodeTypeDeclaration::get_Members()
0x943be  ldloc.s  0x11
0x943c0  callvirt instance int32 [System]System.CodeDom.CodeTypeMemberCollection::Add(class [System]System.CodeDom.CodeTypeMember)
0x943c5  pop
0x943c6  ldarg.0
0x943c7  ldfld    class [mscorlib]System.Collections.ArrayList System.Windows.Forms.Design.AxWrapperGen::dataSourceProps
0x943cc  ldarg.2
0x943cd  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x943d2  pop
0x943d3  ldarg.2
0x943d4  ldtoken  [mscorlib]System.Runtime.InteropServices.DispIdAttribute
0x943d9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x943de  call     class [mscorlib]System.Reflection.CustomAttributeData[] System.Windows.Forms.Design.AxWrapperGen::GetAttributeData(class [mscorlib]System.Reflection.ICustomAttributeProvider attributeProvider, class [mscorlib]System.Type attributeType)
0x943e3  stloc.s  6
0x943e5  ldloc.s  6
0x943e7  brfalse.s loc_9443F
0x943e9  ldloc.s  6
0x943eb  ldlen
0x943ec  brfalse.s loc_9443F
0x943ee  ldloc.s  6
0x943f0  ldc.i4.0
0x943f1  ldelem.ref
0x943f2  stloc.2
0x943f3  ldtoken  [mscorlib]System.Runtime.InteropServices.DispIdAttribute
0x943f8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x943fd  callvirt instance string [mscorlib]System.Type::get_FullName()
0x94402  ldc.i4.1
0x94403  newarr   [System]System.CodeDom.CodeAttributeArgument
0x94408  dup
0x94409  ldc.i4.0
0x9440a  ldloc.2
0x9440b  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<valuetype [mscorlib]System.Reflection.CustomAttributeTypedArgument> [mscorlib]System.Reflection.CustomAttributeData::get_ConstructorArguments()
0x94410  ldc.i4.0
0x94411  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<valuetype [mscorlib]System.Reflection.CustomAttributeTypedArgument>::get_Item(!!T0)
0x94416  stloc.s  0x12
0x94418  ldloca.s 0x12
0x9441a  call     instance object [mscorlib]System.Reflection.CustomAttributeTypedArgument::get_Value()
0x9441f  callvirt instance string [mscorlib]System.Object::ToString()
0x94424  call     int32 [mscorlib]System.Int32::Parse(string)
0x94429  box      [mscorlib]System.Int32
0x9442e  newobj   instance void [System]System.CodeDom.CodePrimitiveExpression::.ctor(object)
0x94433  newobj   instance void [System]System.CodeDom.CodeAttributeArgument::.ctor(class [System]System.CodeDom.CodeExpression)
0x94438  stelem.ref
0x94439  newobj   instance void [System]System.CodeDom.CodeAttributeDeclaration::.ctor(string, class [System]System.CodeDom.CodeAttributeArgument[])
0x9443e  stloc.1
0x9443f  ldc.i4.0
0x94440  stloc.s  7
0x94442  ldc.i4.0
0x94443  stloc.s  8
0x94445  ldarg.0
0x94446  ldarg.2
0x94447  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x9444c  ldloc.s  4
0x9444e  ldloca.s 7
0x94450  ldloca.s 8
0x94452  call     instance string System.Windows.Forms.Design.AxWrapperGen::ResolveConflict(string name, class [mscorlib]System.Type returnType, [out] bool& fOverride, [out] bool& fUseNew)
0x94457  stloc.s  9
0x94459  ldloc.s  7
0x9445b  ldloc.s  8
0x9445d  or
0x9445e  brfalse.s loc_9449E
0x94460  ldloc.2
0x94461  brtrue.s loc_94464
0x94463  ret
0x94464  ldarg.0
0x94465  ldloc.2
0x94466  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<valuetype [mscorlib]System.Reflection.CustomAttributeTypedArgument> [mscorlib]System.Reflection.CustomAttributeData::get_ConstructorArguments()
0x9446b  ldc.i4.0
0x9446c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<valuetype [mscorlib]System.Reflection.CustomAttributeTypedArgument>::get_Item(!!T0)
0x94471  stloc.s  0x12
0x94473  ldloca.s 0x12
0x94475  call     instance object [mscorlib]System.Reflection.CustomAttributeTypedArgument::get_Value()
0x9447a  callvirt instance string [mscorlib]System.Object::ToString()
0x9447f  call     int32 [mscorlib]System.Int32::Parse(string)
0x94484  ldarg.2
0x94485  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x9448a  call     instance bool System.Windows.Forms.Design.AxWrapperGen::IsDispidKnown(int32 dp, string propName)
0x9448f  brtrue.s loc_9449E
0x94491  ldstr    aCtl// "Ctl"
0x94496  stloc.s  9
0x94498  ldc.i4.0
0x94499  stloc.s  7
0x9449b  ldc.i4.0
0x9449c  stloc.s  8
0x9449e  newobj   instance void [System]System.CodeDom.CodeMemberProperty::.ctor()
0x944a3  stloc.s  0xA
0x944a5  ldloc.s  0xA
0x944a7  ldloc.s  4
0x944a9  call     string System.Windows.Forms.Design.AxWrapperGen::MapTypeName(class [mscorlib]System.Type type)
0x944ae  newobj   instance void [System]System.CodeDom.CodeTypeReference::.ctor(string)
0x944b3  callvirt instance void [System]System.CodeDom.CodeMemberProperty::set_Type(class [System]System.CodeDom.CodeTypeReference)
0x944b8  ldloc.s  0xA
0x944ba  ldloc.s  9
0x944bc  ldarg.2
0x944bd  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x944c2  call     string [mscorlib]System.String::Concat(string, string)
0x944c7  callvirt instance void [System]System.CodeDom.CodeTypeMember::set_Name(string)
0x944cc  ldloc.s  0xA
0x944ce  ldc.i4   0x6000
0x944d3  callvirt instance void [System]System.CodeDom.CodeTypeMember::set_Attributes(valuetype [System]System.CodeDom.MemberAttributes)
0x944d8  ldloc.s  7
0x944da  brfalse.s loc_944ED
0x944dc  ldloc.s  0xA
0x944de  dup
0x944df  callvirt instance valuetype [System]System.CodeDom.MemberAttributes [System]System.CodeDom.CodeTypeMember::get_Attributes()
0x944e4  ldc.i4.4
0x944e5  or
0x944e6  callvirt instance void [System]System.CodeDom.CodeTypeMember::set_Attributes(valuetype [System]System.CodeDom.MemberAttributes)
0x944eb  br.s     loc_94501
0x944ed  ldloc.s  8
0x944ef  brfalse.s loc_94501
0x944f1  ldloc.s  0xA
0x944f3  dup
0x944f4  callvirt instance valuetype [System]System.CodeDom.MemberAttributes [System]System.CodeDom.CodeTypeMember::get_Attributes()
0x944f9  ldc.i4.s 0x10
0x944fb  or
0x944fc  callvirt instance void [System]System.CodeDom.CodeTypeMember::set_Attributes(valuetype [System]System.CodeDom.MemberAttributes)
0x94501  ldc.i4.0
0x94502  stloc.s  0xB
0x94504  ldarg.0
0x94505  ldarg.2
0x94506  ldloc.3
0x94507  call     instance bool System.Windows.Forms.Design.AxWrapperGen::IsPropertyBrowsable(class [mscorlib]System.Reflection.PropertyInfo pinfo, valuetype ComAliasEnum alias)
0x9450c  stloc.s  0xC
0x9450e  ldarg.0
0x9450f  ldarg.2
0x94510  ldloca.s 0xB
0x94512  call     instance bool System.Windows.Forms.Design.AxWrapperGen::IsPropertyBindable(class [mscorlib]System.Reflection.PropertyInfo pinfo, [out] bool& isDefaultBind)
0x94517  stloc.s  0xD
0x94519  ldloc.s  0xC
0x9451b  brfalse.s loc_94521
0x9451d  ldloc.3
0x9451e  ldc.i4.4
0x9451f  bne.un.s loc_94543
0x94521  ldc.i4.3
0x94522  newarr   [System]System.CodeDom.CodeAttributeDeclaration
0x94527  dup
0x94528  ldc.i4.0
0x94529  ldsfld   class [System]System.CodeDom.CodeAttributeDeclaration System.Windows.Forms.Design.AxWrapperGen::nobrowse
0x9452e  stelem.ref
0x9452f  dup
0x94530  ldc.i4.1
0x94531  ldsfld   class [System]System.CodeDom.CodeAttributeDeclaration System.Windows.Forms.Design.AxWrapperGen::nopersist
0x94536  stelem.ref
0x94537  dup
0x94538  ldc.i4.2
0x94539  ldloc.1
0x9453a  stelem.ref
0x9453b  newobj   instance void [System]System.CodeDom.CodeAttributeDeclarationCollection::.ctor(class [System]System.CodeDom.CodeAttributeDeclaration[])
0x94540  stloc.0
0x94541  br.s     loc_9459A
0x94543  ldloc.s  5
0x94545  brfalse.s loc_94559
0x94547  ldc.i4.1
0x94548  newarr   [System]System.CodeDom.CodeAttributeDeclaration
0x9454d  dup
0x9454e  ldc.i4.0
0x9454f  ldloc.1
0x94550  stelem.ref
0x94551  newobj   instance void [System]System.CodeDom.CodeAttributeDeclarationCollection::.ctor(class [System]System.CodeDom.CodeAttributeDeclaration[])
0x94556  stloc.0
0x94557  br.s     loc_9459A
0x94559  ldloc.s  7
0x9455b  ldloc.s  8
0x9455d  or
0x9455e  brfalse.s loc_94582
0x94560  ldc.i4.3
0x94561  newarr   [System]System.CodeDom.CodeAttributeDeclaration
0x94566  dup
0x94567  ldc.i4.0
0x94568  ldsfld   class [System]System.CodeDom.CodeAttributeDeclaration System.Windows.Forms.Design.AxWrapperGen::browse
0x9456d  stelem.ref
0x9456e  dup
0x9456f  ldc.i4.1
0x94570  ldsfld   class [System]System.CodeDom.CodeAttributeDeclaration System.Windows.Forms.Design.AxWrapperGen::nopersist
0x94575  stelem.ref
0x94576  dup
0x94577  ldc.i4.2
0x94578  ldloc.1
0x94579  stelem.ref
0x9457a  newobj   instance void [System]System.CodeDom.CodeAttributeDeclarationCollection::.ctor(class [System]System.CodeDom.CodeAttributeDeclaration[])
0x9457f  stloc.0
0x94580  br.s     loc_9459A
0x94582  ldc.i4.2
0x94583  newarr   [System]System.CodeDom.CodeAttributeDeclaration
0x94588  dup
0x94589  ldc.i4.0
0x9458a  ldsfld   class [System]System.CodeDom.CodeAttributeDeclaration System.Windows.Forms.Design.AxWrapperGen::nopersist
0x9458f  stelem.ref
0x94590  dup
0x94591  ldc.i4.1
0x94592  ldloc.1
  ... truncated ...
```
