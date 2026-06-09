# System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteEnumAndArrayTypes

- ea: `0x8e4c0`
- end: `0x8e7e6`
- name: `System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteEnumAndArrayTypes`
- size: `806`
- prototype: ``
- caller_count: `1`
- callee_count: `29`
- tags: `registry_config`

## callers

- `0x8e9e0`

## callees

- `0x68450`
- `0x68460`
- `0x68470`
- `0x684b0`
- `0x68b80`
- `0x68c10`
- `0x68c30`
- `0x68c50`
- `0x68dc0`
- `0x69630`
- `0x69670`
- `0x69a50`
- `0x72ba0`
- `0x72c20`
- `0x72d00`
- `0x72d80`
- `0x72e10`
- `0x74f30`
- `0x86170`
- `0x861a0`
- `0x861f0`
- `0x86260`
- `0x8e4c0`
- `0x8fba0`
- `0x91d30`
- `0xa3e50`
- `0x1229d0`
- `0x122c80`
- `0x122c90`

## string_xrefs

- `0x8e567`: `Reader.ReadStartElement();`
- `0x8e5ae`: `ReadEndElement();`
- `0x8e59e`: `(CollapseWhitespace(Reader.ReadString()));`

## pseudocode

```c

```

## disassembly

```asm
0x8e4c0  ldarg.0
0x8e4c1  call     instance class System.Xml.Serialization.TypeScope[] System.Xml.Serialization.XmlSerializationCodeGen::get_Scopes()
0x8e4c6  stloc.0
0x8e4c7  ldc.i4.0
0x8e4c8  stloc.1
0x8e4c9  br       loc_8E7DC
0x8e4ce  ldloc.0
0x8e4cf  ldloc.1
0x8e4d0  ldelem.ref
0x8e4d1  stloc.2
0x8e4d2  ldloc.2
0x8e4d3  callvirt instance class [mscorlib]System.Collections.ICollection System.Xml.Serialization.TypeScope::get_TypeMappings()
0x8e4d8  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x8e4dd  stloc.3
0x8e4de  br       loc_8E7B7
0x8e4e3  ldloc.3
0x8e4e4  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x8e4e9  castclass System.Xml.Serialization.Mapping
0x8e4ee  stloc.s  4
0x8e4f0  ldloc.s  4
0x8e4f2  callvirt instance bool System.Xml.Serialization.Mapping::get_IsSoap()
0x8e4f7  brtrue   loc_8E7B7
0x8e4fc  ldloc.s  4
0x8e4fe  isinst   System.Xml.Serialization.EnumMapping
0x8e503  brfalse  loc_8E5F4
0x8e508  ldloc.s  4
0x8e50a  castclass System.Xml.Serialization.EnumMapping
0x8e50f  stloc.s  5
0x8e511  ldarg.0
0x8e512  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8e517  ldstr    aElseIf// "else if ("
0x8e51c  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x8e521  ldarg.0
0x8e522  ldstr    aXsitype// "xsiType"
0x8e527  ldloc.s  5
0x8e529  callvirt instance string System.Xml.Serialization.TypeMapping::get_TypeName()
0x8e52e  ldloc.s  5
0x8e530  callvirt instance string System.Xml.Serialization.TypeMapping::get_Namespace()
0x8e535  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteQNameEqual(string source, string name, string ns)
0x8e53a  ldarg.0
0x8e53b  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8e540  ldstr    asc_134612// ") {"
0x8e545  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8e54a  ldarg.0
0x8e54b  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8e550  dup
0x8e551  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x8e556  stloc.s  7
0x8e558  ldloc.s  7
0x8e55a  ldc.i4.1
0x8e55b  add
0x8e55c  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x8e561  ldarg.0
0x8e562  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8e567  ldstr    aReaderReadstar// "Reader.ReadStartElement();"
0x8e56c  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8e571  ldarg.0
0x8e572  ldloc.s  5
0x8e574  call     instance string System.Xml.Serialization.XmlSerializationCodeGen::ReferenceMapping(class System.Xml.Serialization.TypeMapping mapping)
0x8e579  stloc.s  6
0x8e57b  ldarg.0
0x8e57c  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8e581  ldstr    aObjectE// "object e = "
0x8e586  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x8e58b  ldarg.0
0x8e58c  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8e591  ldloc.s  6
0x8e593  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x8e598  ldarg.0
0x8e599  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8e59e  ldstr    aCollapsewhites_0// "(CollapseWhitespace(Reader.ReadString()"...
0x8e5a3  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8e5a8  ldarg.0
0x8e5a9  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8e5ae  ldstr    aReadendelement// "ReadEndElement();"
0x8e5b3  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8e5b8  ldarg.0
0x8e5b9  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8e5be  ldstr    aReturnE// "return e;"
0x8e5c3  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8e5c8  ldarg.0
0x8e5c9  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8e5ce  dup
0x8e5cf  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x8e5d4  stloc.s  7
0x8e5d6  ldloc.s  7
0x8e5d8  ldc.i4.1
0x8e5d9  sub
0x8e5da  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x8e5df  ldarg.0
0x8e5e0  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8e5e5  ldstr    asc_12E936// "}"
0x8e5ea  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8e5ef  br       loc_8E7B7
0x8e5f4  ldloc.s  4
0x8e5f6  isinst   System.Xml.Serialization.ArrayMapping
0x8e5fb  brfalse  loc_8E7B7
0x8e600  ldloc.s  4
0x8e602  castclass System.Xml.Serialization.ArrayMapping
0x8e607  stloc.s  8
0x8e609  ldloc.s  8
0x8e60b  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x8e610  callvirt instance bool System.Xml.Serialization.TypeDesc::get_HasDefaultConstructor()
0x8e615  brfalse  loc_8E7B7
0x8e61a  ldarg.0
0x8e61b  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8e620  ldstr    aElseIf// "else if ("
0x8e625  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x8e62a  ldarg.0
0x8e62b  ldstr    aXsitype// "xsiType"
0x8e630  ldloc.s  8
0x8e632  callvirt instance string System.Xml.Serialization.TypeMapping::get_TypeName()
0x8e637  ldloc.s  8
0x8e639  callvirt instance string System.Xml.Serialization.TypeMapping::get_Namespace()
0x8e63e  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteQNameEqual(string source, string name, string ns)
0x8e643  ldarg.0
0x8e644  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8e649  ldstr    asc_134612// ") {"
0x8e64e  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8e653  ldarg.0
0x8e654  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8e659  dup
0x8e65a  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x8e65f  stloc.s  7
0x8e661  ldloc.s  7
0x8e663  ldc.i4.1
0x8e664  add
0x8e665  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x8e66a  newobj   instance void System.Xml.Serialization.MemberMapping::.ctor()
0x8e66f  stloc.s  9
0x8e671  ldloc.s  9
0x8e673  ldloc.s  8
0x8e675  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x8e67a  callvirt instance void System.Xml.Serialization.AccessorMapping::set_TypeDesc(class System.Xml.Serialization.TypeDesc value)
0x8e67f  ldloc.s  9
0x8e681  ldloc.s  8
0x8e683  callvirt instance class System.Xml.Serialization.ElementAccessor[] System.Xml.Serialization.ArrayMapping::get_Elements()
0x8e688  callvirt instance void System.Xml.Serialization.AccessorMapping::set_Elements(class System.Xml.Serialization.ElementAccessor[] value)
0x8e68d  ldarg.0
0x8e68e  ldstr    aA_0// "a"
0x8e693  ldstr    aZ// "z"
0x8e698  ldc.i4.0
0x8e699  ldloc.s  9
0x8e69b  newobj   instance void Member::.ctor(class System.Xml.Serialization.XmlSerializationReaderCodeGen outerClass, string source, string arrayName, int32 i, class System.Xml.Serialization.MemberMapping mapping)
0x8e6a0  stloc.s  0xA
0x8e6a2  ldloc.s  8
0x8e6a4  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x8e6a9  stloc.s  0xB
0x8e6ab  ldloc.s  8
0x8e6ad  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x8e6b2  callvirt instance string System.Xml.Serialization.TypeDesc::get_CSharpName()
0x8e6b7  stloc.s  0xC
0x8e6b9  ldloc.s  0xB
0x8e6bb  callvirt instance bool System.Xml.Serialization.TypeDesc::get_UseReflection()
0x8e6c0  brfalse.s loc_8E6F9
0x8e6c2  ldloc.s  0xB
0x8e6c4  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsArray()
0x8e6c9  brfalse.s loc_8E6E7
0x8e6cb  ldarg.0
0x8e6cc  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8e6d1  ldtoken  [mscorlib]System.Array
0x8e6d6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x8e6db  callvirt instance string [mscorlib]System.Type::get_FullName()
0x8e6e0  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x8e6e5  br.s     loc_8E706
0x8e6e7  ldarg.0
0x8e6e8  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8e6ed  ldstr    aObject_3// "object"
0x8e6f2  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x8e6f7  br.s     loc_8E706
0x8e6f9  ldarg.0
0x8e6fa  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8e6ff  ldloc.s  0xC
0x8e701  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x8e706  ldarg.0
0x8e707  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8e70c  ldstr    aA_1// " a = "
0x8e711  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x8e716  ldloc.s  8
0x8e718  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x8e71d  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsValueType()
0x8e722  brfalse.s loc_8E757
0x8e724  ldarg.0
0x8e725  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8e72a  ldarg.0
0x8e72b  call     instance class System.Xml.Serialization.ReflectionAwareCodeGen System.Xml.Serialization.XmlSerializationCodeGen::get_RaCodeGen()
0x8e730  ldloc.s  0xC
0x8e732  ldloc.s  0xB
0x8e734  callvirt instance bool System.Xml.Serialization.TypeDesc::get_UseReflection()
0x8e739  ldc.i4.0
0x8e73a  ldc.i4.0
0x8e73b  callvirt instance string System.Xml.Serialization.ReflectionAwareCodeGen::GetStringForCreateInstance(string escapedTypeName, bool useReflection, bool ctorInaccessible, bool cast)
0x8e740  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x8e745  ldarg.0
0x8e746  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8e74b  ldstr    asc_12B71A// ";"
0x8e750  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8e755  br.s     loc_8E767
0x8e757  ldarg.0
0x8e758  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8e75d  ldstr    aNull_4// "null;"
0x8e762  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8e767  ldarg.0
0x8e768  ldloc.s  0xA
0x8e76a  callvirt instance string Member::get_Source()
0x8e76f  ldloc.s  0xA
0x8e771  callvirt instance string Member::get_ArrayName()
0x8e776  ldloc.s  8
0x8e778  ldc.i4.0
0x8e779  ldc.i4.0
0x8e77a  ldc.i4.m1
0x8e77b  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteArray(string source, string arrayName, class System.Xml.Serialization.ArrayMapping arrayMapping, bool readOnly, bool isNullable, int32 fixupIndex)
0x8e780  ldarg.0
0x8e781  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8e786  ldstr    aReturnA// "return a;"
0x8e78b  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8e790  ldarg.0
0x8e791  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8e796  dup
0x8e797  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x8e79c  stloc.s  7
0x8e79e  ldloc.s  7
0x8e7a0  ldc.i4.1
0x8e7a1  sub
0x8e7a2  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x8e7a7  ldarg.0
0x8e7a8  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8e7ad  ldstr    asc_12E936// "}"
0x8e7b2  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8e7b7  ldloc.3
0x8e7b8  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x8e7bd  brtrue   loc_8E4E3
0x8e7c2  leave.s  loc_8E7D8
0x8e7c4  ldloc.3
0x8e7c5  isinst   [mscorlib]System.IDisposable
0x8e7ca  stloc.s  0xD
0x8e7cc  ldloc.s  0xD
0x8e7ce  brfalse.s loc_8E7D7
0x8e7d0  ldloc.s  0xD
0x8e7d2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8e7d7  endfinally
0x8e7d8  ldloc.1
0x8e7d9  ldc.i4.1
0x8e7da  add
0x8e7db  stloc.1
0x8e7dc  ldloc.1
0x8e7dd  ldloc.0
0x8e7de  ldlen
0x8e7df  conv.i4
0x8e7e0  blt      loc_8E4CE
0x8e7e5  ret
```
