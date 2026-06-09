# XmlFilteredReader::.cctor

- ea: `0x2a360`
- end: `0x2a39b`
- name: `XmlFilteredReader::.cctor`
- size: `59`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0x2a38f`: `http://www.w3.org/2000/09/xmldsig#`
- `0x2a36f`: `urn:schemas-microsoft-com:asm.v1`
- `0x2a37f`: `urn:schemas-microsoft-com:asm.v2`

## pseudocode

```c

```

## disassembly

```asm
0x2a360  newobj   instance void [System]System.Collections.Specialized.StringCollection::.ctor()
0x2a365  stsfld   class [System]System.Collections.Specialized.StringCollection XmlFilteredReader::KnownNamespaces
0x2a36a  ldsfld   class [System]System.Collections.Specialized.StringCollection XmlFilteredReader::KnownNamespaces
0x2a36f  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:asm.v1"
0x2a374  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x2a379  pop
0x2a37a  ldsfld   class [System]System.Collections.Specialized.StringCollection XmlFilteredReader::KnownNamespaces
0x2a37f  ldstr    aUrnSchemasMicr_0// "urn:schemas-microsoft-com:asm.v2"
0x2a384  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x2a389  pop
0x2a38a  ldsfld   class [System]System.Collections.Specialized.StringCollection XmlFilteredReader::KnownNamespaces
0x2a38f  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/09/xmldsig#"
0x2a394  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x2a399  pop
0x2a39a  ret
```
