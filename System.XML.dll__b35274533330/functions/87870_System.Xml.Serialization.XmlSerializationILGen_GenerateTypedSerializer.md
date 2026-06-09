# System.Xml.Serialization.XmlSerializationILGen::GenerateTypedSerializer

- ea: `0x87870`
- end: `0x87c58`
- name: `System.Xml.Serialization.XmlSerializationILGen::GenerateTypedSerializer`
- size: `1000`
- prototype: ``
- caller_count: `1`
- callee_count: `30`
- tags: `registry_config`

## callers

- `0x66630`

## callees

- `0x63040`
- `0x630b0`
- `0x63220`
- `0x632a0`
- `0x632c0`
- `0x632f0`
- `0x637d0`
- `0x63c60`
- `0x63c70`
- `0x640d0`
- `0x64260`
- `0x642b0`
- `0x64320`
- `0x643a0`
- `0x643b0`
- `0x645b0`
- `0x64620`
- `0x64950`
- `0x654e0`
- `0x65640`
- `0x65ac0`
- `0x68600`
- `0x68660`
- `0x68690`
- `0x686d0`
- `0x68810`
- `0x68c50`
- `0x72b80`
- `0x79510`
- `0x87870`

## string_xrefs

- `0x87bba`: `reader`
- `0x87bf1`: `reader`
- `0x87909`: `xmlReader`
- `0x879ab`: `xmlReader`
- `0x878e9`: `CanDeserialize`
- `0x87aad`: `writer`
- `0x87b06`: `writer`
- `0x87b9a`: `Deserialize`

## pseudocode

```c

```

## disassembly

```asm
0x87870  ldarg.3
0x87871  callvirt instance class System.Xml.Serialization.ElementAccessor System.Xml.Serialization.XmlMapping::get_Accessor()
0x87876  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x8787b  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x87880  callvirt instance string System.Xml.Serialization.TypeDesc::get_Name()
0x87885  call     string System.Xml.Serialization.Accessor::UnescapeName(string name)
0x8788a  call     string System.Xml.Serialization.CodeIdentifier::MakeValid(string identifier)
0x8788f  stloc.0
0x87890  ldarg.s  4
0x87892  ldloc.0
0x87893  ldstr    aSerializer// "Serializer"
0x87898  call     string [mscorlib]System.String::Concat(string, string)
0x8789d  ldarg.3
0x8789e  callvirt instance string System.Xml.Serialization.CodeIdentifiers::AddUnique(string identifier, object value)
0x878a3  stloc.0
0x878a4  ldarg.0
0x878a5  ldfld    class [mscorlib]System.Reflection.Emit.ModuleBuilder System.Xml.Serialization.XmlSerializationILGen::moduleBuilder
0x878aa  ldloc.0
0x878ab  call     string System.Xml.Serialization.CodeIdentifier::GetCSharpName(string name)
0x878b0  ldc.i4   0x100101
0x878b5  ldarg.0
0x878b6  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Type> System.Xml.Serialization.XmlSerializationILGen::CreatedTypes
0x878bb  ldarg.s  5
0x878bd  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Type>::get_Item(void)
0x878c2  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0x878c7  call     class [mscorlib]System.Reflection.Emit.TypeBuilder System.Xml.Serialization.CodeGenerator::CreateTypeBuilder(class [mscorlib]System.Reflection.Emit.ModuleBuilder moduleBuilder, string name, valuetype [mscorlib]System.Reflection.TypeAttributes attributes, class [mscorlib]System.Type parent, class [mscorlib]System.Type[] interfaces)
0x878cc  stloc.1
0x878cd  ldarg.0
0x878ce  ldloc.1
0x878cf  newobj   instance void System.Xml.Serialization.CodeGenerator::.ctor(class [mscorlib]System.Reflection.Emit.TypeBuilder typeBuilder)
0x878d4  stfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x878d9  ldarg.0
0x878da  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x878df  ldtoken  [mscorlib]System.Boolean
0x878e4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x878e9  ldstr    aCandeserialize_0// "CanDeserialize"
0x878ee  ldc.i4.1
0x878ef  newarr   [mscorlib]System.Type
0x878f4  dup
0x878f5  ldc.i4.0
0x878f6  ldtoken  System.Xml.XmlReader
0x878fb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x87900  stelem.ref
0x87901  ldc.i4.1
0x87902  newarr   [mscorlib]System.String
0x87907  dup
0x87908  ldc.i4.0
0x87909  ldstr    aXmlreader// "xmlReader"
0x8790e  stelem.ref
0x8790f  ldsfld   valuetype [mscorlib]System.Reflection.MethodAttributes System.Xml.Serialization.CodeGenerator::PublicOverrideMethodAttributes
0x87914  callvirt instance void System.Xml.Serialization.CodeGenerator::BeginMethod(class [mscorlib]System.Type returnType, string methodName, class [mscorlib]System.Type[] argTypes, string[] argNames, valuetype [mscorlib]System.Reflection.MethodAttributes methodAttributes)
0x87919  ldarg.3
0x8791a  callvirt instance class System.Xml.Serialization.ElementAccessor System.Xml.Serialization.XmlMapping::get_Accessor()
0x8791f  callvirt instance bool System.Xml.Serialization.Accessor::get_Any()
0x87924  brfalse.s loc_87963
0x87926  ldarg.0
0x87927  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x8792c  ldc.i4.1
0x8792d  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldc(bool boolVar)
0x87932  ldarg.0
0x87933  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x87938  ldarg.0
0x87939  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x8793e  callvirt instance class [mscorlib]System.Reflection.Emit.LocalBuilder System.Xml.Serialization.CodeGenerator::get_ReturnLocal()
0x87943  callvirt instance void System.Xml.Serialization.CodeGenerator::Stloc(class [mscorlib]System.Reflection.Emit.LocalBuilder local)
0x87948  ldarg.0
0x87949  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x8794e  ldarg.0
0x8794f  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x87954  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Serialization.CodeGenerator::get_ReturnLabel()
0x87959  callvirt instance void System.Xml.Serialization.CodeGenerator::Br(valuetype [mscorlib]System.Reflection.Emit.Label label)
0x8795e  br       loc_87A1E
0x87963  ldtoken  System.Xml.XmlReader
0x87968  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x8796d  ldstr    aIsstartelement// "IsStartElement"
0x87972  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x87977  ldnull
0x87978  ldc.i4.2
0x87979  newarr   [mscorlib]System.Type
0x8797e  dup
0x8797f  ldc.i4.0
0x87980  ldtoken  [mscorlib]System.String
0x87985  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x8798a  stelem.ref
0x8798b  dup
0x8798c  ldc.i4.1
0x8798d  ldtoken  [mscorlib]System.String
0x87992  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x87997  stelem.ref
0x87998  ldnull
0x87999  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x8799e  stloc.3
0x8799f  ldarg.0
0x879a0  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x879a5  ldarg.0
0x879a6  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x879ab  ldstr    aXmlreader// "xmlReader"
0x879b0  callvirt instance class System.Xml.Serialization.ArgBuilder System.Xml.Serialization.CodeGenerator::GetArg(string name)
0x879b5  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(class System.Xml.Serialization.ArgBuilder arg)
0x879ba  ldarg.0
0x879bb  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x879c0  ldarg.3
0x879c1  callvirt instance class System.Xml.Serialization.ElementAccessor System.Xml.Serialization.XmlMapping::get_Accessor()
0x879c6  callvirt instance string System.Xml.Serialization.Accessor::get_Name()
0x879cb  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldstr(string strVar)
0x879d0  ldarg.0
0x879d1  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x879d6  ldarg.3
0x879d7  callvirt instance class System.Xml.Serialization.ElementAccessor System.Xml.Serialization.XmlMapping::get_Accessor()
0x879dc  callvirt instance string System.Xml.Serialization.Accessor::get_Namespace()
0x879e1  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldstr(string strVar)
0x879e6  ldarg.0
0x879e7  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x879ec  ldloc.3
0x879ed  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x879f2  ldarg.0
0x879f3  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x879f8  ldarg.0
0x879f9  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x879fe  callvirt instance class [mscorlib]System.Reflection.Emit.LocalBuilder System.Xml.Serialization.CodeGenerator::get_ReturnLocal()
0x87a03  callvirt instance void System.Xml.Serialization.CodeGenerator::Stloc(class [mscorlib]System.Reflection.Emit.LocalBuilder local)
0x87a08  ldarg.0
0x87a09  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x87a0e  ldarg.0
0x87a0f  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x87a14  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Serialization.CodeGenerator::get_ReturnLabel()
0x87a19  callvirt instance void System.Xml.Serialization.CodeGenerator::Br(valuetype [mscorlib]System.Reflection.Emit.Label label)
0x87a1e  ldarg.0
0x87a1f  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x87a24  ldarg.0
0x87a25  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x87a2a  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Serialization.CodeGenerator::get_ReturnLabel()
0x87a2f  callvirt instance void System.Xml.Serialization.CodeGenerator::MarkLabel(valuetype [mscorlib]System.Reflection.Emit.Label label)
0x87a34  ldarg.0
0x87a35  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x87a3a  ldarg.0
0x87a3b  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x87a40  callvirt instance class [mscorlib]System.Reflection.Emit.LocalBuilder System.Xml.Serialization.CodeGenerator::get_ReturnLocal()
0x87a45  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldloc(class [mscorlib]System.Reflection.Emit.LocalBuilder localBuilder)
0x87a4a  ldarg.0
0x87a4b  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x87a50  callvirt instance class [mscorlib]System.Reflection.Emit.MethodBuilder System.Xml.Serialization.CodeGenerator::EndMethod()
0x87a55  pop
0x87a56  ldarg.2
0x87a57  brfalse  loc_87B78
0x87a5c  ldarg.0
0x87a5d  ldloc.1
0x87a5e  newobj   instance void System.Xml.Serialization.CodeGenerator::.ctor(class [mscorlib]System.Reflection.Emit.TypeBuilder typeBuilder)
0x87a63  stfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x87a68  ldarg.0
0x87a69  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x87a6e  ldtoken  [mscorlib]System.Void
0x87a73  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x87a78  ldstr    aSerialize// "Serialize"
0x87a7d  ldc.i4.2
0x87a7e  newarr   [mscorlib]System.Type
0x87a83  dup
0x87a84  ldc.i4.0
0x87a85  ldtoken  [mscorlib]System.Object
0x87a8a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x87a8f  stelem.ref
0x87a90  dup
0x87a91  ldc.i4.1
0x87a92  ldtoken  System.Xml.Serialization.XmlSerializationWriter
0x87a97  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x87a9c  stelem.ref
0x87a9d  ldc.i4.2
0x87a9e  newarr   [mscorlib]System.String
0x87aa3  dup
0x87aa4  ldc.i4.0
0x87aa5  ldstr    aObjecttoserial_0// "objectToSerialize"
0x87aaa  stelem.ref
0x87aab  dup
0x87aac  ldc.i4.1
0x87aad  ldstr    aWriter_1// "writer"
0x87ab2  stelem.ref
0x87ab3  ldsfld   valuetype [mscorlib]System.Reflection.MethodAttributes System.Xml.Serialization.CodeGenerator::ProtectedOverrideMethodAttributes
0x87ab8  callvirt instance void System.Xml.Serialization.CodeGenerator::BeginMethod(class [mscorlib]System.Type returnType, string methodName, class [mscorlib]System.Type[] argTypes, string[] argNames, valuetype [mscorlib]System.Reflection.MethodAttributes methodAttributes)
0x87abd  ldarg.0
0x87abe  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Type> System.Xml.Serialization.XmlSerializationILGen::CreatedTypes
0x87ac3  ldarg.s  7
0x87ac5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Type>::get_Item(void)
0x87aca  ldarg.2
0x87acb  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x87ad0  ldnull
0x87ad1  ldc.i4.1
0x87ad2  newarr   [mscorlib]System.Type
0x87ad7  dup
0x87ad8  ldc.i4.0
0x87ad9  ldarg.3
0x87ada  isinst   System.Xml.Serialization.XmlMembersMapping
0x87adf  brtrue.s loc_87AED
0x87ae1  ldtoken  [mscorlib]System.Object
0x87ae6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x87aeb  br.s     loc_87AF7
0x87aed  ldtoken  object[]
0x87af2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x87af7  stelem.ref
0x87af8  ldnull
0x87af9  callvirt instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x87afe  stloc.s  4
0x87b00  ldarg.0
0x87b01  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x87b06  ldstr    aWriter_1// "writer"
0x87b0b  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(string arg)
0x87b10  ldarg.0
0x87b11  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x87b16  ldarg.0
0x87b17  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Type> System.Xml.Serialization.XmlSerializationILGen::CreatedTypes
0x87b1c  ldarg.s  7
0x87b1e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Type>::get_Item(void)
0x87b23  callvirt instance void System.Xml.Serialization.CodeGenerator::Castclass(class [mscorlib]System.Type target)
0x87b28  ldarg.0
0x87b29  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x87b2e  ldstr    aObjecttoserial_0// "objectToSerialize"
0x87b33  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(string arg)
0x87b38  ldarg.3
0x87b39  isinst   System.Xml.Serialization.XmlMembersMapping
0x87b3e  brfalse.s loc_87B5F
0x87b40  ldarg.0
0x87b41  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x87b46  ldtoken  [mscorlib]System.Object
0x87b4b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x87b50  ldtoken  object[]
0x87b55  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x87b5a  callvirt instance void System.Xml.Serialization.CodeGenerator::ConvertValue(class [mscorlib]System.Type source, class [mscorlib]System.Type target)
0x87b5f  ldarg.0
0x87b60  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x87b65  ldloc.s  4
0x87b67  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x87b6c  ldarg.0
0x87b6d  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x87b72  callvirt instance class [mscorlib]System.Reflection.Emit.MethodBuilder System.Xml.Serialization.CodeGenerator::EndMethod()
0x87b77  pop
0x87b78  ldarg.1
0x87b79  brfalse  loc_87C2C
0x87b7e  ldarg.0
0x87b7f  ldloc.1
0x87b80  newobj   instance void System.Xml.Serialization.CodeGenerator::.ctor(class [mscorlib]System.Reflection.Emit.TypeBuilder typeBuilder)
0x87b85  stfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x87b8a  ldarg.0
0x87b8b  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x87b90  ldtoken  [mscorlib]System.Object
0x87b95  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x87b9a  ldstr    aDeserialize// "Deserialize"
0x87b9f  ldc.i4.1
0x87ba0  newarr   [mscorlib]System.Type
0x87ba5  dup
0x87ba6  ldc.i4.0
0x87ba7  ldtoken  System.Xml.Serialization.XmlSerializationReader
0x87bac  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x87bb1  stelem.ref
0x87bb2  ldc.i4.1
0x87bb3  newarr   [mscorlib]System.String
0x87bb8  dup
0x87bb9  ldc.i4.0
0x87bba  ldstr    aReader// "reader"
0x87bbf  stelem.ref
0x87bc0  ldsfld   valuetype [mscorlib]System.Reflection.MethodAttributes System.Xml.Serialization.CodeGenerator::ProtectedOverrideMethodAttributes
0x87bc5  callvirt instance void System.Xml.Serialization.CodeGenerator::BeginMethod(class [mscorlib]System.Type returnType, string methodName, class [mscorlib]System.Type[] argTypes, string[] argNames, valuetype [mscorlib]System.Reflection.MethodAttributes methodAttributes)
0x87bca  ldarg.0
0x87bcb  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Type> System.Xml.Serialization.XmlSerializationILGen::CreatedTypes
0x87bd0  ldarg.s  6
0x87bd2  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Type>::get_Item(void)
0x87bd7  ldarg.1
0x87bd8  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x87bdd  ldnull
0x87bde  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0x87be3  ldnull
0x87be4  callvirt instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x87be9  stloc.s  5
0x87beb  ldarg.0
0x87bec  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x87bf1  ldstr    aReader// "reader"
0x87bf6  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(string arg)
0x87bfb  ldarg.0
0x87bfc  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x87c01  ldarg.0
0x87c02  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Type> System.Xml.Serialization.XmlSerializationILGen::CreatedTypes
0x87c07  ldarg.s  6
0x87c09  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Type>::get_Item(void)
0x87c0e  callvirt instance void System.Xml.Serialization.CodeGenerator::Castclass(class [mscorlib]System.Type target)
0x87c13  ldarg.0
0x87c14  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x87c19  ldloc.s  5
0x87c1b  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x87c20  ldarg.0
0x87c21  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x87c26  callvirt instance class [mscorlib]System.Reflection.Emit.MethodBuilder System.Xml.Serialization.CodeGenerator::EndMethod()
0x87c2b  pop
0x87c2c  ldloc.1
0x87c2d  ldsfld   valuetype [mscorlib]System.Reflection.MethodAttributes System.Xml.Serialization.CodeGenerator::PublicMethodAttributes
0x87c32  callvirt instance class [mscorlib]System.Reflection.Emit.ConstructorBuilder [mscorlib]System.Reflection.Emit.TypeBuilder::DefineDefaultConstructor(valuetype [mscorlib]System.Reflection.MethodAttributes)
0x87c37  pop
0x87c38  ldloc.1
0x87c39  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.Emit.TypeBuilder::CreateType()
0x87c3e  stloc.2
0x87c3f  ldarg.0
0x87c40  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Type> System.Xml.Serialization.XmlSerializationILGen::CreatedTypes
0x87c45  ldloc.2
  ... truncated ...
```
