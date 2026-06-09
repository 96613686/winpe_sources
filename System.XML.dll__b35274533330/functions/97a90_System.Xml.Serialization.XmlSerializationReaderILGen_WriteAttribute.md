# System.Xml.Serialization.XmlSerializationReaderILGen::WriteAttribute

- ea: `0x97a90`
- end: `0x97ea7`
- name: `System.Xml.Serialization.XmlSerializationReaderILGen::WriteAttribute`
- size: `1047`
- prototype: ``
- caller_count: `1`
- callee_count: `39`
- tags: `registry_config`

## callers

- `0x972b0`

## callees

- `0x62370`
- `0x632b0`
- `0x634c0`
- `0x634e0`
- `0x63540`
- `0x63610`
- `0x636f0`
- `0x637d0`
- `0x63bc0`
- `0x63c60`
- `0x63d80`
- `0x642b0`
- `0x642d0`
- `0x64320`
- `0x643c0`
- `0x64b20`
- `0x68600`
- `0x68a60`
- `0x68c50`
- `0x69620`
- `0x69640`
- `0x69b00`
- `0x72bf0`
- `0x72c10`
- `0x72c30`
- `0x72dd0`
- `0x72fd0`
- `0x94a20`
- `0x97a90`
- `0x98dc0`
- `0x991c0`
- `0x99470`
- `0x9b3b0`
- `0x9b4b0`
- `0x123090`
- `0x1230b0`
- `0x1230c0`
- `0x123160`
- `0x123180`

## string_xrefs

- `0x97c32`: `XmlInternalError`
- `0x97cbe`: `get_Reader`
- `0x97e05`: `Reader.Value`

## pseudocode

```c

```

## disassembly

```asm
0x97a90  ldarg.1
0x97a91  callvirt instance class System.Xml.Serialization.MemberMapping Member::get_Mapping()
0x97a96  callvirt instance class System.Xml.Serialization.AttributeAccessor System.Xml.Serialization.AccessorMapping::get_Attribute()
0x97a9b  stloc.0
0x97a9c  ldloc.0
0x97a9d  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x97aa2  isinst   System.Xml.Serialization.SpecialMapping
0x97aa7  brfalse  loc_97C42
0x97aac  ldloc.0
0x97aad  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x97ab2  castclass System.Xml.Serialization.SpecialMapping
0x97ab7  stloc.1
0x97ab8  ldloc.1
0x97ab9  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x97abe  callvirt instance valuetype System.Xml.Serialization.TypeKind System.Xml.Serialization.TypeDesc::get_Kind()
0x97ac3  ldc.i4.s 0xA
0x97ac5  bne.un.s loc_97B2D
0x97ac7  ldarg.0
0x97ac8  ldarg.1
0x97ac9  callvirt instance string Member::get_ArraySource()
0x97ace  call     instance void System.Xml.Serialization.XmlSerializationReaderILGen::WriteSourceBegin(string source)
0x97ad3  ldarg.0
0x97ad4  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x97ad9  ldstr    aAttr_0// "attr"
0x97ade  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldloc(string name)
0x97ae3  ldarg.0
0x97ae4  ldarg.1
0x97ae5  callvirt instance string Member::get_ArraySource()
0x97aea  ldarg.1
0x97aeb  callvirt instance class System.Xml.Serialization.MemberMapping Member::get_Mapping()
0x97af0  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.AccessorMapping::get_TypeDesc()
0x97af5  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsArrayLike()
0x97afa  brtrue.s loc_97B0E
0x97afc  ldarg.1
0x97afd  callvirt instance class System.Xml.Serialization.MemberMapping Member::get_Mapping()
0x97b02  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.AccessorMapping::get_TypeDesc()
0x97b07  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeDesc::get_Type()
0x97b0c  br.s     loc_97B23
0x97b0e  ldarg.1
0x97b0f  callvirt instance class System.Xml.Serialization.MemberMapping Member::get_Mapping()
0x97b14  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.AccessorMapping::get_TypeDesc()
0x97b19  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeDesc::get_ArrayElementTypeDesc()
0x97b1e  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeDesc::get_Type()
0x97b23  call     instance void System.Xml.Serialization.XmlSerializationReaderILGen::WriteSourceEnd(string source, class [mscorlib]System.Type elementType)
0x97b28  br       loc_97E5B
0x97b2d  ldloc.1
0x97b2e  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x97b33  callvirt instance bool System.Xml.Serialization.TypeDesc::get_CanBeAttributeValue()
0x97b38  brfalse  loc_97C32
0x97b3d  ldarg.0
0x97b3e  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x97b43  ldstr    aAttr_0// "attr"
0x97b48  callvirt instance class [mscorlib]System.Reflection.Emit.LocalBuilder System.Xml.Serialization.CodeGenerator::GetLocal(string name)
0x97b4d  stloc.2
0x97b4e  ldarg.0
0x97b4f  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x97b54  ldloc.2
0x97b55  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldloc(class [mscorlib]System.Reflection.Emit.LocalBuilder localBuilder)
0x97b5a  ldloc.2
0x97b5b  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.LocalVariableInfo::get_LocalType()
0x97b60  ldtoken  System.Xml.XmlAttribute
0x97b65  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x97b6a  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x97b6f  brfalse.s loc_97B8A
0x97b71  ldarg.0
0x97b72  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x97b77  ldnull
0x97b78  callvirt instance void System.Xml.Serialization.CodeGenerator::Load(object obj)
0x97b7d  ldarg.0
0x97b7e  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x97b83  callvirt instance void System.Xml.Serialization.CodeGenerator::Cne()
0x97b88  br.s     loc_97B9F
0x97b8a  ldarg.0
0x97b8b  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x97b90  ldtoken  System.Xml.XmlAttribute
0x97b95  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x97b9a  callvirt instance void System.Xml.Serialization.CodeGenerator::IsInst(class [mscorlib]System.Type type)
0x97b9f  ldarg.0
0x97ba0  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x97ba5  callvirt instance void System.Xml.Serialization.CodeGenerator::If()
0x97baa  ldarg.0
0x97bab  ldarg.1
0x97bac  callvirt instance string Member::get_ArraySource()
0x97bb1  call     instance void System.Xml.Serialization.XmlSerializationReaderILGen::WriteSourceBegin(string source)
0x97bb6  ldarg.0
0x97bb7  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x97bbc  ldloc.2
0x97bbd  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldloc(class [mscorlib]System.Reflection.Emit.LocalBuilder localBuilder)
0x97bc2  ldarg.0
0x97bc3  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x97bc8  ldloc.2
0x97bc9  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.LocalVariableInfo::get_LocalType()
0x97bce  ldtoken  System.Xml.XmlAttribute
0x97bd3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x97bd8  callvirt instance void System.Xml.Serialization.CodeGenerator::ConvertValue(class [mscorlib]System.Type source, class [mscorlib]System.Type target)
0x97bdd  ldarg.0
0x97bde  ldarg.1
0x97bdf  callvirt instance string Member::get_ArraySource()
0x97be4  ldarg.1
0x97be5  callvirt instance class System.Xml.Serialization.MemberMapping Member::get_Mapping()
0x97bea  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.AccessorMapping::get_TypeDesc()
0x97bef  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsArrayLike()
0x97bf4  brtrue.s loc_97C08
0x97bf6  ldarg.1
0x97bf7  callvirt instance class System.Xml.Serialization.MemberMapping Member::get_Mapping()
0x97bfc  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.AccessorMapping::get_TypeDesc()
0x97c01  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeDesc::get_Type()
0x97c06  br.s     loc_97C1D
0x97c08  ldarg.1
0x97c09  callvirt instance class System.Xml.Serialization.MemberMapping Member::get_Mapping()
0x97c0e  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.AccessorMapping::get_TypeDesc()
0x97c13  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeDesc::get_ArrayElementTypeDesc()
0x97c18  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeDesc::get_Type()
0x97c1d  call     instance void System.Xml.Serialization.XmlSerializationReaderILGen::WriteSourceEnd(string source, class [mscorlib]System.Type elementType)
0x97c22  ldarg.0
0x97c23  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x97c28  callvirt instance void System.Xml.Serialization.CodeGenerator::EndIf()
0x97c2d  br       loc_97E5B
0x97c32  ldstr    aXmlinternalerr// "XmlInternalError"
0x97c37  call     string System.Xml.Res::GetString(string name)
0x97c3c  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x97c41  throw
0x97c42  ldloc.0
0x97c43  callvirt instance bool System.Xml.Serialization.AttributeAccessor::get_IsList()
0x97c48  brfalse  loc_97DEA
0x97c4d  ldarg.0
0x97c4e  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x97c53  ldtoken  [mscorlib]System.String
0x97c58  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x97c5d  ldstr    aListvalues// "listValues"
0x97c62  callvirt instance class [mscorlib]System.Reflection.Emit.LocalBuilder System.Xml.Serialization.CodeGenerator::DeclareOrGetLocal(class [mscorlib]System.Type type, string name)
0x97c67  stloc.3
0x97c68  ldarg.0
0x97c69  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x97c6e  ldtoken  string[]
0x97c73  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x97c78  ldstr    aVals// "vals"
0x97c7d  callvirt instance class [mscorlib]System.Reflection.Emit.LocalBuilder System.Xml.Serialization.CodeGenerator::DeclareOrGetLocal(class [mscorlib]System.Type type, string name)
0x97c82  stloc.s  4
0x97c84  ldtoken  [mscorlib]System.String
0x97c89  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x97c8e  ldstr    aSplit// "Split"
0x97c93  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x97c98  ldnull
0x97c99  ldc.i4.1
0x97c9a  newarr   [mscorlib]System.Type
0x97c9f  dup
0x97ca0  ldc.i4.0
0x97ca1  ldtoken  char[]
0x97ca6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x97cab  stelem.ref
0x97cac  ldnull
0x97cad  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x97cb2  stloc.s  5
0x97cb4  ldtoken  System.Xml.Serialization.XmlSerializationReader
0x97cb9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x97cbe  ldstr    aGetReader// "get_Reader"
0x97cc3  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x97cc8  ldnull
0x97cc9  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0x97cce  ldnull
0x97ccf  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x97cd4  stloc.s  6
0x97cd6  ldtoken  System.Xml.XmlReader
0x97cdb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x97ce0  ldstr    aGetValue// "get_Value"
0x97ce5  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x97cea  ldnull
0x97ceb  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0x97cf0  ldnull
0x97cf1  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x97cf6  stloc.s  7
0x97cf8  ldarg.0
0x97cf9  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x97cfe  ldc.i4.0
0x97cff  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(int32 slot)
0x97d04  ldarg.0
0x97d05  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x97d0a  ldloc.s  6
0x97d0c  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x97d11  ldarg.0
0x97d12  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x97d17  ldloc.s  7
0x97d19  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x97d1e  ldarg.0
0x97d1f  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x97d24  ldloc.3
0x97d25  callvirt instance void System.Xml.Serialization.CodeGenerator::Stloc(class [mscorlib]System.Reflection.Emit.LocalBuilder local)
0x97d2a  ldarg.0
0x97d2b  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x97d30  ldloc.3
0x97d31  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldloc(class [mscorlib]System.Reflection.Emit.LocalBuilder localBuilder)
0x97d36  ldarg.0
0x97d37  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x97d3c  ldnull
0x97d3d  callvirt instance void System.Xml.Serialization.CodeGenerator::Load(object obj)
0x97d42  ldarg.0
0x97d43  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x97d48  ldloc.s  5
0x97d4a  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x97d4f  ldarg.0
0x97d50  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x97d55  ldloc.s  4
0x97d57  callvirt instance void System.Xml.Serialization.CodeGenerator::Stloc(class [mscorlib]System.Reflection.Emit.LocalBuilder local)
0x97d5c  ldarg.0
0x97d5d  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x97d62  ldtoken  [mscorlib]System.Int32
0x97d67  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x97d6c  ldstr    aI// "i"
0x97d71  callvirt instance class [mscorlib]System.Reflection.Emit.LocalBuilder System.Xml.Serialization.CodeGenerator::DeclareOrGetLocal(class [mscorlib]System.Type type, string name)
0x97d76  stloc.s  8
0x97d78  ldarg.0
0x97d79  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x97d7e  ldloc.s  8
0x97d80  ldc.i4.0
0x97d81  box      [mscorlib]System.Int32
0x97d86  ldloc.s  4
0x97d88  callvirt instance object System.Xml.Serialization.CodeGenerator::For(class [mscorlib]System.Reflection.Emit.LocalBuilder local, object start, object end)
0x97d8d  pop
0x97d8e  ldarg.0
0x97d8f  ldarg.1
0x97d90  callvirt instance class System.Xml.Serialization.MemberMapping Member::get_Mapping()
0x97d95  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.AccessorMapping::get_TypeDesc()
0x97d9a  ldarg.1
0x97d9b  callvirt instance string Member::get_ArrayName()
0x97da0  call     instance string System.Xml.Serialization.XmlSerializationReaderILGen::GetArraySource(class System.Xml.Serialization.TypeDesc typeDesc, string arrayName)
0x97da5  stloc.s  9
0x97da7  ldarg.0
0x97da8  ldloc.s  9
0x97daa  call     instance void System.Xml.Serialization.XmlSerializationReaderILGen::WriteSourceBegin(string source)
0x97daf  ldarg.0
0x97db0  ldloc.0
0x97db1  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x97db6  ldstr    aValsI// "vals[i]"
0x97dbb  call     instance void System.Xml.Serialization.XmlSerializationReaderILGen::WritePrimitive(class System.Xml.Serialization.TypeMapping mapping, string source)
0x97dc0  ldarg.0
0x97dc1  ldloc.s  9
0x97dc3  ldarg.1
0x97dc4  callvirt instance class System.Xml.Serialization.MemberMapping Member::get_Mapping()
0x97dc9  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.AccessorMapping::get_TypeDesc()
0x97dce  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeDesc::get_ArrayElementTypeDesc()
0x97dd3  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeDesc::get_Type()
0x97dd8  call     instance void System.Xml.Serialization.XmlSerializationReaderILGen::WriteSourceEnd(string source, class [mscorlib]System.Type elementType)
0x97ddd  ldarg.0
0x97dde  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x97de3  callvirt instance void System.Xml.Serialization.CodeGenerator::EndFor()
0x97de8  br.s     loc_97E5B
0x97dea  ldarg.0
0x97deb  ldarg.1
0x97dec  callvirt instance string Member::get_ArraySource()
0x97df1  call     instance void System.Xml.Serialization.XmlSerializationReaderILGen::WriteSourceBegin(string source)
0x97df6  ldarg.0
0x97df7  ldloc.0
0x97df8  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x97dfd  ldloc.0
0x97dfe  callvirt instance bool System.Xml.Serialization.AttributeAccessor::get_IsList()
0x97e03  brtrue.s loc_97E0C
0x97e05  ldstr    aReaderValue// "Reader.Value"
0x97e0a  br.s     loc_97E11
0x97e0c  ldstr    aValsI// "vals[i]"
0x97e11  call     instance void System.Xml.Serialization.XmlSerializationReaderILGen::WritePrimitive(class System.Xml.Serialization.TypeMapping mapping, string source)
0x97e16  ldarg.0
0x97e17  ldarg.1
0x97e18  callvirt instance string Member::get_ArraySource()
0x97e1d  ldarg.1
0x97e1e  callvirt instance class System.Xml.Serialization.MemberMapping Member::get_Mapping()
0x97e23  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.AccessorMapping::get_TypeDesc()
0x97e28  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsArrayLike()
0x97e2d  brtrue.s loc_97E41
0x97e2f  ldarg.1
0x97e30  callvirt instance class System.Xml.Serialization.MemberMapping Member::get_Mapping()
0x97e35  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.AccessorMapping::get_TypeDesc()
0x97e3a  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeDesc::get_Type()
0x97e3f  br.s     loc_97E56
0x97e41  ldarg.1
0x97e42  callvirt instance class System.Xml.Serialization.MemberMapping Member::get_Mapping()
0x97e47  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.AccessorMapping::get_TypeDesc()
0x97e4c  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeDesc::get_ArrayElementTypeDesc()
0x97e51  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeDesc::get_Type()
0x97e56  call     instance void System.Xml.Serialization.XmlSerializationReaderILGen::WriteSourceEnd(string source, class [mscorlib]System.Type elementType)
0x97e5b  ldarg.1
0x97e5c  callvirt instance class System.Xml.Serialization.MemberMapping Member::get_Mapping()
0x97e61  callvirt instance valuetype System.Xml.Serialization.SpecifiedAccessor System.Xml.Serialization.MemberMapping::get_CheckSpecified()
0x97e66  ldc.i4.2
0x97e67  bne.un.s loc_97E91
0x97e69  ldarg.1
0x97e6a  callvirt instance string Member::get_CheckSpecifiedSource()
0x97e6f  brfalse.s loc_97E91
0x97e71  ldarg.1
0x97e72  callvirt instance string Member::get_CheckSpecifiedSource()
0x97e77  callvirt instance int32 [mscorlib]System.String::get_Length()
0x97e7c  ldc.i4.0
0x97e7d  ble.s    loc_97E91
0x97e7f  ldarg.0
0x97e80  ldarg.1
0x97e81  callvirt instance string Member::get_CheckSpecifiedSource()
0x97e86  ldc.i4.1
0x97e87  box      [mscorlib]System.Boolean
0x97e8c  call     instance void System.Xml.Serialization.XmlSerializationReaderILGen::ILGenSet(string source, object value)
0x97e91  ldarg.1
  ... truncated ...
```
