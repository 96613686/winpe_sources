# System.Xml.Serialization.XmlSerializationWriterCodeGen::GenerateElement

- ea: `0x9d750`
- end: `0x9d7b6`
- name: `System.Xml.Serialization.XmlSerializationWriterCodeGen::GenerateElement`
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
- `0x795a0`
- `0x9d750`
- `0x9e060`
- `0x9e870`

## string_xrefs

- `0x9d762`: `XmlInternalError`
- `0x9d7a1`: `XmlInternalError`
- `0x9d76c`: `xmlMapping`
- `0x9d7ab`: `xmlMapping`

## pseudocode

```c

```

## disassembly

```asm
0x9d750  ldarg.1
0x9d751  callvirt instance bool System.Xml.Serialization.XmlMapping::get_IsWriteable()
0x9d756  brtrue.s loc_9D75A
0x9d758  ldnull
0x9d759  ret
0x9d75a  ldarg.1
0x9d75b  callvirt instance bool System.Xml.Serialization.XmlMapping::get_GenerateSerializer()
0x9d760  brtrue.s loc_9D777
0x9d762  ldstr    aXmlinternalerr// "XmlInternalError"
0x9d767  call     string System.Xml.Res::GetString(string name)
0x9d76c  ldstr    aXmlmapping// "xmlMapping"
0x9d771  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x9d776  throw
0x9d777  ldarg.1
0x9d778  isinst   System.Xml.Serialization.XmlTypeMapping
0x9d77d  brfalse.s loc_9D78C
0x9d77f  ldarg.0
0x9d780  ldarg.1
0x9d781  castclass System.Xml.Serialization.XmlTypeMapping
0x9d786  call     instance string System.Xml.Serialization.XmlSerializationWriterCodeGen::GenerateTypeElement(class System.Xml.Serialization.XmlTypeMapping xmlTypeMapping)
0x9d78b  ret
0x9d78c  ldarg.1
0x9d78d  isinst   System.Xml.Serialization.XmlMembersMapping
0x9d792  brfalse.s loc_9D7A1
0x9d794  ldarg.0
0x9d795  ldarg.1
0x9d796  castclass System.Xml.Serialization.XmlMembersMapping
0x9d79b  call     instance string System.Xml.Serialization.XmlSerializationWriterCodeGen::GenerateMembersElement(class System.Xml.Serialization.XmlMembersMapping xmlMembersMapping)
0x9d7a0  ret
0x9d7a1  ldstr    aXmlinternalerr// "XmlInternalError"
0x9d7a6  call     string System.Xml.Res::GetString(string name)
0x9d7ab  ldstr    aXmlmapping// "xmlMapping"
0x9d7b0  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x9d7b5  throw
```
