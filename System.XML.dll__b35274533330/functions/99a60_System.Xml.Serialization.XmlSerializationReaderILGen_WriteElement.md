# System.Xml.Serialization.XmlSerializationReaderILGen::WriteElement

- ea: `0x99a60`
- end: `0x9a52e`
- name: `System.Xml.Serialization.XmlSerializationReaderILGen::WriteElement`
- size: `2766`
- prototype: ``
- caller_count: `3`
- callee_count: `59`
- tags: `registry_config`

## callers

- `0x95ea0`
- `0x98910`
- `0x989c0`

## callees

- `0xc240`
- `0x13310`
- `0x13320`
- `0x62370`
- `0x63290`
- `0x634c0`
- `0x63610`
- `0x63640`
- `0x636b0`
- `0x636f0`
- `0x637d0`
- `0x63830`
- `0x63bc0`
- `0x63c60`
- `0x63c70`
- `0x63d40`
- `0x640d0`
- `0x64200`
- `0x642b0`
- `0x642d0`
- `0x64320`
- `0x643c0`
- `0x645a0`
- `0x645b0`
- `0x64640`
- `0x646a0`
- `0x65610`
- `0x68600`
- `0x68620`
- `0x68690`
- `0x688b0`
- `0x689b0`
- `0x68c50`
- `0x69ff0`
- `0x6a070`
- `0x72b90`
- `0x72bf0`
- `0x72c00`
- `0x72c10`
- `0x72c20`
- `0x72d40`
- `0x72e40`
- `0x87190`
- `0x871b0`
- `0x87270`
- `0x87300`
- `0x881f0`
- `0x93c40`
- `0x94a20`
- `0x96f50`

## string_xrefs

- `0x9a4af`: `XmlInternalError`
- `0x9a4bf`: `XmlInternalError`
- `0x99c44`: `get_Reader`
- `0x99d3d`: `get_Reader`
- `0x99fb5`: `get_Reader`
- `0x99e7a`: `Reader.ReadElementString()`
- `0x99f3c`: `Reader.ReadElementString()`
- `0x99b77`: `ReadNull`
- `0x99bcb`: `No such condition.  PrimitiveMapping && IsNullable = String, XmlQualifiedName and never IsValueType`
- `0x99ed1`: `ReadElementQualifiedName`
- `0x9a18f`: `ReadXmlNode`
- `0x9a196`: `ReadXmlDocument`
- `0x9a37c`: `ReadSerializable`

## pseudocode

```c

```

## disassembly

```asm
0x99a60  ldarg.s  6
0x99a62  brfalse.s loc_99A7C
0x99a64  ldarg.s  6
0x99a66  callvirt instance int32 [mscorlib]System.String::get_Length()
0x99a6b  ldc.i4.0
0x99a6c  ble.s    loc_99A7C
0x99a6e  ldarg.0
0x99a6f  ldarg.s  6
0x99a71  ldc.i4.1
0x99a72  box      [mscorlib]System.Boolean
0x99a77  call     instance void System.Xml.Serialization.XmlSerializationReaderILGen::ILGenSet(string source, object value)
0x99a7c  ldarg.s  4
0x99a7e  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x99a83  isinst   System.Xml.Serialization.ArrayMapping
0x99a88  brfalse.s loc_99AB0
0x99a8a  ldarg.0
0x99a8b  ldarg.1
0x99a8c  ldarg.2
0x99a8d  ldarg.s  4
0x99a8f  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x99a94  castclass System.Xml.Serialization.ArrayMapping
0x99a99  ldarg.s  8
0x99a9b  ldarg.s  4
0x99a9d  callvirt instance bool System.Xml.Serialization.ElementAccessor::get_IsNullable()
0x99aa2  ldarg.s  9
0x99aa4  ldarg.s  0xA
0x99aa6  call     instance void System.Xml.Serialization.XmlSerializationReaderILGen::WriteArray(string source, string arrayName, class System.Xml.Serialization.ArrayMapping arrayMapping, bool readOnly, bool isNullable, int32 fixupIndex, int32 elementIndex)
0x99aab  br       loc_9A4CF
0x99ab0  ldarg.s  4
0x99ab2  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x99ab7  isinst   System.Xml.Serialization.NullableMapping
0x99abc  brfalse  loc_99B4E
0x99ac1  ldarg.0
0x99ac2  ldarg.s  4
0x99ac4  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x99ac9  call     instance string System.Xml.Serialization.XmlSerializationILGen::ReferenceMapping(class System.Xml.Serialization.TypeMapping mapping)
0x99ace  stloc.0
0x99acf  ldarg.0
0x99ad0  ldarg.1
0x99ad1  call     instance void System.Xml.Serialization.XmlSerializationReaderILGen::WriteSourceBegin(string source)
0x99ad6  ldarg.0
0x99ad7  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x99adc  ldc.i4.0
0x99add  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(int32 slot)
0x99ae2  ldarg.0
0x99ae3  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x99ae8  ldc.i4.1
0x99ae9  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldc(bool boolVar)
0x99aee  ldarg.0
0x99aef  ldarg.0
0x99af0  ldfld    class [mscorlib]System.Reflection.Emit.TypeBuilder System.Xml.Serialization.XmlSerializationILGen::typeBuilder
0x99af5  ldloc.0
0x99af6  ldsfld   valuetype [mscorlib]System.Reflection.MethodAttributes System.Xml.Serialization.CodeGenerator::PrivateMethodAttributes
0x99afb  ldarg.s  4
0x99afd  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x99b02  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x99b07  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeDesc::get_Type()
0x99b0c  ldc.i4.1
0x99b0d  newarr   [mscorlib]System.Type
0x99b12  dup
0x99b13  ldc.i4.0
0x99b14  ldtoken  [mscorlib]System.Boolean
0x99b19  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x99b1e  stelem.ref
0x99b1f  call     instance class [mscorlib]System.Reflection.Emit.MethodBuilder System.Xml.Serialization.XmlSerializationILGen::EnsureMethodBuilder(class [mscorlib]System.Reflection.Emit.TypeBuilder typeBuilder, string methodName, valuetype [mscorlib]System.Reflection.MethodAttributes attributes, class [mscorlib]System.Type returnType, class [mscorlib]System.Type[] parameterTypes)
0x99b24  stloc.1
0x99b25  ldarg.0
0x99b26  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x99b2b  ldloc.1
0x99b2c  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x99b31  ldarg.0
0x99b32  ldarg.1
0x99b33  ldarg.s  4
0x99b35  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x99b3a  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x99b3f  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeDesc::get_Type()
0x99b44  call     instance void System.Xml.Serialization.XmlSerializationReaderILGen::WriteSourceEnd(string source, class [mscorlib]System.Type elementType)
0x99b49  br       loc_9A4CF
0x99b4e  ldarg.s  4
0x99b50  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x99b55  isinst   System.Xml.Serialization.PrimitiveMapping
0x99b5a  brfalse  loc_99F80
0x99b5f  ldc.i4.0
0x99b60  stloc.2
0x99b61  ldarg.s  4
0x99b63  callvirt instance bool System.Xml.Serialization.ElementAccessor::get_IsNullable()
0x99b68  brfalse  loc_99C07
0x99b6d  ldtoken  System.Xml.Serialization.XmlSerializationReader
0x99b72  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x99b77  ldstr    aReadnull// "ReadNull"
0x99b7c  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x99b81  ldnull
0x99b82  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0x99b87  ldnull
0x99b88  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x99b8d  stloc.3
0x99b8e  ldarg.0
0x99b8f  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x99b94  ldc.i4.0
0x99b95  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(int32 slot)
0x99b9a  ldarg.0
0x99b9b  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x99ba0  ldloc.3
0x99ba1  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x99ba6  ldarg.0
0x99ba7  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x99bac  callvirt instance void System.Xml.Serialization.CodeGenerator::If()
0x99bb1  ldarg.0
0x99bb2  ldarg.1
0x99bb3  call     instance void System.Xml.Serialization.XmlSerializationReaderILGen::WriteSourceBegin(string source)
0x99bb8  ldarg.s  4
0x99bba  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x99bbf  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x99bc4  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsValueType()
0x99bc9  brfalse.s loc_99BD6
0x99bcb  ldstr    aNoSuchConditio// "No such condition.  PrimitiveMapping &&"...
0x99bd0  call     class [mscorlib]System.Exception System.Xml.Serialization.CodeGenerator::NotSupported(string msg)
0x99bd5  throw
0x99bd6  ldarg.0
0x99bd7  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x99bdc  ldnull
0x99bdd  callvirt instance void System.Xml.Serialization.CodeGenerator::Load(object obj)
0x99be2  ldarg.0
0x99be3  ldarg.1
0x99be4  ldarg.s  4
0x99be6  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x99beb  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x99bf0  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeDesc::get_Type()
0x99bf5  call     instance void System.Xml.Serialization.XmlSerializationReaderILGen::WriteSourceEnd(string source, class [mscorlib]System.Type elementType)
0x99bfa  ldarg.0
0x99bfb  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x99c00  callvirt instance void System.Xml.Serialization.CodeGenerator::Else()
0x99c05  ldc.i4.1
0x99c06  stloc.2
0x99c07  ldarg.s  4
0x99c09  callvirt instance object System.Xml.Serialization.Accessor::get_Default()
0x99c0e  brfalse  loc_99D04
0x99c13  ldarg.s  4
0x99c15  callvirt instance object System.Xml.Serialization.Accessor::get_Default()
0x99c1a  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x99c1f  beq      loc_99D04
0x99c24  ldarg.s  4
0x99c26  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x99c2b  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x99c30  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsValueType()
0x99c35  brfalse  loc_99D04
0x99c3a  ldtoken  System.Xml.Serialization.XmlSerializationReader
0x99c3f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x99c44  ldstr    aGetReader// "get_Reader"
0x99c49  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x99c4e  ldnull
0x99c4f  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0x99c54  ldnull
0x99c55  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x99c5a  stloc.s  4
0x99c5c  ldtoken  System.Xml.XmlReader
0x99c61  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x99c66  ldstr    aGetIsemptyelem// "get_IsEmptyElement"
0x99c6b  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x99c70  ldnull
0x99c71  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0x99c76  ldnull
0x99c77  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x99c7c  stloc.s  5
0x99c7e  ldarg.0
0x99c7f  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x99c84  ldc.i4.0
0x99c85  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(int32 slot)
0x99c8a  ldarg.0
0x99c8b  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x99c90  ldloc.s  4
0x99c92  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x99c97  ldarg.0
0x99c98  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x99c9d  ldloc.s  5
0x99c9f  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x99ca4  ldarg.0
0x99ca5  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x99caa  callvirt instance void System.Xml.Serialization.CodeGenerator::If()
0x99caf  ldtoken  System.Xml.XmlReader
0x99cb4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x99cb9  ldstr    aSkip_0// "Skip"
0x99cbe  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x99cc3  ldnull
0x99cc4  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0x99cc9  ldnull
0x99cca  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x99ccf  stloc.s  6
0x99cd1  ldarg.0
0x99cd2  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x99cd7  ldc.i4.0
0x99cd8  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(int32 slot)
0x99cdd  ldarg.0
0x99cde  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x99ce3  ldloc.s  4
0x99ce5  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x99cea  ldarg.0
0x99ceb  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x99cf0  ldloc.s  6
0x99cf2  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x99cf7  ldarg.0
0x99cf8  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x99cfd  callvirt instance void System.Xml.Serialization.CodeGenerator::Else()
0x99d02  ldc.i4.1
0x99d03  stloc.2
0x99d04  call     bool System.LocalAppContextSwitches::get_EnableTimeSpanSerialization()
0x99d09  brfalse  loc_99EAC
0x99d0e  ldarg.s  4
0x99d10  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x99d15  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x99d1a  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeDesc::get_Type()
0x99d1f  ldtoken  [mscorlib]System.TimeSpan
0x99d24  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x99d29  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x99d2e  brfalse  loc_99EAC
0x99d33  ldtoken  System.Xml.Serialization.XmlSerializationReader
0x99d38  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x99d3d  ldstr    aGetReader// "get_Reader"
0x99d42  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x99d47  ldnull
0x99d48  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0x99d4d  ldnull
0x99d4e  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x99d53  stloc.s  7
0x99d55  ldtoken  System.Xml.XmlReader
0x99d5a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x99d5f  ldstr    aGetIsemptyelem// "get_IsEmptyElement"
0x99d64  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x99d69  ldnull
0x99d6a  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0x99d6f  ldnull
0x99d70  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x99d75  stloc.s  8
0x99d77  ldarg.0
0x99d78  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x99d7d  ldc.i4.0
0x99d7e  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(int32 slot)
0x99d83  ldarg.0
0x99d84  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x99d89  ldloc.s  7
0x99d8b  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x99d90  ldarg.0
0x99d91  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x99d96  ldloc.s  8
0x99d98  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x99d9d  ldarg.0
0x99d9e  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x99da3  callvirt instance void System.Xml.Serialization.CodeGenerator::If()
0x99da8  ldarg.0
0x99da9  ldarg.1
0x99daa  call     instance void System.Xml.Serialization.XmlSerializationReaderILGen::WriteSourceBegin(string source)
0x99daf  ldtoken  System.Xml.XmlReader
0x99db4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x99db9  ldstr    aSkip_0// "Skip"
0x99dbe  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x99dc3  ldnull
0x99dc4  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0x99dc9  ldnull
0x99dca  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x99dcf  stloc.s  9
0x99dd1  ldarg.0
0x99dd2  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x99dd7  ldc.i4.0
0x99dd8  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(int32 slot)
0x99ddd  ldarg.0
0x99dde  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x99de3  ldloc.s  7
0x99de5  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x99dea  ldarg.0
0x99deb  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x99df0  ldloc.s  9
0x99df2  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x99df7  ldtoken  [mscorlib]System.TimeSpan
0x99dfc  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x99e01  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x99e06  ldnull
0x99e07  ldc.i4.1
0x99e08  newarr   [mscorlib]System.Type
0x99e0d  dup
0x99e0e  ldc.i4.0
0x99e0f  ldtoken  [mscorlib]System.Int64
0x99e14  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x99e19  stelem.ref
0x99e1a  ldnull
0x99e1b  call     instance class [mscorlib]System.Reflection.ConstructorInfo [mscorlib]System.Type::GetConstructor(valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x99e20  stloc.s  0xA
0x99e22  ldarg.0
0x99e23  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x99e28  ldloca.s 0xB
0x99e2a  dup
0x99e2b  initobj  [mscorlib]System.TimeSpan
0x99e31  call     instance int64 [mscorlib]System.TimeSpan::get_Ticks()
0x99e36  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldc(int64 l)
0x99e3b  ldarg.0
0x99e3c  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x99e41  ldloc.s  0xA
0x99e43  callvirt instance void System.Xml.Serialization.CodeGenerator::New(class [mscorlib]System.Reflection.ConstructorInfo constructorInfo)
0x99e48  ldarg.0
0x99e49  ldarg.1
0x99e4a  ldarg.s  4
  ... truncated ...
```
