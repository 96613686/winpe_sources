# System.Xml.Serialization.XmlSerializationWriterILGen::WriteAttribute

- ea: `0xa7380`
- end: `0xa74bb`
- name: `System.Xml.Serialization.XmlSerializationWriterILGen::WriteAttribute`
- size: `315`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config`

## callers

- `0xa6c70`

## callees

- `0x62370`
- `0x632a0`
- `0x637d0`
- `0x63c60`
- `0x642d0`
- `0x643a0`
- `0x643c0`
- `0x68600`
- `0x68620`
- `0x68660`
- `0x686d0`
- `0x686f0`
- `0x68c50`
- `0x723c0`
- `0x72c10`
- `0x72c30`
- `0xa48f0`
- `0xa7380`
- `0xa74c0`

## string_xrefs

- `0xa7453`: `XmlInternalError`
- `0xa7479`: `WriteAttribute`
- `0xa73c5`: `WriteXmlAttribute`

## pseudocode

```c

```

## disassembly

```asm
0xa7380  ldarg.2
0xa7381  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa7386  isinst   System.Xml.Serialization.SpecialMapping
0xa738b  brfalse  loc_A7463
0xa7390  ldarg.2
0xa7391  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa7396  castclass System.Xml.Serialization.SpecialMapping
0xa739b  stloc.0
0xa739c  ldloc.0
0xa739d  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa73a2  callvirt instance valuetype System.Xml.Serialization.TypeKind System.Xml.Serialization.TypeDesc::get_Kind()
0xa73a7  ldc.i4.s 0xA
0xa73a9  beq.s    loc_A73BB
0xa73ab  ldloc.0
0xa73ac  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa73b1  callvirt instance bool System.Xml.Serialization.TypeDesc::get_CanBeAttributeValue()
0xa73b6  brfalse  loc_A7453
0xa73bb  ldtoken  System.Xml.Serialization.XmlSerializationWriter
0xa73c0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa73c5  ldstr    aWritexmlattrib_0// "WriteXmlAttribute"
0xa73ca  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0xa73cf  ldnull
0xa73d0  ldc.i4.2
0xa73d1  newarr   [mscorlib]System.Type
0xa73d6  dup
0xa73d7  ldc.i4.0
0xa73d8  ldtoken  System.Xml.XmlNode
0xa73dd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa73e2  stelem.ref
0xa73e3  dup
0xa73e4  ldc.i4.1
0xa73e5  ldtoken  [mscorlib]System.Object
0xa73ea  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa73ef  stelem.ref
0xa73f0  ldnull
0xa73f1  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0xa73f6  stloc.1
0xa73f7  ldarg.0
0xa73f8  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa73fd  ldc.i4.0
0xa73fe  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(int32 slot)
0xa7403  ldarg.0
0xa7404  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa7409  ldarg.1
0xa740a  ldfld    string System.Xml.Serialization.SourceInfo::Source
0xa740f  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldloc(string name)
0xa7414  ldarg.0
0xa7415  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa741a  ldarg.3
0xa741b  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(string arg)
0xa7420  ldarg.0
0xa7421  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa7426  ldarg.0
0xa7427  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa742c  ldarg.3
0xa742d  callvirt instance class System.Xml.Serialization.ArgBuilder System.Xml.Serialization.CodeGenerator::GetArg(string name)
0xa7432  ldfld    class [mscorlib]System.Type System.Xml.Serialization.ArgBuilder::ArgType
0xa7437  ldtoken  [mscorlib]System.Object
0xa743c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa7441  callvirt instance void System.Xml.Serialization.CodeGenerator::ConvertValue(class [mscorlib]System.Type source, class [mscorlib]System.Type target)
0xa7446  ldarg.0
0xa7447  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa744c  ldloc.1
0xa744d  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0xa7452  ret
0xa7453  ldstr    aXmlinternalerr// "XmlInternalError"
0xa7458  call     string System.Xml.Res::GetString(string name)
0xa745d  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xa7462  throw
0xa7463  ldarg.2
0xa7464  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa7469  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa746e  stloc.2
0xa746f  ldarg.1
0xa7470  ldloc.2
0xa7471  callvirt instance class System.Xml.Serialization.SourceInfo System.Xml.Serialization.SourceInfo::CastTo(class System.Xml.Serialization.TypeDesc td)
0xa7476  starg.s  1
0xa7478  ldarg.0
0xa7479  ldstr    aWriteattribute_0// "WriteAttribute"
0xa747e  ldarg.2
0xa747f  callvirt instance string System.Xml.Serialization.Accessor::get_Name()
0xa7484  ldarg.2
0xa7485  callvirt instance valuetype System.Xml.Schema.XmlSchemaForm System.Xml.Serialization.Accessor::get_Form()
0xa748a  ldc.i4.1
0xa748b  beq.s    loc_A7494
0xa748d  ldstr    asc_1284AE// ""
0xa7492  br.s     loc_A749A
0xa7494  ldarg.2
0xa7495  callvirt instance string System.Xml.Serialization.Accessor::get_Namespace()
0xa749a  ldarg.1
0xa749b  ldfld    class [mscorlib]System.Type System.Xml.Serialization.SourceInfo::Type
0xa74a0  ldarg.2
0xa74a1  callvirt instance object System.Xml.Serialization.Accessor::get_Default()
0xa74a6  call     object System.Xml.Serialization.XmlSerializationWriterILGen::GetConvertedDefaultValue(class [mscorlib]System.Type targetType, object rawDefaultValue)
0xa74ab  ldarg.1
0xa74ac  ldarg.2
0xa74ad  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa74b2  ldc.i4.0
0xa74b3  ldc.i4.0
0xa74b4  ldc.i4.0
0xa74b5  call     instance void System.Xml.Serialization.XmlSerializationWriterILGen::WritePrimitive(string method, string name, string ns, object defaultValue, class System.Xml.Serialization.SourceInfo source, class System.Xml.Serialization.TypeMapping mapping, bool writeXsiType, bool isElement, bool isNullable)
0xa74ba  ret
```
