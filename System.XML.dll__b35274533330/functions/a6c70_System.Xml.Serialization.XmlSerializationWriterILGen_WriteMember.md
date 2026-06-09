# System.Xml.Serialization.XmlSerializationWriterILGen::WriteMember

- ea: `0xa6c70`
- end: `0xa7376`
- name: `System.Xml.Serialization.XmlSerializationWriterILGen::WriteMember`
- size: `1798`
- prototype: ``
- caller_count: `2`
- callee_count: `41`
- tags: `registry_config`

## callers

- `0xa4d30`
- `0xa62e0`

## callees

- `0x63290`
- `0x632b0`
- `0x634c0`
- `0x634e0`
- `0x63540`
- `0x63640`
- `0x636f0`
- `0x637d0`
- `0x63830`
- `0x63bc0`
- `0x64100`
- `0x64260`
- `0x642d0`
- `0x64320`
- `0x64340`
- `0x643c0`
- `0x646c0`
- `0x68600`
- `0x68660`
- `0x686d0`
- `0x686f0`
- `0x68a60`
- `0x72380`
- `0x72b80`
- `0x72ba0`
- `0x72bf0`
- `0x72d60`
- `0x72dd0`
- `0x72e00`
- `0x72e10`
- `0x72e40`
- `0x72fd0`
- `0x87190`
- `0xa4770`
- `0xa47e0`
- `0xa6c50`
- `0xa6c70`
- `0xa7380`
- `0xa9280`
- `0xa92a0`
- `0xa9600`

## string_xrefs

- `0xa6d2d`: `get_Writer`
- `0xa6f3b`: `get_Writer`
- `0xa71a0`: `get_Writer`
- `0xa7325`: `WriteAttribute`
- `0xa6f5d`: `WriteString`
- `0xa6d4f`: `WriteStartAttribute`
- `0xa6e44`: `CDF15337, DDB176069: Also fail in whidbey IEnumerable member with XmlAttributeAttribute`
- `0xa7167`: `CDF15337, DDB176069: Also fail in whidbey IEnumerable member with XmlAttributeAttribute`
- `0xa6fd0`: `WriteValue`
- `0xa71c2`: `WriteEndAttribute`

## pseudocode

```c

```

## disassembly

```asm
0xa6c70  ldarg.3
0xa6c71  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsAbstract()
0xa6c76  brfalse.s loc_A6C79
0xa6c78  ret
0xa6c79  ldarg.3
0xa6c7a  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsArrayLike()
0xa6c7f  brfalse  loc_A736B
0xa6c84  ldstr    aA_0// "a"
0xa6c89  ldarg.3
0xa6c8a  callvirt instance string System.Xml.Serialization.TypeDesc::get_Name()
0xa6c8f  call     string [mscorlib]System.String::Concat(string, string)
0xa6c94  stloc.0
0xa6c95  ldstr    aAi// "ai"
0xa6c9a  ldarg.3
0xa6c9b  callvirt instance string System.Xml.Serialization.TypeDesc::get_Name()
0xa6ca0  call     string [mscorlib]System.String::Concat(string, string)
0xa6ca5  stloc.1
0xa6ca6  ldstr    aI// "i"
0xa6cab  stloc.2
0xa6cac  ldarg.3
0xa6cad  callvirt instance string System.Xml.Serialization.TypeDesc::get_CSharpName()
0xa6cb2  stloc.3
0xa6cb3  ldarg.0
0xa6cb4  ldloc.3
0xa6cb5  ldloc.0
0xa6cb6  ldarg.1
0xa6cb7  ldarg.3
0xa6cb8  call     instance void System.Xml.Serialization.XmlSerializationWriterILGen::WriteArrayLocalDecl(string typeName, string variableName, class System.Xml.Serialization.SourceInfo initValue, class System.Xml.Serialization.TypeDesc arrayTypeDesc)
0xa6cbd  ldarg.3
0xa6cbe  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsNullable()
0xa6cc3  brfalse.s loc_A6CEF
0xa6cc5  ldarg.0
0xa6cc6  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa6ccb  ldarg.3
0xa6ccc  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeDesc::get_Type()
0xa6cd1  ldloc.0
0xa6cd2  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldloc(class [mscorlib]System.Type type, string name)
0xa6cd7  ldarg.0
0xa6cd8  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa6cdd  ldnull
0xa6cde  callvirt instance void System.Xml.Serialization.CodeGenerator::Load(object obj)
0xa6ce3  ldarg.0
0xa6ce4  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa6ce9  ldc.i4.4
0xa6cea  callvirt instance void System.Xml.Serialization.CodeGenerator::If(valuetype System.Xml.Serialization.Cmp cmpOp)
0xa6cef  ldarg.2
0xa6cf0  callvirt instance bool System.Xml.Serialization.AttributeAccessor::get_IsList()
0xa6cf5  brfalse  loc_A6E34
0xa6cfa  ldarg.0
0xa6cfb  ldarg.3
0xa6cfc  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeDesc::get_ArrayElementTypeDesc()
0xa6d01  call     instance bool System.Xml.Serialization.XmlSerializationWriterILGen::CanOptimizeWriteListSequence(class System.Xml.Serialization.TypeDesc listElementTypeDesc)
0xa6d06  brfalse  loc_A6DE1
0xa6d0b  ldarg.2
0xa6d0c  callvirt instance valuetype System.Xml.Schema.XmlSchemaForm System.Xml.Serialization.Accessor::get_Form()
0xa6d11  ldc.i4.1
0xa6d12  beq.s    loc_A6D1B
0xa6d14  ldsfld   string [mscorlib]System.String::Empty
0xa6d19  br.s     loc_A6D21
0xa6d1b  ldarg.2
0xa6d1c  callvirt instance string System.Xml.Serialization.Accessor::get_Namespace()
0xa6d21  stloc.s  5
0xa6d23  ldtoken  System.Xml.Serialization.XmlSerializationWriter
0xa6d28  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa6d2d  ldstr    aGetWriter// "get_Writer"
0xa6d32  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0xa6d37  ldnull
0xa6d38  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0xa6d3d  ldnull
0xa6d3e  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0xa6d43  stloc.s  6
0xa6d45  ldtoken  System.Xml.XmlWriter
0xa6d4a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa6d4f  ldstr    aWritestartattr// "WriteStartAttribute"
0xa6d54  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0xa6d59  ldnull
0xa6d5a  ldc.i4.3
0xa6d5b  newarr   [mscorlib]System.Type
0xa6d60  dup
0xa6d61  ldc.i4.0
0xa6d62  ldtoken  [mscorlib]System.String
0xa6d67  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa6d6c  stelem.ref
0xa6d6d  dup
0xa6d6e  ldc.i4.1
0xa6d6f  ldtoken  [mscorlib]System.String
0xa6d74  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa6d79  stelem.ref
0xa6d7a  dup
0xa6d7b  ldc.i4.2
0xa6d7c  ldtoken  [mscorlib]System.String
0xa6d81  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa6d86  stelem.ref
0xa6d87  ldnull
0xa6d88  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0xa6d8d  stloc.s  7
0xa6d8f  ldarg.0
0xa6d90  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa6d95  ldc.i4.0
0xa6d96  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(int32 slot)
0xa6d9b  ldarg.0
0xa6d9c  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa6da1  ldloc.s  6
0xa6da3  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0xa6da8  ldarg.0
0xa6da9  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa6dae  ldnull
0xa6daf  callvirt instance void System.Xml.Serialization.CodeGenerator::Load(object obj)
0xa6db4  ldarg.0
0xa6db5  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa6dba  ldarg.2
0xa6dbb  callvirt instance string System.Xml.Serialization.Accessor::get_Name()
0xa6dc0  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldstr(string strVar)
0xa6dc5  ldarg.0
0xa6dc6  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa6dcb  ldloc.s  5
0xa6dcd  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldstr(string strVar)
0xa6dd2  ldarg.0
0xa6dd3  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa6dd8  ldloc.s  7
0xa6dda  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0xa6ddf  br.s     loc_A6E34
0xa6de1  ldarg.0
0xa6de2  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa6de7  ldtoken  [mscorlib]System.Text.StringBuilder
0xa6dec  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa6df1  ldstr    aSb// "sb"
0xa6df6  callvirt instance class [mscorlib]System.Reflection.Emit.LocalBuilder System.Xml.Serialization.CodeGenerator::DeclareOrGetLocal(class [mscorlib]System.Type type, string name)
0xa6dfb  stloc.s  8
0xa6dfd  ldtoken  [mscorlib]System.Text.StringBuilder
0xa6e02  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa6e07  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0xa6e0c  ldnull
0xa6e0d  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0xa6e12  ldnull
0xa6e13  call     instance class [mscorlib]System.Reflection.ConstructorInfo [mscorlib]System.Type::GetConstructor(valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0xa6e18  stloc.s  9
0xa6e1a  ldarg.0
0xa6e1b  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa6e20  ldloc.s  9
0xa6e22  callvirt instance void System.Xml.Serialization.CodeGenerator::New(class [mscorlib]System.Reflection.ConstructorInfo constructorInfo)
0xa6e27  ldarg.0
0xa6e28  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa6e2d  ldloc.s  8
0xa6e2f  callvirt instance void System.Xml.Serialization.CodeGenerator::Stloc(class [mscorlib]System.Reflection.Emit.LocalBuilder local)
0xa6e34  ldarg.3
0xa6e35  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeDesc::get_ArrayElementTypeDesc()
0xa6e3a  stloc.s  4
0xa6e3c  ldarg.3
0xa6e3d  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsEnumerable()
0xa6e42  brfalse.s loc_A6E4F
0xa6e44  ldstr    aCdf15337Ddb176// "CDF15337, DDB176069: Also fail in whidb"...
0xa6e49  call     class [mscorlib]System.Exception System.Xml.Serialization.CodeGenerator::NotSupported(string msg)
0xa6e4e  throw
0xa6e4f  ldarg.3
0xa6e50  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsArray()
0xa6e55  brfalse.s loc_A6E91
0xa6e57  ldarg.0
0xa6e58  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa6e5d  ldtoken  [mscorlib]System.Int32
0xa6e62  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa6e67  ldloc.2
0xa6e68  callvirt instance class [mscorlib]System.Reflection.Emit.LocalBuilder System.Xml.Serialization.CodeGenerator::DeclareOrGetLocal(class [mscorlib]System.Type type, string name)
0xa6e6d  stloc.s  0xA
0xa6e6f  ldarg.0
0xa6e70  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa6e75  ldloc.s  0xA
0xa6e77  ldc.i4.0
0xa6e78  box      [mscorlib]System.Int32
0xa6e7d  ldarg.0
0xa6e7e  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa6e83  ldloc.0
0xa6e84  callvirt instance class [mscorlib]System.Reflection.Emit.LocalBuilder System.Xml.Serialization.CodeGenerator::GetLocal(string name)
0xa6e89  callvirt instance object System.Xml.Serialization.CodeGenerator::For(class [mscorlib]System.Reflection.Emit.LocalBuilder local, object start, object end)
0xa6e8e  pop
0xa6e8f  br.s     loc_A6EC9
0xa6e91  ldarg.0
0xa6e92  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa6e97  ldtoken  [mscorlib]System.Int32
0xa6e9c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa6ea1  ldloc.2
0xa6ea2  callvirt instance class [mscorlib]System.Reflection.Emit.LocalBuilder System.Xml.Serialization.CodeGenerator::DeclareOrGetLocal(class [mscorlib]System.Type type, string name)
0xa6ea7  stloc.s  0xB
0xa6ea9  ldarg.0
0xa6eaa  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa6eaf  ldloc.s  0xB
0xa6eb1  ldc.i4.0
0xa6eb2  box      [mscorlib]System.Int32
0xa6eb7  ldarg.0
0xa6eb8  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa6ebd  ldloc.0
0xa6ebe  callvirt instance class [mscorlib]System.Reflection.Emit.LocalBuilder System.Xml.Serialization.CodeGenerator::GetLocal(string name)
0xa6ec3  callvirt instance object System.Xml.Serialization.CodeGenerator::For(class [mscorlib]System.Reflection.Emit.LocalBuilder local, object start, object end)
0xa6ec8  pop
0xa6ec9  ldarg.0
0xa6eca  ldloc.1
0xa6ecb  ldarg.0
0xa6ecc  call     instance class System.Xml.Serialization.ReflectionAwareILGen System.Xml.Serialization.XmlSerializationILGen::get_RaCodeGen()
0xa6ed1  ldloc.0
0xa6ed2  ldloc.2
0xa6ed3  ldarg.3
0xa6ed4  callvirt instance string System.Xml.Serialization.ReflectionAwareILGen::GetStringForArrayMember(string arrayName, string subscript, class System.Xml.Serialization.TypeDesc arrayTypeDesc)
0xa6ed9  ldloc.s  4
0xa6edb  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeDesc::get_Type()
0xa6ee0  call     instance void System.Xml.Serialization.XmlSerializationWriterILGen::WriteLocalDecl(string variableName, string initValue, class [mscorlib]System.Type type)
0xa6ee5  ldarg.2
0xa6ee6  callvirt instance bool System.Xml.Serialization.AttributeAccessor::get_IsList()
0xa6eeb  brfalse  loc_A7147
0xa6ef0  ldtoken  [mscorlib]System.String
0xa6ef5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa6efa  stloc.s  0xE
0xa6efc  ldarg.0
0xa6efd  ldarg.3
0xa6efe  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeDesc::get_ArrayElementTypeDesc()
0xa6f03  call     instance bool System.Xml.Serialization.XmlSerializationWriterILGen::CanOptimizeWriteListSequence(class System.Xml.Serialization.TypeDesc listElementTypeDesc)
0xa6f08  brfalse  loc_A6FE8
0xa6f0d  ldarg.0
0xa6f0e  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa6f13  ldloc.2
0xa6f14  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldloc(string name)
0xa6f19  ldarg.0
0xa6f1a  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa6f1f  ldc.i4.0
0xa6f20  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldc(int32 intVar)
0xa6f25  ldarg.0
0xa6f26  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa6f2b  ldc.i4.4
0xa6f2c  callvirt instance void System.Xml.Serialization.CodeGenerator::If(valuetype System.Xml.Serialization.Cmp cmpOp)
0xa6f31  ldtoken  System.Xml.Serialization.XmlSerializationWriter
0xa6f36  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa6f3b  ldstr    aGetWriter// "get_Writer"
0xa6f40  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0xa6f45  ldnull
0xa6f46  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0xa6f4b  ldnull
0xa6f4c  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0xa6f51  stloc.s  0x10
0xa6f53  ldtoken  System.Xml.XmlWriter
0xa6f58  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa6f5d  ldstr    aWritestring// "WriteString"
0xa6f62  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0xa6f67  ldnull
0xa6f68  ldc.i4.1
0xa6f69  newarr   [mscorlib]System.Type
0xa6f6e  dup
0xa6f6f  ldc.i4.0
0xa6f70  ldtoken  [mscorlib]System.String
0xa6f75  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa6f7a  stelem.ref
0xa6f7b  ldnull
0xa6f7c  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0xa6f81  stloc.s  0x11
0xa6f83  ldarg.0
0xa6f84  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa6f89  ldc.i4.0
0xa6f8a  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(int32 slot)
0xa6f8f  ldarg.0
0xa6f90  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa6f95  ldloc.s  0x10
0xa6f97  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0xa6f9c  ldarg.0
0xa6f9d  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa6fa2  ldstr    asc_129382// " "
0xa6fa7  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldstr(string strVar)
0xa6fac  ldarg.0
0xa6fad  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa6fb2  ldloc.s  0x11
0xa6fb4  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0xa6fb9  ldarg.0
0xa6fba  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa6fbf  callvirt instance void System.Xml.Serialization.CodeGenerator::EndIf()
0xa6fc4  ldarg.0
0xa6fc5  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa6fca  ldc.i4.0
0xa6fcb  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(int32 slot)
0xa6fd0  ldstr    aWritevalue_0// "WriteValue"
0xa6fd5  stloc.s  0xC
0xa6fd7  ldtoken  System.Xml.Serialization.XmlSerializationWriter
0xa6fdc  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa6fe1  stloc.s  0xD
0xa6fe3  br       loc_A70A2
0xa6fe8  ldtoken  [mscorlib]System.Text.StringBuilder
0xa6fed  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa6ff2  ldstr    aAppend// "Append"
0xa6ff7  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0xa6ffc  ldnull
0xa6ffd  ldc.i4.1
0xa6ffe  newarr   [mscorlib]System.Type
0xa7003  dup
0xa7004  ldc.i4.0
0xa7005  ldtoken  [mscorlib]System.String
0xa700a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa700f  stelem.ref
0xa7010  ldnull
0xa7011  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0xa7016  stloc.s  0x12
0xa7018  ldarg.0
0xa7019  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa701e  ldloc.2
0xa701f  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldloc(string name)
  ... truncated ...
```
