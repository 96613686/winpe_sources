# <LogicStream_CheckForStartGetCollectionFromMember>d__43::MoveNext

- ea: `0x35c10`
- end: `0x35fc0`
- name: `<LogicStream_CheckForStartGetCollectionFromMember>d__43::MoveNext`
- size: `944`
- prototype: ``
- caller_count: `0`
- callee_count: `37`
- tags: ``

## callees

- `0x2100`
- `0x8940`
- `0x89b0`
- `0xa590`
- `0xa6a0`
- `0xa6e0`
- `0xd100`
- `0xd110`
- `0xd130`
- `0xd150`
- `0xd230`
- `0xd310`
- `0xd600`
- `0xef20`
- `0xefa0`
- `0x1a790`
- `0x1a840`
- `0x22ec0`
- `0x23040`
- `0x23180`
- `0x23220`
- `0x23730`
- `0x25880`
- `0x258f0`
- `0x25900`
- `0x25970`
- `0x25a70`
- `0x25aa0`
- `0x25ad0`
- `0x25b00`
- `0x25b40`
- `0x26050`
- `0x26060`
- `0x260d0`
- `0x35bf0`
- `0x35c10`
- `0x35fc0`

## pseudocode

```c

```

## disassembly

```asm
0x35c10  ldarg.0
0x35c11  ldfld    int32 <LogicStream_CheckForStartGetCollectionFromMember>d__43::<>1__state
0x35c16  stloc.1
0x35c17  ldarg.0
0x35c18  ldfld    class MS.Internal.Xaml.Parser.XamlPullParser <LogicStream_CheckForStartGetCollectionFromMember>d__43::<>4__this
0x35c1d  stloc.2
0x35c1e  ldloc.1
0x35c1f  switch   loc_35C53, loc_35D50, loc_35D93, loc_35DC6, loc_35DED, loc_35E0E, loc_35E2F, loc_35E56, loc_35F87, loc_35FAC
0x35c4c  ldc.i4.0
0x35c4d  stloc.0
0x35c4e  leave    loc_35FBE
0x35c53  ldarg.0
0x35c54  ldc.i4.m1
0x35c55  stfld    int32 <LogicStream_CheckForStartGetCollectionFromMember>d__43::<>1__state
0x35c5a  ldloc.2
0x35c5b  ldfld    class MS.Internal.Xaml.Context.XamlParserContext MS.Internal.Xaml.Parser.XamlPullParser::_context
0x35c60  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.XamlParserContext::get_CurrentType()
0x35c65  stloc.3
0x35c66  ldloc.2
0x35c67  ldfld    class MS.Internal.Xaml.Context.XamlParserContext MS.Internal.Xaml.Parser.XamlPullParser::_context
0x35c6c  callvirt instance class System.Xaml.XamlMember MS.Internal.Xaml.Context.XamlParserContext::get_CurrentMember()
0x35c71  stloc.s  4
0x35c73  ldarg.0
0x35c74  ldloc.s  4
0x35c76  callvirt instance class System.Xaml.XamlType System.Xaml.XamlMember::get_Type()
0x35c7b  stfld    class System.Xaml.XamlType <LogicStream_CheckForStartGetCollectionFromMember>d__43::<propertyType>5__2
0x35c80  ldarg.0
0x35c81  ldloc.2
0x35c82  ldfld    class MS.Internal.Xaml.Parser.XamlScanner MS.Internal.Xaml.Parser.XamlPullParser::_xamlScanner
0x35c87  callvirt instance valuetype MS.Internal.Xaml.Parser.ScannerNodeType MS.Internal.Xaml.Parser.XamlScanner::get_NodeType()
0x35c8c  ldc.i4.8
0x35c8d  beq.s    loc_35C9C
0x35c8f  ldloc.2
0x35c90  ldfld    class MS.Internal.Xaml.Parser.XamlScanner MS.Internal.Xaml.Parser.XamlPullParser::_xamlScanner
0x35c95  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Parser.XamlScanner::get_Type()
0x35c9a  br.s     loc_35CA1
0x35c9c  call     class System.Xaml.XamlType System.Xaml.XamlLanguage::get_String()
0x35ca1  stfld    class System.Xaml.XamlType <LogicStream_CheckForStartGetCollectionFromMember>d__43::<valueElementType>5__3
0x35ca6  ldarg.0
0x35ca7  ldfld    class System.Xaml.XamlType <LogicStream_CheckForStartGetCollectionFromMember>d__43::<propertyType>5__2
0x35cac  callvirt instance bool System.Xaml.XamlType::get_IsArray()
0x35cb1  brfalse  loc_35E8A
0x35cb6  ldloc.2
0x35cb7  ldfld    class MS.Internal.Xaml.Parser.XamlScanner MS.Internal.Xaml.Parser.XamlPullParser::_xamlScanner
0x35cbc  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Parser.XamlScanner::get_Type()
0x35cc1  ldloc.2
0x35cc2  call     instance class System.Xaml.XamlType MS.Internal.Xaml.Parser.XamlPullParser::get_ArrayExtensionType()
0x35cc7  call     bool System.Xaml.XamlType::op_Inequality(class System.Xaml.XamlType xamlType1, class System.Xaml.XamlType xamlType2)
0x35ccc  brfalse  loc_35E8A
0x35cd1  ldnull
0x35cd2  stloc.s  5
0x35cd4  ldarg.0
0x35cd5  ldfld    class System.Xaml.XamlType <LogicStream_CheckForStartGetCollectionFromMember>d__43::<propertyType>5__2
0x35cda  callvirt instance class System.Xaml.XamlType System.Xaml.XamlType::get_ItemType()
0x35cdf  newobj   instance void System.Xaml.Schema.XamlTypeName::.ctor(class System.Xaml.XamlType xamlType)
0x35ce4  stloc.s  6
0x35ce6  ldloca.s 5
0x35ce8  ldloc.2
0x35ce9  ldfld    class MS.Internal.Xaml.Context.XamlParserContext MS.Internal.Xaml.Parser.XamlPullParser::_context
0x35cee  dup
0x35cef  ldvirtftn instance string MS.Internal.Xaml.XamlContext::FindNamespaceByPrefix(string prefix)
0x35cf5  newobj   instance void class [mscorlib]System.Func`2<string, string>::.ctor(object, native int)
0x35cfa  newobj   instance void MS.Internal.Xaml.Parser.NamespacePrefixLookup::.ctor([out] class [mscorlib]System.Collections.Generic.IEnumerable`1<class System.Xaml.NamespaceDeclaration>& newNamespaces, class [mscorlib]System.Func`2<string, string> nsResolver)
0x35cff  stloc.s  7
0x35d01  ldarg.0
0x35d02  ldloc.s  6
0x35d04  ldloc.s  7
0x35d06  callvirt instance string System.Xaml.Schema.XamlTypeName::ToString(class System.Xaml.INamespacePrefixLookup prefixLookup)
0x35d0b  stfld    string <LogicStream_CheckForStartGetCollectionFromMember>d__43::<typeNameString>5__4
0x35d10  ldarg.0
0x35d11  ldloc.s  5
0x35d13  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class System.Xaml.NamespaceDeclaration>::GetEnumerator()
0x35d18  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class System.Xaml.NamespaceDeclaration> <LogicStream_CheckForStartGetCollectionFromMember>d__43::<>7__wrap4
0x35d1d  ldarg.0
0x35d1e  ldc.i4.s 0xFD
0x35d20  stfld    int32 <LogicStream_CheckForStartGetCollectionFromMember>d__43::<>1__state
0x35d25  br.s     loc_35D58
0x35d27  ldarg.0
0x35d28  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class System.Xaml.NamespaceDeclaration> <LogicStream_CheckForStartGetCollectionFromMember>d__43::<>7__wrap4
0x35d2d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class System.Xaml.NamespaceDeclaration>::get_Current()
0x35d32  stloc.s  8
0x35d34  ldarg.0
0x35d35  ldc.i4.7
0x35d36  ldloc.s  8
0x35d38  newobj   instance void System.Xaml.XamlNode::.ctor(valuetype System.Xaml.XamlNodeType nodeType, object data)
0x35d3d  stfld    valuetype System.Xaml.XamlNode <LogicStream_CheckForStartGetCollectionFromMember>d__43::<>2__current
0x35d42  ldarg.0
0x35d43  ldc.i4.1
0x35d44  stfld    int32 <LogicStream_CheckForStartGetCollectionFromMember>d__43::<>1__state
0x35d49  ldc.i4.1
0x35d4a  stloc.0
0x35d4b  leave    loc_35FBE
0x35d50  ldarg.0
0x35d51  ldc.i4.s 0xFD
0x35d53  stfld    int32 <LogicStream_CheckForStartGetCollectionFromMember>d__43::<>1__state
0x35d58  ldarg.0
0x35d59  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class System.Xaml.NamespaceDeclaration> <LogicStream_CheckForStartGetCollectionFromMember>d__43::<>7__wrap4
0x35d5e  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x35d63  brtrue.s loc_35D27
0x35d65  ldarg.0
0x35d66  call     instance void <LogicStream_CheckForStartGetCollectionFromMember>d__43::<>m__Finally1()
0x35d6b  ldarg.0
0x35d6c  ldnull
0x35d6d  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class System.Xaml.NamespaceDeclaration> <LogicStream_CheckForStartGetCollectionFromMember>d__43::<>7__wrap4
0x35d72  ldarg.0
0x35d73  ldloc.2
0x35d74  ldloc.2
0x35d75  call     instance class System.Xaml.XamlType MS.Internal.Xaml.Parser.XamlPullParser::get_ArrayExtensionType()
0x35d7a  ldnull
0x35d7b  call     instance valuetype System.Xaml.XamlNode MS.Internal.Xaml.Parser.XamlPullParser::Logic_StartObject(class System.Xaml.XamlType xamlType, string xamlNamespace)
0x35d80  stfld    valuetype System.Xaml.XamlNode <LogicStream_CheckForStartGetCollectionFromMember>d__43::<>2__current
0x35d85  ldarg.0
0x35d86  ldc.i4.2
0x35d87  stfld    int32 <LogicStream_CheckForStartGetCollectionFromMember>d__43::<>1__state
0x35d8c  ldc.i4.1
0x35d8d  stloc.0
0x35d8e  leave    loc_35FBE
0x35d93  ldarg.0
0x35d94  ldc.i4.m1
0x35d95  stfld    int32 <LogicStream_CheckForStartGetCollectionFromMember>d__43::<>1__state
0x35d9a  ldloc.2
0x35d9b  ldfld    class MS.Internal.Xaml.Context.XamlParserContext MS.Internal.Xaml.Parser.XamlPullParser::_context
0x35da0  ldc.i4.1
0x35da1  callvirt instance void MS.Internal.Xaml.Context.XamlParserContext::set_CurrentInImplicitArray(bool value)
0x35da6  ldarg.0
0x35da7  ldloc.2
0x35da8  ldloc.2
0x35da9  call     instance class System.Xaml.XamlMember MS.Internal.Xaml.Parser.XamlPullParser::get_ArrayTypeMember()
0x35dae  call     instance valuetype System.Xaml.XamlNode MS.Internal.Xaml.Parser.XamlPullParser::Logic_StartMember(class System.Xaml.XamlMember member)
0x35db3  stfld    valuetype System.Xaml.XamlNode <LogicStream_CheckForStartGetCollectionFromMember>d__43::<>2__current
0x35db8  ldarg.0
0x35db9  ldc.i4.3
0x35dba  stfld    int32 <LogicStream_CheckForStartGetCollectionFromMember>d__43::<>1__state
0x35dbf  ldc.i4.1
0x35dc0  stloc.0
0x35dc1  leave    loc_35FBE
0x35dc6  ldarg.0
0x35dc7  ldc.i4.m1
0x35dc8  stfld    int32 <LogicStream_CheckForStartGetCollectionFromMember>d__43::<>1__state
0x35dcd  ldarg.0
0x35dce  ldc.i4.6
0x35dcf  ldarg.0
0x35dd0  ldfld    string <LogicStream_CheckForStartGetCollectionFromMember>d__43::<typeNameString>5__4
0x35dd5  newobj   instance void System.Xaml.XamlNode::.ctor(valuetype System.Xaml.XamlNodeType nodeType, object data)
0x35dda  stfld    valuetype System.Xaml.XamlNode <LogicStream_CheckForStartGetCollectionFromMember>d__43::<>2__current
0x35ddf  ldarg.0
0x35de0  ldc.i4.4
0x35de1  stfld    int32 <LogicStream_CheckForStartGetCollectionFromMember>d__43::<>1__state
0x35de6  ldc.i4.1
0x35de7  stloc.0
0x35de8  leave    loc_35FBE
0x35ded  ldarg.0
0x35dee  ldc.i4.m1
0x35def  stfld    int32 <LogicStream_CheckForStartGetCollectionFromMember>d__43::<>1__state
0x35df4  ldarg.0
0x35df5  ldloc.2
0x35df6  call     instance valuetype System.Xaml.XamlNode MS.Internal.Xaml.Parser.XamlPullParser::Logic_EndMember()
0x35dfb  stfld    valuetype System.Xaml.XamlNode <LogicStream_CheckForStartGetCollectionFromMember>d__43::<>2__current
0x35e00  ldarg.0
0x35e01  ldc.i4.5
0x35e02  stfld    int32 <LogicStream_CheckForStartGetCollectionFromMember>d__43::<>1__state
0x35e07  ldc.i4.1
0x35e08  stloc.0
0x35e09  leave    loc_35FBE
0x35e0e  ldarg.0
0x35e0f  ldc.i4.m1
0x35e10  stfld    int32 <LogicStream_CheckForStartGetCollectionFromMember>d__43::<>1__state
0x35e15  ldarg.0
0x35e16  ldloc.2
0x35e17  call     instance valuetype System.Xaml.XamlNode MS.Internal.Xaml.Parser.XamlPullParser::Logic_EndOfAttributes()
0x35e1c  stfld    valuetype System.Xaml.XamlNode <LogicStream_CheckForStartGetCollectionFromMember>d__43::<>2__current
0x35e21  ldarg.0
0x35e22  ldc.i4.6
0x35e23  stfld    int32 <LogicStream_CheckForStartGetCollectionFromMember>d__43::<>1__state
0x35e28  ldc.i4.1
0x35e29  stloc.0
0x35e2a  leave    loc_35FBE
0x35e2f  ldarg.0
0x35e30  ldc.i4.m1
0x35e31  stfld    int32 <LogicStream_CheckForStartGetCollectionFromMember>d__43::<>1__state
0x35e36  ldarg.0
0x35e37  ldloc.2
0x35e38  ldloc.2
0x35e39  call     instance class System.Xaml.XamlMember MS.Internal.Xaml.Parser.XamlPullParser::get_ItemsTypeMember()
0x35e3e  call     instance valuetype System.Xaml.XamlNode MS.Internal.Xaml.Parser.XamlPullParser::Logic_StartMember(class System.Xaml.XamlMember member)
0x35e43  stfld    valuetype System.Xaml.XamlNode <LogicStream_CheckForStartGetCollectionFromMember>d__43::<>2__current
0x35e48  ldarg.0
0x35e49  ldc.i4.7
0x35e4a  stfld    int32 <LogicStream_CheckForStartGetCollectionFromMember>d__43::<>1__state
0x35e4f  ldc.i4.1
0x35e50  stloc.0
0x35e51  leave    loc_35FBE
0x35e56  ldarg.0
0x35e57  ldc.i4.m1
0x35e58  stfld    int32 <LogicStream_CheckForStartGetCollectionFromMember>d__43::<>1__state
0x35e5d  ldloc.2
0x35e5e  ldfld    class MS.Internal.Xaml.Context.XamlParserContext MS.Internal.Xaml.Parser.XamlPullParser::_context
0x35e63  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.XamlParserContext::get_CurrentType()
0x35e68  stloc.3
0x35e69  ldloc.2
0x35e6a  ldfld    class MS.Internal.Xaml.Context.XamlParserContext MS.Internal.Xaml.Parser.XamlPullParser::_context
0x35e6f  callvirt instance class System.Xaml.XamlMember MS.Internal.Xaml.Context.XamlParserContext::get_CurrentMember()
0x35e74  stloc.s  4
0x35e76  ldarg.0
0x35e77  ldloc.s  4
0x35e79  callvirt instance class System.Xaml.XamlType System.Xaml.XamlMember::get_Type()
0x35e7e  stfld    class System.Xaml.XamlType <LogicStream_CheckForStartGetCollectionFromMember>d__43::<propertyType>5__2
0x35e83  ldarg.0
0x35e84  ldnull
0x35e85  stfld    string <LogicStream_CheckForStartGetCollectionFromMember>d__43::<typeNameString>5__4
0x35e8a  ldloc.s  4
0x35e8c  callvirt instance bool System.Xaml.XamlMember::get_IsDirective()
0x35e91  brtrue   loc_35FB3
0x35e96  ldarg.0
0x35e97  ldfld    class System.Xaml.XamlType <LogicStream_CheckForStartGetCollectionFromMember>d__43::<propertyType>5__2
0x35e9c  callvirt instance bool System.Xaml.XamlType::get_IsCollection()
0x35ea1  brtrue.s loc_35EB3
0x35ea3  ldarg.0
0x35ea4  ldfld    class System.Xaml.XamlType <LogicStream_CheckForStartGetCollectionFromMember>d__43::<propertyType>5__2
0x35ea9  callvirt instance bool System.Xaml.XamlType::get_IsDictionary()
0x35eae  brfalse  loc_35FB3
0x35eb3  ldc.i4.0
0x35eb4  stloc.s  9
0x35eb6  ldloc.s  4
0x35eb8  callvirt instance bool System.Xaml.XamlMember::get_IsReadOnly()
0x35ebd  brtrue.s loc_35ECC
0x35ebf  ldloc.2
0x35ec0  ldfld    class MS.Internal.Xaml.Context.XamlParserContext MS.Internal.Xaml.Parser.XamlPullParser::_context
0x35ec5  callvirt instance bool MS.Internal.Xaml.Context.XamlParserContext::CurrentMemberIsWriteVisible()
0x35eca  brtrue.s loc_35ED4
0x35ecc  ldc.i4.1
0x35ecd  stloc.s  9
0x35ecf  br       loc_35F66
0x35ed4  ldarg.0
0x35ed5  ldfld    class System.Xaml.XamlType <LogicStream_CheckForStartGetCollectionFromMember>d__43::<propertyType>5__2
0x35eda  callvirt instance class System.Xaml.Schema.XamlValueConverter`1<class [System]System.ComponentModel.TypeConverter> System.Xaml.XamlType::get_TypeConverter()
0x35edf  ldnull
0x35ee0  call     bool class System.Xaml.Schema.XamlValueConverter`1<class [System]System.ComponentModel.TypeConverter>::op_Inequality(class System.Xaml.Schema.XamlValueConverter`1<var<u1>>, !!T0)
0x35ee5  brfalse.s loc_35F03
0x35ee7  ldloc.s  4
0x35ee9  callvirt instance bool System.Xaml.XamlMember::get_IsReadOnly()
0x35eee  brtrue.s loc_35F03
0x35ef0  ldloc.2
0x35ef1  ldfld    class MS.Internal.Xaml.Parser.XamlScanner MS.Internal.Xaml.Parser.XamlPullParser::_xamlScanner
0x35ef6  callvirt instance valuetype MS.Internal.Xaml.Parser.ScannerNodeType MS.Internal.Xaml.Parser.XamlScanner::get_NodeType()
0x35efb  ldc.i4.8
0x35efc  bne.un.s loc_35F03
0x35efe  ldc.i4.0
0x35eff  stloc.s  9
0x35f01  br.s     loc_35F66
0x35f03  ldarg.0
0x35f04  ldfld    class System.Xaml.XamlType <LogicStream_CheckForStartGetCollectionFromMember>d__43::<valueElementType>5__3
0x35f09  ldnull
0x35f0a  call     bool System.Xaml.XamlType::op_Equality(class System.Xaml.XamlType xamlType1, class System.Xaml.XamlType xamlType2)
0x35f0f  brtrue.s loc_35F24
0x35f11  ldarg.0
0x35f12  ldfld    class System.Xaml.XamlType <LogicStream_CheckForStartGetCollectionFromMember>d__43::<valueElementType>5__3
0x35f17  ldarg.0
0x35f18  ldfld    class System.Xaml.XamlType <LogicStream_CheckForStartGetCollectionFromMember>d__43::<propertyType>5__2
0x35f1d  callvirt instance bool System.Xaml.XamlType::CanAssignTo(class System.Xaml.XamlType xamlType)
0x35f22  brtrue.s loc_35F66
0x35f24  ldarg.0
0x35f25  ldfld    class System.Xaml.XamlType <LogicStream_CheckForStartGetCollectionFromMember>d__43::<valueElementType>5__3
0x35f2a  ldnull
0x35f2b  call     bool System.Xaml.XamlType::op_Inequality(class System.Xaml.XamlType xamlType1, class System.Xaml.XamlType xamlType2)
0x35f30  brfalse.s loc_35F66
0x35f32  ldarg.0
0x35f33  ldfld    class System.Xaml.XamlType <LogicStream_CheckForStartGetCollectionFromMember>d__43::<valueElementType>5__3
0x35f38  callvirt instance bool System.Xaml.XamlType::get_IsMarkupExtension()
0x35f3d  brfalse.s loc_35F4C
0x35f3f  ldloc.2
0x35f40  ldfld    class MS.Internal.Xaml.Parser.XamlScanner MS.Internal.Xaml.Parser.XamlPullParser::_xamlScanner
0x35f45  callvirt instance bool MS.Internal.Xaml.Parser.XamlScanner::get_HasKeyAttribute()
0x35f4a  brfalse.s loc_35F51
0x35f4c  ldc.i4.1
0x35f4d  stloc.s  9
0x35f4f  br.s     loc_35F66
0x35f51  ldarg.0
0x35f52  ldfld    class System.Xaml.XamlType <LogicStream_CheckForStartGetCollectionFromMember>d__43::<valueElementType>5__3
0x35f57  call     class System.Xaml.XamlType System.Xaml.XamlLanguage::get_Array()
0x35f5c  call     bool System.Xaml.XamlType::op_Equality(class System.Xaml.XamlType xamlType1, class System.Xaml.XamlType xamlType2)
0x35f61  brfalse.s loc_35F66
0x35f63  ldc.i4.1
0x35f64  stloc.s  9
0x35f66  ldloc.s  9
0x35f68  brfalse.s loc_35FB3
0x35f6a  ldarg.0
0x35f6b  ldloc.2
0x35f6c  ldarg.0
0x35f6d  ldfld    class System.Xaml.XamlType <LogicStream_CheckForStartGetCollectionFromMember>d__43::<propertyType>5__2
0x35f72  call     instance valuetype System.Xaml.XamlNode MS.Internal.Xaml.Parser.XamlPullParser::Logic_StartGetObjectFromMember(class System.Xaml.XamlType realType)
0x35f77  stfld    valuetype System.Xaml.XamlNode <LogicStream_CheckForStartGetCollectionFromMember>d__43::<>2__current
0x35f7c  ldarg.0
0x35f7d  ldc.i4.8
0x35f7e  stfld    int32 <LogicStream_CheckForStartGetCollectionFromMember>d__43::<>1__state
0x35f83  ldc.i4.1
0x35f84  stloc.0
0x35f85  leave.s  loc_35FBE
0x35f87  ldarg.0
0x35f88  ldc.i4.m1
  ... truncated ...
```
