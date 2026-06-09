# System.Xml.Schema.XmlSchemaSet::Add_4

- ea: `0xd53f0`
- end: `0xd54f3`
- name: `System.Xml.Schema.XmlSchemaSet::Add_4`
- size: `259`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0xd95d0`

## callees

- `0x21560`
- `0xcfd30`
- `0xcff00`
- `0xd0210`
- `0xd2fb0`
- `0xd4d10`
- `0xd53c0`
- `0xd53f0`
- `0xd5500`
- `0xd5a70`
- `0xd5f40`

## string_xrefs

- `0xd53f3`: `reader`
- `0xd5428`: `Sch_ComponentAlreadySeenForNS`
- `0xd54d4`: `Sch_ComponentAlreadySeenForNS`

## pseudocode

```c

```

## disassembly

```asm
0xd53f0  ldarg.2
0xd53f1  brtrue.s loc_D53FE
0xd53f3  ldstr    aReader// "reader"
0xd53f8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xd53fd  throw
0xd53fe  ldarg.1
0xd53ff  brtrue.s loc_D5408
0xd5401  ldsfld   string [mscorlib]System.String::Empty
0xd5406  starg.s  1
0xd5408  ldarg.3
0xd5409  ldarg.1
0xd540a  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0xd540f  brfalse.s loc_D5434
0xd5411  ldarg.0
0xd5412  ldarg.2
0xd5413  callvirt instance string System.Xml.XmlReader::get_BaseURI()
0xd5418  ldc.i4.0
0xd5419  newobj   instance void [System]System.Uri::.ctor(string, valuetype [System]System.UriKind)
0xd541e  ldarg.1
0xd541f  ldnull
0xd5420  call     instance class System.Xml.Schema.XmlSchema System.Xml.Schema.XmlSchemaSet::FindSchemaByNSAndUrl(class [System]System.Uri schemaUri, string ns, valuetype [mscorlib]System.Collections.DictionaryEntry[] locationsTable)
0xd5425  brfalse.s loc_D5428
0xd5427  ret
0xd5428  ldstr    aSchComponental// "Sch_ComponentAlreadySeenForNS"
0xd542d  ldarg.1
0xd542e  newobj   instance void System.Xml.Schema.XmlSchemaException::.ctor(string res, string arg)
0xd5433  throw
0xd5434  ldarg.0
0xd5435  ldarg.2
0xd5436  callvirt instance string System.Xml.XmlReader::get_BaseURI()
0xd543b  ldc.i4.0
0xd543c  newobj   instance void [System]System.Uri::.ctor(string, valuetype [System]System.UriKind)
0xd5441  ldarg.1
0xd5442  ldloca.s 0
0xd5444  call     instance bool System.Xml.Schema.XmlSchemaSet::IsSchemaLoaded(class [System]System.Uri schemaUri, string targetNamespace, [out] class System.Xml.Schema.XmlSchema& schema)
0xd5449  brfalse.s loc_D544C
0xd544b  ret
0xd544c  ldarg.0
0xd544d  ldarg.1
0xd544e  ldarg.2
0xd544f  call     instance class System.Xml.Schema.XmlSchema System.Xml.Schema.XmlSchemaSet::ParseSchema(string targetNamespace, class System.Xml.XmlReader reader)
0xd5454  stloc.0
0xd5455  ldarg.0
0xd5456  ldfld    class [mscorlib]System.Collections.Hashtable System.Xml.Schema.XmlSchemaSet::schemaLocations
0xd545b  callvirt instance int32 [mscorlib]System.Collections.Hashtable::get_Count()
0xd5460  newarr   [mscorlib]System.Collections.DictionaryEntry
0xd5465  stloc.1
0xd5466  ldarg.0
0xd5467  ldfld    class [mscorlib]System.Collections.Hashtable System.Xml.Schema.XmlSchemaSet::schemaLocations
0xd546c  ldloc.1
0xd546d  ldc.i4.0
0xd546e  callvirt instance void [mscorlib]System.Collections.Hashtable::CopyTo(class [mscorlib]System.Array, int32)
0xd5473  ldarg.0
0xd5474  ldarg.1
0xd5475  ldloc.0
0xd5476  call     instance class System.Xml.Schema.XmlSchema System.Xml.Schema.XmlSchemaSet::Add(string targetNamespace, class System.Xml.Schema.XmlSchema schema)
0xd547b  pop
0xd547c  ldloc.0
0xd547d  callvirt instance class [mscorlib]System.Collections.ArrayList System.Xml.Schema.XmlSchema::get_ImportedSchemas()
0xd5482  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0xd5487  ldc.i4.0
0xd5488  ble.s    loc_D54F2
0xd548a  ldc.i4.0
0xd548b  stloc.3
0xd548c  br.s     loc_D54E4
0xd548e  ldloc.0
0xd548f  callvirt instance class [mscorlib]System.Collections.ArrayList System.Xml.Schema.XmlSchema::get_ImportedSchemas()
0xd5494  ldloc.3
0xd5495  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0xd549a  castclass System.Xml.Schema.XmlSchema
0xd549f  stloc.s  4
0xd54a1  ldloc.s  4
0xd54a3  callvirt instance string System.Xml.Schema.XmlSchema::get_TargetNamespace()
0xd54a8  stloc.2
0xd54a9  ldloc.2
0xd54aa  brtrue.s loc_D54B2
0xd54ac  ldsfld   string [mscorlib]System.String::Empty
0xd54b1  stloc.2
0xd54b2  ldarg.3
0xd54b3  ldloc.2
0xd54b4  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0xd54b9  brfalse.s loc_D54E0
0xd54bb  ldarg.0
0xd54bc  ldloc.s  4
0xd54be  callvirt instance class [System]System.Uri System.Xml.Schema.XmlSchema::get_BaseUri()
0xd54c3  ldloc.2
0xd54c4  ldloc.1
0xd54c5  call     instance class System.Xml.Schema.XmlSchema System.Xml.Schema.XmlSchemaSet::FindSchemaByNSAndUrl(class [System]System.Uri schemaUri, string ns, valuetype [mscorlib]System.Collections.DictionaryEntry[] locationsTable)
0xd54ca  brtrue.s loc_D54E0
0xd54cc  ldarg.0
0xd54cd  ldloc.0
0xd54ce  call     instance bool System.Xml.Schema.XmlSchemaSet::RemoveRecursive(class System.Xml.Schema.XmlSchema schemaToRemove)
0xd54d3  pop
0xd54d4  ldstr    aSchComponental// "Sch_ComponentAlreadySeenForNS"
0xd54d9  ldloc.2
0xd54da  newobj   instance void System.Xml.Schema.XmlSchemaException::.ctor(string res, string arg)
0xd54df  throw
0xd54e0  ldloc.3
0xd54e1  ldc.i4.1
0xd54e2  add
0xd54e3  stloc.3
0xd54e4  ldloc.3
0xd54e5  ldloc.0
0xd54e6  callvirt instance class [mscorlib]System.Collections.ArrayList System.Xml.Schema.XmlSchema::get_ImportedSchemas()
0xd54eb  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0xd54f0  blt.s    loc_D548E
0xd54f2  ret
```
