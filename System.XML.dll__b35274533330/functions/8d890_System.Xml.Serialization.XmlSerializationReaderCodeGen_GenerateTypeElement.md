# System.Xml.Serialization.XmlSerializationReaderCodeGen::GenerateTypeElement

- ea: `0x8d890`
- end: `0x8d9f7`
- name: `System.Xml.Serialization.XmlSerializationReaderCodeGen::GenerateTypeElement`
- size: `359`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config`

## callers

- `0x8c710`

## callees

- `0x68450`
- `0x68460`
- `0x68470`
- `0x684b0`
- `0x684e0`
- `0x68600`
- `0x68660`
- `0x68690`
- `0x68890`
- `0x68c50`
- `0x69630`
- `0x69670`
- `0x69a50`
- `0x79510`
- `0x86170`
- `0x8d890`
- `0x8da00`
- `0x90970`
- `0x90a90`
- `0x122a10`

## string_xrefs

- `0x8d953`: `Reader.MoveToContent();`
- `0x8d9b4`: `ReadReferencedElements();`
- `0x8d979`: `throw CreateUnknownNodeException();`

## pseudocode

```c

```

## disassembly

```asm
0x8d890  ldarg.1
0x8d891  callvirt instance class System.Xml.Serialization.ElementAccessor System.Xml.Serialization.XmlMapping::get_Accessor()
0x8d896  stloc.0
0x8d897  ldloc.0
0x8d898  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x8d89d  stloc.1
0x8d89e  ldarg.0
0x8d89f  ldloc.0
0x8d8a0  callvirt instance string System.Xml.Serialization.Accessor::get_Name()
0x8d8a5  call     instance string System.Xml.Serialization.XmlSerializationReaderCodeGen::NextMethodName(string name)
0x8d8aa  stloc.2
0x8d8ab  ldarg.0
0x8d8ac  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8d8b1  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine()
0x8d8b6  ldarg.0
0x8d8b7  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8d8bc  ldstr    aPublicObject_0// "public object "
0x8d8c1  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x8d8c6  ldarg.0
0x8d8c7  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8d8cc  ldloc.2
0x8d8cd  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x8d8d2  ldarg.0
0x8d8d3  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8d8d8  ldstr    asc_133CB8// "() {"
0x8d8dd  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8d8e2  ldarg.0
0x8d8e3  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8d8e8  dup
0x8d8e9  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x8d8ee  stloc.s  6
0x8d8f0  ldloc.s  6
0x8d8f2  ldc.i4.1
0x8d8f3  add
0x8d8f4  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x8d8f9  ldarg.0
0x8d8fa  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8d8ff  ldstr    aObjectONull// "object o = null;"
0x8d904  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8d909  newobj   instance void System.Xml.Serialization.MemberMapping::.ctor()
0x8d90e  stloc.3
0x8d90f  ldloc.3
0x8d910  ldloc.1
0x8d911  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x8d916  callvirt instance void System.Xml.Serialization.AccessorMapping::set_TypeDesc(class System.Xml.Serialization.TypeDesc value)
0x8d91b  ldloc.3
0x8d91c  ldc.i4.1
0x8d91d  newarr   System.Xml.Serialization.ElementAccessor
0x8d922  dup
0x8d923  ldc.i4.0
0x8d924  ldloc.0
0x8d925  stelem.ref
0x8d926  callvirt instance void System.Xml.Serialization.AccessorMapping::set_Elements(class System.Xml.Serialization.ElementAccessor[] value)
0x8d92b  ldc.i4.1
0x8d92c  newarr   Member
0x8d931  dup
0x8d932  ldc.i4.0
0x8d933  ldarg.0
0x8d934  ldstr    aO_0// "o"
0x8d939  ldstr    aO_0// "o"
0x8d93e  ldstr    aA_0// "a"
0x8d943  ldc.i4.0
0x8d944  ldloc.3
0x8d945  newobj   instance void Member::.ctor(class System.Xml.Serialization.XmlSerializationReaderCodeGen outerClass, string source, string arraySource, string arrayName, int32 i, class System.Xml.Serialization.MemberMapping mapping)
0x8d94a  stelem.ref
0x8d94b  stloc.s  4
0x8d94d  ldarg.0
0x8d94e  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8d953  ldstr    aReaderMovetoco// "Reader.MoveToContent();"
0x8d958  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8d95d  ldstr    aUnknownnodeNul_0// "UnknownNode(null, "
0x8d962  ldarg.0
0x8d963  ldloc.s  4
0x8d965  call     instance string System.Xml.Serialization.XmlSerializationReaderCodeGen::ExpectedElements(class Member[] members)
0x8d96a  ldstr    asc_133068// ");"
0x8d96f  call     string [mscorlib]System.String::Concat(string, string, string)
0x8d974  stloc.s  5
0x8d976  ldarg.0
0x8d977  ldloc.s  4
0x8d979  ldstr    aThrowCreateunk_0// "throw CreateUnknownNodeException();"
0x8d97e  ldloc.s  5
0x8d980  ldloc.0
0x8d981  callvirt instance bool System.Xml.Serialization.Accessor::get_Any()
0x8d986  brtrue.s loc_8D98B
0x8d988  ldnull
0x8d989  br.s     loc_8D98F
0x8d98b  ldloc.s  4
0x8d98d  ldc.i4.0
0x8d98e  ldelem.ref
0x8d98f  ldnull
0x8d990  ldnull
0x8d991  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteMemberElements(class Member[] members, string elementElseString, string elseString, class Member anyElement, class Member anyText, string checkTypeHrefsSource)
0x8d996  ldloc.0
0x8d997  callvirt instance bool System.Xml.Serialization.ElementAccessor::get_IsSoap()
0x8d99c  brfalse.s loc_8D9BE
0x8d99e  ldarg.0
0x8d99f  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8d9a4  ldstr    aReferencedO// "Referenced(o);"
0x8d9a9  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8d9ae  ldarg.0
0x8d9af  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8d9b4  ldstr    aReadreferenced// "ReadReferencedElements();"
0x8d9b9  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8d9be  ldarg.0
0x8d9bf  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8d9c4  ldstr    aReturnObjectO// "return (object)o;"
0x8d9c9  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8d9ce  ldarg.0
0x8d9cf  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8d9d4  dup
0x8d9d5  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x8d9da  stloc.s  6
0x8d9dc  ldloc.s  6
0x8d9de  ldc.i4.1
0x8d9df  sub
0x8d9e0  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x8d9e5  ldarg.0
0x8d9e6  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x8d9eb  ldstr    asc_12E936// "}"
0x8d9f0  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8d9f5  ldloc.2
0x8d9f6  ret
```
