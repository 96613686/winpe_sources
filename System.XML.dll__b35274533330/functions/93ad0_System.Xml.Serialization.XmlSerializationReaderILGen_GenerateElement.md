# System.Xml.Serialization.XmlSerializationReaderILGen::GenerateElement

- ea: `0x93ad0`
- end: `0x93b36`
- name: `System.Xml.Serialization.XmlSerializationReaderILGen::GenerateElement`
- size: `102`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x66630`

## callees

- `0x62370`
- `0x79570`
- `0x79590`
- `0x93ad0`
- `0x93e60`
- `0x947e0`

## string_xrefs

- `0x93ae2`: `XmlInternalError`
- `0x93b21`: `XmlInternalError`
- `0x93aec`: `xmlMapping`
- `0x93b2b`: `xmlMapping`

## pseudocode

```c

```

## disassembly

```asm
0x93ad0  ldarg.1
0x93ad1  callvirt instance bool System.Xml.Serialization.XmlMapping::get_IsReadable()
0x93ad6  brtrue.s loc_93ADA
0x93ad8  ldnull
0x93ad9  ret
0x93ada  ldarg.1
0x93adb  callvirt instance bool System.Xml.Serialization.XmlMapping::get_GenerateSerializer()
0x93ae0  brtrue.s loc_93AF7
0x93ae2  ldstr    aXmlinternalerr// "XmlInternalError"
0x93ae7  call     string System.Xml.Res::GetString(string name)
0x93aec  ldstr    aXmlmapping// "xmlMapping"
0x93af1  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x93af6  throw
0x93af7  ldarg.1
0x93af8  isinst   System.Xml.Serialization.XmlTypeMapping
0x93afd  brfalse.s loc_93B0C
0x93aff  ldarg.0
0x93b00  ldarg.1
0x93b01  castclass System.Xml.Serialization.XmlTypeMapping
0x93b06  call     instance string System.Xml.Serialization.XmlSerializationReaderILGen::GenerateTypeElement(class System.Xml.Serialization.XmlTypeMapping xmlTypeMapping)
0x93b0b  ret
0x93b0c  ldarg.1
0x93b0d  isinst   System.Xml.Serialization.XmlMembersMapping
0x93b12  brfalse.s loc_93B21
0x93b14  ldarg.0
0x93b15  ldarg.1
0x93b16  castclass System.Xml.Serialization.XmlMembersMapping
0x93b1b  call     instance string System.Xml.Serialization.XmlSerializationReaderILGen::GenerateMembersElement(class System.Xml.Serialization.XmlMembersMapping xmlMembersMapping)
0x93b20  ret
0x93b21  ldstr    aXmlinternalerr// "XmlInternalError"
0x93b26  call     string System.Xml.Res::GetString(string name)
0x93b2b  ldstr    aXmlmapping// "xmlMapping"
0x93b30  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x93b35  throw
```
