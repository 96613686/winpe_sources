# System.Xml.Serialization.XmlSerializationWriterILGen::WriteQualifiedNameElement

- ea: `0xa4690`
- end: `0xa476a`
- name: `System.Xml.Serialization.XmlSerializationWriterILGen::WriteQualifiedNameElement`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0xa8750`

## callees

- `0x63290`
- `0x637d0`
- `0x64260`
- `0x643c0`
- `0x68c50`
- `0x72430`
- `0x72bf0`
- `0xa4690`

## string_xrefs

- `0xa4730`: `WriteElementQualifiedName`
- `0xa46a5`: `XmlQualifiedName DefaultValue not supported.  Fail in WriteValue()`
- `0xa475e`: `XmlQualifiedName DefaultValue not supported.  Fail in WriteValue()`
- `0xa4737`: `WriteNullableQualifiedNameLiteral`

## pseudocode

```c

```

## disassembly

```asm
0xa4690  ldarg.3
0xa4691  brfalse.s loc_A46A0
0xa4693  ldarg.3
0xa4694  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xa4699  ceq
0xa469b  ldc.i4.0
0xa469c  ceq
0xa469e  br.s     loc_A46A1
0xa46a0  ldc.i4.0
0xa46a1  stloc.0
0xa46a2  ldloc.0
0xa46a3  brfalse.s loc_A46B0
0xa46a5  ldstr    aXmlqualifiedna_0// "XmlQualifiedName DefaultValue not suppo"...
0xa46aa  call     class [mscorlib]System.Exception System.Xml.Serialization.CodeGenerator::NotSupported(string msg)
0xa46af  throw
0xa46b0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Type>::.ctor()
0xa46b5  stloc.1
0xa46b6  ldarg.0
0xa46b7  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa46bc  ldc.i4.0
0xa46bd  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldarg(int32 slot)
0xa46c2  ldarg.0
0xa46c3  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa46c8  ldarg.1
0xa46c9  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldstr(string strVar)
0xa46ce  ldloc.1
0xa46cf  ldtoken  [mscorlib]System.String
0xa46d4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa46d9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Type>::Add(var<u1>)
0xa46de  ldarg.2
0xa46df  brfalse.s loc_A46FD
0xa46e1  ldarg.0
0xa46e2  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa46e7  ldarg.2
0xa46e8  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldstr(string strVar)
0xa46ed  ldloc.1
0xa46ee  ldtoken  [mscorlib]System.String
0xa46f3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa46f8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Type>::Add(var<u1>)
0xa46fd  ldarg.s  4
0xa46ff  ldarg.s  6
0xa4701  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa4706  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeDesc::get_Type()
0xa470b  callvirt instance void System.Xml.Serialization.SourceInfo::Load(class [mscorlib]System.Type elementType)
0xa4710  ldloc.1
0xa4711  ldarg.s  6
0xa4713  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa4718  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeDesc::get_Type()
0xa471d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Type>::Add(var<u1>)
0xa4722  ldtoken  System.Xml.Serialization.XmlSerializationWriter
0xa4727  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa472c  ldarg.s  5
0xa472e  brtrue.s loc_A4737
0xa4730  ldstr    aWriteelementqu// "WriteElementQualifiedName"
0xa4735  br.s     loc_A473C
0xa4737  ldstr    aWritenullableq_0// "WriteNullableQualifiedNameLiteral"
0xa473c  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0xa4741  ldnull
0xa4742  ldloc.1
0xa4743  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Type>::ToArray()
0xa4748  ldnull
0xa4749  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0xa474e  stloc.2
0xa474f  ldarg.0
0xa4750  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa4755  ldloc.2
0xa4756  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0xa475b  ldloc.0
0xa475c  brfalse.s loc_A4769
0xa475e  ldstr    aXmlqualifiedna_0// "XmlQualifiedName DefaultValue not suppo"...
0xa4763  call     class [mscorlib]System.Exception System.Xml.Serialization.CodeGenerator::NotSupported(string msg)
0xa4768  throw
0xa4769  ret
```
