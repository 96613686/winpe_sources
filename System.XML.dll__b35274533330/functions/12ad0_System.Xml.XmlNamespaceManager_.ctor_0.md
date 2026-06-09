# System.Xml.XmlNamespaceManager::.ctor_0

- ea: `0x12ad0`
- end: `0x12b83`
- name: `System.Xml.XmlNamespaceManager::.ctor_0`
- size: `179`
- prototype: ``
- caller_count: `26`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x13b0`
- `0x12a90`
- `0x23f50`
- `0x26e60`
- `0x27120`
- `0x271c0`
- `0x273a0`
- `0x28c90`
- `0x29dd0`
- `0x318c0`
- `0x42310`
- `0x489b0`
- `0x4ce50`
- `0x4ff90`
- `0x50310`
- `0x5a2c0`
- `0xbdde0`
- `0xbe010`
- `0xcdf80`
- `0xe7130`
- `0xe8f30`
- `0xed460`
- `0xed470`
- `0xf0270`
- `0xf0370`
- `0x124d90`

## callees

- `0x13200`
- `0xf3af0`

## string_xrefs

- `0x12b63`: `http://www.w3.org/XML/1998/namespace`
- `0x12b3f`: `http://www.w3.org/2000/xmlns/`
- `0x12af0`: `xmlns`

## pseudocode

```c

```

## disassembly

```asm
0x12ad0  ldarg.0
0x12ad1  call     instance void [mscorlib]System.Object::.ctor()
0x12ad6  ldarg.0
0x12ad7  ldarg.1
0x12ad8  stfld    class System.Xml.XmlNameTable System.Xml.XmlNamespaceManager::nameTable
0x12add  ldarg.0
0x12ade  ldarg.1
0x12adf  ldstr    aXml// "xml"
0x12ae4  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x12ae9  stfld    string System.Xml.XmlNamespaceManager::xml
0x12aee  ldarg.0
0x12aef  ldarg.1
0x12af0  ldstr    aXmlns// "xmlns"
0x12af5  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x12afa  stfld    string System.Xml.XmlNamespaceManager::xmlNs
0x12aff  ldarg.0
0x12b00  ldc.i4.8
0x12b01  newarr   NamespaceDeclaration
0x12b06  stfld    valuetype NamespaceDeclaration[] System.Xml.XmlNamespaceManager::nsdecls
0x12b0b  ldarg.1
0x12b0c  ldsfld   string [mscorlib]System.String::Empty
0x12b11  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x12b16  stloc.0
0x12b17  ldarg.0
0x12b18  ldfld    valuetype NamespaceDeclaration[] System.Xml.XmlNamespaceManager::nsdecls
0x12b1d  ldc.i4.0
0x12b1e  ldelema  NamespaceDeclaration
0x12b23  ldloc.0
0x12b24  ldloc.0
0x12b25  ldc.i4.m1
0x12b26  ldc.i4.m1
0x12b27  call     instance void NamespaceDeclaration::Set(string prefix, string uri, int32 scopeId, int32 previousNsIndex)
0x12b2c  ldarg.0
0x12b2d  ldfld    valuetype NamespaceDeclaration[] System.Xml.XmlNamespaceManager::nsdecls
0x12b32  ldc.i4.1
0x12b33  ldelema  NamespaceDeclaration
0x12b38  ldarg.0
0x12b39  ldfld    string System.Xml.XmlNamespaceManager::xmlNs
0x12b3e  ldarg.1
0x12b3f  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/xmlns/"
0x12b44  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x12b49  ldc.i4.m1
0x12b4a  ldc.i4.m1
0x12b4b  call     instance void NamespaceDeclaration::Set(string prefix, string uri, int32 scopeId, int32 previousNsIndex)
0x12b50  ldarg.0
0x12b51  ldfld    valuetype NamespaceDeclaration[] System.Xml.XmlNamespaceManager::nsdecls
0x12b56  ldc.i4.2
0x12b57  ldelema  NamespaceDeclaration
0x12b5c  ldarg.0
0x12b5d  ldfld    string System.Xml.XmlNamespaceManager::xml
0x12b62  ldarg.1
0x12b63  ldstr    aHttpWwwW3OrgXm// "http://www.w3.org/XML/1998/namespace"
0x12b68  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x12b6d  ldc.i4.0
0x12b6e  ldc.i4.m1
0x12b6f  call     instance void NamespaceDeclaration::Set(string prefix, string uri, int32 scopeId, int32 previousNsIndex)
0x12b74  ldarg.0
0x12b75  ldc.i4.2
0x12b76  stfld    int32 System.Xml.XmlNamespaceManager::lastDecl
0x12b7b  ldarg.0
0x12b7c  ldc.i4.1
0x12b7d  stfld    int32 System.Xml.XmlNamespaceManager::scopeId
0x12b82  ret
```
