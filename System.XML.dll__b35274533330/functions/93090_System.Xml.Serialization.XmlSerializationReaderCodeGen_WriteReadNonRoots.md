# System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteReadNonRoots

- ea: `0x93090`
- end: `0x93188`
- name: `System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteReadNonRoots`
- size: `248`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x8d310`

## callees

- `0x68450`
- `0x68460`
- `0x68470`
- `0x684b0`
- `0x86170`
- `0x92f70`
- `0x92fa0`

## string_xrefs

- `0x9310c`: `http://schemas.xmlsoap.org/soap/encoding/`
- `0x93096`: `Reader.MoveToContent();`
- `0x93176`: `Reader.MoveToContent();`
- `0x930ad`: `while (Reader.NodeType == `
- `0x930fc`: `string root = Reader.GetAttribute("root", "`
- `0x93166`: `ReadReferencedElement();`

## pseudocode

```c

```

## disassembly

```asm
0x93090  ldarg.0
0x93091  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x93096  ldstr    aReaderMovetoco// "Reader.MoveToContent();"
0x9309b  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x930a0  ldarg.0
0x930a1  call     instance int32 System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteWhileLoopStartCheck()
0x930a6  stloc.0
0x930a7  ldarg.0
0x930a8  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x930ad  ldstr    aWhileReaderNod_0// "while (Reader.NodeType == "
0x930b2  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x930b7  ldarg.0
0x930b8  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x930bd  ldtoken  System.Xml.XmlNodeType
0x930c2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x930c7  callvirt instance string [mscorlib]System.Type::get_FullName()
0x930cc  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x930d1  ldarg.0
0x930d2  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x930d7  ldstr    aElement_1// ".Element) {"
0x930dc  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x930e1  ldarg.0
0x930e2  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x930e7  dup
0x930e8  callvirt instance int32 System.Xml.Serialization.IndentedWriter::get_Indent()
0x930ed  stloc.1
0x930ee  ldloc.1
0x930ef  ldc.i4.1
0x930f0  add
0x930f1  callvirt instance void System.Xml.Serialization.IndentedWriter::set_Indent(int32 value)
0x930f6  ldarg.0
0x930f7  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x930fc  ldstr    aStringRootRead// "string root = Reader.GetAttribute(\"roo"...
0x93101  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x93106  ldarg.0
0x93107  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9310c  ldstr    aHttpSchemasXml// "http://schemas.xmlsoap.org/soap/encodin"...
0x93111  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x93116  ldarg.0
0x93117  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9311c  ldstr    asc_136322// "\");"
0x93121  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x93126  ldarg.0
0x93127  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9312c  ldstr    aIfRootNull// "if (root == null || "
0x93131  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x93136  ldarg.0
0x93137  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x9313c  ldtoken  System.Xml.XmlConvert
0x93141  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x93146  callvirt instance string [mscorlib]System.Type::get_FullName()
0x9314b  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0x93150  ldarg.0
0x93151  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x93156  ldstr    aTobooleanRootB// ".ToBoolean(root)) break;"
0x9315b  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x93160  ldarg.0
0x93161  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x93166  ldstr    aReadreferenced_1// "ReadReferencedElement();"
0x9316b  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x93170  ldarg.0
0x93171  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0x93176  ldstr    aReaderMovetoco// "Reader.MoveToContent();"
0x9317b  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0x93180  ldarg.0
0x93181  ldloc.0
0x93182  call     instance void System.Xml.Serialization.XmlSerializationReaderCodeGen::WriteWhileLoopEnd(int32 loopIndex)
0x93187  ret
```
