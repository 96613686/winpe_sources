# System.Xml.Serialization.XmlSerializationReaderILGen::WriteDerivedSerializable

- ea: `0x9a530`
- end: `0x9a92c`
- name: `System.Xml.Serialization.XmlSerializationReaderILGen::WriteDerivedSerializable`
- size: `1020`
- prototype: ``
- caller_count: `2`
- callee_count: `31`
- tags: `registry_config`

## callers

- `0x99a60`
- `0x9a530`

## callees

- `0x13310`
- `0x13320`
- `0x632b0`
- `0x637d0`
- `0x63bc0`
- `0x63c60`
- `0x63d40`
- `0x63dc0`
- `0x640d0`
- `0x64260`
- `0x642b0`
- `0x643c0`
- `0x645a0`
- `0x645b0`
- `0x64640`
- `0x646a0`
- `0x64970`
- `0x64a90`
- `0x68c50`
- `0x69ff0`
- `0x6a000`
- `0x6a030`
- `0x6a070`
- `0x72bf0`
- `0x72d40`
- `0x87190`
- `0x96f50`
- `0x991b0`
- `0x99470`
- `0x9a530`
- `0xa9640`

## string_xrefs

- `0x9a63d`: `ReadSerializable`
- `0x9a74f`: `CreateBadDerivationException`
- `0x9a86d`: `CreateMissingIXmlSerializableType`

## pseudocode

```c

```

## disassembly

```asm
0x9a530  ldarg.2
0x9a531  brtrue.s loc_9A534
0x9a533  ret
0x9a534  ldarg.2
0x9a535  callvirt instance class System.Xml.Serialization.SerializableMapping System.Xml.Serialization.SerializableMapping::get_DerivedMappings()
0x9a53a  stloc.0
0x9a53b  br       loc_9A925
0x9a540  ldarg.0
0x9a541  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9a546  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Serialization.CodeGenerator::DefineLabel()
0x9a54b  stloc.1
0x9a54c  ldarg.0
0x9a54d  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9a552  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Serialization.CodeGenerator::DefineLabel()
0x9a557  stloc.2
0x9a558  ldarg.0
0x9a559  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9a55e  ldstr    aTser// "tser"
0x9a563  callvirt instance class [mscorlib]System.Reflection.Emit.LocalBuilder System.Xml.Serialization.CodeGenerator::GetLocal(string name)
0x9a568  stloc.3
0x9a569  ldarg.0
0x9a56a  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9a56f  callvirt instance void System.Xml.Serialization.CodeGenerator::InitElseIf()
0x9a574  ldarg.0
0x9a575  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9a57a  ldloc.3
0x9a57b  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldloc(class [mscorlib]System.Reflection.Emit.LocalBuilder localBuilder)
0x9a580  ldarg.0
0x9a581  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9a586  ldnull
0x9a587  callvirt instance void System.Xml.Serialization.CodeGenerator::Load(object obj)
0x9a58c  ldarg.0
0x9a58d  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9a592  callvirt instance void System.Xml.Serialization.CodeGenerator::Ceq()
0x9a597  ldarg.0
0x9a598  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9a59d  ldloc.1
0x9a59e  callvirt instance void System.Xml.Serialization.CodeGenerator::Brtrue(valuetype [mscorlib]System.Reflection.Emit.Label label)
0x9a5a3  ldarg.0
0x9a5a4  ldstr    aTser// "tser"
0x9a5a9  ldloc.0
0x9a5aa  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Serialization.SerializableMapping::get_XsiType()
0x9a5af  callvirt instance string System.Xml.XmlQualifiedName::get_Name()
0x9a5b4  ldloc.0
0x9a5b5  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Serialization.SerializableMapping::get_XsiType()
0x9a5ba  callvirt instance string System.Xml.XmlQualifiedName::get_Namespace()
0x9a5bf  call     instance void System.Xml.Serialization.XmlSerializationReaderILGen::WriteQNameEqual(string source, string name, string ns)
0x9a5c4  ldarg.0
0x9a5c5  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9a5ca  ldloc.2
0x9a5cb  callvirt instance void System.Xml.Serialization.CodeGenerator::Br_S(valuetype [mscorlib]System.Reflection.Emit.Label label)
0x9a5d0  ldarg.0
0x9a5d1  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9a5d6  ldloc.1
0x9a5d7  callvirt instance void System.Xml.Serialization.CodeGenerator::MarkLabel(valuetype [mscorlib]System.Reflection.Emit.Label label)
0x9a5dc  ldarg.0
0x9a5dd  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9a5e2  ldc.i4.1
0x9a5e3  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldc(bool boolVar)
0x9a5e8  ldarg.0
0x9a5e9  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9a5ee  ldloc.2
0x9a5ef  callvirt instance void System.Xml.Serialization.CodeGenerator::MarkLabel(valuetype [mscorlib]System.Reflection.Emit.Label label)
0x9a5f4  ldarg.0
0x9a5f5  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9a5fa  callvirt instance void System.Xml.Serialization.CodeGenerator::AndIf()
0x9a5ff  ldloc.0
0x9a600  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.SerializableMapping::get_Type()
0x9a605  ldnull
0x9a606  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x9a60b  brfalse  loc_9A863
0x9a610  ldarg.1
0x9a611  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.SerializableMapping::get_Type()
0x9a616  ldloc.0
0x9a617  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.SerializableMapping::get_Type()
0x9a61c  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0x9a621  brfalse  loc_9A745
0x9a626  ldarg.0
0x9a627  ldarg.3
0x9a628  ldarg.1
0x9a629  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x9a62e  call     instance void System.Xml.Serialization.XmlSerializationReaderILGen::WriteSourceBeginTyped(string source, class System.Xml.Serialization.TypeDesc typeDesc)
0x9a633  ldtoken  System.Xml.Serialization.XmlSerializationReader
0x9a638  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9a63d  ldstr    aReadserializab_0// "ReadSerializable"
0x9a642  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x9a647  ldnull
0x9a648  ldarg.s  4
0x9a64a  brtrue.s loc_9A661
0x9a64c  ldc.i4.1
0x9a64d  newarr   [mscorlib]System.Type
0x9a652  dup
0x9a653  ldc.i4.0
0x9a654  ldtoken  System.Xml.Serialization.IXmlSerializable
0x9a659  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9a65e  stelem.ref
0x9a65f  br.s     loc_9A681
0x9a661  ldc.i4.2
0x9a662  newarr   [mscorlib]System.Type
0x9a667  dup
0x9a668  ldc.i4.0
0x9a669  ldtoken  System.Xml.Serialization.IXmlSerializable
0x9a66e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9a673  stelem.ref
0x9a674  dup
0x9a675  ldc.i4.1
0x9a676  ldtoken  [mscorlib]System.Boolean
0x9a67b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9a680  stelem.ref
0x9a681  ldnull
0x9a682  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x9a687  stloc.s  4
0x9a689  ldarg.0
0x9a68a  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9a68f  ldc.i4.0
0x9a690  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(int32 slot)
0x9a695  ldarg.0
0x9a696  call     instance class System.Xml.Serialization.ReflectionAwareILGen System.Xml.Serialization.XmlSerializationILGen::get_RaCodeGen()
0x9a69b  ldarg.0
0x9a69c  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9a6a1  ldloc.0
0x9a6a2  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x9a6a7  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeDesc::get_Type()
0x9a6ac  ldloc.0
0x9a6ad  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x9a6b2  callvirt instance bool System.Xml.Serialization.TypeDesc::get_CannotNew()
0x9a6b7  ldc.i4.0
0x9a6b8  callvirt instance void System.Xml.Serialization.ReflectionAwareILGen::ILGenForCreateInstance(class System.Xml.Serialization.CodeGenerator ilg, class [mscorlib]System.Type type, bool ctorInaccessible, bool cast)
0x9a6bd  ldloc.0
0x9a6be  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x9a6c3  callvirt instance bool System.Xml.Serialization.TypeDesc::get_CannotNew()
0x9a6c8  brfalse.s loc_9A6E9
0x9a6ca  ldarg.0
0x9a6cb  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9a6d0  ldtoken  [mscorlib]System.Object
0x9a6d5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9a6da  ldtoken  System.Xml.Serialization.IXmlSerializable
0x9a6df  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9a6e4  callvirt instance void System.Xml.Serialization.CodeGenerator::ConvertValue(class [mscorlib]System.Type source, class [mscorlib]System.Type target)
0x9a6e9  ldarg.s  4
0x9a6eb  brfalse.s loc_9A6F9
0x9a6ed  ldarg.0
0x9a6ee  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9a6f3  ldc.i4.1
0x9a6f4  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldc(bool boolVar)
0x9a6f9  ldarg.0
0x9a6fa  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9a6ff  ldloc.s  4
0x9a701  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x9a706  ldarg.1
0x9a707  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x9a70c  brfalse.s loc_9A72E
0x9a70e  ldarg.0
0x9a70f  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9a714  ldtoken  System.Xml.Serialization.IXmlSerializable
0x9a719  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9a71e  ldarg.1
0x9a71f  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x9a724  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeDesc::get_Type()
0x9a729  callvirt instance void System.Xml.Serialization.CodeGenerator::ConvertValue(class [mscorlib]System.Type source, class [mscorlib]System.Type target)
0x9a72e  ldarg.0
0x9a72f  ldarg.3
0x9a730  ldarg.1
0x9a731  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x9a736  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeDesc::get_Type()
0x9a73b  call     instance void System.Xml.Serialization.XmlSerializationReaderILGen::WriteSourceEnd(string source, class [mscorlib]System.Type elementType)
0x9a740  br       loc_9A913
0x9a745  ldtoken  System.Xml.Serialization.XmlSerializationReader
0x9a74a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9a74f  ldstr    aCreatebadderiv// "CreateBadDerivationException"
0x9a754  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x9a759  ldnull
0x9a75a  ldc.i4.6
0x9a75b  newarr   [mscorlib]System.Type
0x9a760  dup
0x9a761  ldc.i4.0
0x9a762  ldtoken  [mscorlib]System.String
0x9a767  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9a76c  stelem.ref
0x9a76d  dup
0x9a76e  ldc.i4.1
0x9a76f  ldtoken  [mscorlib]System.String
0x9a774  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9a779  stelem.ref
0x9a77a  dup
0x9a77b  ldc.i4.2
0x9a77c  ldtoken  [mscorlib]System.String
0x9a781  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9a786  stelem.ref
0x9a787  dup
0x9a788  ldc.i4.3
0x9a789  ldtoken  [mscorlib]System.String
0x9a78e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9a793  stelem.ref
0x9a794  dup
0x9a795  ldc.i4.4
0x9a796  ldtoken  [mscorlib]System.String
0x9a79b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9a7a0  stelem.ref
0x9a7a1  dup
0x9a7a2  ldc.i4.5
0x9a7a3  ldtoken  [mscorlib]System.String
0x9a7a8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9a7ad  stelem.ref
0x9a7ae  ldnull
0x9a7af  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x9a7b4  stloc.s  5
0x9a7b6  ldarg.0
0x9a7b7  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9a7bc  ldc.i4.0
0x9a7bd  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(int32 slot)
0x9a7c2  ldarg.0
0x9a7c3  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9a7c8  ldloc.0
0x9a7c9  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Serialization.SerializableMapping::get_XsiType()
0x9a7ce  callvirt instance string System.Xml.XmlQualifiedName::get_Name()
0x9a7d3  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldstr(string strVar)
0x9a7d8  ldarg.0
0x9a7d9  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9a7de  ldloc.0
0x9a7df  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Serialization.SerializableMapping::get_XsiType()
0x9a7e4  callvirt instance string System.Xml.XmlQualifiedName::get_Namespace()
0x9a7e9  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldstr(string strVar)
0x9a7ee  ldarg.0
0x9a7ef  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9a7f4  ldarg.1
0x9a7f5  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Serialization.SerializableMapping::get_XsiType()
0x9a7fa  callvirt instance string System.Xml.XmlQualifiedName::get_Name()
0x9a7ff  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldstr(string strVar)
0x9a804  ldarg.0
0x9a805  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9a80a  ldarg.1
0x9a80b  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Serialization.SerializableMapping::get_XsiType()
0x9a810  callvirt instance string System.Xml.XmlQualifiedName::get_Namespace()
0x9a815  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldstr(string strVar)
0x9a81a  ldarg.0
0x9a81b  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9a820  ldloc.0
0x9a821  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.SerializableMapping::get_Type()
0x9a826  callvirt instance string [mscorlib]System.Type::get_FullName()
0x9a82b  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldstr(string strVar)
0x9a830  ldarg.0
0x9a831  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9a836  ldarg.1
0x9a837  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.SerializableMapping::get_Type()
0x9a83c  callvirt instance string [mscorlib]System.Type::get_FullName()
0x9a841  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldstr(string strVar)
0x9a846  ldarg.0
0x9a847  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9a84c  ldloc.s  5
0x9a84e  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0x9a853  ldarg.0
0x9a854  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9a859  callvirt instance void System.Xml.Serialization.CodeGenerator::Throw()
0x9a85e  br       loc_9A913
0x9a863  ldtoken  System.Xml.Serialization.XmlSerializationReader
0x9a868  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9a86d  ldstr    aCreatemissingi// "CreateMissingIXmlSerializableType"
0x9a872  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0x9a877  ldnull
0x9a878  ldc.i4.3
0x9a879  newarr   [mscorlib]System.Type
0x9a87e  dup
0x9a87f  ldc.i4.0
0x9a880  ldtoken  [mscorlib]System.String
0x9a885  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9a88a  stelem.ref
0x9a88b  dup
0x9a88c  ldc.i4.1
0x9a88d  ldtoken  [mscorlib]System.String
0x9a892  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9a897  stelem.ref
0x9a898  dup
0x9a899  ldc.i4.2
0x9a89a  ldtoken  [mscorlib]System.String
0x9a89f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9a8a4  stelem.ref
0x9a8a5  ldnull
0x9a8a6  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x9a8ab  stloc.s  6
0x9a8ad  ldarg.0
0x9a8ae  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9a8b3  ldc.i4.0
0x9a8b4  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(int32 slot)
0x9a8b9  ldarg.0
0x9a8ba  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9a8bf  ldloc.0
0x9a8c0  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Serialization.SerializableMapping::get_XsiType()
0x9a8c5  callvirt instance string System.Xml.XmlQualifiedName::get_Name()
0x9a8ca  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldstr(string strVar)
0x9a8cf  ldarg.0
0x9a8d0  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9a8d5  ldloc.0
0x9a8d6  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Serialization.SerializableMapping::get_XsiType()
0x9a8db  callvirt instance string System.Xml.XmlQualifiedName::get_Namespace()
0x9a8e0  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldstr(string strVar)
0x9a8e5  ldarg.0
0x9a8e6  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0x9a8eb  ldarg.1
0x9a8ec  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.SerializableMapping::get_Type()
  ... truncated ...
```
