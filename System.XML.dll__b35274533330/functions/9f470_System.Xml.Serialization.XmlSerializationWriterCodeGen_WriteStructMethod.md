# System.Xml.Serialization.XmlSerializationWriterCodeGen::WriteStructMethod

- ea: `0x9f470`
- end: `0x9fe47`
- name: `System.Xml.Serialization.XmlSerializationWriterCodeGen::WriteStructMethod`
- size: `2519`
- prototype: ``
- caller_count: `2`
- callee_count: `44`
- tags: `registry_config`

## callers

- `0x9d500`
- `0x9d6c0`

## callees

- `0x65610`
- `0x68450`
- `0x68460`
- `0x68470`
- `0x684b0`
- `0x684e0`
- `0x68990`
- `0x68b80`
- `0x68c10`
- `0x68c30`
- `0x68c50`
- `0x69620`
- `0x69640`
- `0x69660`
- `0x69690`
- `0x696f0`
- `0x69710`
- `0x69730`
- `0x69ae0`
- `0x69b00`
- `0x69b20`
- `0x72ba0`
- `0x72bf0`
- `0x72d60`
- `0x72d80`
- `0x72e40`
- `0x72e50`
- `0x74660`
- `0x86170`
- `0x861a0`
- `0x86200`
- `0x862f0`
- `0x9e000`
- `0x9efa0`
- `0x9f0f0`
- `0x9f470`
- `0x9fe70`
- `0xa05c0`
- `0xa2ac0`
- `0xa2af0`
- `0xa2bf0`
- `0xa2c30`
- `0xa3b40`
- `0xa3cc0`

## string_xrefs

- `0x9f5d3`: `if (isNullable) WriteNullTagLiteral(n, ns);`
- `0x9f6fa`: `WriteTypedPrimitive(n, ns, o, true);`
- `0x9f71c`: `throw CreateUnknownTypeException(o);`
- `0x9f85e`: `WriteStartElement(n, ns, o, false, `
- `0x9f8ac`: `if (needType) WriteXsiType(`

## pseudocode

```c

```

## disassembly

```asm
0x9f470  ldarg.1
0x9f471  callvirt instance bool System.Xml.Serialization.Mapping::get_IsSoap()
0x9f476  brfalse.s loc_9F486
0x9f478  ldarg.1
0x9f479  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x9f47e  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsRoot()
0x9f483  brfalse.s loc_9F486
0x9f485  ret
0x9f486  ldarg.0
0x9f487  call     instance class [mscorlib]System.Collections.Hashtable System.Xml.Serialization.XmlSerializationCodeGen::get_MethodNames()
0x9f48c  ldarg.1
0x9f48d  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x9f492  castclass [mscorlib]System.String
0x9f497  stloc.0
0x9f498  ldarg.0
0x9f499  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f49e  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine()
0x9f4a3  ldarg.0
0x9f4a4  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f4a9  ldstr    aVoid// "void "
0x9f4ae  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9f4b3  ldarg.0
0x9f4b4  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f4b9  ldloc.0
0x9f4ba  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9f4bf  ldarg.1
0x9f4c0  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x9f4c5  callvirt instance string System.Xml.Serialization.TypeDesc::get_CSharpName()
0x9f4ca  stloc.1
0x9f4cb  ldarg.1
0x9f4cc  callvirt instance bool System.Xml.Serialization.Mapping::get_IsSoap()
0x9f4d1  brfalse.s loc_9F519
0x9f4d3  ldarg.0
0x9f4d4  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f4d9  ldstr    aObjectS// "(object s) {"
0x9f4de  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9f4e3  ldarg.0
0x9f4e4  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f4e9  dup
0x9f4ea  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x9f4ef  stloc.2
0x9f4f0  ldloc.2
0x9f4f1  ldc.i4.1
0x9f4f2  add
0x9f4f3  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x9f4f8  ldarg.0
0x9f4f9  ldloc.1
0x9f4fa  ldstr    aO_0// "o"
0x9f4ff  ldstr    aS// "s"
0x9f504  ldarg.1
0x9f505  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x9f50a  callvirt instance bool System.Xml.Serialization.TypeDesc::get_UseReflection()
0x9f50f  call     instance void System.Xml.Serialization.XmlSerializationWriterCodeGen::WriteLocalDecl(string typeName, string variableName, string initValue, bool useReflection)
0x9f514  br       loc_9F770
0x9f519  ldarg.0
0x9f51a  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f51f  ldstr    aStringNStringN// "(string n, string ns, "
0x9f524  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9f529  ldarg.0
0x9f52a  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f52f  ldarg.1
0x9f530  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x9f535  callvirt instance bool System.Xml.Serialization.TypeDesc::get_UseReflection()
0x9f53a  brtrue.s loc_9F53F
0x9f53c  ldloc.1
0x9f53d  br.s     loc_9F544
0x9f53f  ldstr    aObject_3// "object"
0x9f544  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9f549  ldarg.0
0x9f54a  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f54f  ldstr    aO_3// " o"
0x9f554  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9f559  ldarg.1
0x9f55a  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x9f55f  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsNullable()
0x9f564  brfalse.s loc_9F576
0x9f566  ldarg.0
0x9f567  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f56c  ldstr    aBoolIsnullable_0// ", bool isNullable"
0x9f571  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9f576  ldarg.0
0x9f577  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f57c  ldstr    aBoolNeedtype// ", bool needType) {"
0x9f581  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9f586  ldarg.0
0x9f587  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f58c  dup
0x9f58d  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x9f592  stloc.2
0x9f593  ldloc.2
0x9f594  ldc.i4.1
0x9f595  add
0x9f596  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x9f59b  ldarg.1
0x9f59c  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x9f5a1  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsNullable()
0x9f5a6  brfalse.s loc_9F612
0x9f5a8  ldarg.0
0x9f5a9  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f5ae  ldstr    aIfObjectONull// "if ((object)o == null) {"
0x9f5b3  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9f5b8  ldarg.0
0x9f5b9  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f5be  dup
0x9f5bf  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x9f5c4  stloc.2
0x9f5c5  ldloc.2
0x9f5c6  ldc.i4.1
0x9f5c7  add
0x9f5c8  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x9f5cd  ldarg.0
0x9f5ce  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f5d3  ldstr    aIfIsnullableWr// "if (isNullable) WriteNullTagLiteral(n, "...
0x9f5d8  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9f5dd  ldarg.0
0x9f5de  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f5e3  ldstr    aReturn_3// "return;"
0x9f5e8  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9f5ed  ldarg.0
0x9f5ee  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f5f3  dup
0x9f5f4  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x9f5f9  stloc.2
0x9f5fa  ldloc.2
0x9f5fb  ldc.i4.1
0x9f5fc  sub
0x9f5fd  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x9f602  ldarg.0
0x9f603  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f608  ldstr    asc_12E936// "}"
0x9f60d  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9f612  ldarg.0
0x9f613  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f618  ldstr    aIfNeedtype// "if (!needType) {"
0x9f61d  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9f622  ldarg.0
0x9f623  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f628  dup
0x9f629  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x9f62e  stloc.2
0x9f62f  ldloc.2
0x9f630  ldc.i4.1
0x9f631  add
0x9f632  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x9f637  ldarg.0
0x9f638  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f63d  ldtoken  [mscorlib]System.Type
0x9f642  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9f647  callvirt instance string [mscorlib]System.Type::get_FullName()
0x9f64c  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9f651  ldarg.0
0x9f652  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f657  ldstr    aTOGettype// " t = o.GetType();"
0x9f65c  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9f661  ldarg.0
0x9f662  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f667  ldstr    aIf// "if ("
0x9f66c  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9f671  ldarg.0
0x9f672  ldstr    aT_0// "t"
0x9f677  ldloc.1
0x9f678  ldarg.1
0x9f679  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x9f67e  callvirt instance bool System.Xml.Serialization.TypeDesc::get_UseReflection()
0x9f683  call     instance void System.Xml.Serialization.XmlSerializationWriterCodeGen::WriteTypeCompare(string variable, string escapedTypeName, bool useReflection)
0x9f688  ldarg.0
0x9f689  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f68e  ldstr    asc_134612// ") {"
0x9f693  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9f698  ldarg.0
0x9f699  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f69e  ldstr    asc_12E936// "}"
0x9f6a3  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9f6a8  ldarg.0
0x9f6a9  ldarg.1
0x9f6aa  call     instance void System.Xml.Serialization.XmlSerializationWriterCodeGen::WriteDerivedTypes(class System.Xml.Serialization.StructMapping mapping)
0x9f6af  ldarg.1
0x9f6b0  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x9f6b5  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsRoot()
0x9f6ba  brfalse.s loc_9F6C2
0x9f6bc  ldarg.0
0x9f6bd  call     instance void System.Xml.Serialization.XmlSerializationWriterCodeGen::WriteEnumAndArrayTypes()
0x9f6c2  ldarg.0
0x9f6c3  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f6c8  ldstr    aElse// "else {"
0x9f6cd  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9f6d2  ldarg.0
0x9f6d3  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f6d8  dup
0x9f6d9  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x9f6de  stloc.2
0x9f6df  ldloc.2
0x9f6e0  ldc.i4.1
0x9f6e1  add
0x9f6e2  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x9f6e7  ldarg.1
0x9f6e8  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x9f6ed  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsRoot()
0x9f6f2  brfalse.s loc_9F716
0x9f6f4  ldarg.0
0x9f6f5  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f6fa  ldstr    aWritetypedprim// "WriteTypedPrimitive(n, ns, o, true);"
0x9f6ff  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9f704  ldarg.0
0x9f705  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f70a  ldstr    aReturn_3// "return;"
0x9f70f  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9f714  br.s     loc_9F726
0x9f716  ldarg.0
0x9f717  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f71c  ldstr    aThrowCreateunk_2// "throw CreateUnknownTypeException(o);"
0x9f721  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9f726  ldarg.0
0x9f727  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f72c  dup
0x9f72d  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x9f732  stloc.2
0x9f733  ldloc.2
0x9f734  ldc.i4.1
0x9f735  sub
0x9f736  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x9f73b  ldarg.0
0x9f73c  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f741  ldstr    asc_12E936// "}"
0x9f746  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9f74b  ldarg.0
0x9f74c  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f751  dup
0x9f752  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x9f757  stloc.2
0x9f758  ldloc.2
0x9f759  ldc.i4.1
0x9f75a  sub
0x9f75b  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x9f760  ldarg.0
0x9f761  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f766  ldstr    asc_12E936// "}"
0x9f76b  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9f770  ldarg.1
0x9f771  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x9f776  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsAbstract()
0x9f77b  brtrue   loc_9FE21
0x9f780  ldarg.1
0x9f781  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x9f786  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeDesc::get_Type()
0x9f78b  ldnull
0x9f78c  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x9f791  brfalse.s loc_9F7BF
0x9f793  ldtoken  System.Xml.Schema.XmlSchemaObject
0x9f798  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9f79d  ldarg.1
0x9f79e  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x9f7a3  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeDesc::get_Type()
0x9f7a8  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0x9f7ad  brfalse.s loc_9F7BF
0x9f7af  ldarg.0
0x9f7b0  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9f7b5  ldstr    aEscapenameFals// "EscapeName = false;"
0x9f7ba  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9f7bf  ldnull
0x9f7c0  stloc.3
0x9f7c1  ldarg.1
0x9f7c2  call     class System.Xml.Serialization.MemberMapping[] System.Xml.Serialization.TypeScope::GetAllMembers(class System.Xml.Serialization.StructMapping mapping)
0x9f7c7  stloc.s  4
0x9f7c9  ldarg.0
0x9f7ca  ldloc.s  4
0x9f7cc  call     instance int32 System.Xml.Serialization.XmlSerializationWriterCodeGen::FindXmlnsIndex(class System.Xml.Serialization.MemberMapping[] members)
0x9f7d1  stloc.s  5
0x9f7d3  ldloc.s  5
0x9f7d5  ldc.i4.0
0x9f7d6  blt.s    loc_9F84D
0x9f7d8  ldloc.s  4
0x9f7da  ldloc.s  5
0x9f7dc  ldelem.ref
0x9f7dd  stloc.s  6
0x9f7df  ldloc.s  6
0x9f7e1  callvirt instance string System.Xml.Serialization.MemberMapping::get_Name()
0x9f7e6  call     void System.Xml.Serialization.CodeIdentifier::CheckValidIdentifier(string ident)
0x9f7eb  ldarg.0
0x9f7ec  call     instance class System.Xml.Serialization.ReflectionAwareCodeGen System.Xml.Serialization.XmlSerializationCodeGen::get_RaCodeGen()
0x9f7f1  ldstr    aO_0// "o"
0x9f7f6  ldloc.s  6
0x9f7f8  callvirt instance string System.Xml.Serialization.MemberMapping::get_Name()
0x9f7fd  ldarg.1
0x9f7fe  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x9f803  callvirt instance string System.Xml.Serialization.ReflectionAwareCodeGen::GetStringForMember(string obj, string memberName, class System.Xml.Serialization.TypeDesc typeDesc)
0x9f808  stloc.3
0x9f809  ldarg.1
0x9f80a  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x9f80f  callvirt instance bool System.Xml.Serialization.TypeDesc::get_UseReflection()
0x9f814  brfalse.s loc_9F84D
0x9f816  ldc.i4.5
0x9f817  newarr   [mscorlib]System.String
0x9f81c  dup
0x9f81d  ldc.i4.0
0x9f81e  ldstr    asc_12FF58// "(("
0x9f823  stelem.ref
0x9f824  dup
0x9f825  ldc.i4.1
0x9f826  ldloc.s  6
  ... truncated ...
```
