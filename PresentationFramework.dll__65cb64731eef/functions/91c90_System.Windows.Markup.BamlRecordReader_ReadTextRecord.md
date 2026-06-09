# System.Windows.Markup.BamlRecordReader::ReadTextRecord

- ea: `0x91c90`
- end: `0x92017`
- name: `System.Windows.Markup.BamlRecordReader::ReadTextRecord`
- size: `903`
- prototype: ``
- caller_count: `1`
- callee_count: `34`
- tags: `broker_com_uri`

## callers

- `0x8f180`

## callees

- `0x89e10`
- `0x89e30`
- `0x8aa60`
- `0x8ece0`
- `0x91900`
- `0x919d0`
- `0x91c90`
- `0x92080`
- `0x92340`
- `0x923d0`
- `0x924f0`
- `0x925f0`
- `0x92900`
- `0x92910`
- `0x93180`
- `0x934d0`
- `0x93540`
- `0x93560`
- `0x93920`
- `0x93940`
- `0x95e60`
- `0x969a0`
- `0x969b0`
- `0x98ed0`
- `0x98f70`
- `0x99a80`
- `0x99ac0`
- `0xadcc0`
- `0xadcd0`
- `0xadce0`
- `0xadd50`
- `0xadd70`
- `0xadd80`
- `0xaddb0`

## string_xrefs

- `0x91e6b`: `ParserNoComplexMulti`
- `0x91f15`: `ParserNoComplexMulti`
- `0x91dd8`: `ParserCantCreateInstanceType`
- `0x91ee4`: `ParserCantCreateTextComplexProp`
- `0x91f5d`: `ParserCantCreateTextComplexProp`

## pseudocode

```c

```

## disassembly

```asm
0x91c90  ldarg.1
0x91c91  isinst   System.Windows.Markup.BamlTextWithIdRecord
0x91c96  stloc.0
0x91c97  ldloc.0
0x91c98  brfalse.s loc_91CB1
0x91c9a  ldloc.0
0x91c9b  ldarg.0
0x91c9c  call     instance class System.Windows.Markup.BamlMapTable System.Windows.Markup.BamlRecordReader::get_MapTable()
0x91ca1  ldloc.0
0x91ca2  callvirt instance int16 System.Windows.Markup.BamlTextWithIdRecord::get_ValueId()
0x91ca7  callvirt instance string System.Windows.Markup.BamlMapTable::GetStringFromStringId(int32 id)
0x91cac  callvirt instance void System.Windows.Markup.BamlStringValueRecord::set_Value(string value)
0x91cb1  ldarg.0
0x91cb2  call     instance class System.Windows.Markup.ReaderContextStackData System.Windows.Markup.BamlRecordReader::get_CurrentContext()
0x91cb7  brtrue.s loc_91CDA
0x91cb9  ldarg.0
0x91cba  ldnull
0x91cbb  stfld    class [System.Xaml]System.Windows.Markup.IComponentConnector System.Windows.Markup.BamlRecordReader::_componentConnector
0x91cc0  ldarg.0
0x91cc1  ldnull
0x91cc2  stfld    object System.Windows.Markup.BamlRecordReader::_rootElement
0x91cc7  ldarg.0
0x91cc8  call     instance class [mscorlib]System.Collections.ArrayList System.Windows.Markup.BamlRecordReader::get_RootList()
0x91ccd  ldarg.1
0x91cce  callvirt instance string System.Windows.Markup.BamlStringValueRecord::get_Value()
0x91cd3  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x91cd8  pop
0x91cd9  ret
0x91cda  ldc.i4.0
0x91cdb  stloc.1
0x91cdc  ldarg.1
0x91cdd  isinst   System.Windows.Markup.BamlTextWithConverterRecord
0x91ce2  stloc.2
0x91ce3  ldloc.2
0x91ce4  brfalse.s loc_91CED
0x91ce6  ldloc.2
0x91ce7  callvirt instance int16 System.Windows.Markup.BamlTextWithConverterRecord::get_ConverterTypeId()
0x91cec  stloc.1
0x91ced  ldarg.0
0x91cee  call     instance class System.Windows.Markup.ReaderContextStackData System.Windows.Markup.BamlRecordReader::get_CurrentContext()
0x91cf3  callvirt instance valuetype System.Windows.Markup.ReaderFlags System.Windows.Markup.ReaderContextStackData::get_ContextType()
0x91cf8  stloc.3
0x91cf9  ldloc.3
0x91cfa  ldc.i4   0x3000
0x91cff  bgt.un.s loc_91D21
0x91d01  ldloc.3
0x91d02  ldc.i4   0x1000
0x91d07  beq.s    loc_91D5F
0x91d09  ldloc.3
0x91d0a  ldc.i4   0x2000
0x91d0f  beq.s    loc_91D5F
0x91d11  ldloc.3
0x91d12  ldc.i4   0x3000
0x91d17  beq      loc_91F01
0x91d1c  br       loc_92006
0x91d21  ldloc.3
0x91d22  ldc.i4   0x6000
0x91d27  bgt.un.s loc_91D44
0x91d29  ldloc.3
0x91d2a  ldc.i4   0x4000
0x91d2f  beq      loc_91E57
0x91d34  ldloc.3
0x91d35  ldc.i4   0x6000
0x91d3a  beq      loc_91FBD
0x91d3f  br       loc_92006
0x91d44  ldloc.3
0x91d45  ldc.i4   0x8000
0x91d4a  beq      loc_91F7E
0x91d4f  ldloc.3
0x91d50  ldc.i4   0xA000
0x91d55  beq      loc_91FF9
0x91d5a  br       loc_92006
0x91d5f  ldarg.0
0x91d60  call     instance class System.Windows.Markup.ReaderContextStackData System.Windows.Markup.BamlRecordReader::get_CurrentContext()
0x91d65  callvirt instance bool System.Windows.Markup.ReaderContextStackData::get_CreateUsingTypeConverter()
0x91d6a  brfalse.s loc_91DCB
0x91d6c  ldarg.0
0x91d6d  ldarg.0
0x91d6e  call     instance class System.Windows.Markup.ReaderContextStackData System.Windows.Markup.BamlRecordReader::get_CurrentContext()
0x91d73  callvirt instance class [mscorlib]System.Type System.Windows.Markup.ReaderContextStackData::get_ExpectedType()
0x91d78  ldarg.1
0x91d79  callvirt instance string System.Windows.Markup.BamlStringValueRecord::get_Value()
0x91d7e  ldloc.1
0x91d7f  call     instance object System.Windows.Markup.BamlRecordReader::GetObjectFromString(class [mscorlib]System.Type type, string s, int16 converterTypeId)
0x91d84  stloc.s  4
0x91d86  ldsfld   object [WindowsBase]System.Windows.DependencyProperty::UnsetValue
0x91d8b  ldloc.s  4
0x91d8d  beq.s    loc_91DA9
0x91d8f  ldarg.0
0x91d90  call     instance class System.Windows.Markup.ReaderContextStackData System.Windows.Markup.BamlRecordReader::get_CurrentContext()
0x91d95  ldloc.s  4
0x91d97  callvirt instance void System.Windows.Markup.ReaderContextStackData::set_ObjectData(object value)
0x91d9c  ldarg.0
0x91d9d  call     instance class System.Windows.Markup.ReaderContextStackData System.Windows.Markup.BamlRecordReader::get_CurrentContext()
0x91da2  ldnull
0x91da3  callvirt instance void System.Windows.Markup.ReaderContextStackData::set_ExpectedType(class [mscorlib]System.Type value)
0x91da8  ret
0x91da9  ldarg.0
0x91daa  ldstr    aParsercannotco// "ParserCannotConvertString"
0x91daf  ldarg.1
0x91db0  callvirt instance string System.Windows.Markup.BamlStringValueRecord::get_Value()
0x91db5  ldarg.0
0x91db6  call     instance class System.Windows.Markup.ReaderContextStackData System.Windows.Markup.BamlRecordReader::get_CurrentContext()
0x91dbb  callvirt instance class [mscorlib]System.Type System.Windows.Markup.ReaderContextStackData::get_ExpectedType()
0x91dc0  callvirt instance string [mscorlib]System.Type::get_FullName()
0x91dc5  call     instance void System.Windows.Markup.BamlRecordReader::ThrowException(string id, string parameter1, string parameter2)
0x91dca  ret
0x91dcb  ldarg.0
0x91dcc  call     instance object System.Windows.Markup.BamlRecordReader::GetCurrentObjectData()
0x91dd1  stloc.s  5
0x91dd3  ldloc.s  5
0x91dd5  brtrue.s loc_91DF2
0x91dd7  ldarg.0
0x91dd8  ldstr    aParsercantcrea_0// "ParserCantCreateInstanceType"
0x91ddd  ldarg.0
0x91dde  call     instance class System.Windows.Markup.ReaderContextStackData System.Windows.Markup.BamlRecordReader::get_CurrentContext()
0x91de3  callvirt instance class [mscorlib]System.Type System.Windows.Markup.ReaderContextStackData::get_ExpectedType()
0x91de8  callvirt instance string [mscorlib]System.Type::get_FullName()
0x91ded  call     instance void System.Windows.Markup.BamlRecordReader::ThrowException(string id, string parameter)
0x91df2  ldarg.0
0x91df3  ldarg.0
0x91df4  call     instance class System.Windows.Markup.ReaderContextStackData System.Windows.Markup.BamlRecordReader::get_CurrentContext()
0x91df9  call     instance class [PresentationCore]System.Windows.Markup.IAddChild System.Windows.Markup.BamlRecordReader::GetIAddChildFromContext(class System.Windows.Markup.ReaderContextStackData context)
0x91dfe  stloc.s  6
0x91e00  ldloc.s  6
0x91e02  brfalse.s loc_91E12
0x91e04  ldloc.s  6
0x91e06  ldarg.1
0x91e07  callvirt instance string System.Windows.Markup.BamlStringValueRecord::get_Value()
0x91e0c  callvirt instance void [PresentationCore]System.Windows.Markup.IAddChild::AddText(string)
0x91e11  ret
0x91e12  ldarg.0
0x91e13  call     instance class System.Windows.Markup.ReaderContextStackData System.Windows.Markup.BamlRecordReader::get_CurrentContext()
0x91e18  callvirt instance object System.Windows.Markup.ReaderContextStackData::get_ContentProperty()
0x91e1d  brfalse.s loc_91E39
0x91e1f  ldarg.0
0x91e20  ldloc.s  5
0x91e22  ldarg.0
0x91e23  call     instance class System.Windows.Markup.ReaderContextStackData System.Windows.Markup.BamlRecordReader::get_CurrentContext()
0x91e28  callvirt instance object System.Windows.Markup.ReaderContextStackData::get_ContentProperty()
0x91e2d  ldarg.1
0x91e2e  callvirt instance string System.Windows.Markup.BamlStringValueRecord::get_Value()
0x91e33  call     instance void System.Windows.Markup.BamlRecordReader::AddToContentProperty(object container, object contentProperty, object value)
0x91e38  ret
0x91e39  ldarg.0
0x91e3a  ldstr    aParseriaddchil// "ParserIAddChildText"
0x91e3f  ldloc.s  5
0x91e41  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x91e46  callvirt instance string [mscorlib]System.Type::get_FullName()
0x91e4b  ldarg.1
0x91e4c  callvirt instance string System.Windows.Markup.BamlStringValueRecord::get_Value()
0x91e51  call     instance void System.Windows.Markup.BamlRecordReader::ThrowException(string id, string parameter1, string parameter2)
0x91e56  ret
0x91e57  ldnull
0x91e58  ldarg.0
0x91e59  call     instance class System.Windows.Markup.ReaderContextStackData System.Windows.Markup.BamlRecordReader::get_CurrentContext()
0x91e5e  callvirt instance class [mscorlib]System.Type System.Windows.Markup.ReaderContextStackData::get_ExpectedType()
0x91e63  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x91e68  brfalse.s loc_91E86
0x91e6a  ldarg.0
0x91e6b  ldstr    aParsernocomple// "ParserNoComplexMulti"
0x91e70  ldarg.0
0x91e71  ldarg.0
0x91e72  call     instance class System.Windows.Markup.ReaderContextStackData System.Windows.Markup.BamlRecordReader::get_CurrentContext()
0x91e77  callvirt instance object System.Windows.Markup.ReaderContextStackData::get_ObjectData()
0x91e7c  call     instance string System.Windows.Markup.BamlRecordReader::GetPropNameFrom(object PiOrAttribInfo)
0x91e81  call     instance void System.Windows.Markup.BamlRecordReader::ThrowException(string id, string parameter)
0x91e86  ldarg.0
0x91e87  call     instance class System.Windows.Markup.ReaderContextStackData System.Windows.Markup.BamlRecordReader::get_CurrentContext()
0x91e8c  callvirt instance object System.Windows.Markup.ReaderContextStackData::get_ObjectData()
0x91e91  isinst   System.Windows.Markup.BamlAttributeInfoRecord
0x91e96  stloc.s  7
0x91e98  ldarg.0
0x91e99  ldarg.0
0x91e9a  call     instance object System.Windows.Markup.BamlRecordReader::GetParentObjectData()
0x91e9f  castclass [WindowsBase]System.Windows.DependencyObject
0x91ea4  ldloc.s  7
0x91ea6  callvirt instance class [WindowsBase]System.Windows.DependencyProperty System.Windows.Markup.BamlAttributeInfoRecord::get_DP()
0x91eab  callvirt instance class [mscorlib]System.Type [WindowsBase]System.Windows.DependencyProperty::get_PropertyType()
0x91eb0  ldloc.s  7
0x91eb2  callvirt instance class [WindowsBase]System.Windows.DependencyProperty System.Windows.Markup.BamlAttributeInfoRecord::get_DP()
0x91eb7  callvirt instance string [WindowsBase]System.Windows.DependencyProperty::get_Name()
0x91ebc  ldloc.s  7
0x91ebe  callvirt instance class [WindowsBase]System.Windows.DependencyProperty System.Windows.Markup.BamlAttributeInfoRecord::get_DP()
0x91ec3  ldarg.1
0x91ec4  callvirt instance string System.Windows.Markup.BamlStringValueRecord::get_Value()
0x91ec9  ldloc.1
0x91eca  call     instance object System.Windows.Markup.BamlRecordReader::ParseProperty(object element, class [mscorlib]System.Type propertyType, string propertyName, object dpOrPi, string attribValue, int16 converterTypeId)
0x91ecf  stloc.s  8
0x91ed1  ldsfld   object [WindowsBase]System.Windows.DependencyProperty::UnsetValue
0x91ed6  ldloc.s  8
0x91ed8  beq.s    loc_91EE3
0x91eda  ldarg.0
0x91edb  ldloc.s  8
0x91edd  call     instance void System.Windows.Markup.BamlRecordReader::SetDependencyComplexProperty(object o)
0x91ee2  ret
0x91ee3  ldarg.0
0x91ee4  ldstr    aParsercantcrea_1// "ParserCantCreateTextComplexProp"
0x91ee9  ldloc.s  7
0x91eeb  callvirt instance class [mscorlib]System.Type System.Windows.Markup.BamlAttributeInfoRecord::get_OwnerType()
0x91ef0  callvirt instance string [mscorlib]System.Type::get_FullName()
0x91ef5  ldarg.1
0x91ef6  callvirt instance string System.Windows.Markup.BamlStringValueRecord::get_Value()
0x91efb  call     instance void System.Windows.Markup.BamlRecordReader::ThrowException(string id, string parameter1, string parameter2)
0x91f00  ret
0x91f01  ldnull
0x91f02  ldarg.0
0x91f03  call     instance class System.Windows.Markup.ReaderContextStackData System.Windows.Markup.BamlRecordReader::get_CurrentContext()
0x91f08  callvirt instance class [mscorlib]System.Type System.Windows.Markup.ReaderContextStackData::get_ExpectedType()
0x91f0d  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x91f12  brfalse.s loc_91F30
0x91f14  ldarg.0
0x91f15  ldstr    aParsernocomple// "ParserNoComplexMulti"
0x91f1a  ldarg.0
0x91f1b  ldarg.0
0x91f1c  call     instance class System.Windows.Markup.ReaderContextStackData System.Windows.Markup.BamlRecordReader::get_CurrentContext()
0x91f21  callvirt instance object System.Windows.Markup.ReaderContextStackData::get_ObjectData()
0x91f26  call     instance string System.Windows.Markup.BamlRecordReader::GetPropNameFrom(object PiOrAttribInfo)
0x91f2b  call     instance void System.Windows.Markup.BamlRecordReader::ThrowException(string id, string parameter)
0x91f30  ldarg.0
0x91f31  ldarg.0
0x91f32  call     instance class System.Windows.Markup.ReaderContextStackData System.Windows.Markup.BamlRecordReader::get_CurrentContext()
0x91f37  callvirt instance class [mscorlib]System.Type System.Windows.Markup.ReaderContextStackData::get_ExpectedType()
0x91f3c  ldarg.1
0x91f3d  callvirt instance string System.Windows.Markup.BamlStringValueRecord::get_Value()
0x91f42  ldloc.1
0x91f43  call     instance object System.Windows.Markup.BamlRecordReader::GetObjectFromString(class [mscorlib]System.Type type, string s, int16 converterTypeId)
0x91f48  stloc.s  9
0x91f4a  ldsfld   object [WindowsBase]System.Windows.DependencyProperty::UnsetValue
0x91f4f  ldloc.s  9
0x91f51  beq.s    loc_91F5C
0x91f53  ldarg.0
0x91f54  ldloc.s  9
0x91f56  call     instance void System.Windows.Markup.BamlRecordReader::SetClrComplexProperty(object o)
0x91f5b  ret
0x91f5c  ldarg.0
0x91f5d  ldstr    aParsercantcrea_1// "ParserCantCreateTextComplexProp"
0x91f62  ldarg.0
0x91f63  call     instance class System.Windows.Markup.ReaderContextStackData System.Windows.Markup.BamlRecordReader::get_CurrentContext()
0x91f68  callvirt instance class [mscorlib]System.Type System.Windows.Markup.ReaderContextStackData::get_ExpectedType()
0x91f6d  callvirt instance string [mscorlib]System.Type::get_FullName()
0x91f72  ldarg.1
0x91f73  callvirt instance string System.Windows.Markup.BamlStringValueRecord::get_Value()
0x91f78  call     instance void System.Windows.Markup.BamlRecordReader::ThrowException(string id, string parameter1, string parameter2)
0x91f7d  ret
0x91f7e  ldarg.0
0x91f7f  ldarg.0
0x91f80  call     instance class System.Windows.Markup.ReaderContextStackData System.Windows.Markup.BamlRecordReader::get_CurrentContext()
0x91f85  ldc.i4.1
0x91f86  call     instance class System.Windows.Markup.BamlCollectionHolder System.Windows.Markup.BamlRecordReader::GetCollectionHolderFromContext(class System.Windows.Markup.ReaderContextStackData context, bool toInsert)
0x91f8b  stloc.s  0xA
0x91f8d  ldloc.s  0xA
0x91f8f  callvirt instance object System.Windows.Markup.BamlCollectionHolder::get_Collection()
0x91f94  call     class [PresentationCore]System.Windows.Markup.IAddChild System.Windows.Markup.BamlRecordManager::AsIAddChild(object obj)
0x91f99  stloc.s  0xB
0x91f9b  ldloc.s  0xB
0x91f9d  brtrue.s loc_91FAF
0x91f9f  ldarg.0
0x91fa0  ldstr    aParsernomatchi_1// "ParserNoMatchingIList"
0x91fa5  ldstr    asc_29D322// "?"
0x91faa  call     instance void System.Windows.Markup.BamlRecordReader::ThrowException(string id, string parameter)
0x91faf  ldloc.s  0xB
0x91fb1  ldarg.1
0x91fb2  callvirt instance string System.Windows.Markup.BamlStringValueRecord::get_Value()
0x91fb7  callvirt instance void [PresentationCore]System.Windows.Markup.IAddChild::AddText(string)
0x91fbc  ret
0x91fbd  ldarg.0
0x91fbe  ldarg.0
0x91fbf  call     instance class System.Windows.Markup.ReaderContextStackData System.Windows.Markup.BamlRecordReader::get_CurrentContext()
0x91fc4  ldc.i4.1
0x91fc5  call     instance class System.Windows.Markup.BamlCollectionHolder System.Windows.Markup.BamlRecordReader::GetCollectionHolderFromContext(class System.Windows.Markup.ReaderContextStackData context, bool toInsert)
0x91fca  stloc.s  0xC
0x91fcc  ldloc.s  0xC
0x91fce  callvirt instance class [mscorlib]System.Collections.IList System.Windows.Markup.BamlCollectionHolder::get_List()
0x91fd3  brtrue.s loc_91FE5
0x91fd5  ldarg.0
0x91fd6  ldstr    aParsernomatchi_1// "ParserNoMatchingIList"
0x91fdb  ldstr    asc_29D322// "?"
0x91fe0  call     instance void System.Windows.Markup.BamlRecordReader::ThrowException(string id, string parameter)
0x91fe5  ldloc.s  0xC
0x91fe7  callvirt instance class [mscorlib]System.Collections.IList System.Windows.Markup.BamlCollectionHolder::get_List()
0x91fec  ldarg.1
0x91fed  callvirt instance string System.Windows.Markup.BamlStringValueRecord::get_Value()
0x91ff2  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x91ff7  pop
0x91ff8  ret
0x91ff9  ldarg.0
0x91ffa  ldarg.1
0x91ffb  callvirt instance string System.Windows.Markup.BamlStringValueRecord::get_Value()
0x92000  call     instance void System.Windows.Markup.BamlRecordReader::SetConstructorParameter(object o)
0x92005  ret
0x92006  ldarg.0
0x92007  ldstr    aParserunexpinb// "ParserUnexpInBAML"
0x9200c  ldstr    aText// "Text"
0x92011  call     instance void System.Windows.Markup.BamlRecordReader::ThrowException(string id, string parameter)
0x92016  ret
```
