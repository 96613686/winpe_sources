# System.Xml.Serialization.XmlSerializationReaderILGen::WriteEnumAndArrayTypes

- ea: `0x95a80`
- end: `0x95e95`
- name: `System.Xml.Serialization.XmlSerializationReaderILGen::WriteEnumAndArrayTypes`
- size: `1045`
- prototype: ``
- caller_count: `1`
- callee_count: `37`
- tags: `registry_config`

## callers

- `0x96090`

## callees

- `0x632c0`
- `0x632f0`
- `0x633f0`
- `0x63410`
- `0x63480`
- `0x634c0`
- `0x637d0`
- `0x63bc0`
- `0x63c60`
- `0x642b0`
- `0x64320`
- `0x643c0`
- `0x64620`
- `0x64970`
- `0x64a90`
- `0x68c10`
- `0x68c30`
- `0x68c50`
- `0x68dc0`
- `0x69630`
- `0x69670`
- `0x69a50`
- `0x72bf0`
- `0x72c20`
- `0x72d00`
- `0x74f30`
- `0x87190`
- `0x871d0`
- `0x87270`
- `0x87300`
- `0x95a80`
- `0x96f50`
- `0x99700`
- `0xa9640`
- `0x122e20`
- `0x1230a0`
- `0x1230b0`

## string_xrefs

- `0x95afe`: `get_Reader`
- `0x95b20`: `ReadStartElement`
- `0x95c92`: `ReadEndElement`
- `0x95bf2`: `ReadString`

## pseudocode

```c

```

## disassembly

```asm
0x95a80  ldarg.0
0x95a81  call     instance class System.Xml.Serialization.TypeScope[] System.Xml.Serialization.XmlSerializationILGen::get_Scopes()
0x95a86  stloc.0
0x95a87  ldc.i4.0
0x95a88  stloc.1
0x95a89  br       loc_95E8B
0x95a8e  ldloc.0
0x95a8f  ldloc.1
0x95a90  ldelem.ref
0x95a91  stloc.2
0x95a92  ldloc.2
0x95a93  callvirt instance class [mscorlib]System.Collections.ICollection System.Xml.Serialization.TypeScope::get_TypeMappings()
0x95a98  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x95a9d  stloc.3
0x95a9e  br       loc_95E66
0x95aa3  ldloc.3
0x95aa4  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x95aa9  castclass System.Xml.Serialization.Mapping
0x95aae  stloc.s  4
0x95ab0  ldloc.s  4
0x95ab2  isinst   System.Xml.Serialization.EnumMapping
0x95ab7  brfalse  loc_95D01
0x95abc  ldloc.s  4
0x95abe  castclass System.Xml.Serialization.EnumMapping
0x95ac3  stloc.s  5
0x95ac5  ldarg.0
0x95ac6  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x95acb  callvirt instance void System.Xml.Serialization.CodeGenerator::InitElseIf()
0x95ad0  ldarg.0
0x95ad1  ldstr    aXsitype// "xsiType"
0x95ad6  ldloc.s  5
0x95ad8  callvirt instance string System.Xml.Serialization.TypeMapping::get_TypeName()
0x95add  ldloc.s  5
0x95adf  callvirt instance string System.Xml.Serialization.TypeMapping::get_Namespace()
0x95ae4  call     instance void System.Xml.Serialization.XmlSerializationReaderILGen::WriteQNameEqual(string source, string name, string ns)
0x95ae9  ldarg.0
0x95aea  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x95aef  callvirt instance void System.Xml.Serialization.CodeGenerator::AndIf()
0x95af4  ldtoken  System.Xml.Serialization.XmlSerializationReader
0x95af9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x95afe  ldstr    aGetReader// "get_Reader"
0x95b03  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x95b08  ldnull
0x95b09  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0x95b0e  ldnull
0x95b0f  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x95b14  stloc.s  6
0x95b16  ldtoken  System.Xml.XmlReader
0x95b1b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x95b20  ldstr    aReadstarteleme// "ReadStartElement"
0x95b25  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x95b2a  ldnull
0x95b2b  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0x95b30  ldnull
0x95b31  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x95b36  stloc.s  7
0x95b38  ldarg.0
0x95b39  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x95b3e  ldc.i4.0
0x95b3f  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(int32 slot)
0x95b44  ldarg.0
0x95b45  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x95b4a  ldloc.s  6
0x95b4c  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x95b51  ldarg.0
0x95b52  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x95b57  ldloc.s  7
0x95b59  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x95b5e  ldarg.0
0x95b5f  ldloc.s  5
0x95b61  call     instance string System.Xml.Serialization.XmlSerializationILGen::ReferenceMapping(class System.Xml.Serialization.TypeMapping mapping)
0x95b66  stloc.s  8
0x95b68  ldarg.0
0x95b69  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x95b6e  ldtoken  [mscorlib]System.Object
0x95b73  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x95b78  ldstr    aE// "e"
0x95b7d  callvirt instance class [mscorlib]System.Reflection.Emit.LocalBuilder System.Xml.Serialization.CodeGenerator::DeclareOrGetLocal(class [mscorlib]System.Type type, string name)
0x95b82  stloc.s  9
0x95b84  ldarg.0
0x95b85  ldarg.0
0x95b86  ldfld    class [mscorlib]System.Reflection.Emit.TypeBuilder System.Xml.Serialization.XmlSerializationILGen::typeBuilder
0x95b8b  ldloc.s  8
0x95b8d  ldsfld   valuetype [mscorlib]System.Reflection.MethodAttributes System.Xml.Serialization.CodeGenerator::PrivateMethodAttributes
0x95b92  ldloc.s  5
0x95b94  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x95b99  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeDesc::get_Type()
0x95b9e  ldc.i4.1
0x95b9f  newarr   [mscorlib]System.Type
0x95ba4  dup
0x95ba5  ldc.i4.0
0x95ba6  ldtoken  [mscorlib]System.String
0x95bab  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x95bb0  stelem.ref
0x95bb1  call     instance class [mscorlib]System.Reflection.Emit.MethodBuilder System.Xml.Serialization.XmlSerializationILGen::EnsureMethodBuilder(class [mscorlib]System.Reflection.Emit.TypeBuilder typeBuilder, string methodName, valuetype [mscorlib]System.Reflection.MethodAttributes attributes, class [mscorlib]System.Type returnType, class [mscorlib]System.Type[] parameterTypes)
0x95bb6  stloc.s  0xA
0x95bb8  ldtoken  System.Xml.Serialization.XmlSerializationReader
0x95bbd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x95bc2  ldstr    aCollapsewhites_2// "CollapseWhitespace"
0x95bc7  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x95bcc  ldnull
0x95bcd  ldc.i4.1
0x95bce  newarr   [mscorlib]System.Type
0x95bd3  dup
0x95bd4  ldc.i4.0
0x95bd5  ldtoken  [mscorlib]System.String
0x95bda  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x95bdf  stelem.ref
0x95be0  ldnull
0x95be1  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x95be6  stloc.s  0xB
0x95be8  ldtoken  System.Xml.XmlReader
0x95bed  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x95bf2  ldstr    aReadstring// "ReadString"
0x95bf7  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x95bfc  ldnull
0x95bfd  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0x95c02  ldnull
0x95c03  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x95c08  stloc.s  0xC
0x95c0a  ldarg.0
0x95c0b  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x95c10  ldc.i4.0
0x95c11  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(int32 slot)
0x95c16  ldarg.0
0x95c17  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x95c1c  ldc.i4.0
0x95c1d  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(int32 slot)
0x95c22  ldarg.0
0x95c23  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x95c28  ldc.i4.0
0x95c29  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(int32 slot)
0x95c2e  ldarg.0
0x95c2f  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x95c34  ldloc.s  6
0x95c36  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x95c3b  ldarg.0
0x95c3c  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x95c41  ldloc.s  0xC
0x95c43  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x95c48  ldarg.0
0x95c49  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x95c4e  ldloc.s  0xB
0x95c50  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x95c55  ldarg.0
0x95c56  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x95c5b  ldloc.s  0xA
0x95c5d  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x95c62  ldarg.0
0x95c63  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x95c68  ldloc.s  0xA
0x95c6a  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.MethodInfo::get_ReturnType()
0x95c6f  ldloc.s  9
0x95c71  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.LocalVariableInfo::get_LocalType()
0x95c76  callvirt instance void System.Xml.Serialization.CodeGenerator::ConvertValue(class [mscorlib]System.Type source, class [mscorlib]System.Type target)
0x95c7b  ldarg.0
0x95c7c  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x95c81  ldloc.s  9
0x95c83  callvirt instance void System.Xml.Serialization.CodeGenerator::Stloc(class [mscorlib]System.Reflection.Emit.LocalBuilder local)
0x95c88  ldtoken  System.Xml.Serialization.XmlSerializationReader
0x95c8d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x95c92  ldstr    aReadendelement_0// "ReadEndElement"
0x95c97  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x95c9c  ldnull
0x95c9d  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0x95ca2  ldnull
0x95ca3  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x95ca8  stloc.s  0xD
0x95caa  ldarg.0
0x95cab  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x95cb0  ldc.i4.0
0x95cb1  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(int32 slot)
0x95cb6  ldarg.0
0x95cb7  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x95cbc  ldloc.s  0xD
0x95cbe  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x95cc3  ldarg.0
0x95cc4  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x95cc9  ldloc.s  9
0x95ccb  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldloc(class [mscorlib]System.Reflection.Emit.LocalBuilder localBuilder)
0x95cd0  ldarg.0
0x95cd1  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x95cd6  ldarg.0
0x95cd7  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x95cdc  callvirt instance class [mscorlib]System.Reflection.Emit.LocalBuilder System.Xml.Serialization.CodeGenerator::get_ReturnLocal()
0x95ce1  callvirt instance void System.Xml.Serialization.CodeGenerator::Stloc(class [mscorlib]System.Reflection.Emit.LocalBuilder local)
0x95ce6  ldarg.0
0x95ce7  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x95cec  ldarg.0
0x95ced  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x95cf2  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Serialization.CodeGenerator::get_ReturnLabel()
0x95cf7  callvirt instance void System.Xml.Serialization.CodeGenerator::Br(valuetype [mscorlib]System.Reflection.Emit.Label label)
0x95cfc  br       loc_95E66
0x95d01  ldloc.s  4
0x95d03  isinst   System.Xml.Serialization.ArrayMapping
0x95d08  brfalse  loc_95E66
0x95d0d  ldloc.s  4
0x95d0f  castclass System.Xml.Serialization.ArrayMapping
0x95d14  stloc.s  0xE
0x95d16  ldloc.s  0xE
0x95d18  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x95d1d  callvirt instance bool System.Xml.Serialization.TypeDesc::get_HasDefaultConstructor()
0x95d22  brfalse  loc_95E66
0x95d27  ldarg.0
0x95d28  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x95d2d  callvirt instance void System.Xml.Serialization.CodeGenerator::InitElseIf()
0x95d32  ldarg.0
0x95d33  ldstr    aXsitype// "xsiType"
0x95d38  ldloc.s  0xE
0x95d3a  callvirt instance string System.Xml.Serialization.TypeMapping::get_TypeName()
0x95d3f  ldloc.s  0xE
0x95d41  callvirt instance string System.Xml.Serialization.TypeMapping::get_Namespace()
0x95d46  call     instance void System.Xml.Serialization.XmlSerializationReaderILGen::WriteQNameEqual(string source, string name, string ns)
0x95d4b  ldarg.0
0x95d4c  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x95d51  callvirt instance void System.Xml.Serialization.CodeGenerator::AndIf()
0x95d56  ldarg.0
0x95d57  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x95d5c  callvirt instance void System.Xml.Serialization.CodeGenerator::EnterScope()
0x95d61  newobj   instance void System.Xml.Serialization.MemberMapping::.ctor()
0x95d66  stloc.s  0xF
0x95d68  ldloc.s  0xF
0x95d6a  ldloc.s  0xE
0x95d6c  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x95d71  callvirt instance void System.Xml.Serialization.AccessorMapping::set_TypeDesc(class System.Xml.Serialization.TypeDesc value)
0x95d76  ldloc.s  0xF
0x95d78  ldloc.s  0xE
0x95d7a  callvirt instance class System.Xml.Serialization.ElementAccessor[] System.Xml.Serialization.ArrayMapping::get_Elements()
0x95d7f  callvirt instance void System.Xml.Serialization.AccessorMapping::set_Elements(class System.Xml.Serialization.ElementAccessor[] value)
0x95d84  ldstr    aA_0// "a"
0x95d89  stloc.s  0x10
0x95d8b  ldstr    aZ// "z"
0x95d90  stloc.s  0x11
0x95d92  ldarg.0
0x95d93  ldloc.s  0x10
0x95d95  ldloc.s  0x11
0x95d97  ldc.i4.0
0x95d98  ldloc.s  0xF
0x95d9a  newobj   instance void Member::.ctor(class System.Xml.Serialization.XmlSerializationReaderILGen outerClass, string source, string arrayName, int32 i, class System.Xml.Serialization.MemberMapping mapping)
0x95d9f  stloc.s  0x12
0x95da1  ldloc.s  0xE
0x95da3  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x95da8  stloc.s  0x13
0x95daa  ldarg.0
0x95dab  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x95db0  ldloc.s  0xE
0x95db2  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x95db7  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeDesc::get_Type()
0x95dbc  ldloc.s  0x10
0x95dbe  callvirt instance class [mscorlib]System.Reflection.Emit.LocalBuilder System.Xml.Serialization.CodeGenerator::DeclareLocal(class [mscorlib]System.Type type, string name)
0x95dc3  stloc.s  0x14
0x95dc5  ldloc.s  0xE
0x95dc7  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x95dcc  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsValueType()
0x95dd1  brfalse.s loc_95DEF
0x95dd3  ldarg.0
0x95dd4  call     instance class System.Xml.Serialization.ReflectionAwareILGen System.Xml.Serialization.XmlSerializationILGen::get_RaCodeGen()
0x95dd9  ldarg.0
0x95dda  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x95ddf  ldloc.s  0x13
0x95de1  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeDesc::get_Type()
0x95de6  ldc.i4.0
0x95de7  ldc.i4.0
0x95de8  callvirt instance void System.Xml.Serialization.ReflectionAwareILGen::ILGenForCreateInstance(class System.Xml.Serialization.CodeGenerator ilg, class [mscorlib]System.Type type, bool ctorInaccessible, bool cast)
0x95ded  br.s     loc_95DFB
0x95def  ldarg.0
0x95df0  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x95df5  ldnull
0x95df6  callvirt instance void System.Xml.Serialization.CodeGenerator::Load(object obj)
0x95dfb  ldarg.0
0x95dfc  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x95e01  ldloc.s  0x14
0x95e03  callvirt instance void System.Xml.Serialization.CodeGenerator::Stloc(class [mscorlib]System.Reflection.Emit.LocalBuilder local)
0x95e08  ldarg.0
0x95e09  ldloc.s  0x12
0x95e0b  callvirt instance string Member::get_Source()
0x95e10  ldloc.s  0x12
0x95e12  callvirt instance string Member::get_ArrayName()
0x95e17  ldloc.s  0xE
0x95e19  ldc.i4.0
0x95e1a  ldc.i4.0
0x95e1b  ldc.i4.m1
0x95e1c  ldc.i4.0
0x95e1d  call     instance void System.Xml.Serialization.XmlSerializationReaderILGen::WriteArray(string source, string arrayName, class System.Xml.Serialization.ArrayMapping arrayMapping, bool readOnly, bool isNullable, int32 fixupIndex, int32 elementIndex)
0x95e22  ldarg.0
0x95e23  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x95e28  ldloc.s  0x14
0x95e2a  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldloc(class [mscorlib]System.Reflection.Emit.LocalBuilder localBuilder)
0x95e2f  ldarg.0
0x95e30  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x95e35  ldarg.0
0x95e36  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x95e3b  callvirt instance class [mscorlib]System.Reflection.Emit.LocalBuilder System.Xml.Serialization.CodeGenerator::get_ReturnLocal()
0x95e40  callvirt instance void System.Xml.Serialization.CodeGenerator::Stloc(class [mscorlib]System.Reflection.Emit.LocalBuilder local)
0x95e45  ldarg.0
0x95e46  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x95e4b  ldarg.0
0x95e4c  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x95e51  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Serialization.CodeGenerator::get_ReturnLabel()
0x95e56  callvirt instance void System.Xml.Serialization.CodeGenerator::Br(valuetype [mscorlib]System.Reflection.Emit.Label label)
  ... truncated ...
```
