# System.Xml.Serialization.XmlSerializationCodeGen::GenerateSerializerContract

- ea: `0x86f20`
- end: `0x8708c`
- name: `System.Xml.Serialization.XmlSerializationCodeGen::GenerateSerializerContract`
- size: `364`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x66150`

## callees

- `0x68450`
- `0x68460`
- `0x68470`
- `0x684b0`
- `0x684e0`
- `0x86560`
- `0x865e0`
- `0x86ce0`
- `0x86d90`

## string_xrefs

- `0x86f31`: `public class XmlSerializerContract : global::`
- `0x86faa`: ` Reader { get { return new `
- `0x87001`: ` Writer { get { return new `
- `0x87029`: `readMethods`
- `0x8702e`: `ReadMethods`
- `0x8703c`: `writeMethods`
- `0x87041`: `WriteMethods`

## pseudocode

```c

```

## disassembly

```asm
0x86f20  ldarg.0
0x86f21  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x86f26  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine()
0x86f2b  ldarg.0
0x86f2c  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x86f31  ldstr    aPublicClassXml// "public class XmlSerializerContract : gl"...
0x86f36  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x86f3b  ldarg.0
0x86f3c  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x86f41  ldtoken  System.Xml.Serialization.XmlSerializerImplementation
0x86f46  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x86f4b  callvirt instance string [mscorlib]System.Type::get_FullName()
0x86f50  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x86f55  ldarg.0
0x86f56  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x86f5b  ldstr    asc_132D98// " {"
0x86f60  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x86f65  ldarg.0
0x86f66  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x86f6b  dup
0x86f6c  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x86f71  stloc.0
0x86f72  ldloc.0
0x86f73  ldc.i4.1
0x86f74  add
0x86f75  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x86f7a  ldarg.0
0x86f7b  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x86f80  ldstr    aPublicOverride_0// "public override global::"
0x86f85  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x86f8a  ldarg.0
0x86f8b  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x86f90  ldtoken  System.Xml.Serialization.XmlSerializationReader
0x86f95  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x86f9a  callvirt instance string [mscorlib]System.Type::get_FullName()
0x86f9f  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x86fa4  ldarg.0
0x86fa5  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x86faa  ldstr    aReaderGetRetur// " Reader { get { return new "
0x86faf  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x86fb4  ldarg.0
0x86fb5  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x86fba  ldarg.s  4
0x86fbc  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x86fc1  ldarg.0
0x86fc2  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x86fc7  ldstr    asc_13336A// "(); } }"
0x86fcc  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x86fd1  ldarg.0
0x86fd2  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x86fd7  ldstr    aPublicOverride_0// "public override global::"
0x86fdc  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x86fe1  ldarg.0
0x86fe2  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x86fe7  ldtoken  System.Xml.Serialization.XmlSerializationWriter
0x86fec  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x86ff1  callvirt instance string [mscorlib]System.Type::get_FullName()
0x86ff6  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x86ffb  ldarg.0
0x86ffc  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x87001  ldstr    aWriterGetRetur// " Writer { get { return new "
0x87006  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x8700b  ldarg.0
0x8700c  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x87011  ldarg.s  6
0x87013  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x87018  ldarg.0
0x87019  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x8701e  ldstr    asc_13336A// "(); } }"
0x87023  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x87028  ldarg.0
0x87029  ldstr    aReadmethods// "readMethods"
0x8702e  ldstr    aReadmethods_0// "ReadMethods"
0x87033  ldarg.s  5
0x87035  ldarg.2
0x87036  call     instance void System.Xml.Serialization.XmlSerializationCodeGen::GeneratePublicMethods(string privateName, string publicName, string[] methods, class System.Xml.Serialization.XmlMapping[] xmlMappings)
0x8703b  ldarg.0
0x8703c  ldstr    aWritemethods// "writeMethods"
0x87041  ldstr    aWritemethods_0// "WriteMethods"
0x87046  ldarg.s  7
0x87048  ldarg.2
0x87049  call     instance void System.Xml.Serialization.XmlSerializationCodeGen::GeneratePublicMethods(string privateName, string publicName, string[] methods, class System.Xml.Serialization.XmlMapping[] xmlMappings)
0x8704e  ldarg.0
0x8704f  ldarg.s  8
0x87051  call     instance void System.Xml.Serialization.XmlSerializationCodeGen::GenerateTypedSerializers(class [mscorlib]System.Collections.Hashtable serializers)
0x87056  ldarg.0
0x87057  ldarg.3
0x87058  call     instance void System.Xml.Serialization.XmlSerializationCodeGen::GenerateSupportedTypes(class [mscorlib]System.Type[] types)
0x8705d  ldarg.0
0x8705e  ldarg.s  8
0x87060  ldarg.2
0x87061  call     instance void System.Xml.Serialization.XmlSerializationCodeGen::GenerateGetSerializer(class [mscorlib]System.Collections.Hashtable serializers, class System.Xml.Serialization.XmlMapping[] xmlMappings)
0x87066  ldarg.0
0x87067  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x8706c  dup
0x8706d  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x87072  stloc.0
0x87073  ldloc.0
0x87074  ldc.i4.1
0x87075  sub
0x87076  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x8707b  ldarg.0
0x8707c  ldfld    class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::writer
0x87081  ldstr    asc_12E936// "}"
0x87086  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x8708b  ret
```
