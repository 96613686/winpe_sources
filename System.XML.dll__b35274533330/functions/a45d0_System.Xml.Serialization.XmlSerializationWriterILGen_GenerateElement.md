# System.Xml.Serialization.XmlSerializationWriterILGen::GenerateElement

- ea: `0xa45d0`
- end: `0xa4636`
- name: `System.Xml.Serialization.XmlSerializationWriterILGen::GenerateElement`
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
- `0x795a0`
- `0xa45d0`
- `0xa4d30`
- `0xa53e0`

## string_xrefs

- `0xa45e2`: `XmlInternalError`
- `0xa4621`: `XmlInternalError`
- `0xa45ec`: `xmlMapping`
- `0xa462b`: `xmlMapping`

## pseudocode

```c

```

## disassembly

```asm
0xa45d0  ldarg.1
0xa45d1  callvirt instance bool System.Xml.Serialization.XmlMapping::get_IsWriteable()
0xa45d6  brtrue.s loc_A45DA
0xa45d8  ldnull
0xa45d9  ret
0xa45da  ldarg.1
0xa45db  callvirt instance bool System.Xml.Serialization.XmlMapping::get_GenerateSerializer()
0xa45e0  brtrue.s loc_A45F7
0xa45e2  ldstr    aXmlinternalerr// "XmlInternalError"
0xa45e7  call     string System.Xml.Res::GetString(string name)
0xa45ec  ldstr    aXmlmapping// "xmlMapping"
0xa45f1  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0xa45f6  throw
0xa45f7  ldarg.1
0xa45f8  isinst   System.Xml.Serialization.XmlTypeMapping
0xa45fd  brfalse.s loc_A460C
0xa45ff  ldarg.0
0xa4600  ldarg.1
0xa4601  castclass System.Xml.Serialization.XmlTypeMapping
0xa4606  call     instance string System.Xml.Serialization.XmlSerializationWriterILGen::GenerateTypeElement(class System.Xml.Serialization.XmlTypeMapping xmlTypeMapping)
0xa460b  ret
0xa460c  ldarg.1
0xa460d  isinst   System.Xml.Serialization.XmlMembersMapping
0xa4612  brfalse.s loc_A4621
0xa4614  ldarg.0
0xa4615  ldarg.1
0xa4616  castclass System.Xml.Serialization.XmlMembersMapping
0xa461b  call     instance string System.Xml.Serialization.XmlSerializationWriterILGen::GenerateMembersElement(class System.Xml.Serialization.XmlMembersMapping xmlMembersMapping)
0xa4620  ret
0xa4621  ldstr    aXmlinternalerr// "XmlInternalError"
0xa4626  call     string System.Xml.Res::GetString(string name)
0xa462b  ldstr    aXmlmapping// "xmlMapping"
0xa4630  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0xa4635  throw
```
