# System.Xml.Serialization.XmlSerializationWriterILGen::WriteText

- ea: `0xa8600`
- end: `0xa874e`
- name: `System.Xml.Serialization.XmlSerializationWriterILGen::WriteText`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0xa7b90`

## callees

- `0x62370`
- `0x637d0`
- `0x643c0`
- `0x68600`
- `0x68c50`
- `0x72430`
- `0x72c10`
- `0xa4770`
- `0xa47e0`
- `0xa8600`

## string_xrefs

- `0xa873d`: `XmlInternalError`
- `0xa86f2`: `get_Writer`
- `0xa8661`: `WriteValue`
- `0xa86c2`: `WriteTo`

## pseudocode

```c

```

## disassembly

```asm
0xa8600  ldarg.2
0xa8601  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa8606  isinst   System.Xml.Serialization.PrimitiveMapping
0xa860b  brfalse.s loc_A868A
0xa860d  ldarg.2
0xa860e  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa8613  castclass System.Xml.Serialization.PrimitiveMapping
0xa8618  stloc.0
0xa8619  ldarg.0
0xa861a  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa861f  ldc.i4.0
0xa8620  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(int32 slot)
0xa8625  ldarg.2
0xa8626  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa862b  isinst   System.Xml.Serialization.EnumMapping
0xa8630  brfalse.s loc_A8648
0xa8632  ldarg.0
0xa8633  ldarg.2
0xa8634  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa8639  castclass System.Xml.Serialization.EnumMapping
0xa863e  ldarg.1
0xa863f  ldloca.s 1
0xa8641  call     instance void System.Xml.Serialization.XmlSerializationWriterILGen::WriteEnumValue(class System.Xml.Serialization.EnumMapping mapping, class System.Xml.Serialization.SourceInfo source, [out] class [mscorlib]System.Type& returnType)
0xa8646  br.s     loc_A8657
0xa8648  ldarg.0
0xa8649  ldloc.0
0xa864a  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa864f  ldarg.1
0xa8650  ldloca.s 1
0xa8652  call     instance void System.Xml.Serialization.XmlSerializationWriterILGen::WritePrimitiveValue(class System.Xml.Serialization.TypeDesc typeDesc, class System.Xml.Serialization.SourceInfo source, [out] class [mscorlib]System.Type& returnType)
0xa8657  ldtoken  System.Xml.Serialization.XmlSerializationWriter
0xa865c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa8661  ldstr    aWritevalue_0// "WriteValue"
0xa8666  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0xa866b  ldnull
0xa866c  ldc.i4.1
0xa866d  newarr   [mscorlib]System.Type
0xa8672  dup
0xa8673  ldc.i4.0
0xa8674  ldloc.1
0xa8675  stelem.ref
0xa8676  ldnull
0xa8677  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0xa867c  stloc.2
0xa867d  ldarg.0
0xa867e  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa8683  ldloc.2
0xa8684  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0xa8689  ret
0xa868a  ldarg.2
0xa868b  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa8690  isinst   System.Xml.Serialization.SpecialMapping
0xa8695  brfalse  loc_A874D
0xa869a  ldarg.2
0xa869b  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa86a0  castclass System.Xml.Serialization.SpecialMapping
0xa86a5  stloc.3
0xa86a6  ldloc.3
0xa86a7  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa86ac  callvirt instance valuetype System.Xml.Serialization.TypeKind System.Xml.Serialization.TypeDesc::get_Kind()
0xa86b1  stloc.s  6
0xa86b3  ldloc.s  6
0xa86b5  ldc.i4.s 9
0xa86b7  bne.un   loc_A873D
0xa86bc  ldarg.1
0xa86bd  ldfld    class [mscorlib]System.Type System.Xml.Serialization.SourceInfo::Type
0xa86c2  ldstr    aWriteto// "WriteTo"
0xa86c7  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0xa86cc  ldnull
0xa86cd  ldc.i4.1
0xa86ce  newarr   [mscorlib]System.Type
0xa86d3  dup
0xa86d4  ldc.i4.0
0xa86d5  ldtoken  System.Xml.XmlWriter
0xa86da  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa86df  stelem.ref
0xa86e0  ldnull
0xa86e1  callvirt instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0xa86e6  stloc.s  4
0xa86e8  ldtoken  System.Xml.Serialization.XmlSerializationWriter
0xa86ed  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa86f2  ldstr    aGetWriter// "get_Writer"
0xa86f7  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0xa86fc  ldnull
0xa86fd  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0xa8702  ldnull
0xa8703  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0xa8708  stloc.s  5
0xa870a  ldarg.1
0xa870b  ldarg.1
0xa870c  ldfld    class [mscorlib]System.Type System.Xml.Serialization.SourceInfo::Type
0xa8711  callvirt instance void System.Xml.Serialization.SourceInfo::Load(class [mscorlib]System.Type elementType)
0xa8716  ldarg.0
0xa8717  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa871c  ldc.i4.0
0xa871d  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(int32 slot)
0xa8722  ldarg.0
0xa8723  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa8728  ldloc.s  5
0xa872a  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0xa872f  ldarg.0
0xa8730  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa8735  ldloc.s  4
0xa8737  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0xa873c  ret
0xa873d  ldstr    aXmlinternalerr// "XmlInternalError"
0xa8742  call     string System.Xml.Res::GetString(string name)
0xa8747  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xa874c  throw
0xa874d  ret
```
