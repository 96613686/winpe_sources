# System.Xml.Serialization.XmlSerializationCodeGen::GenerateTypedSerializer

- ea: `0x86930`
- end: `0x86cd7`
- name: `System.Xml.Serialization.XmlSerializationCodeGen::GenerateTypedSerializer`
- size: `935`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config`

## callers

- `0x66150`

## callees

- `0x654e0`
- `0x65640`
- `0x65ac0`
- `0x68450`
- `0x68460`
- `0x68470`
- `0x684b0`
- `0x684e0`
- `0x68600`
- `0x68660`
- `0x68690`
- `0x686d0`
- `0x68810`
- `0x68c50`
- `0x72b80`
- `0x79510`
- `0x862f0`
- `0x86930`

## string_xrefs

- `0x86a0d`: ` CanDeserialize(`
- `0x86a37`: ` xmlReader) {`
- `0x86a7b`: `return xmlReader.IsStartElement(`
- `0x86b2d`: ` writer) {`
- `0x86b6f`: `)writer).`
- `0x86bf9`: `protected override object Deserialize(`
- `0x86c23`: ` reader) {`
- `0x86c65`: `)reader).`

## pseudocode

```c

```

## disassembly

```asm
0x86930  ldarg.3
0x86931  callvirt instance class System.Xml.Serialization.ElementAccessor System.Xml.Serialization.XmlMapping::get_Accessor()
0x86936  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x8693b  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x86940  callvirt instance string System.Xml.Serialization.TypeDesc::get_Name()
0x86945  call     string System.Xml.Serialization.Accessor::UnescapeName(string name)
0x8694a  call     string System.Xml.Serialization.CodeIdentifier::MakeValid(string identifier)
0x8694f  stloc.0
0x86950  ldarg.s  4
0x86952  ldloc.0
0x86953  ldstr    aSerializer// "Serializer"
0x86958  call     string [mscorlib]System.String::Concat(string, string)
0x8695d  ldarg.3
0x8695e  callvirt instance string System.Xml.Serialization.CodeIdentifiers::AddUnique(string identifier, object value)
0x86963  stloc.0
0x86964  ldarg.0
0x86965  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x8696a  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine()
0x8696f  ldarg.0
0x86970  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x86975  ldstr    aPublicSealedCl// "public sealed class "
0x8697a  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x8697f  ldarg.0
0x86980  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x86985  ldloc.0
0x86986  call     string System.Xml.Serialization.CodeIdentifier::GetCSharpName(string name)
0x8698b  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x86990  ldarg.0
0x86991  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x86996  ldstr    asc_132EFE// " : "
0x8699b  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x869a0  ldarg.0
0x869a1  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x869a6  ldarg.s  5
0x869a8  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x869ad  ldarg.0
0x869ae  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x869b3  ldstr    asc_132D98// " {"
0x869b8  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x869bd  ldarg.0
0x869be  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x869c3  dup
0x869c4  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x869c9  stloc.1
0x869ca  ldloc.1
0x869cb  ldc.i4.1
0x869cc  add
0x869cd  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x869d2  ldarg.0
0x869d3  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x869d8  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine()
0x869dd  ldarg.0
0x869de  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x869e3  ldstr    aPublicOverride// "public override "
0x869e8  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x869ed  ldarg.0
0x869ee  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x869f3  ldtoken  [mscorlib]System.Boolean
0x869f8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x869fd  callvirt instance string [mscorlib]System.Type::get_FullName()
0x86a02  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x86a07  ldarg.0
0x86a08  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x86a0d  ldstr    aCandeserialize// " CanDeserialize("
0x86a12  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x86a17  ldarg.0
0x86a18  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x86a1d  ldtoken  System.Xml.XmlReader
0x86a22  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x86a27  callvirt instance string [mscorlib]System.Type::get_FullName()
0x86a2c  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x86a31  ldarg.0
0x86a32  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x86a37  ldstr    aXmlreader_0// " xmlReader) {"
0x86a3c  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x86a41  ldarg.0
0x86a42  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x86a47  dup
0x86a48  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x86a4d  stloc.1
0x86a4e  ldloc.1
0x86a4f  ldc.i4.1
0x86a50  add
0x86a51  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x86a56  ldarg.3
0x86a57  callvirt instance class System.Xml.Serialization.ElementAccessor System.Xml.Serialization.XmlMapping::get_Accessor()
0x86a5c  callvirt instance bool System.Xml.Serialization.Accessor::get_Any()
0x86a61  brfalse.s loc_86A75
0x86a63  ldarg.0
0x86a64  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x86a69  ldstr    aReturnTrue_0// "return true;"
0x86a6e  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x86a73  br.s     loc_86AC7
0x86a75  ldarg.0
0x86a76  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x86a7b  ldstr    aReturnXmlreade// "return xmlReader.IsStartElement("
0x86a80  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x86a85  ldarg.0
0x86a86  ldarg.3
0x86a87  callvirt instance class System.Xml.Serialization.ElementAccessor System.Xml.Serialization.XmlMapping::get_Accessor()
0x86a8c  callvirt instance string System.Xml.Serialization.Accessor::get_Name()
0x86a91  call     instance void System.Xml.Serialization.XmlSerializationCodeGen::WriteQuotedCSharpString(string value)
0x86a96  ldarg.0
0x86a97  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x86a9c  ldstr    asc_128826// ", "
0x86aa1  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x86aa6  ldarg.0
0x86aa7  ldarg.3
0x86aa8  callvirt instance class System.Xml.Serialization.ElementAccessor System.Xml.Serialization.XmlMapping::get_Accessor()
0x86aad  callvirt instance string System.Xml.Serialization.Accessor::get_Namespace()
0x86ab2  call     instance void System.Xml.Serialization.XmlSerializationCodeGen::WriteQuotedCSharpString(string value)
0x86ab7  ldarg.0
0x86ab8  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x86abd  ldstr    asc_133068// ");"
0x86ac2  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x86ac7  ldarg.0
0x86ac8  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x86acd  dup
0x86ace  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x86ad3  stloc.1
0x86ad4  ldloc.1
0x86ad5  ldc.i4.1
0x86ad6  sub
0x86ad7  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x86adc  ldarg.0
0x86add  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x86ae2  ldstr    asc_12E936// "}"
0x86ae7  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x86aec  ldarg.2
0x86aed  brfalse  loc_86BE2
0x86af2  ldarg.0
0x86af3  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x86af8  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine()
0x86afd  ldarg.0
0x86afe  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x86b03  ldstr    aProtectedOverr_0// "protected override void Serialize(objec"...
0x86b08  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x86b0d  ldarg.0
0x86b0e  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x86b13  ldtoken  System.Xml.Serialization.XmlSerializationWriter
0x86b18  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x86b1d  callvirt instance string [mscorlib]System.Type::get_FullName()
0x86b22  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x86b27  ldarg.0
0x86b28  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x86b2d  ldstr    aWriter// " writer) {"
0x86b32  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x86b37  ldarg.0
0x86b38  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x86b3d  dup
0x86b3e  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x86b43  stloc.1
0x86b44  ldloc.1
0x86b45  ldc.i4.1
0x86b46  add
0x86b47  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x86b4c  ldarg.0
0x86b4d  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x86b52  ldstr    asc_12FF58// "(("
0x86b57  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x86b5c  ldarg.0
0x86b5d  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x86b62  ldarg.s  7
0x86b64  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x86b69  ldarg.0
0x86b6a  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x86b6f  ldstr    aWriter_0// ")writer)."
0x86b74  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x86b79  ldarg.0
0x86b7a  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x86b7f  ldarg.2
0x86b80  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x86b85  ldarg.0
0x86b86  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x86b8b  ldstr    asc_12DDFC// "("
0x86b90  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x86b95  ldarg.3
0x86b96  isinst   System.Xml.Serialization.XmlMembersMapping
0x86b9b  brfalse.s loc_86BAD
0x86b9d  ldarg.0
0x86b9e  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x86ba3  ldstr    aObject_0// "(object[])"
0x86ba8  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x86bad  ldarg.0
0x86bae  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x86bb3  ldstr    aObjecttoserial// "objectToSerialize);"
0x86bb8  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x86bbd  ldarg.0
0x86bbe  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x86bc3  dup
0x86bc4  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x86bc9  stloc.1
0x86bca  ldloc.1
0x86bcb  ldc.i4.1
0x86bcc  sub
0x86bcd  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x86bd2  ldarg.0
0x86bd3  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x86bd8  ldstr    asc_12E936// "}"
0x86bdd  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x86be2  ldarg.1
0x86be3  brfalse  loc_86CB0
0x86be8  ldarg.0
0x86be9  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x86bee  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine()
0x86bf3  ldarg.0
0x86bf4  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x86bf9  ldstr    aProtectedOverr_1// "protected override object Deserialize("
0x86bfe  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x86c03  ldarg.0
0x86c04  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x86c09  ldtoken  System.Xml.Serialization.XmlSerializationReader
0x86c0e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x86c13  callvirt instance string [mscorlib]System.Type::get_FullName()
0x86c18  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x86c1d  ldarg.0
0x86c1e  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x86c23  ldstr    aReader_0// " reader) {"
0x86c28  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x86c2d  ldarg.0
0x86c2e  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x86c33  dup
0x86c34  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x86c39  stloc.1
0x86c3a  ldloc.1
0x86c3b  ldc.i4.1
0x86c3c  add
0x86c3d  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x86c42  ldarg.0
0x86c43  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x86c48  ldstr    aReturn_0// "return (("
0x86c4d  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x86c52  ldarg.0
0x86c53  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x86c58  ldarg.s  6
0x86c5a  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x86c5f  ldarg.0
0x86c60  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x86c65  ldstr    aReader_1// ")reader)."
0x86c6a  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x86c6f  ldarg.0
0x86c70  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x86c75  ldarg.1
0x86c76  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x86c7b  ldarg.0
0x86c7c  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x86c81  ldstr    asc_132DE6// "();"
0x86c86  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x86c8b  ldarg.0
0x86c8c  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x86c91  dup
0x86c92  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x86c97  stloc.1
0x86c98  ldloc.1
0x86c99  ldc.i4.1
0x86c9a  sub
0x86c9b  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x86ca0  ldarg.0
0x86ca1  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x86ca6  ldstr    asc_12E936// "}"
0x86cab  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x86cb0  ldarg.0
0x86cb1  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x86cb6  dup
0x86cb7  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x86cbc  stloc.1
0x86cbd  ldloc.1
0x86cbe  ldc.i4.1
0x86cbf  sub
0x86cc0  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x86cc5  ldarg.0
0x86cc6  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x86ccb  ldstr    asc_12E936// "}"
0x86cd0  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x86cd5  ldloc.0
0x86cd6  ret
```
