# System.Xml.Serialization.XmlSerializationWriterILGen::WriteEnumAndArrayTypes

- ea: `0xa5db0`
- end: `0xa62df`
- name: `System.Xml.Serialization.XmlSerializationWriterILGen::WriteEnumAndArrayTypes`
- size: `1327`
- prototype: ``
- caller_count: `1`
- callee_count: `28`
- tags: `registry_config`

## callers

- `0xa62e0`

## callees

- `0x63350`
- `0x63380`
- `0x633f0`
- `0x63410`
- `0x637d0`
- `0x63bc0`
- `0x63c60`
- `0x64260`
- `0x643a0`
- `0x643c0`
- `0x64970`
- `0x64a90`
- `0x64b80`
- `0x68c10`
- `0x68c30`
- `0x68c50`
- `0x68de0`
- `0x72380`
- `0x72bf0`
- `0x72e10`
- `0x74f30`
- `0x871d0`
- `0x87270`
- `0x87300`
- `0xa5db0`
- `0xa74e0`
- `0xa92c0`
- `0xa9300`

## string_xrefs

- `0xa5e36`: `get_Writer`
- `0xa610e`: `get_Writer`
- `0xa5e58`: `WriteStartElement`
- `0xa6130`: `WriteStartElement`
- `0xa603b`: `WriteEndElement`
- `0xa625c`: `WriteEndElement`
- `0xa5edb`: `WriteXsiType`
- `0xa61b3`: `WriteXsiType`
- `0xa5f89`: `WriteString`

## pseudocode

```c

```

## disassembly

```asm
0xa5db0  ldarg.0
0xa5db1  call     instance class System.Xml.Serialization.TypeScope[] System.Xml.Serialization.XmlSerializationILGen::get_Scopes()
0xa5db6  stloc.0
0xa5db7  ldc.i4.0
0xa5db8  stloc.1
0xa5db9  br       loc_A62D5
0xa5dbe  ldloc.0
0xa5dbf  ldloc.1
0xa5dc0  ldelem.ref
0xa5dc1  stloc.2
0xa5dc2  ldloc.2
0xa5dc3  callvirt instance class [mscorlib]System.Collections.ICollection System.Xml.Serialization.TypeScope::get_TypeMappings()
0xa5dc8  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0xa5dcd  stloc.3
0xa5dce  br       loc_A62B0
0xa5dd3  ldloc.3
0xa5dd4  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xa5dd9  castclass System.Xml.Serialization.Mapping
0xa5dde  stloc.s  4
0xa5de0  ldloc.s  4
0xa5de2  isinst   System.Xml.Serialization.EnumMapping
0xa5de7  brfalse  loc_A6089
0xa5dec  ldloc.s  4
0xa5dee  castclass System.Xml.Serialization.EnumMapping
0xa5df3  stloc.s  5
0xa5df5  ldarg.0
0xa5df6  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa5dfb  callvirt instance void System.Xml.Serialization.CodeGenerator::InitElseIf()
0xa5e00  ldarg.0
0xa5e01  ldstr    aT_0// "t"
0xa5e06  ldloc.s  5
0xa5e08  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa5e0d  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeDesc::get_Type()
0xa5e12  call     instance void System.Xml.Serialization.XmlSerializationWriterILGen::WriteTypeCompare(string variable, class [mscorlib]System.Type type)
0xa5e17  ldarg.0
0xa5e18  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa5e1d  callvirt instance void System.Xml.Serialization.CodeGenerator::AndIf()
0xa5e22  ldarg.0
0xa5e23  ldloc.s  5
0xa5e25  call     instance string System.Xml.Serialization.XmlSerializationILGen::ReferenceMapping(class System.Xml.Serialization.TypeMapping mapping)
0xa5e2a  stloc.s  6
0xa5e2c  ldtoken  System.Xml.Serialization.XmlSerializationWriter
0xa5e31  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa5e36  ldstr    aGetWriter// "get_Writer"
0xa5e3b  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0xa5e40  ldnull
0xa5e41  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0xa5e46  ldnull
0xa5e47  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0xa5e4c  stloc.s  7
0xa5e4e  ldtoken  System.Xml.XmlWriter
0xa5e53  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa5e58  ldstr    aWritestartelem// "WriteStartElement"
0xa5e5d  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0xa5e62  ldnull
0xa5e63  ldc.i4.2
0xa5e64  newarr   [mscorlib]System.Type
0xa5e69  dup
0xa5e6a  ldc.i4.0
0xa5e6b  ldtoken  [mscorlib]System.String
0xa5e70  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa5e75  stelem.ref
0xa5e76  dup
0xa5e77  ldc.i4.1
0xa5e78  ldtoken  [mscorlib]System.String
0xa5e7d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa5e82  stelem.ref
0xa5e83  ldnull
0xa5e84  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0xa5e89  stloc.s  8
0xa5e8b  ldarg.0
0xa5e8c  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa5e91  ldc.i4.0
0xa5e92  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(int32 slot)
0xa5e97  ldarg.0
0xa5e98  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa5e9d  ldloc.s  7
0xa5e9f  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0xa5ea4  ldarg.0
0xa5ea5  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa5eaa  ldstr    aN_0// "n"
0xa5eaf  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(string arg)
0xa5eb4  ldarg.0
0xa5eb5  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa5eba  ldstr    aNs// "ns"
0xa5ebf  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(string arg)
0xa5ec4  ldarg.0
0xa5ec5  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa5eca  ldloc.s  8
0xa5ecc  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0xa5ed1  ldtoken  System.Xml.Serialization.XmlSerializationWriter
0xa5ed6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa5edb  ldstr    aWritexsitype_0// "WriteXsiType"
0xa5ee0  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0xa5ee5  ldnull
0xa5ee6  ldc.i4.2
0xa5ee7  newarr   [mscorlib]System.Type
0xa5eec  dup
0xa5eed  ldc.i4.0
0xa5eee  ldtoken  [mscorlib]System.String
0xa5ef3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa5ef8  stelem.ref
0xa5ef9  dup
0xa5efa  ldc.i4.1
0xa5efb  ldtoken  [mscorlib]System.String
0xa5f00  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa5f05  stelem.ref
0xa5f06  ldnull
0xa5f07  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0xa5f0c  stloc.s  9
0xa5f0e  ldarg.0
0xa5f0f  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa5f14  ldc.i4.0
0xa5f15  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(int32 slot)
0xa5f1a  ldarg.0
0xa5f1b  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa5f20  ldloc.s  5
0xa5f22  callvirt instance string System.Xml.Serialization.TypeMapping::get_TypeName()
0xa5f27  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldstr(string strVar)
0xa5f2c  ldarg.0
0xa5f2d  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa5f32  ldloc.s  5
0xa5f34  callvirt instance string System.Xml.Serialization.TypeMapping::get_Namespace()
0xa5f39  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldstr(string strVar)
0xa5f3e  ldarg.0
0xa5f3f  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa5f44  ldloc.s  9
0xa5f46  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0xa5f4b  ldarg.0
0xa5f4c  ldarg.0
0xa5f4d  ldfld    class [mscorlib]System.Reflection.Emit.TypeBuilder System.Xml.Serialization.XmlSerializationILGen::typeBuilder
0xa5f52  ldloc.s  6
0xa5f54  ldsfld   valuetype [mscorlib]System.Reflection.MethodAttributes System.Xml.Serialization.CodeGenerator::PrivateMethodAttributes
0xa5f59  ldtoken  [mscorlib]System.String
0xa5f5e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa5f63  ldc.i4.1
0xa5f64  newarr   [mscorlib]System.Type
0xa5f69  dup
0xa5f6a  ldc.i4.0
0xa5f6b  ldloc.s  5
0xa5f6d  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa5f72  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeDesc::get_Type()
0xa5f77  stelem.ref
0xa5f78  call     instance class [mscorlib]System.Reflection.Emit.MethodBuilder System.Xml.Serialization.XmlSerializationILGen::EnsureMethodBuilder(class [mscorlib]System.Reflection.Emit.TypeBuilder typeBuilder, string methodName, valuetype [mscorlib]System.Reflection.MethodAttributes attributes, class [mscorlib]System.Type returnType, class [mscorlib]System.Type[] parameterTypes)
0xa5f7d  stloc.s  0xA
0xa5f7f  ldtoken  System.Xml.XmlWriter
0xa5f84  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa5f89  ldstr    aWritestring// "WriteString"
0xa5f8e  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0xa5f93  ldnull
0xa5f94  ldc.i4.1
0xa5f95  newarr   [mscorlib]System.Type
0xa5f9a  dup
0xa5f9b  ldc.i4.0
0xa5f9c  ldtoken  [mscorlib]System.String
0xa5fa1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa5fa6  stelem.ref
0xa5fa7  ldnull
0xa5fa8  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0xa5fad  stloc.s  0xB
0xa5faf  ldarg.0
0xa5fb0  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa5fb5  ldc.i4.0
0xa5fb6  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(int32 slot)
0xa5fbb  ldarg.0
0xa5fbc  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa5fc1  ldloc.s  7
0xa5fc3  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0xa5fc8  ldarg.0
0xa5fc9  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa5fce  ldstr    aO_0// "o"
0xa5fd3  callvirt instance object System.Xml.Serialization.CodeGenerator::GetVariable(string name)
0xa5fd8  stloc.s  0xC
0xa5fda  ldarg.0
0xa5fdb  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa5fe0  ldc.i4.0
0xa5fe1  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(int32 slot)
0xa5fe6  ldarg.0
0xa5fe7  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa5fec  ldloc.s  0xC
0xa5fee  callvirt instance void System.Xml.Serialization.CodeGenerator::Load(object obj)
0xa5ff3  ldarg.0
0xa5ff4  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa5ff9  ldarg.0
0xa5ffa  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa5fff  ldloc.s  0xC
0xa6001  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.CodeGenerator::GetVariableType(object var)
0xa6006  ldloc.s  5
0xa6008  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa600d  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeDesc::get_Type()
0xa6012  callvirt instance void System.Xml.Serialization.CodeGenerator::ConvertValue(class [mscorlib]System.Type source, class [mscorlib]System.Type target)
0xa6017  ldarg.0
0xa6018  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa601d  ldloc.s  0xA
0xa601f  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0xa6024  ldarg.0
0xa6025  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa602a  ldloc.s  0xB
0xa602c  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0xa6031  ldtoken  System.Xml.XmlWriter
0xa6036  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa603b  ldstr    aWriteendelemen_1// "WriteEndElement"
0xa6040  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0xa6045  ldnull
0xa6046  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0xa604b  ldnull
0xa604c  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0xa6051  stloc.s  0xD
0xa6053  ldarg.0
0xa6054  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa6059  ldc.i4.0
0xa605a  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(int32 slot)
0xa605f  ldarg.0
0xa6060  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa6065  ldloc.s  7
0xa6067  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0xa606c  ldarg.0
0xa606d  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa6072  ldloc.s  0xD
0xa6074  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0xa6079  ldarg.0
0xa607a  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa607f  callvirt instance void System.Xml.Serialization.CodeGenerator::GotoMethodEnd()
0xa6084  br       loc_A62B0
0xa6089  ldloc.s  4
0xa608b  isinst   System.Xml.Serialization.ArrayMapping
0xa6090  brfalse  loc_A62B0
0xa6095  ldloc.s  4
0xa6097  isinst   System.Xml.Serialization.ArrayMapping
0xa609c  stloc.s  0xE
0xa609e  ldloc.s  0xE
0xa60a0  brfalse  loc_A62B0
0xa60a5  ldarg.0
0xa60a6  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa60ab  callvirt instance void System.Xml.Serialization.CodeGenerator::InitElseIf()
0xa60b0  ldloc.s  0xE
0xa60b2  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa60b7  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsArray()
0xa60bc  brfalse.s loc_A60D7
0xa60be  ldarg.0
0xa60bf  ldstr    aT_0// "t"
0xa60c4  ldloc.s  0xE
0xa60c6  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa60cb  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeDesc::get_Type()
0xa60d0  call     instance void System.Xml.Serialization.XmlSerializationWriterILGen::WriteArrayTypeCompare(string variable, class [mscorlib]System.Type arrayType)
0xa60d5  br.s     loc_A60EE
0xa60d7  ldarg.0
0xa60d8  ldstr    aT_0// "t"
0xa60dd  ldloc.s  0xE
0xa60df  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa60e4  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeDesc::get_Type()
0xa60e9  call     instance void System.Xml.Serialization.XmlSerializationWriterILGen::WriteTypeCompare(string variable, class [mscorlib]System.Type type)
0xa60ee  ldarg.0
0xa60ef  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa60f4  callvirt instance void System.Xml.Serialization.CodeGenerator::AndIf()
0xa60f9  ldarg.0
0xa60fa  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa60ff  callvirt instance void System.Xml.Serialization.CodeGenerator::EnterScope()
0xa6104  ldtoken  System.Xml.Serialization.XmlSerializationWriter
0xa6109  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa610e  ldstr    aGetWriter// "get_Writer"
0xa6113  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0xa6118  ldnull
0xa6119  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0xa611e  ldnull
0xa611f  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0xa6124  stloc.s  0xF
0xa6126  ldtoken  System.Xml.XmlWriter
0xa612b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa6130  ldstr    aWritestartelem// "WriteStartElement"
0xa6135  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0xa613a  ldnull
0xa613b  ldc.i4.2
0xa613c  newarr   [mscorlib]System.Type
0xa6141  dup
0xa6142  ldc.i4.0
0xa6143  ldtoken  [mscorlib]System.String
0xa6148  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa614d  stelem.ref
0xa614e  dup
0xa614f  ldc.i4.1
0xa6150  ldtoken  [mscorlib]System.String
0xa6155  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa615a  stelem.ref
0xa615b  ldnull
0xa615c  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0xa6161  stloc.s  0x10
0xa6163  ldarg.0
0xa6164  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa6169  ldc.i4.0
0xa616a  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(int32 slot)
0xa616f  ldarg.0
0xa6170  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa6175  ldloc.s  0xF
0xa6177  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0xa617c  ldarg.0
0xa617d  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa6182  ldstr    aN_0// "n"
0xa6187  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(string arg)
0xa618c  ldarg.0
  ... truncated ...
```
