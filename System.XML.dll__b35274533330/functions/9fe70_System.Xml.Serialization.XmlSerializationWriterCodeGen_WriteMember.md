# System.Xml.Serialization.XmlSerializationWriterCodeGen::WriteMember

- ea: `0x9fe70`
- end: `0xa04a5`
- name: `System.Xml.Serialization.XmlSerializationWriterCodeGen::WriteMember`
- size: `1589`
- prototype: ``
- caller_count: `2`
- callee_count: `32`
- tags: `registry_config`

## callers

- `0x9e060`
- `0x9f470`

## callees

- `0x68450`
- `0x68460`
- `0x68470`
- `0x684b0`
- `0x68600`
- `0x68660`
- `0x686d0`
- `0x686f0`
- `0x68a60`
- `0x72ba0`
- `0x72d20`
- `0x72d30`
- `0x72d60`
- `0x72d80`
- `0x72dd0`
- `0x72e00`
- `0x72e10`
- `0x72e40`
- `0x72fd0`
- `0x86170`
- `0x861a0`
- `0x862f0`
- `0x9dae0`
- `0x9db30`
- `0x9fe50`
- `0x9fe70`
- `0xa04b0`
- `0xa2bf0`
- `0xa2c10`
- `0xa3b10`
- `0xa3b40`
- `0xa3d90`

## string_xrefs

- `0x9ff0a`: `Writer.WriteStartAttribute(null, `
- `0xa019f`: `while (e.MoveNext()) {`
- `0xa02ac`: `if (i != 0) Writer.WriteString(" ");`
- `0xa02bc`: `WriteValue(`
- `0xa037e`: `Writer.WriteEndAttribute();`
- `0xa03b8`: `WriteAttribute(`

## pseudocode

```c

```

## disassembly

```asm
0x9fe70  ldarg.3
0x9fe71  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsAbstract()
0x9fe76  brfalse.s loc_9FE79
0x9fe78  ret
0x9fe79  ldarg.3
0x9fe7a  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsArrayLike()
0x9fe7f  brfalse  loc_A049A
0x9fe84  ldarg.0
0x9fe85  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9fe8a  ldstr    asc_12FB82// "{"
0x9fe8f  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9fe94  ldarg.0
0x9fe95  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9fe9a  dup
0x9fe9b  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x9fea0  stloc.2
0x9fea1  ldloc.2
0x9fea2  ldc.i4.1
0x9fea3  add
0x9fea4  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x9fea9  ldarg.3
0x9feaa  callvirt instance string System.Xml.Serialization.TypeDesc::get_CSharpName()
0x9feaf  stloc.0
0x9feb0  ldarg.0
0x9feb1  ldloc.0
0x9feb2  ldstr    aA_0// "a"
0x9feb7  ldarg.1
0x9feb8  ldarg.3
0x9feb9  call     instance void System.Xml.Serialization.XmlSerializationWriterCodeGen::WriteArrayLocalDecl(string typeName, string variableName, string initValue, class System.Xml.Serialization.TypeDesc arrayTypeDesc)
0x9febe  ldarg.3
0x9febf  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsNullable()
0x9fec4  brfalse.s loc_9FEEB
0x9fec6  ldarg.0
0x9fec7  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9fecc  ldstr    aIfANull// "if (a != null) {"
0x9fed1  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9fed6  ldarg.0
0x9fed7  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9fedc  dup
0x9fedd  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x9fee2  stloc.2
0x9fee3  ldloc.2
0x9fee4  ldc.i4.1
0x9fee5  add
0x9fee6  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x9feeb  ldarg.2
0x9feec  callvirt instance bool System.Xml.Serialization.AttributeAccessor::get_IsList()
0x9fef1  brfalse  loc_9FFC9
0x9fef6  ldarg.0
0x9fef7  ldarg.3
0x9fef8  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeDesc::get_ArrayElementTypeDesc()
0x9fefd  call     instance bool System.Xml.Serialization.XmlSerializationWriterCodeGen::CanOptimizeWriteListSequence(class System.Xml.Serialization.TypeDesc listElementTypeDesc)
0x9ff02  brfalse.s loc_9FF75
0x9ff04  ldarg.0
0x9ff05  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9ff0a  ldstr    aWriterWritesta_0// "Writer.WriteStartAttribute(null, "
0x9ff0f  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9ff14  ldarg.0
0x9ff15  ldarg.2
0x9ff16  callvirt instance string System.Xml.Serialization.Accessor::get_Name()
0x9ff1b  call     instance void System.Xml.Serialization.XmlSerializationCodeGen::WriteQuotedCSharpString(string value)
0x9ff20  ldarg.0
0x9ff21  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9ff26  ldstr    asc_128826// ", "
0x9ff2b  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9ff30  ldarg.2
0x9ff31  callvirt instance valuetype System.Xml.Schema.XmlSchemaForm System.Xml.Serialization.Accessor::get_Form()
0x9ff36  ldc.i4.1
0x9ff37  beq.s    loc_9FF40
0x9ff39  ldsfld   string [mscorlib]System.String::Empty
0x9ff3e  br.s     loc_9FF46
0x9ff40  ldarg.2
0x9ff41  callvirt instance string System.Xml.Serialization.Accessor::get_Namespace()
0x9ff46  stloc.3
0x9ff47  ldloc.3
0x9ff48  brfalse.s loc_9FF53
0x9ff4a  ldarg.0
0x9ff4b  ldloc.3
0x9ff4c  call     instance void System.Xml.Serialization.XmlSerializationCodeGen::WriteQuotedCSharpString(string value)
0x9ff51  br.s     loc_9FF63
0x9ff53  ldarg.0
0x9ff54  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9ff59  ldstr    aNull_0// "null"
0x9ff5e  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9ff63  ldarg.0
0x9ff64  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9ff69  ldstr    asc_133068// ");"
0x9ff6e  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9ff73  br.s     loc_9FFC9
0x9ff75  ldarg.0
0x9ff76  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9ff7b  ldtoken  [mscorlib]System.Text.StringBuilder
0x9ff80  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9ff85  callvirt instance string [mscorlib]System.Type::get_FullName()
0x9ff8a  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9ff8f  ldarg.0
0x9ff90  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9ff95  ldstr    aSbNew// " sb = new "
0x9ff9a  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9ff9f  ldarg.0
0x9ffa0  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9ffa5  ldtoken  [mscorlib]System.Text.StringBuilder
0x9ffaa  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9ffaf  callvirt instance string [mscorlib]System.Type::get_FullName()
0x9ffb4  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9ffb9  ldarg.0
0x9ffba  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9ffbf  ldstr    asc_132DE6// "();"
0x9ffc4  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x9ffc9  ldarg.3
0x9ffca  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeDesc::get_ArrayElementTypeDesc()
0x9ffcf  stloc.1
0x9ffd0  ldarg.3
0x9ffd1  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsEnumerable()
0x9ffd6  brfalse  loc_A01E3
0x9ffdb  ldarg.0
0x9ffdc  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9ffe1  ldstr    aE_0// " e = "
0x9ffe6  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x9ffeb  ldarg.0
0x9ffec  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9fff1  ldtoken  [mscorlib]System.Collections.IEnumerator
0x9fff6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9fffb  callvirt instance string [mscorlib]System.Type::get_FullName()
0xa0000  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0xa0005  ldarg.3
0xa0006  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsPrivateImplementation()
0xa000b  brfalse.s loc_A004C
0xa000d  ldarg.0
0xa000e  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa0013  ldstr    asc_12FF58// "(("
0xa0018  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0xa001d  ldarg.0
0xa001e  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa0023  ldtoken  [mscorlib]System.Collections.IEnumerable
0xa0028  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa002d  callvirt instance string [mscorlib]System.Type::get_FullName()
0xa0032  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0xa0037  ldarg.0
0xa0038  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa003d  ldstr    aGetenumerator_0// ").GetEnumerator();"
0xa0042  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0xa0047  br       loc_A0189
0xa004c  ldarg.3
0xa004d  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsGenericInterface()
0xa0052  brfalse  loc_A0105
0xa0057  ldarg.3
0xa0058  callvirt instance bool System.Xml.Serialization.TypeDesc::get_UseReflection()
0xa005d  brfalse.s loc_A00CF
0xa005f  ldarg.0
0xa0060  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa0065  ldstr    asc_12DDFC// "("
0xa006a  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0xa006f  ldarg.0
0xa0070  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa0075  ldtoken  [mscorlib]System.Collections.IEnumerator
0xa007a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa007f  callvirt instance string [mscorlib]System.Type::get_FullName()
0xa0084  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0xa0089  ldarg.0
0xa008a  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa008f  ldstr    asc_129CD8// ")"
0xa0094  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0xa0099  ldarg.0
0xa009a  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa009f  ldarg.0
0xa00a0  call     instance class System.Xml.Serialization.ReflectionAwareCodeGen System.Xml.Serialization.XmlSerializationCodeGen::get_RaCodeGen()
0xa00a5  ldarg.3
0xa00a6  callvirt instance string System.Xml.Serialization.TypeDesc::get_CSharpName()
0xa00ab  ldstr    aSystemCollecti_1// "System.Collections.Generic.IEnumerable*"
0xa00b0  callvirt instance string System.Xml.Serialization.ReflectionAwareCodeGen::GetReflectionVariable(string typeFullName, string memberName)
0xa00b5  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0xa00ba  ldarg.0
0xa00bb  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa00c0  ldstr    aInvokeANewObje// ".Invoke(a, new object[0]);"
0xa00c5  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0xa00ca  br       loc_A0189
0xa00cf  ldarg.0
0xa00d0  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa00d5  ldstr    aSystemCollecti_2// "((System.Collections.Generic.IEnumerabl"...
0xa00da  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0xa00df  ldarg.0
0xa00e0  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa00e5  ldloc.1
0xa00e6  callvirt instance string System.Xml.Serialization.TypeDesc::get_CSharpName()
0xa00eb  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0xa00f0  ldarg.0
0xa00f1  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa00f6  ldstr    aAGetenumerator// ">)a).GetEnumerator();"
0xa00fb  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0xa0100  br       loc_A0189
0xa0105  ldarg.3
0xa0106  callvirt instance bool System.Xml.Serialization.TypeDesc::get_UseReflection()
0xa010b  brfalse.s loc_A0147
0xa010d  ldarg.0
0xa010e  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa0113  ldstr    asc_12DDFC// "("
0xa0118  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0xa011d  ldarg.0
0xa011e  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa0123  ldtoken  [mscorlib]System.Collections.IEnumerator
0xa0128  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa012d  callvirt instance string [mscorlib]System.Type::get_FullName()
0xa0132  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0xa0137  ldarg.0
0xa0138  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa013d  ldstr    asc_129CD8// ")"
0xa0142  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0xa0147  ldarg.0
0xa0148  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa014d  ldarg.0
0xa014e  call     instance class System.Xml.Serialization.ReflectionAwareCodeGen System.Xml.Serialization.XmlSerializationCodeGen::get_RaCodeGen()
0xa0153  ldstr    aA_0// "a"
0xa0158  ldarg.3
0xa0159  callvirt instance string System.Xml.Serialization.TypeDesc::get_CSharpName()
0xa015e  ldstr    aGetenumerator// "GetEnumerator"
0xa0163  ldarg.3
0xa0164  callvirt instance bool System.Xml.Serialization.TypeDesc::get_UseReflection()
0xa0169  ldc.i4.0
0xa016a  newarr   [mscorlib]System.String
0xa016f  callvirt instance string System.Xml.Serialization.ReflectionAwareCodeGen::GetStringForMethodInvoke(string obj, string escapedTypeName, string methodName, bool useReflection, string[] args)
0xa0174  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0xa0179  ldarg.0
0xa017a  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa017f  ldstr    asc_12B71A// ";"
0xa0184  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0xa0189  ldarg.0
0xa018a  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa018f  ldstr    aIfENull// "if (e != null)"
0xa0194  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0xa0199  ldarg.0
0xa019a  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa019f  ldstr    aWhileEMovenext// "while (e.MoveNext()) {"
0xa01a4  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0xa01a9  ldarg.0
0xa01aa  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa01af  dup
0xa01b0  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0xa01b5  stloc.2
0xa01b6  ldloc.2
0xa01b7  ldc.i4.1
0xa01b8  add
0xa01b9  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0xa01be  ldloc.1
0xa01bf  callvirt instance string System.Xml.Serialization.TypeDesc::get_CSharpName()
0xa01c4  stloc.s  4
0xa01c6  ldarg.0
0xa01c7  ldloc.s  4
0xa01c9  ldstr    aAi// "ai"
0xa01ce  ldstr    aECurrent// "e.Current"
0xa01d3  ldloc.1
0xa01d4  callvirt instance bool System.Xml.Serialization.TypeDesc::get_UseReflection()
0xa01d9  call     instance void System.Xml.Serialization.XmlSerializationWriterCodeGen::WriteLocalDecl(string typeName, string variableName, string initValue, bool useReflection)
0xa01de  br       loc_A028D
0xa01e3  ldarg.0
0xa01e4  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa01e9  ldstr    aForIntI0I// "for (int i = 0; i < "
0xa01ee  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0xa01f3  ldarg.3
0xa01f4  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsArray()
0xa01f9  brfalse.s loc_A020D
0xa01fb  ldarg.0
0xa01fc  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa0201  ldstr    aALengthI// "a.Length; i++) {"
0xa0206  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0xa020b  br.s     loc_A0247
0xa020d  ldarg.0
0xa020e  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa0213  ldstr    asc_12FF58// "(("
0xa0218  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0xa021d  ldarg.0
0xa021e  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa0223  ldtoken  [mscorlib]System.Collections.ICollection
0xa0228  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa022d  callvirt instance string [mscorlib]System.Type::get_FullName()
0xa0232  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0xa0237  ldarg.0
0xa0238  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa023d  ldstr    aACountI// ")a).Count; i++) {"
0xa0242  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0xa0247  ldarg.0
0xa0248  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa024d  dup
0xa024e  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0xa0253  stloc.2
0xa0254  ldloc.2
0xa0255  ldc.i4.1
0xa0256  add
0xa0257  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0xa025c  ldloc.1
0xa025d  callvirt instance string System.Xml.Serialization.TypeDesc::get_CSharpName()
0xa0262  stloc.s  5
0xa0264  ldarg.0
0xa0265  ldloc.s  5
0xa0267  ldstr    aAi// "ai"
0xa026c  ldarg.0
0xa026d  call     instance class System.Xml.Serialization.ReflectionAwareCodeGen System.Xml.Serialization.XmlSerializationCodeGen::get_RaCodeGen()
0xa0272  ldstr    aA_0// "a"
0xa0277  ldstr    aI// "i"
0xa027c  ldarg.3
  ... truncated ...
```
