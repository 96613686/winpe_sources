# System.Xml.XmlNamespaceManager::AddNamespace

- ea: `0x12c50`
- end: `0x12de8`
- name: `System.Xml.XmlNamespaceManager::AddNamespace`
- size: `408`
- prototype: ``
- caller_count: `22`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x250f0`
- `0x25250`
- `0x30050`
- `0x44060`
- `0x489b0`
- `0x4d420`
- `0x4db90`
- `0x50310`
- `0x50660`
- `0x5a2c0`
- `0xbe010`
- `0xbe4c0`
- `0xbe690`
- `0xce3c0`
- `0xe7680`
- `0xe8f30`
- `0xe91d0`
- `0xe95c0`
- `0xea740`
- `0xf0270`
- `0xf0370`
- `0x117a40`

## callees

- `0xe6c0`
- `0x12c50`
- `0x12fd0`
- `0x13200`
- `0x62370`
- `0xf3af0`

## string_xrefs

- `0x12c97`: `http://www.w3.org/XML/1998/namespace`
- `0x12ca3`: `Xml_XmlPrefix`
- `0x12cc1`: `Xml_XmlnsPrefix`

## pseudocode

```c

```

## disassembly

```asm
0x12c50  ldarg.2
0x12c51  brtrue.s loc_12C5E
0x12c53  ldstr    aUri_0// "uri"
0x12c58  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x12c5d  throw
0x12c5e  ldarg.1
0x12c5f  brtrue.s loc_12C6C
0x12c61  ldstr    aPrefix// "prefix"
0x12c66  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x12c6b  throw
0x12c6c  ldarg.0
0x12c6d  ldfld    class System.Xml.XmlNameTable System.Xml.XmlNamespaceManager::nameTable
0x12c72  ldarg.1
0x12c73  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x12c78  starg.s  1
0x12c7a  ldarg.0
0x12c7b  ldfld    class System.Xml.XmlNameTable System.Xml.XmlNamespaceManager::nameTable
0x12c80  ldarg.2
0x12c81  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x12c86  starg.s  2
0x12c88  ldarg.0
0x12c89  ldfld    string System.Xml.XmlNamespaceManager::xml
0x12c8e  ldarg.1
0x12c8f  call     bool System.Xml.Ref::Equal(string strA, string strB)
0x12c94  brfalse.s loc_12CB3
0x12c96  ldarg.2
0x12c97  ldstr    aHttpWwwW3OrgXm// "http://www.w3.org/XML/1998/namespace"
0x12c9c  callvirt instance bool [mscorlib]System.String::Equals(string)
0x12ca1  brtrue.s loc_12CB3
0x12ca3  ldstr    aXmlXmlprefix// "Xml_XmlPrefix"
0x12ca8  call     string System.Xml.Res::GetString(string name)
0x12cad  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x12cb2  throw
0x12cb3  ldarg.0
0x12cb4  ldfld    string System.Xml.XmlNamespaceManager::xmlNs
0x12cb9  ldarg.1
0x12cba  call     bool System.Xml.Ref::Equal(string strA, string strB)
0x12cbf  brfalse.s loc_12CD1
0x12cc1  ldstr    aXmlXmlnsprefix// "Xml_XmlnsPrefix"
0x12cc6  call     string System.Xml.Res::GetString(string name)
0x12ccb  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x12cd0  throw
0x12cd1  ldarg.0
0x12cd2  ldarg.1
0x12cd3  call     instance int32 System.Xml.XmlNamespaceManager::LookupNamespaceDecl(string prefix)
0x12cd8  stloc.0
0x12cd9  ldc.i4.m1
0x12cda  stloc.1
0x12cdb  ldloc.0
0x12cdc  ldc.i4.m1
0x12cdd  beq.s    loc_12D0D
0x12cdf  ldarg.0
0x12ce0  ldfld    valuetype NamespaceDeclaration[] System.Xml.XmlNamespaceManager::nsdecls
0x12ce5  ldloc.0
0x12ce6  ldelema  NamespaceDeclaration
0x12ceb  ldfld    int32 NamespaceDeclaration::scopeId
0x12cf0  ldarg.0
0x12cf1  ldfld    int32 System.Xml.XmlNamespaceManager::scopeId
0x12cf6  bne.un.s loc_12D0B
0x12cf8  ldarg.0
0x12cf9  ldfld    valuetype NamespaceDeclaration[] System.Xml.XmlNamespaceManager::nsdecls
0x12cfe  ldloc.0
0x12cff  ldelema  NamespaceDeclaration
0x12d04  ldarg.2
0x12d05  stfld    string NamespaceDeclaration::uri
0x12d0a  ret
0x12d0b  ldloc.0
0x12d0c  stloc.1
0x12d0d  ldarg.0
0x12d0e  ldfld    int32 System.Xml.XmlNamespaceManager::lastDecl
0x12d13  ldarg.0
0x12d14  ldfld    valuetype NamespaceDeclaration[] System.Xml.XmlNamespaceManager::nsdecls
0x12d19  ldlen
0x12d1a  conv.i4
0x12d1b  ldc.i4.1
0x12d1c  sub
0x12d1d  bne.un.s loc_12D4C
0x12d1f  ldarg.0
0x12d20  ldfld    valuetype NamespaceDeclaration[] System.Xml.XmlNamespaceManager::nsdecls
0x12d25  ldlen
0x12d26  conv.i4
0x12d27  ldc.i4.2
0x12d28  mul
0x12d29  newarr   NamespaceDeclaration
0x12d2e  stloc.2
0x12d2f  ldarg.0
0x12d30  ldfld    valuetype NamespaceDeclaration[] System.Xml.XmlNamespaceManager::nsdecls
0x12d35  ldc.i4.0
0x12d36  ldloc.2
0x12d37  ldc.i4.0
0x12d38  ldarg.0
0x12d39  ldfld    valuetype NamespaceDeclaration[] System.Xml.XmlNamespaceManager::nsdecls
0x12d3e  ldlen
0x12d3f  conv.i4
0x12d40  call     void [mscorlib]System.Array::Copy(class [mscorlib]System.Array, int32, class [mscorlib]System.Array, int32, int32)
0x12d45  ldarg.0
0x12d46  ldloc.2
0x12d47  stfld    valuetype NamespaceDeclaration[] System.Xml.XmlNamespaceManager::nsdecls
0x12d4c  ldarg.0
0x12d4d  ldfld    valuetype NamespaceDeclaration[] System.Xml.XmlNamespaceManager::nsdecls
0x12d52  ldarg.0
0x12d53  ldarg.0
0x12d54  ldfld    int32 System.Xml.XmlNamespaceManager::lastDecl
0x12d59  ldc.i4.1
0x12d5a  add
0x12d5b  stloc.3
0x12d5c  ldloc.3
0x12d5d  stfld    int32 System.Xml.XmlNamespaceManager::lastDecl
0x12d62  ldloc.3
0x12d63  ldelema  NamespaceDeclaration
0x12d68  ldarg.1
0x12d69  ldarg.2
0x12d6a  ldarg.0
0x12d6b  ldfld    int32 System.Xml.XmlNamespaceManager::scopeId
0x12d70  ldloc.1
0x12d71  call     instance void NamespaceDeclaration::Set(string prefix, string uri, int32 scopeId, int32 previousNsIndex)
0x12d76  ldarg.0
0x12d77  ldfld    bool System.Xml.XmlNamespaceManager::useHashtable
0x12d7c  brfalse.s loc_12D91
0x12d7e  ldarg.0
0x12d7f  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> System.Xml.XmlNamespaceManager::hashTable
0x12d84  ldarg.1
0x12d85  ldarg.0
0x12d86  ldfld    int32 System.Xml.XmlNamespaceManager::lastDecl
0x12d8b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::set_Item(var<u1>, !!T0)
0x12d90  ret
0x12d91  ldarg.0
0x12d92  ldfld    int32 System.Xml.XmlNamespaceManager::lastDecl
0x12d97  ldc.i4.s 0x10
0x12d99  blt.s    loc_12DE7
0x12d9b  ldarg.0
0x12d9c  ldarg.0
0x12d9d  ldfld    int32 System.Xml.XmlNamespaceManager::lastDecl
0x12da2  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x12da7  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> System.Xml.XmlNamespaceManager::hashTable
0x12dac  ldc.i4.0
0x12dad  stloc.s  4
0x12daf  br.s     loc_12DD6
0x12db1  ldarg.0
0x12db2  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> System.Xml.XmlNamespaceManager::hashTable
0x12db7  ldarg.0
0x12db8  ldfld    valuetype NamespaceDeclaration[] System.Xml.XmlNamespaceManager::nsdecls
0x12dbd  ldloc.s  4
0x12dbf  ldelema  NamespaceDeclaration
0x12dc4  ldfld    string NamespaceDeclaration::prefix
0x12dc9  ldloc.s  4
0x12dcb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::set_Item(var<u1>, !!T0)
0x12dd0  ldloc.s  4
0x12dd2  ldc.i4.1
0x12dd3  add
0x12dd4  stloc.s  4
0x12dd6  ldloc.s  4
0x12dd8  ldarg.0
0x12dd9  ldfld    int32 System.Xml.XmlNamespaceManager::lastDecl
0x12dde  ble.s    loc_12DB1
0x12de0  ldarg.0
0x12de1  ldc.i4.1
0x12de2  stfld    bool System.Xml.XmlNamespaceManager::useHashtable
0x12de7  ret
```
