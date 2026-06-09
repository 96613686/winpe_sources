# System.Xml.Serialization.XmlSerializationReaderCodeGen::GenerateElement

- ea: `0x8c710`
- end: `0x8c776`
- name: `System.Xml.Serialization.XmlSerializationReaderCodeGen::GenerateElement`
- size: `102`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x66150`

## callees

- `0x62370`
- `0x79570`
- `0x79590`
- `0x8c710`
- `0x8cb70`
- `0x8d890`

## string_xrefs

- `0x8c722`: `XmlInternalError`
- `0x8c761`: `XmlInternalError`
- `0x8c72c`: `xmlMapping`
- `0x8c76b`: `xmlMapping`

## pseudocode

```c

```

## disassembly

```asm
0x8c710  ldarg.1
0x8c711  callvirt instance bool System.Xml.Serialization.XmlMapping::get_IsReadable()
0x8c716  brtrue.s loc_8C71A
0x8c718  ldnull
0x8c719  ret
0x8c71a  ldarg.1
0x8c71b  callvirt instance bool System.Xml.Serialization.XmlMapping::get_GenerateSerializer()
0x8c720  brtrue.s loc_8C737
0x8c722  ldstr    aXmlinternalerr// "XmlInternalError"
0x8c727  call     string System.Xml.Res::GetString(string name)
0x8c72c  ldstr    aXmlmapping// "xmlMapping"
0x8c731  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x8c736  throw
0x8c737  ldarg.1
0x8c738  isinst   System.Xml.Serialization.XmlTypeMapping
0x8c73d  brfalse.s loc_8C74C
0x8c73f  ldarg.0
0x8c740  ldarg.1
0x8c741  castclass System.Xml.Serialization.XmlTypeMapping
0x8c746  call     instance string System.Xml.Serialization.XmlSerializationReaderCodeGen::GenerateTypeElement(class System.Xml.Serialization.XmlTypeMapping xmlTypeMapping)
0x8c74b  ret
0x8c74c  ldarg.1
0x8c74d  isinst   System.Xml.Serialization.XmlMembersMapping
0x8c752  brfalse.s loc_8C761
0x8c754  ldarg.0
0x8c755  ldarg.1
0x8c756  castclass System.Xml.Serialization.XmlMembersMapping
0x8c75b  call     instance string System.Xml.Serialization.XmlSerializationReaderCodeGen::GenerateMembersElement(class System.Xml.Serialization.XmlMembersMapping xmlMembersMapping)
0x8c760  ret
0x8c761  ldstr    aXmlinternalerr// "XmlInternalError"
0x8c766  call     string System.Xml.Res::GetString(string name)
0x8c76b  ldstr    aXmlmapping// "xmlMapping"
0x8c770  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x8c775  throw
```
