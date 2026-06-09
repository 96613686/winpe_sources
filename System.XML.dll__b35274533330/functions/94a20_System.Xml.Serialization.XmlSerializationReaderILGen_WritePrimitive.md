# System.Xml.Serialization.XmlSerializationReaderILGen::WritePrimitive

- ea: `0x94a20`
- end: `0x951d3`
- name: `System.Xml.Serialization.XmlSerializationReaderILGen::WritePrimitive`
- size: `1971`
- prototype: ``
- caller_count: `3`
- callee_count: `17`
- tags: `registry_config`

## callers

- `0x97a90`
- `0x98590`
- `0x99a60`

## callees

- `0x622f0`
- `0x63290`
- `0x632b0`
- `0x637d0`
- `0x63890`
- `0x640d0`
- `0x643c0`
- `0x68c50`
- `0x72b80`
- `0x72bf0`
- `0x72c00`
- `0x72cc0`
- `0x72cf0`
- `0x871a0`
- `0x87270`
- `0x87300`
- `0x94a20`

## string_xrefs

- `0x94af0`: `ReadElementString`
- `0x94c8f`: `ReadElementString`
- `0x94e95`: `ReadElementString`
- `0x950bb`: `ReadElementString`
- `0x94fd0`: `XmlQualifiedName`
- `0x94abb`: `get_Reader`
- `0x94b47`: `get_Reader`
- `0x94c59`: `get_Reader`
- `0x94ce5`: `get_Reader`
- `0x94e66`: `get_Reader`
- `0x95085`: `get_Reader`
- `0x95115`: `get_Reader`
- `0x94a36`: `XmlMissingMethodEnum`
- `0x94b31`: `Reader.Value`
- `0x94ccf`: `Reader.Value`
- `0x94e89`: `Reader.Value`
- `0x950ff`: `Reader.Value`
- `0x94aa5`: `Reader.ReadString()`
- `0x94c43`: `Reader.ReadString()`
- `0x9506c`: `Reader.ReadString()`
- `0x94a98`: `Reader.ReadElementString()`
- `0x94add`: `Reader.ReadElementString()`
- `0x94c36`: `Reader.ReadElementString()`
- `0x94c7c`: `Reader.ReadElementString()`
- `0x9505f`: `Reader.ReadElementString()`
- `0x950a8`: `Reader.ReadElementString()`
- `0x94ae9`: `ReadString`
- `0x94c88`: `ReadString`
- `0x950b4`: `ReadString`

## pseudocode

```c

```

## disassembly

```asm
0x94a20  ldarg.1
0x94a21  isinst   System.Xml.Serialization.EnumMapping
0x94a26  brfalse  loc_94C24
0x94a2b  ldarg.0
0x94a2c  ldarg.1
0x94a2d  call     instance string System.Xml.Serialization.XmlSerializationILGen::ReferenceMapping(class System.Xml.Serialization.TypeMapping mapping)
0x94a32  stloc.0
0x94a33  ldloc.0
0x94a34  brtrue.s loc_94A5A
0x94a36  ldstr    aXmlmissingmeth// "XmlMissingMethodEnum"
0x94a3b  ldc.i4.1
0x94a3c  newarr   [mscorlib]System.Object
0x94a41  dup
0x94a42  ldc.i4.0
0x94a43  ldarg.1
0x94a44  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x94a49  callvirt instance string System.Xml.Serialization.TypeDesc::get_Name()
0x94a4e  stelem.ref
0x94a4f  call     string System.Xml.Res::GetString(string name, object[] args)
0x94a54  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x94a59  throw
0x94a5a  ldarg.0
0x94a5b  ldarg.0
0x94a5c  ldfld    class [mscorlib]System.Reflection.Emit.TypeBuilder System.Xml.Serialization.XmlSerializationILGen::typeBuilder
0x94a61  ldloc.0
0x94a62  ldsfld   valuetype [mscorlib]System.Reflection.MethodAttributes System.Xml.Serialization.CodeGenerator::PrivateMethodAttributes
0x94a67  ldarg.1
0x94a68  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x94a6d  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeDesc::get_Type()
0x94a72  ldc.i4.1
0x94a73  newarr   [mscorlib]System.Type
0x94a78  dup
0x94a79  ldc.i4.0
0x94a7a  ldtoken  [mscorlib]System.String
0x94a7f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x94a84  stelem.ref
0x94a85  call     instance class [mscorlib]System.Reflection.Emit.MethodBuilder System.Xml.Serialization.XmlSerializationILGen::EnsureMethodBuilder(class [mscorlib]System.Reflection.Emit.TypeBuilder typeBuilder, string methodName, valuetype [mscorlib]System.Reflection.MethodAttributes attributes, class [mscorlib]System.Type returnType, class [mscorlib]System.Type[] parameterTypes)
0x94a8a  stloc.1
0x94a8b  ldarg.0
0x94a8c  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x94a91  ldc.i4.0
0x94a92  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(int32 slot)
0x94a97  ldarg.2
0x94a98  ldstr    aReaderReadelem// "Reader.ReadElementString()"
0x94a9d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x94aa2  brtrue.s loc_94AB1
0x94aa4  ldarg.2
0x94aa5  ldstr    aReaderReadstri// "Reader.ReadString()"
0x94aaa  call     bool [mscorlib]System.String::op_Equality(string, string)
0x94aaf  brfalse.s loc_94B30
0x94ab1  ldtoken  System.Xml.Serialization.XmlSerializationReader
0x94ab6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x94abb  ldstr    aGetReader// "get_Reader"
0x94ac0  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x94ac5  ldnull
0x94ac6  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0x94acb  ldnull
0x94acc  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x94ad1  stloc.2
0x94ad2  ldtoken  System.Xml.XmlReader
0x94ad7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x94adc  ldarg.2
0x94add  ldstr    aReaderReadelem// "Reader.ReadElementString()"
0x94ae2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x94ae7  brtrue.s loc_94AF0
0x94ae9  ldstr    aReadstring// "ReadString"
0x94aee  br.s     loc_94AF5
0x94af0  ldstr    aReadelementstr// "ReadElementString"
0x94af5  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x94afa  ldnull
0x94afb  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0x94b00  ldnull
0x94b01  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x94b06  stloc.3
0x94b07  ldarg.0
0x94b08  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x94b0d  ldc.i4.0
0x94b0e  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(int32 slot)
0x94b13  ldarg.0
0x94b14  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x94b19  ldloc.2
0x94b1a  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x94b1f  ldarg.0
0x94b20  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x94b25  ldloc.3
0x94b26  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x94b2b  br       loc_94C17
0x94b30  ldarg.2
0x94b31  ldstr    aReaderValue// "Reader.Value"
0x94b36  call     bool [mscorlib]System.String::op_Equality(string, string)
0x94b3b  brfalse.s loc_94BA9
0x94b3d  ldtoken  System.Xml.Serialization.XmlSerializationReader
0x94b42  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x94b47  ldstr    aGetReader// "get_Reader"
0x94b4c  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x94b51  ldnull
0x94b52  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0x94b57  ldnull
0x94b58  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x94b5d  stloc.s  4
0x94b5f  ldtoken  System.Xml.XmlReader
0x94b64  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x94b69  ldstr    aGetValue// "get_Value"
0x94b6e  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x94b73  ldnull
0x94b74  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0x94b79  ldnull
0x94b7a  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x94b7f  stloc.s  5
0x94b81  ldarg.0
0x94b82  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x94b87  ldc.i4.0
0x94b88  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(int32 slot)
0x94b8d  ldarg.0
0x94b8e  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x94b93  ldloc.s  4
0x94b95  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x94b9a  ldarg.0
0x94b9b  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x94ba0  ldloc.s  5
0x94ba2  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x94ba7  br.s     loc_94C17
0x94ba9  ldarg.2
0x94baa  ldstr    aValsI// "vals[i]"
0x94baf  call     bool [mscorlib]System.String::op_Equality(string, string)
0x94bb4  brfalse.s loc_94BEB
0x94bb6  ldarg.0
0x94bb7  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x94bbc  ldstr    aVals// "vals"
0x94bc1  callvirt instance class [mscorlib]System.Reflection.Emit.LocalBuilder System.Xml.Serialization.CodeGenerator::GetLocal(string name)
0x94bc6  stloc.s  6
0x94bc8  ldarg.0
0x94bc9  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x94bce  ldstr    aI// "i"
0x94bd3  callvirt instance class [mscorlib]System.Reflection.Emit.LocalBuilder System.Xml.Serialization.CodeGenerator::GetLocal(string name)
0x94bd8  stloc.s  7
0x94bda  ldarg.0
0x94bdb  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x94be0  ldloc.s  6
0x94be2  ldloc.s  7
0x94be4  callvirt instance void System.Xml.Serialization.CodeGenerator::LoadArrayElement(object obj, object arrayIndex)
0x94be9  br.s     loc_94C17
0x94beb  ldarg.2
0x94bec  ldstr    aFalse// "false"
0x94bf1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x94bf6  brfalse.s loc_94C06
0x94bf8  ldarg.0
0x94bf9  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x94bfe  ldc.i4.0
0x94bff  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldc(bool boolVar)
0x94c04  br.s     loc_94C17
0x94c06  ldstr    aUnexpected// "Unexpected: "
0x94c0b  ldarg.2
0x94c0c  call     string [mscorlib]System.String::Concat(string, string)
0x94c11  call     class [mscorlib]System.Exception System.Xml.Serialization.CodeGenerator::NotSupported(string msg)
0x94c16  throw
0x94c17  ldarg.0
0x94c18  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x94c1d  ldloc.1
0x94c1e  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x94c23  ret
0x94c24  ldarg.1
0x94c25  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x94c2a  ldarg.0
0x94c2b  call     instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.XmlSerializationILGen::get_StringTypeDesc()
0x94c30  bne.un   loc_94D98
0x94c35  ldarg.2
0x94c36  ldstr    aReaderReadelem// "Reader.ReadElementString()"
0x94c3b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x94c40  brtrue.s loc_94C4F
0x94c42  ldarg.2
0x94c43  ldstr    aReaderReadstri// "Reader.ReadString()"
0x94c48  call     bool [mscorlib]System.String::op_Equality(string, string)
0x94c4d  brfalse.s loc_94CCE
0x94c4f  ldtoken  System.Xml.Serialization.XmlSerializationReader
0x94c54  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x94c59  ldstr    aGetReader// "get_Reader"
0x94c5e  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x94c63  ldnull
0x94c64  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0x94c69  ldnull
0x94c6a  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x94c6f  stloc.s  8
0x94c71  ldtoken  System.Xml.XmlReader
0x94c76  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x94c7b  ldarg.2
0x94c7c  ldstr    aReaderReadelem// "Reader.ReadElementString()"
0x94c81  call     bool [mscorlib]System.String::op_Equality(string, string)
0x94c86  brtrue.s loc_94C8F
0x94c88  ldstr    aReadstring// "ReadString"
0x94c8d  br.s     loc_94C94
0x94c8f  ldstr    aReadelementstr// "ReadElementString"
0x94c94  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x94c99  ldnull
0x94c9a  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0x94c9f  ldnull
0x94ca0  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x94ca5  stloc.s  9
0x94ca7  ldarg.0
0x94ca8  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x94cad  ldc.i4.0
0x94cae  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(int32 slot)
0x94cb3  ldarg.0
0x94cb4  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x94cb9  ldloc.s  8
0x94cbb  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x94cc0  ldarg.0
0x94cc1  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x94cc6  ldloc.s  9
0x94cc8  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x94ccd  ret
0x94cce  ldarg.2
0x94ccf  ldstr    aReaderValue// "Reader.Value"
0x94cd4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x94cd9  brfalse.s loc_94D46
0x94cdb  ldtoken  System.Xml.Serialization.XmlSerializationReader
0x94ce0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x94ce5  ldstr    aGetReader// "get_Reader"
0x94cea  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x94cef  ldnull
0x94cf0  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0x94cf5  ldnull
0x94cf6  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x94cfb  stloc.s  0xA
0x94cfd  ldtoken  System.Xml.XmlReader
0x94d02  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x94d07  ldstr    aGetValue// "get_Value"
0x94d0c  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x94d11  ldnull
0x94d12  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0x94d17  ldnull
0x94d18  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x94d1d  stloc.s  0xB
0x94d1f  ldarg.0
0x94d20  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x94d25  ldc.i4.0
0x94d26  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(int32 slot)
0x94d2b  ldarg.0
0x94d2c  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x94d31  ldloc.s  0xA
0x94d33  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x94d38  ldarg.0
0x94d39  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x94d3e  ldloc.s  0xB
0x94d40  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x94d45  ret
0x94d46  ldarg.2
0x94d47  ldstr    aValsI// "vals[i]"
0x94d4c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x94d51  brfalse.s loc_94D87
0x94d53  ldarg.0
0x94d54  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x94d59  ldstr    aVals// "vals"
0x94d5e  callvirt instance class [mscorlib]System.Reflection.Emit.LocalBuilder System.Xml.Serialization.CodeGenerator::GetLocal(string name)
0x94d63  stloc.s  0xC
0x94d65  ldarg.0
0x94d66  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x94d6b  ldstr    aI// "i"
0x94d70  callvirt instance class [mscorlib]System.Reflection.Emit.LocalBuilder System.Xml.Serialization.CodeGenerator::GetLocal(string name)
0x94d75  stloc.s  0xD
0x94d77  ldarg.0
0x94d78  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x94d7d  ldloc.s  0xC
0x94d7f  ldloc.s  0xD
0x94d81  callvirt instance void System.Xml.Serialization.CodeGenerator::LoadArrayElement(object obj, object arrayIndex)
0x94d86  ret
0x94d87  ldstr    aUnexpected// "Unexpected: "
0x94d8c  ldarg.2
0x94d8d  call     string [mscorlib]System.String::Concat(string, string)
0x94d92  call     class [mscorlib]System.Exception System.Xml.Serialization.CodeGenerator::NotSupported(string msg)
0x94d97  throw
0x94d98  ldarg.1
0x94d99  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x94d9e  callvirt instance string System.Xml.Serialization.TypeDesc::get_FormatterName()
0x94da3  ldstr    aString_0// "String"
0x94da8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x94dad  brfalse  loc_94F41
0x94db2  ldarg.2
0x94db3  ldstr    aValsI// "vals[i]"
0x94db8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x94dbd  brfalse  loc_94E5C
0x94dc2  ldarg.1
0x94dc3  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x94dc8  callvirt instance bool System.Xml.Serialization.TypeDesc::get_CollapseWhitespace()
0x94dcd  brfalse.s loc_94DDB
0x94dcf  ldarg.0
0x94dd0  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x94dd5  ldc.i4.0
0x94dd6  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(int32 slot)
0x94ddb  ldarg.0
0x94ddc  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x94de1  ldstr    aVals// "vals"
0x94de6  callvirt instance class [mscorlib]System.Reflection.Emit.LocalBuilder System.Xml.Serialization.CodeGenerator::GetLocal(string name)
0x94deb  stloc.s  0xE
0x94ded  ldarg.0
0x94dee  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x94df3  ldstr    aI// "i"
0x94df8  callvirt instance class [mscorlib]System.Reflection.Emit.LocalBuilder System.Xml.Serialization.CodeGenerator::GetLocal(string name)
0x94dfd  stloc.s  0xF
0x94dff  ldarg.0
  ... truncated ...
```
