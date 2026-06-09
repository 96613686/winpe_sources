# System.Xml.Serialization.XmlSerializationWriterILGen::WriteElement

- ea: `0xa8750`
- end: `0xa8d9f`
- name: `System.Xml.Serialization.XmlSerializationWriterILGen::WriteElement`
- size: `1615`
- prototype: ``
- caller_count: `2`
- callee_count: `60`
- tags: `registry_config`

## callers

- `0xa7b90`
- `0xa8750`

## callees

- `0x62370`
- `0x63290`
- `0x632b0`
- `0x633f0`
- `0x63410`
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
- `0x643c0`
- `0x645a0`
- `0x645b0`
- `0x64620`
- `0x646a0`
- `0x64b20`
- `0x68600`
- `0x68610`
- `0x68620`
- `0x68660`
- `0x68690`
- `0x686d0`
- `0x686f0`
- `0x688b0`
- `0x688d0`
- `0x688f0`
- `0x68c10`
- `0x68c30`
- `0x68c50`
- `0x68d70`
- `0x68de0`
- `0x723c0`
- `0x72420`
- `0x72430`
- `0x72ba0`
- `0x72bf0`
- `0x72c40`
- `0x72e40`
- `0x730b0`
- `0x871b0`
- `0x87270`
- `0x87300`
- `0xa4690`

## string_xrefs

- `0xa8d8f`: `XmlInternalError`
- `0xa8a08`: `WriteElementString`
- `0xa8a9e`: `WriteElementString`
- `0xa8c33`: `WriteSerializable`
- `0xa8cfa`: `WriteElementLiteral`
- `0xa8aac`: `WriteNullableStringLiteral`
- `0xa8d32`: `CreateInvalidAnyTypeException`

## pseudocode

```c

```

## disassembly

```asm
0xa8750  ldarg.s  4
0xa8752  brtrue.s loc_A8761
0xa8754  ldarg.2
0xa8755  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa875a  callvirt instance string System.Xml.Serialization.TypeMapping::get_TypeName()
0xa875f  br.s     loc_A8767
0xa8761  ldarg.2
0xa8762  callvirt instance string System.Xml.Serialization.Accessor::get_Name()
0xa8767  stloc.0
0xa8768  ldarg.2
0xa8769  callvirt instance bool System.Xml.Serialization.Accessor::get_Any()
0xa876e  brfalse.s loc_A877D
0xa8770  ldarg.2
0xa8771  callvirt instance string System.Xml.Serialization.Accessor::get_Name()
0xa8776  callvirt instance int32 [mscorlib]System.String::get_Length()
0xa877b  brfalse.s loc_A87A6
0xa877d  ldarg.2
0xa877e  callvirt instance valuetype System.Xml.Schema.XmlSchemaForm System.Xml.Serialization.Accessor::get_Form()
0xa8783  ldc.i4.1
0xa8784  beq.s    loc_A878D
0xa8786  ldstr    asc_1284AE// ""
0xa878b  br.s     loc_A87A7
0xa878d  ldarg.s  4
0xa878f  brtrue.s loc_A879E
0xa8791  ldarg.2
0xa8792  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa8797  callvirt instance string System.Xml.Serialization.TypeMapping::get_Namespace()
0xa879c  br.s     loc_A87A7
0xa879e  ldarg.2
0xa879f  callvirt instance string System.Xml.Serialization.Accessor::get_Namespace()
0xa87a4  br.s     loc_A87A7
0xa87a6  ldnull
0xa87a7  stloc.1
0xa87a8  ldarg.2
0xa87a9  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa87ae  isinst   System.Xml.Serialization.NullableMapping
0xa87b3  brfalse  loc_A88F0
0xa87b8  ldarg.1
0xa87b9  ldfld    class [mscorlib]System.Type System.Xml.Serialization.SourceInfo::Type
0xa87be  ldarg.2
0xa87bf  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa87c4  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa87c9  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeDesc::get_Type()
0xa87ce  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xa87d3  brfalse.s loc_A8822
0xa87d5  ldarg.2
0xa87d6  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa87db  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa87e0  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeDesc::get_Type()
0xa87e5  ldstr    aGetHasvalue// "get_HasValue"
0xa87ea  ldsfld   valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Serialization.CodeGenerator::InstanceBindingFlags
0xa87ef  ldnull
0xa87f0  ldsfld   class [mscorlib]System.Type[] System.Xml.Serialization.CodeGenerator::EmptyTypeArray
0xa87f5  ldnull
0xa87f6  callvirt instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0xa87fb  stloc.s  5
0xa87fd  ldarg.1
0xa87fe  ldarg.2
0xa87ff  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa8804  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa8809  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeDesc::get_Type()
0xa880e  callvirt instance void System.Xml.Serialization.SourceInfo::LoadAddress(class [mscorlib]System.Type elementType)
0xa8813  ldarg.0
0xa8814  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa8819  ldloc.s  5
0xa881b  callvirt instance void System.Xml.Serialization.CodeGenerator::Call(class [mscorlib]System.Reflection.MethodInfo methodInfo)
0xa8820  br.s     loc_A8840
0xa8822  ldarg.1
0xa8823  ldnull
0xa8824  callvirt instance void System.Xml.Serialization.SourceInfo::Load(class [mscorlib]System.Type elementType)
0xa8829  ldarg.0
0xa882a  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa882f  ldnull
0xa8830  callvirt instance void System.Xml.Serialization.CodeGenerator::Load(object obj)
0xa8835  ldarg.0
0xa8836  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa883b  callvirt instance void System.Xml.Serialization.CodeGenerator::Cne()
0xa8840  ldarg.0
0xa8841  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa8846  callvirt instance void System.Xml.Serialization.CodeGenerator::If()
0xa884b  ldarg.2
0xa884c  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa8851  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa8856  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeDesc::get_BaseTypeDesc()
0xa885b  callvirt instance string System.Xml.Serialization.TypeDesc::get_CSharpName()
0xa8860  stloc.2
0xa8861  ldarg.1
0xa8862  ldarg.2
0xa8863  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa8868  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa886d  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeDesc::get_BaseTypeDesc()
0xa8872  callvirt instance class System.Xml.Serialization.SourceInfo System.Xml.Serialization.SourceInfo::CastTo(class System.Xml.Serialization.TypeDesc td)
0xa8877  stloc.3
0xa8878  ldarg.2
0xa8879  callvirt instance class System.Xml.Serialization.ElementAccessor System.Xml.Serialization.ElementAccessor::Clone()
0xa887e  stloc.s  4
0xa8880  ldloc.s  4
0xa8882  ldarg.2
0xa8883  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa8888  castclass System.Xml.Serialization.NullableMapping
0xa888d  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.NullableMapping::get_BaseMapping()
0xa8892  callvirt instance void System.Xml.Serialization.Accessor::set_Mapping(class System.Xml.Serialization.TypeMapping value)
0xa8897  ldarg.0
0xa8898  ldloc.s  4
0xa889a  callvirt instance bool System.Xml.Serialization.Accessor::get_Any()
0xa889f  brtrue.s loc_A88A4
0xa88a1  ldloc.3
0xa88a2  br.s     loc_A88A5
0xa88a4  ldarg.1
0xa88a5  ldloc.s  4
0xa88a7  ldarg.3
0xa88a8  ldarg.s  4
0xa88aa  call     instance void System.Xml.Serialization.XmlSerializationWriterILGen::WriteElement(class System.Xml.Serialization.SourceInfo source, class System.Xml.Serialization.ElementAccessor element, string arrayName, bool writeAccessor)
0xa88af  ldarg.2
0xa88b0  callvirt instance bool System.Xml.Serialization.ElementAccessor::get_IsNullable()
0xa88b5  brfalse.s loc_A88E4
0xa88b7  ldarg.0
0xa88b8  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa88bd  callvirt instance void System.Xml.Serialization.CodeGenerator::Else()
0xa88c2  ldarg.0
0xa88c3  ldarg.2
0xa88c4  callvirt instance string System.Xml.Serialization.Accessor::get_Name()
0xa88c9  ldarg.2
0xa88ca  callvirt instance valuetype System.Xml.Schema.XmlSchemaForm System.Xml.Serialization.Accessor::get_Form()
0xa88cf  ldc.i4.1
0xa88d0  beq.s    loc_A88D9
0xa88d2  ldstr    asc_1284AE// ""
0xa88d7  br.s     loc_A88DF
0xa88d9  ldarg.2
0xa88da  callvirt instance string System.Xml.Serialization.Accessor::get_Namespace()
0xa88df  call     instance void System.Xml.Serialization.XmlSerializationWriterILGen::WriteLiteralNullTag(string name, string ns)
0xa88e4  ldarg.0
0xa88e5  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa88ea  callvirt instance void System.Xml.Serialization.CodeGenerator::EndIf()
0xa88ef  ret
0xa88f0  ldarg.2
0xa88f1  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa88f6  isinst   System.Xml.Serialization.ArrayMapping
0xa88fb  brfalse  loc_A89FA
0xa8900  ldarg.2
0xa8901  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa8906  castclass System.Xml.Serialization.ArrayMapping
0xa890b  stloc.s  6
0xa890d  ldarg.2
0xa890e  callvirt instance bool System.Xml.Serialization.ElementAccessor::get_IsUnbounded()
0xa8913  brfalse.s loc_A8920
0xa8915  ldstr    aUnreachableIsu// "Unreachable: IsUnbounded is never set t"...
0xa891a  call     class [mscorlib]System.Exception System.Xml.Serialization.CodeGenerator::NotSupported(string msg)
0xa891f  throw
0xa8920  ldarg.0
0xa8921  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa8926  callvirt instance void System.Xml.Serialization.CodeGenerator::EnterScope()
0xa892b  ldloc.s  6
0xa892d  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa8932  callvirt instance string System.Xml.Serialization.TypeDesc::get_CSharpName()
0xa8937  stloc.s  7
0xa8939  ldarg.0
0xa893a  ldloc.s  7
0xa893c  ldarg.3
0xa893d  ldarg.1
0xa893e  ldloc.s  6
0xa8940  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa8945  call     instance void System.Xml.Serialization.XmlSerializationWriterILGen::WriteArrayLocalDecl(string typeName, string variableName, class System.Xml.Serialization.SourceInfo initValue, class System.Xml.Serialization.TypeDesc arrayTypeDesc)
0xa894a  ldarg.2
0xa894b  callvirt instance bool System.Xml.Serialization.ElementAccessor::get_IsNullable()
0xa8950  brfalse.s loc_A895C
0xa8952  ldarg.0
0xa8953  ldarg.3
0xa8954  ldarg.2
0xa8955  call     instance void System.Xml.Serialization.XmlSerializationWriterILGen::WriteNullCheckBegin(string source, class System.Xml.Serialization.ElementAccessor element)
0xa895a  br.s     loc_A8999
0xa895c  ldloc.s  6
0xa895e  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa8963  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsNullable()
0xa8968  brfalse.s loc_A8999
0xa896a  ldarg.0
0xa896b  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa8970  ldarg.0
0xa8971  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa8976  ldarg.3
0xa8977  callvirt instance class [mscorlib]System.Reflection.Emit.LocalBuilder System.Xml.Serialization.CodeGenerator::GetLocal(string name)
0xa897c  callvirt instance void System.Xml.Serialization.CodeGenerator::Ldloc(class [mscorlib]System.Reflection.Emit.LocalBuilder localBuilder)
0xa8981  ldarg.0
0xa8982  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa8987  ldnull
0xa8988  callvirt instance void System.Xml.Serialization.CodeGenerator::Load(object obj)
0xa898d  ldarg.0
0xa898e  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa8993  ldc.i4.4
0xa8994  callvirt instance void System.Xml.Serialization.CodeGenerator::If(valuetype System.Xml.Serialization.Cmp cmpOp)
0xa8999  ldarg.0
0xa899a  ldloc.0
0xa899b  ldloc.1
0xa899c  ldc.i4.0
0xa899d  call     instance void System.Xml.Serialization.XmlSerializationWriterILGen::WriteStartElement(string name, string ns, bool writePrefixed)
0xa89a2  ldarg.0
0xa89a3  ldloc.s  6
0xa89a5  callvirt instance class System.Xml.Serialization.ElementAccessor[] System.Xml.Serialization.ArrayMapping::get_ElementsSortedByDerivation()
0xa89aa  ldnull
0xa89ab  ldnull
0xa89ac  ldloc.s  6
0xa89ae  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa89b3  ldarg.3
0xa89b4  ldnull
0xa89b5  call     instance void System.Xml.Serialization.XmlSerializationWriterILGen::WriteArrayItems(class System.Xml.Serialization.ElementAccessor[] elements, class System.Xml.Serialization.TextAccessor text, class System.Xml.Serialization.ChoiceIdentifierAccessor choice, class System.Xml.Serialization.TypeDesc arrayTypeDesc, string arrayName, string choiceName)
0xa89ba  ldarg.0
0xa89bb  call     instance void System.Xml.Serialization.XmlSerializationWriterILGen::WriteEndElement()
0xa89c0  ldarg.2
0xa89c1  callvirt instance bool System.Xml.Serialization.ElementAccessor::get_IsNullable()
0xa89c6  brfalse.s loc_A89D5
0xa89c8  ldarg.0
0xa89c9  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa89ce  callvirt instance void System.Xml.Serialization.CodeGenerator::EndIf()
0xa89d3  br.s     loc_A89EE
0xa89d5  ldloc.s  6
0xa89d7  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa89dc  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsNullable()
0xa89e1  brfalse.s loc_A89EE
0xa89e3  ldarg.0
0xa89e4  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa89e9  callvirt instance void System.Xml.Serialization.CodeGenerator::EndIf()
0xa89ee  ldarg.0
0xa89ef  ldfld    class System.Xml.Serialization.CodeGenerator System.Xml.Serialization.XmlSerializationILGen::ilg
0xa89f4  callvirt instance void System.Xml.Serialization.CodeGenerator::ExitScope()
0xa89f9  ret
0xa89fa  ldarg.2
0xa89fb  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa8a00  isinst   System.Xml.Serialization.EnumMapping
0xa8a05  brfalse.s loc_A8A2A
0xa8a07  ldarg.0
0xa8a08  ldstr    aWriteelementst// "WriteElementString"
0xa8a0d  ldloc.0
0xa8a0e  ldloc.1
0xa8a0f  ldarg.2
0xa8a10  callvirt instance object System.Xml.Serialization.Accessor::get_Default()
0xa8a15  ldarg.1
0xa8a16  ldarg.2
0xa8a17  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa8a1c  ldc.i4.0
0xa8a1d  ldc.i4.1
0xa8a1e  ldarg.2
0xa8a1f  callvirt instance bool System.Xml.Serialization.ElementAccessor::get_IsNullable()
0xa8a24  call     instance void System.Xml.Serialization.XmlSerializationWriterILGen::WritePrimitive(string method, string name, string ns, object defaultValue, class System.Xml.Serialization.SourceInfo source, class System.Xml.Serialization.TypeMapping mapping, bool writeXsiType, bool isElement, bool isNullable)
0xa8a29  ret
0xa8a2a  ldarg.2
0xa8a2b  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa8a30  isinst   System.Xml.Serialization.PrimitiveMapping
0xa8a35  brfalse  loc_A8ADC
0xa8a3a  ldarg.2
0xa8a3b  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa8a40  castclass System.Xml.Serialization.PrimitiveMapping
0xa8a45  stloc.s  8
0xa8a47  ldloc.s  8
0xa8a49  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa8a4e  ldarg.0
0xa8a4f  call     instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.XmlSerializationILGen::get_QnameTypeDesc()
0xa8a54  bne.un.s loc_A8A79
0xa8a56  ldarg.0
0xa8a57  ldloc.0
0xa8a58  ldloc.1
0xa8a59  ldarg.1
0xa8a5a  ldfld    class [mscorlib]System.Type System.Xml.Serialization.SourceInfo::Type
0xa8a5f  ldarg.2
0xa8a60  callvirt instance object System.Xml.Serialization.Accessor::get_Default()
0xa8a65  call     object System.Xml.Serialization.XmlSerializationWriterILGen::GetConvertedDefaultValue(class [mscorlib]System.Type targetType, object rawDefaultValue)
0xa8a6a  ldarg.1
0xa8a6b  ldarg.2
0xa8a6c  callvirt instance bool System.Xml.Serialization.ElementAccessor::get_IsNullable()
0xa8a71  ldloc.s  8
0xa8a73  call     instance void System.Xml.Serialization.XmlSerializationWriterILGen::WriteQualifiedNameElement(string name, string ns, object defaultValue, class System.Xml.Serialization.SourceInfo source, bool nullable, class System.Xml.Serialization.TypeMapping mapping)
0xa8a78  ret
0xa8a79  ldloc.s  8
0xa8a7b  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa8a80  callvirt instance bool System.Xml.Serialization.TypeDesc::get_XmlEncodingNotRequired()
0xa8a85  brtrue.s loc_A8A8E
0xa8a87  ldstr    asc_1284AE// ""
0xa8a8c  br.s     loc_A8A93
0xa8a8e  ldstr    aRaw// "Raw"
0xa8a93  stloc.s  9
0xa8a95  ldarg.0
0xa8a96  ldarg.2
0xa8a97  callvirt instance bool System.Xml.Serialization.ElementAccessor::get_IsNullable()
0xa8a9c  brtrue.s loc_A8AAC
0xa8a9e  ldstr    aWriteelementst// "WriteElementString"
0xa8aa3  ldloc.s  9
0xa8aa5  call     string [mscorlib]System.String::Concat(string, string)
0xa8aaa  br.s     loc_A8AB8
0xa8aac  ldstr    aWritenullables_0// "WriteNullableStringLiteral"
0xa8ab1  ldloc.s  9
0xa8ab3  call     string [mscorlib]System.String::Concat(string, string)
0xa8ab8  ldloc.0
0xa8ab9  ldloc.1
0xa8aba  ldarg.1
0xa8abb  ldfld    class [mscorlib]System.Type System.Xml.Serialization.SourceInfo::Type
0xa8ac0  ldarg.2
0xa8ac1  callvirt instance object System.Xml.Serialization.Accessor::get_Default()
0xa8ac6  call     object System.Xml.Serialization.XmlSerializationWriterILGen::GetConvertedDefaultValue(class [mscorlib]System.Type targetType, object rawDefaultValue)
0xa8acb  ldarg.1
0xa8acc  ldloc.s  8
0xa8ace  ldc.i4.0
  ... truncated ...
```
