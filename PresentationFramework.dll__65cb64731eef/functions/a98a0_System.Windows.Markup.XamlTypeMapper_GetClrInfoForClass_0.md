# System.Windows.Markup.XamlTypeMapper::GetClrInfoForClass_0

- ea: `0xa98a0`
- end: `0xa9d41`
- name: `System.Windows.Markup.XamlTypeMapper::GetClrInfoForClass_0`
- size: `1185`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0xa9880`

## callees

- `0x8aee0`
- `0x99990`
- `0x99ac0`
- `0x99ae0`
- `0xa4f70`
- `0xa8b00`
- `0xa9460`
- `0xa9830`
- `0xa98a0`
- `0xaa040`
- `0xaa580`
- `0xab280`
- `0xab2a0`
- `0xab300`

## string_xrefs

- `0xa99af`: `ParserEventDelegateTypeNotAccessible`
- `0xa9c13`: `ParserEventDelegateTypeNotAccessible`

## pseudocode

```c

```

## disassembly

```asm
0xa98a0  ldc.i4.0
0xa98a1  stloc.0
0xa98a2  ldnull
0xa98a3  stloc.1
0xa98a4  ldc.i4.s 0x10
0xa98a6  stloc.2
0xa98a7  ldarg.s  7
0xa98a9  ldnull
0xa98aa  stind.ref
0xa98ab  ldnull
0xa98ac  stloc.3
0xa98ad  ldarg.s  5
0xa98af  brfalse  loc_A9B2B
0xa98b4  ldarg.0
0xa98b5  ldarg.3
0xa98b6  ldarg.s  5
0xa98b8  call     instance class System.Windows.Markup.TypeAndSerializer System.Windows.Markup.XamlTypeMapper::GetTypeOnly(string xmlNamespace, string localName)
0xa98bd  stloc.s  4
0xa98bf  ldloc.s  4
0xa98c1  brfalse  loc_A9D31
0xa98c6  ldloc.s  4
0xa98c8  ldfld    class [mscorlib]System.Type System.Windows.Markup.TypeAndSerializer::ObjectType
0xa98cd  ldnull
0xa98ce  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xa98d3  brfalse  loc_A9D31
0xa98d8  ldloc.s  4
0xa98da  ldfld    class [mscorlib]System.Type System.Windows.Markup.TypeAndSerializer::ObjectType
0xa98df  stloc.s  6
0xa98e1  ldarg.0
0xa98e2  ldloc.s  6
0xa98e4  ldarg.s  4
0xa98e6  ldc.i4.0
0xa98e7  ldloca.s 5
0xa98e9  call     instance class [mscorlib]System.Reflection.MemberInfo System.Windows.Markup.XamlTypeMapper::GetCachedMemberInfo(class [mscorlib]System.Type owner, string propName, bool onlyPropInfo, [out] class System.Windows.Markup.BamlAttributeInfoRecord& infoRecord)
0xa98ee  stloc.1
0xa98ef  ldloc.1
0xa98f0  ldnull
0xa98f1  call     bool [mscorlib]System.Reflection.MemberInfo::op_Equality(class [mscorlib]System.Reflection.MemberInfo, class [mscorlib]System.Reflection.MemberInfo)
0xa98f6  brfalse  loc_A9D31
0xa98fb  ldarg.1
0xa98fc  brfalse  loc_A9A11
0xa9901  ldloc.s  6
0xa9903  ldstr    aAdd_0// "Add"
0xa9908  ldarg.s  4
0xa990a  ldstr    aHandler_0// "Handler"
0xa990f  call     string [mscorlib]System.String::Concat(string, string, string)
0xa9914  ldloc.2
0xa9915  ldc.i4.8
0xa9916  or
0xa9917  ldc.i4.s 0x40
0xa9919  or
0xa991a  callvirt instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags)
0xa991f  stloc.1
0xa9920  ldloc.1
0xa9921  ldnull
0xa9922  call     bool [mscorlib]System.Reflection.MemberInfo::op_Inequality(class [mscorlib]System.Reflection.MemberInfo, class [mscorlib]System.Reflection.MemberInfo)
0xa9927  brfalse.s loc_A9970
0xa9929  ldloc.1
0xa992a  isinst   [mscorlib]System.Reflection.MethodInfo
0xa992f  stloc.s  7
0xa9931  ldloc.s  7
0xa9933  ldnull
0xa9934  call     bool [mscorlib]System.Reflection.MethodInfo::op_Inequality(class [mscorlib]System.Reflection.MethodInfo, class [mscorlib]System.Reflection.MethodInfo)
0xa9939  brfalse.s loc_A9970
0xa993b  ldloc.s  7
0xa993d  callvirt instance class [mscorlib]System.Reflection.ParameterInfo[] [mscorlib]System.Reflection.MethodBase::GetParameters()
0xa9942  stloc.3
0xa9943  call     class System.Windows.Markup.TypeIndexer System.Windows.Markup.KnownTypes::get_Types()
0xa9948  ldc.i4   0x87
0xa994d  callvirt instance class [mscorlib]System.Type System.Windows.Markup.TypeIndexer::get_Item(int32 index)
0xa9952  stloc.s  8
0xa9954  ldloc.3
0xa9955  brfalse.s loc_A996E
0xa9957  ldloc.3
0xa9958  ldlen
0xa9959  conv.i4
0xa995a  ldc.i4.2
0xa995b  bne.un.s loc_A996E
0xa995d  ldloc.s  8
0xa995f  ldloc.3
0xa9960  ldc.i4.0
0xa9961  ldelem.ref
0xa9962  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.ParameterInfo::get_ParameterType()
0xa9967  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0xa996c  brtrue.s loc_A9970
0xa996e  ldnull
0xa996f  stloc.1
0xa9970  ldloc.1
0xa9971  ldnull
0xa9972  call     bool [mscorlib]System.Reflection.MemberInfo::op_Equality(class [mscorlib]System.Reflection.MemberInfo, class [mscorlib]System.Reflection.MemberInfo)
0xa9977  brfalse  loc_A9D31
0xa997c  ldloc.s  6
0xa997e  ldarg.s  4
0xa9980  ldloc.2
0xa9981  ldc.i4.4
0xa9982  or
0xa9983  ldc.i4.s 0x40
0xa9985  or
0xa9986  callvirt instance class [mscorlib]System.Reflection.EventInfo [mscorlib]System.Type::GetEvent(string, valuetype [mscorlib]System.Reflection.BindingFlags)
0xa998b  stloc.1
0xa998c  ldloc.1
0xa998d  ldnull
0xa998e  call     bool [mscorlib]System.Reflection.MemberInfo::op_Inequality(class [mscorlib]System.Reflection.MemberInfo, class [mscorlib]System.Reflection.MemberInfo)
0xa9993  brfalse  loc_A9D31
0xa9998  ldloc.1
0xa9999  isinst   [mscorlib]System.Reflection.EventInfo
0xa999e  stloc.s  9
0xa99a0  ldloc.s  9
0xa99a2  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.EventInfo::get_EventHandlerType()
0xa99a7  call     bool [WindowsBase]System.Windows.Markup.ReflectionHelper::IsPublicType(class [mscorlib]System.Type)
0xa99ac  brtrue.s loc_A99D8
0xa99ae  ldarg.0
0xa99af  ldstr    aParsereventdel// "ParserEventDelegateTypeNotAccessible"
0xa99b4  ldloc.s  9
0xa99b6  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.EventInfo::get_EventHandlerType()
0xa99bb  callvirt instance string [mscorlib]System.Type::get_FullName()
0xa99c0  ldloc.s  6
0xa99c2  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0xa99c7  ldstr    asc_28A756// "."
0xa99cc  ldarg.s  4
0xa99ce  call     string [mscorlib]System.String::Concat(string, string, string)
0xa99d3  call     instance void System.Windows.Markup.XamlTypeMapper::ThrowException(string id, string parameter1, string parameter2)
0xa99d8  ldloc.s  9
0xa99da  call     bool System.Windows.Markup.XamlTypeMapper::IsPublicEvent(class [mscorlib]System.Reflection.EventInfo ei)
0xa99df  brtrue   loc_A9D31
0xa99e4  ldarg.0
0xa99e5  ldstr    aParsercantseta// "ParserCantSetAttribute"
0xa99ea  ldstr    aEvent// "event"
0xa99ef  ldloc.s  6
0xa99f1  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0xa99f6  ldstr    asc_28A756// "."
0xa99fb  ldarg.s  4
0xa99fd  call     string [mscorlib]System.String::Concat(string, string, string)
0xa9a02  ldstr    aAdd// "add"
0xa9a07  call     instance void System.Windows.Markup.XamlTypeMapper::ThrowException(string id, string parameter1, string parameter2, string parameter3)
0xa9a0c  br       loc_A9D31
0xa9a11  ldloc.s  6
0xa9a13  ldstr    aSet_0// "Set"
0xa9a18  ldarg.s  4
0xa9a1a  call     string [mscorlib]System.String::Concat(string, string)
0xa9a1f  ldloc.2
0xa9a20  ldc.i4.8
0xa9a21  or
0xa9a22  ldc.i4.s 0x40
0xa9a24  or
0xa9a25  callvirt instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags)
0xa9a2a  stloc.1
0xa9a2b  ldloc.1
0xa9a2c  ldnull
0xa9a2d  call     bool [mscorlib]System.Reflection.MemberInfo::op_Inequality(class [mscorlib]System.Reflection.MemberInfo, class [mscorlib]System.Reflection.MemberInfo)
0xa9a32  brfalse.s loc_A9A46
0xa9a34  ldloc.1
0xa9a35  castclass [mscorlib]System.Reflection.MethodInfo
0xa9a3a  callvirt instance class [mscorlib]System.Reflection.ParameterInfo[] [mscorlib]System.Reflection.MethodBase::GetParameters()
0xa9a3f  ldlen
0xa9a40  conv.i4
0xa9a41  ldc.i4.2
0xa9a42  beq.s    loc_A9A46
0xa9a44  ldnull
0xa9a45  stloc.1
0xa9a46  ldloc.1
0xa9a47  ldnull
0xa9a48  call     bool [mscorlib]System.Reflection.MemberInfo::op_Equality(class [mscorlib]System.Reflection.MemberInfo, class [mscorlib]System.Reflection.MemberInfo)
0xa9a4d  brfalse.s loc_A9A84
0xa9a4f  ldloc.s  6
0xa9a51  ldstr    aGet// "Get"
0xa9a56  ldarg.s  4
0xa9a58  call     string [mscorlib]System.String::Concat(string, string)
0xa9a5d  ldloc.2
0xa9a5e  ldc.i4.8
0xa9a5f  or
0xa9a60  ldc.i4.s 0x40
0xa9a62  or
0xa9a63  callvirt instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags)
0xa9a68  stloc.1
0xa9a69  ldloc.1
0xa9a6a  ldnull
0xa9a6b  call     bool [mscorlib]System.Reflection.MemberInfo::op_Inequality(class [mscorlib]System.Reflection.MemberInfo, class [mscorlib]System.Reflection.MemberInfo)
0xa9a70  brfalse.s loc_A9A84
0xa9a72  ldloc.1
0xa9a73  castclass [mscorlib]System.Reflection.MethodInfo
0xa9a78  callvirt instance class [mscorlib]System.Reflection.ParameterInfo[] [mscorlib]System.Reflection.MethodBase::GetParameters()
0xa9a7d  ldlen
0xa9a7e  conv.i4
0xa9a7f  ldc.i4.1
0xa9a80  beq.s    loc_A9A84
0xa9a82  ldnull
0xa9a83  stloc.1
0xa9a84  ldloc.1
0xa9a85  ldnull
0xa9a86  call     bool [mscorlib]System.Reflection.MemberInfo::op_Equality(class [mscorlib]System.Reflection.MemberInfo, class [mscorlib]System.Reflection.MemberInfo)
0xa9a8b  brfalse.s loc_A9AEE
0xa9a8d  ldarg.0
0xa9a8e  ldarg.s  4
0xa9a90  ldloc.s  6
0xa9a92  ldarg.s  6
0xa9a94  ldc.i4.1
0xa9a95  ldloca.s 0
0xa9a97  call     instance class [mscorlib]System.Reflection.PropertyInfo System.Windows.Markup.XamlTypeMapper::PropertyInfoFromName(string localName, class [mscorlib]System.Type ownerType, bool tryInternal, bool tryPublicOnly, [out] bool& isInternal)
0xa9a9c  stloc.1
0xa9a9d  ldloc.1
0xa9a9e  ldnull
0xa9a9f  call     bool [mscorlib]System.Reflection.MemberInfo::op_Inequality(class [mscorlib]System.Reflection.MemberInfo, class [mscorlib]System.Reflection.MemberInfo)
0xa9aa4  brfalse.s loc_A9AEE
0xa9aa6  ldarg.2
0xa9aa7  ldnull
0xa9aa8  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xa9aad  brfalse.s loc_A9AEE
0xa9aaf  ldloc.s  6
0xa9ab1  ldarg.2
0xa9ab2  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0xa9ab7  brtrue.s loc_A9AEE
0xa9ab9  ldarg.0
0xa9aba  ldstr    aParserattached// "ParserAttachedPropInheritError"
0xa9abf  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xa9ac4  ldstr    a01_0// "{0}.{1}"
0xa9ac9  ldc.i4.2
0xa9aca  newarr   [mscorlib]System.Object
0xa9acf  dup
0xa9ad0  ldc.i4.0
0xa9ad1  ldloc.s  6
0xa9ad3  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0xa9ad8  stelem.ref
0xa9ad9  dup
0xa9ada  ldc.i4.1
0xa9adb  ldarg.s  4
0xa9add  stelem.ref
0xa9ade  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa9ae3  ldarg.2
0xa9ae4  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0xa9ae9  call     instance void System.Windows.Markup.XamlTypeMapper::ThrowException(string id, string parameter1, string parameter2)
0xa9aee  ldnull
0xa9aef  ldloc.1
0xa9af0  call     bool [mscorlib]System.Reflection.MemberInfo::op_Inequality(class [mscorlib]System.Reflection.MemberInfo, class [mscorlib]System.Reflection.MemberInfo)
0xa9af5  brfalse  loc_A9D31
0xa9afa  ldloc.s  5
0xa9afc  brfalse  loc_A9D31
0xa9b01  ldloc.s  5
0xa9b03  callvirt instance class [WindowsBase]System.Windows.DependencyProperty System.Windows.Markup.BamlAttributeInfoRecord::get_DP()
0xa9b08  brtrue.s loc_A9B1E
0xa9b0a  ldloc.s  5
0xa9b0c  ldarg.0
0xa9b0d  call     instance class System.Windows.Markup.BamlMapTable System.Windows.Markup.XamlTypeMapper::get_MapTable()
0xa9b12  ldloc.s  5
0xa9b14  callvirt instance class [WindowsBase]System.Windows.DependencyProperty System.Windows.Markup.BamlMapTable::GetDependencyProperty(class System.Windows.Markup.BamlAttributeInfoRecord bamlAttributeInfoRecord)
0xa9b19  callvirt instance void System.Windows.Markup.BamlAttributeInfoRecord::set_DP(class [WindowsBase]System.Windows.DependencyProperty value)
0xa9b1e  ldloc.s  5
0xa9b20  ldloc.1
0xa9b21  callvirt instance void System.Windows.Markup.BamlAttributeInfoRecord::SetPropertyMember(object propertyMember)
0xa9b26  br       loc_A9D31
0xa9b2b  ldnull
0xa9b2c  ldarg.2
0xa9b2d  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xa9b32  brfalse  loc_A9D31
0xa9b37  ldarg.2
0xa9b38  stloc.s  0xA
0xa9b3a  ldnull
0xa9b3b  ldloc.s  0xA
0xa9b3d  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xa9b42  brfalse  loc_A9D31
0xa9b47  ldarg.0
0xa9b48  ldloc.s  0xA
0xa9b4a  ldarg.s  4
0xa9b4c  ldc.i4.0
0xa9b4d  ldloca.s 0xB
0xa9b4f  call     instance class [mscorlib]System.Reflection.MemberInfo System.Windows.Markup.XamlTypeMapper::GetCachedMemberInfo(class [mscorlib]System.Type owner, string propName, bool onlyPropInfo, [out] class System.Windows.Markup.BamlAttributeInfoRecord& infoRecord)
0xa9b54  stloc.1
0xa9b55  ldloc.1
0xa9b56  ldnull
0xa9b57  call     bool [mscorlib]System.Reflection.MemberInfo::op_Equality(class [mscorlib]System.Reflection.MemberInfo, class [mscorlib]System.Reflection.MemberInfo)
0xa9b5c  brfalse  loc_A9D31
0xa9b61  ldarg.1
0xa9b62  brfalse  loc_A9C73
0xa9b67  ldloc.s  0xA
0xa9b69  ldstr    aAdd_0// "Add"
0xa9b6e  ldarg.s  4
0xa9b70  ldstr    aHandler_0// "Handler"
0xa9b75  call     string [mscorlib]System.String::Concat(string, string, string)
0xa9b7a  ldloc.2
0xa9b7b  ldc.i4.8
0xa9b7c  or
0xa9b7d  ldc.i4.s 0x40
0xa9b7f  or
0xa9b80  callvirt instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags)
0xa9b85  stloc.1
0xa9b86  ldloc.1
0xa9b87  ldnull
0xa9b88  call     bool [mscorlib]System.Reflection.MemberInfo::op_Inequality(class [mscorlib]System.Reflection.MemberInfo, class [mscorlib]System.Reflection.MemberInfo)
0xa9b8d  brfalse.s loc_A9BD6
0xa9b8f  ldloc.1
0xa9b90  isinst   [mscorlib]System.Reflection.MethodInfo
0xa9b95  stloc.s  0xC
0xa9b97  ldloc.s  0xC
0xa9b99  ldnull
0xa9b9a  call     bool [mscorlib]System.Reflection.MethodInfo::op_Inequality(class [mscorlib]System.Reflection.MethodInfo, class [mscorlib]System.Reflection.MethodInfo)
0xa9b9f  brfalse.s loc_A9BD6
0xa9ba1  ldloc.s  0xC
0xa9ba3  callvirt instance class [mscorlib]System.Reflection.ParameterInfo[] [mscorlib]System.Reflection.MethodBase::GetParameters()
0xa9ba8  stloc.3
0xa9ba9  call     class System.Windows.Markup.TypeIndexer System.Windows.Markup.KnownTypes::get_Types()
  ... truncated ...
```
