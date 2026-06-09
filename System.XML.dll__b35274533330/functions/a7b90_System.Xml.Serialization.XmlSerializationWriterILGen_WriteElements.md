# System.Xml.Serialization.XmlSerializationWriterILGen::WriteElements

- ea: `0xa7b90`
- end: `0xa85f7`
- name: `System.Xml.Serialization.XmlSerializationWriterILGen::WriteElements`
- size: `2663`
- prototype: ``
- caller_count: `2`
- callee_count: `49`
- tags: `registry_config, broker_com_uri`

## callers

- `0xa74e0`
- `0xa77a0`

## callees

- `0x63480`
- `0x63610`
- `0x63640`
- `0x636b0`
- `0x636f0`
- `0x637d0`
- `0x63bc0`
- `0x63d40`
- `0x63d80`
- `0x63dc0`
- `0x640d0`
- `0x64260`
- `0x642b0`
- `0x64320`
- `0x643c0`
- `0x645a0`
- `0x645b0`
- `0x64620`
- `0x64640`
- `0x64680`
- `0x64970`
- `0x649c0`
- `0x649e0`
- `0x64a90`
- `0x64b20`
- `0x64b60`
- `0x68600`
- `0x68660`
- `0x68690`
- `0x686d0`
- `0x688b0`
- `0x688d0`
- `0x68990`
- `0x68c50`
- `0x72380`
- `0x723c0`
- `0x72430`
- `0x72b90`
- `0x72ba0`
- `0x72bf0`
- `0x72d70`
- `0x73000`
- `0x88220`
- `0xa7b90`
- `0xa8600`
- `0xa8750`
- `0xa9050`
- `0xa92e0`
- `0xa9320`

## string_xrefs

- `0xa8583`: `CreateUnknownTypeException`
- `0xa8130`: `get_NamespaceURI`
- `0xa8446`: `get_NamespaceURI`
- `0xa8294`: `CreateChoiceIdentifierValueException`
- `0xa83ce`: `CreateUnknownAnyElementException`

## pseudocode

```c

```

## disassembly

```asm
0xa7b90  ldarg.3
0xa7b91  ldlen
0xa7b92  brtrue.s loc_A7B99
0xa7b94  ldarg.s  4
0xa7b96  brtrue.s loc_A7B99
0xa7b98  ret
0xa7b99  ldarg.3
0xa7b9a  ldlen
0xa7b9b  conv.i4
0xa7b9c  ldc.i4.1
0xa7b9d  bne.un.s loc_A7C05
0xa7b9f  ldarg.s  4
0xa7ba1  brtrue.s loc_A7C05
0xa7ba3  ldarg.3
0xa7ba4  ldc.i4.0
0xa7ba5  ldelem.ref
0xa7ba6  callvirt instance bool System.Xml.Serialization.ElementAccessor::get_IsUnbounded()
0xa7bab  brtrue.s loc_A7BBC
0xa7bad  ldarg.3
0xa7bae  ldc.i4.0
0xa7baf  ldelem.ref
0xa7bb0  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa7bb5  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa7bba  br.s     loc_A7BCE
0xa7bbc  ldarg.3
0xa7bbd  ldc.i4.0
0xa7bbe  ldelem.ref
0xa7bbf  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa7bc4  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa7bc9  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeDesc::CreateArrayTypeDesc()
0xa7bce  stloc.0
0xa7bcf  ldarg.3
0xa7bd0  ldc.i4.0
0xa7bd1  ldelem.ref
0xa7bd2  callvirt instance bool System.Xml.Serialization.Accessor::get_Any()
0xa7bd7  brtrue.s loc_A7BF6
0xa7bd9  ldarg.3
0xa7bda  ldc.i4.0
0xa7bdb  ldelem.ref
0xa7bdc  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa7be1  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa7be6  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsOptionalValue()
0xa7beb  brtrue.s loc_A7BF6
0xa7bed  ldarg.1
0xa7bee  ldloc.0
0xa7bef  callvirt instance class System.Xml.Serialization.SourceInfo System.Xml.Serialization.SourceInfo::CastTo(class System.Xml.Serialization.TypeDesc td)
0xa7bf4  starg.s  1
0xa7bf6  ldarg.0
0xa7bf7  ldarg.1
0xa7bf8  ldarg.3
0xa7bf9  ldc.i4.0
0xa7bfa  ldelem.ref
0xa7bfb  ldarg.s  6
0xa7bfd  ldarg.s  7
0xa7bff  call     instance void System.Xml.Serialization.XmlSerializationWriterILGen::WriteElement(class System.Xml.Serialization.SourceInfo source, class System.Xml.Serialization.ElementAccessor element, string arrayName, bool writeAccessor)
0xa7c04  ret
0xa7c05  ldc.i4.0
0xa7c06  stloc.1
0xa7c07  ldarg.s  8
0xa7c09  brfalse.s loc_A7C39
0xa7c0b  ldarg.s  5
0xa7c0d  brtrue.s loc_A7C39
0xa7c0f  ldarg.1
0xa7c10  ldtoken  [mscorlib]System.Object
0xa7c15  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa7c1a  callvirt instance void System.Xml.Serialization.SourceInfo::Load(class [mscorlib]System.Type elementType)
0xa7c1f  ldarg.0
0xa7c20  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa7c25  ldnull
0xa7c26  callvirt instance void System.Xml.Serialization.CodeGenerator::Load(object obj)
0xa7c2b  ldarg.0
0xa7c2c  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa7c31  ldc.i4.4
0xa7c32  callvirt instance void System.Xml.Serialization.CodeGenerator::If(valuetype System.Xml.Serialization.Cmp cmpOp)
0xa7c37  ldc.i4.1
0xa7c38  stloc.1
0xa7c39  ldc.i4.0
0xa7c3a  stloc.2
0xa7c3b  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0xa7c40  stloc.3
0xa7c41  ldnull
0xa7c42  stloc.s  4
0xa7c44  ldc.i4.0
0xa7c45  stloc.s  5
0xa7c47  ldarg.s  5
0xa7c49  brfalse.s loc_A7C5E
0xa7c4b  ldarg.s  5
0xa7c4d  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa7c52  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa7c57  callvirt instance string System.Xml.Serialization.TypeDesc::get_FullName()
0xa7c5c  br.s     loc_A7C5F
0xa7c5e  ldnull
0xa7c5f  stloc.s  6
0xa7c61  ldc.i4.0
0xa7c62  stloc.s  7
0xa7c64  br       loc_A7ECC
0xa7c69  ldarg.3
0xa7c6a  ldloc.s  7
0xa7c6c  ldelem.ref
0xa7c6d  stloc.s  8
0xa7c6f  ldloc.s  8
0xa7c71  callvirt instance bool System.Xml.Serialization.Accessor::get_Any()
0xa7c76  brfalse.s loc_A7CB2
0xa7c78  ldloc.2
0xa7c79  ldc.i4.1
0xa7c7a  add
0xa7c7b  stloc.2
0xa7c7c  ldloc.s  8
0xa7c7e  callvirt instance string System.Xml.Serialization.Accessor::get_Name()
0xa7c83  brfalse.s loc_A7CA2
0xa7c85  ldloc.s  8
0xa7c87  callvirt instance string System.Xml.Serialization.Accessor::get_Name()
0xa7c8c  callvirt instance int32 [mscorlib]System.String::get_Length()
0xa7c91  ldc.i4.0
0xa7c92  ble.s    loc_A7CA2
0xa7c94  ldloc.3
0xa7c95  ldloc.s  8
0xa7c97  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xa7c9c  pop
0xa7c9d  br       loc_A7EC6
0xa7ca2  ldloc.s  4
0xa7ca4  brtrue   loc_A7EC6
0xa7ca9  ldloc.s  8
0xa7cab  stloc.s  4
0xa7cad  br       loc_A7EC6
0xa7cb2  ldarg.s  5
0xa7cb4  brfalse  loc_A7E34
0xa7cb9  ldloc.s  8
0xa7cbb  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa7cc0  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa7cc5  callvirt instance string System.Xml.Serialization.TypeDesc::get_CSharpName()
0xa7cca  stloc.s  9
0xa7ccc  ldloc.s  6
0xa7cce  ldstr    asc_13444E// ".@"
0xa7cd3  ldarg.0
0xa7cd4  ldloc.s  8
0xa7cd6  ldarg.s  5
0xa7cd8  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa7cdd  castclass System.Xml.Serialization.EnumMapping
0xa7ce2  ldloca.s 0xA
0xa7ce4  call     instance string System.Xml.Serialization.XmlSerializationWriterILGen::FindChoiceEnumValue(class System.Xml.Serialization.ElementAccessor element, class System.Xml.Serialization.EnumMapping choiceMapping, [out] object& eValue)
0xa7ce9  call     string [mscorlib]System.String::Concat(string, string, string)
0xa7cee  stloc.s  0xB
0xa7cf0  ldloc.s  5
0xa7cf2  brfalse.s loc_A7D01
0xa7cf4  ldarg.0
0xa7cf5  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa7cfa  callvirt instance void System.Xml.Serialization.CodeGenerator::InitElseIf()
0xa7cff  br.s     loc_A7D0F
0xa7d01  ldc.i4.1
0xa7d02  stloc.s  5
0xa7d04  ldarg.0
0xa7d05  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa7d0a  callvirt instance void System.Xml.Serialization.CodeGenerator::InitIf()
0xa7d0f  ldarg.0
0xa7d10  ldarg.2
0xa7d11  ldarg.s  5
0xa7d13  brfalse.s loc_A7D28
0xa7d15  ldarg.s  5
0xa7d17  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa7d1c  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa7d21  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeDesc::get_Type()
0xa7d26  br.s     loc_A7D29
0xa7d28  ldnull
0xa7d29  call     instance void System.Xml.Serialization.XmlSerializationILGen::ILGenLoad(string source, class [mscorlib]System.Type type)
0xa7d2e  ldarg.0
0xa7d2f  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa7d34  ldloc.s  0xA
0xa7d36  callvirt instance void System.Xml.Serialization.CodeGenerator::Load(object obj)
0xa7d3b  ldarg.0
0xa7d3c  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa7d41  callvirt instance void System.Xml.Serialization.CodeGenerator::Ceq()
0xa7d46  ldarg.s  8
0xa7d48  brfalse  loc_A7DDA
0xa7d4d  ldloc.s  8
0xa7d4f  callvirt instance bool System.Xml.Serialization.ElementAccessor::get_IsNullable()
0xa7d54  brtrue   loc_A7DDA
0xa7d59  ldarg.0
0xa7d5a  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa7d5f  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Serialization.CodeGenerator::DefineLabel()
0xa7d64  stloc.s  0xD
0xa7d66  ldarg.0
0xa7d67  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa7d6c  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Serialization.CodeGenerator::DefineLabel()
0xa7d71  stloc.s  0xE
0xa7d73  ldarg.0
0xa7d74  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa7d79  ldloc.s  0xD
0xa7d7b  callvirt instance void System.Xml.Serialization.CodeGenerator::Brfalse(valuetype [mscorlib]System.Reflection.Emit.Label label)
0xa7d80  ldarg.1
0xa7d81  ldtoken  [mscorlib]System.Object
0xa7d86  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa7d8b  callvirt instance void System.Xml.Serialization.SourceInfo::Load(class [mscorlib]System.Type elementType)
0xa7d90  ldarg.0
0xa7d91  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa7d96  ldnull
0xa7d97  callvirt instance void System.Xml.Serialization.CodeGenerator::Load(object obj)
0xa7d9c  ldarg.0
0xa7d9d  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa7da2  callvirt instance void System.Xml.Serialization.CodeGenerator::Cne()
0xa7da7  ldarg.0
0xa7da8  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa7dad  ldloc.s  0xE
0xa7daf  callvirt instance void System.Xml.Serialization.CodeGenerator::Br_S(valuetype [mscorlib]System.Reflection.Emit.Label label)
0xa7db4  ldarg.0
0xa7db5  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa7dba  ldloc.s  0xD
0xa7dbc  callvirt instance void System.Xml.Serialization.CodeGenerator::MarkLabel(valuetype [mscorlib]System.Reflection.Emit.Label label)
0xa7dc1  ldarg.0
0xa7dc2  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa7dc7  ldc.i4.0
0xa7dc8  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldc(bool boolVar)
0xa7dcd  ldarg.0
0xa7dce  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa7dd3  ldloc.s  0xE
0xa7dd5  callvirt instance void System.Xml.Serialization.CodeGenerator::MarkLabel(valuetype [mscorlib]System.Reflection.Emit.Label label)
0xa7dda  ldarg.0
0xa7ddb  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa7de0  callvirt instance void System.Xml.Serialization.CodeGenerator::AndIf()
0xa7de5  ldarg.0
0xa7de6  ldarg.1
0xa7de7  ldloc.s  9
0xa7de9  ldarg.s  5
0xa7deb  ldloc.s  0xB
0xa7ded  ldloc.s  8
0xa7def  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa7df4  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa7df9  call     instance void System.Xml.Serialization.XmlSerializationWriterILGen::WriteChoiceTypeCheck(class System.Xml.Serialization.SourceInfo source, string fullTypeName, class System.Xml.Serialization.ChoiceIdentifierAccessor choice, string enumName, class System.Xml.Serialization.TypeDesc typeDesc)
0xa7dfe  ldarg.1
0xa7dff  stloc.s  0xC
0xa7e01  ldarg.1
0xa7e02  ldloc.s  8
0xa7e04  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa7e09  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa7e0e  callvirt instance class System.Xml.Serialization.SourceInfo System.Xml.Serialization.SourceInfo::CastTo(class System.Xml.Serialization.TypeDesc td)
0xa7e13  stloc.s  0xC
0xa7e15  ldarg.0
0xa7e16  ldloc.s  8
0xa7e18  callvirt instance bool System.Xml.Serialization.Accessor::get_Any()
0xa7e1d  brtrue.s loc_A7E23
0xa7e1f  ldloc.s  0xC
0xa7e21  br.s     loc_A7E24
0xa7e23  ldarg.1
0xa7e24  ldloc.s  8
0xa7e26  ldarg.s  6
0xa7e28  ldarg.s  7
0xa7e2a  call     instance void System.Xml.Serialization.XmlSerializationWriterILGen::WriteElement(class System.Xml.Serialization.SourceInfo source, class System.Xml.Serialization.ElementAccessor element, string arrayName, bool writeAccessor)
0xa7e2f  br       loc_A7EC6
0xa7e34  ldloc.s  8
0xa7e36  callvirt instance bool System.Xml.Serialization.ElementAccessor::get_IsUnbounded()
0xa7e3b  brtrue.s loc_A7E4B
0xa7e3d  ldloc.s  8
0xa7e3f  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa7e44  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa7e49  br.s     loc_A7E5C
0xa7e4b  ldloc.s  8
0xa7e4d  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa7e52  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa7e57  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeDesc::CreateArrayTypeDesc()
0xa7e5c  stloc.s  0xF
0xa7e5e  ldloc.s  0xF
0xa7e60  callvirt instance string System.Xml.Serialization.TypeDesc::get_CSharpName()
0xa7e65  stloc.s  0x10
0xa7e67  ldloc.s  5
0xa7e69  brfalse.s loc_A7E78
0xa7e6b  ldarg.0
0xa7e6c  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa7e71  callvirt instance void System.Xml.Serialization.CodeGenerator::InitElseIf()
0xa7e76  br.s     loc_A7E86
0xa7e78  ldc.i4.1
0xa7e79  stloc.s  5
0xa7e7b  ldarg.0
0xa7e7c  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa7e81  callvirt instance void System.Xml.Serialization.CodeGenerator::InitIf()
0xa7e86  ldarg.0
0xa7e87  ldarg.1
0xa7e88  ldloc.s  0xF
0xa7e8a  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeDesc::get_Type()
0xa7e8f  call     instance void System.Xml.Serialization.XmlSerializationWriterILGen::WriteInstanceOf(class System.Xml.Serialization.SourceInfo source, class [mscorlib]System.Type type)
0xa7e94  ldarg.0
0xa7e95  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa7e9a  callvirt instance void System.Xml.Serialization.CodeGenerator::AndIf()
0xa7e9f  ldarg.1
0xa7ea0  stloc.s  0x11
0xa7ea2  ldarg.1
0xa7ea3  ldloc.s  0xF
0xa7ea5  callvirt instance class System.Xml.Serialization.SourceInfo System.Xml.Serialization.SourceInfo::CastTo(class System.Xml.Serialization.TypeDesc td)
0xa7eaa  stloc.s  0x11
0xa7eac  ldarg.0
0xa7ead  ldloc.s  8
0xa7eaf  callvirt instance bool System.Xml.Serialization.Accessor::get_Any()
0xa7eb4  brtrue.s loc_A7EBA
0xa7eb6  ldloc.s  0x11
0xa7eb8  br.s     loc_A7EBB
0xa7eba  ldarg.1
0xa7ebb  ldloc.s  8
0xa7ebd  ldarg.s  6
0xa7ebf  ldarg.s  7
0xa7ec1  call     instance void System.Xml.Serialization.XmlSerializationWriterILGen::WriteElement(class System.Xml.Serialization.SourceInfo source, class System.Xml.Serialization.ElementAccessor element, string arrayName, bool writeAccessor)
0xa7ec6  ldloc.s  7
  ... truncated ...
```
