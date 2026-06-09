# System.Xml.Schema.Preprocessor::GetBuildInSchema

- ea: `0xbf100`
- end: `0xbf304`
- name: `System.Xml.Schema.Preprocessor::GetBuildInSchema`
- size: `516`
- prototype: ``
- caller_count: `8`
- callee_count: `27`
- tags: `registry_config, broker_com_uri`

## callers

- `0xae6f0`
- `0xbe980`
- `0xbebc0`
- `0xbed50`
- `0xc65c0`
- `0xd4f50`
- `0xd6320`
- `0xd9530`

## callees

- `0xe390`
- `0x132e0`
- `0xab110`
- `0xbf100`
- `0xcf8c0`
- `0xcfc90`
- `0xcfd40`
- `0xcfd80`
- `0xcfde0`
- `0xd08d0`
- `0xd0930`
- `0xd0950`
- `0xd0980`
- `0xd09b0`
- `0xd0b50`
- `0xd0bb0`
- `0xd0bc0`
- `0xd0d00`
- `0xd3310`
- `0xd3430`
- `0xd3d80`
- `0xd3f00`
- `0xd6690`
- `0xd66b0`
- `0xd6830`
- `0xd6870`
- `0xd68a0`

## string_xrefs

- `0xbf111`: `http://www.w3.org/XML/1998/namespace`
- `0xbf126`: `http://www.w3.org/XML/1998/namespace`
- `0xbf259`: `http://www.w3.org/XML/1998/namespace`
- `0xbf285`: `http://www.w3.org/XML/1998/namespace`
- `0xbf2b1`: `http://www.w3.org/XML/1998/namespace`
- `0xbf147`: `http://www.w3.org/2001/XMLSchema`
- `0xbf17a`: `http://www.w3.org/2001/XMLSchema`
- `0xbf1bc`: `http://www.w3.org/2001/XMLSchema`
- `0xbf175`: `anyURI`

## pseudocode

```c

```

## disassembly

```asm
0xbf100  ldsfld   class System.Xml.Schema.XmlSchema System.Xml.Schema.Preprocessor::builtInSchemaForXmlNS
0xbf105  brtrue   loc_BF2FE
0xbf10a  newobj   instance void System.Xml.Schema.XmlSchema::.ctor()
0xbf10f  stloc.0
0xbf110  ldloc.0
0xbf111  ldstr    aHttpWwwW3OrgXm// "http://www.w3.org/XML/1998/namespace"
0xbf116  callvirt instance void System.Xml.Schema.XmlSchema::set_TargetNamespace(string value)
0xbf11b  ldloc.0
0xbf11c  callvirt instance class System.Xml.Serialization.XmlSerializerNamespaces System.Xml.Schema.XmlSchemaObject::get_Namespaces()
0xbf121  ldstr    aXml// "xml"
0xbf126  ldstr    aHttpWwwW3OrgXm// "http://www.w3.org/XML/1998/namespace"
0xbf12b  callvirt instance void System.Xml.Serialization.XmlSerializerNamespaces::Add(string prefix, string ns)
0xbf130  newobj   instance void System.Xml.Schema.XmlSchemaAttribute::.ctor()
0xbf135  stloc.1
0xbf136  ldloc.1
0xbf137  ldstr    aLang// "lang"
0xbf13c  callvirt instance void System.Xml.Schema.XmlSchemaAttribute::set_Name(string value)
0xbf141  ldloc.1
0xbf142  ldstr    aLanguage// "language"
0xbf147  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0xbf14c  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0xbf151  callvirt instance void System.Xml.Schema.XmlSchemaAttribute::set_SchemaTypeName(class System.Xml.XmlQualifiedName value)
0xbf156  ldloc.0
0xbf157  callvirt instance class System.Xml.Schema.XmlSchemaObjectCollection System.Xml.Schema.XmlSchema::get_Items()
0xbf15c  ldloc.1
0xbf15d  callvirt instance int32 System.Xml.Schema.XmlSchemaObjectCollection::Add(class System.Xml.Schema.XmlSchemaObject item)
0xbf162  pop
0xbf163  newobj   instance void System.Xml.Schema.XmlSchemaAttribute::.ctor()
0xbf168  stloc.2
0xbf169  ldloc.2
0xbf16a  ldstr    aBase// "base"
0xbf16f  callvirt instance void System.Xml.Schema.XmlSchemaAttribute::set_Name(string value)
0xbf174  ldloc.2
0xbf175  ldstr    aAnyuri// "anyURI"
0xbf17a  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0xbf17f  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0xbf184  callvirt instance void System.Xml.Schema.XmlSchemaAttribute::set_SchemaTypeName(class System.Xml.XmlQualifiedName value)
0xbf189  ldloc.0
0xbf18a  callvirt instance class System.Xml.Schema.XmlSchemaObjectCollection System.Xml.Schema.XmlSchema::get_Items()
0xbf18f  ldloc.2
0xbf190  callvirt instance int32 System.Xml.Schema.XmlSchemaObjectCollection::Add(class System.Xml.Schema.XmlSchemaObject item)
0xbf195  pop
0xbf196  newobj   instance void System.Xml.Schema.XmlSchemaAttribute::.ctor()
0xbf19b  stloc.3
0xbf19c  ldloc.3
0xbf19d  ldstr    aSpace// "space"
0xbf1a2  callvirt instance void System.Xml.Schema.XmlSchemaAttribute::set_Name(string value)
0xbf1a7  newobj   instance void System.Xml.Schema.XmlSchemaSimpleType::.ctor()
0xbf1ac  stloc.s  4
0xbf1ae  newobj   instance void System.Xml.Schema.XmlSchemaSimpleTypeRestriction::.ctor()
0xbf1b3  stloc.s  5
0xbf1b5  ldloc.s  5
0xbf1b7  ldstr    aNcname// "NCName"
0xbf1bc  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0xbf1c1  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0xbf1c6  callvirt instance void System.Xml.Schema.XmlSchemaSimpleTypeRestriction::set_BaseTypeName(class System.Xml.XmlQualifiedName value)
0xbf1cb  newobj   instance void System.Xml.Schema.XmlSchemaEnumerationFacet::.ctor()
0xbf1d0  stloc.s  6
0xbf1d2  ldloc.s  6
0xbf1d4  ldstr    aDefault// "default"
0xbf1d9  callvirt instance void System.Xml.Schema.XmlSchemaFacet::set_Value(string value)
0xbf1de  ldloc.s  5
0xbf1e0  callvirt instance class System.Xml.Schema.XmlSchemaObjectCollection System.Xml.Schema.XmlSchemaSimpleTypeRestriction::get_Facets()
0xbf1e5  ldloc.s  6
0xbf1e7  callvirt instance int32 System.Xml.Schema.XmlSchemaObjectCollection::Add(class System.Xml.Schema.XmlSchemaObject item)
0xbf1ec  pop
0xbf1ed  newobj   instance void System.Xml.Schema.XmlSchemaEnumerationFacet::.ctor()
0xbf1f2  stloc.s  7
0xbf1f4  ldloc.s  7
0xbf1f6  ldstr    aPreserve// "preserve"
0xbf1fb  callvirt instance void System.Xml.Schema.XmlSchemaFacet::set_Value(string value)
0xbf200  ldloc.s  5
0xbf202  callvirt instance class System.Xml.Schema.XmlSchemaObjectCollection System.Xml.Schema.XmlSchemaSimpleTypeRestriction::get_Facets()
0xbf207  ldloc.s  7
0xbf209  callvirt instance int32 System.Xml.Schema.XmlSchemaObjectCollection::Add(class System.Xml.Schema.XmlSchemaObject item)
0xbf20e  pop
0xbf20f  ldloc.s  4
0xbf211  ldloc.s  5
0xbf213  callvirt instance void System.Xml.Schema.XmlSchemaSimpleType::set_Content(class System.Xml.Schema.XmlSchemaSimpleTypeContent value)
0xbf218  ldloc.3
0xbf219  ldloc.s  4
0xbf21b  callvirt instance void System.Xml.Schema.XmlSchemaAttribute::set_SchemaType(class System.Xml.Schema.XmlSchemaSimpleType value)
0xbf220  ldloc.3
0xbf221  ldstr    aPreserve// "preserve"
0xbf226  callvirt instance void System.Xml.Schema.XmlSchemaAttribute::set_DefaultValue(string value)
0xbf22b  ldloc.0
0xbf22c  callvirt instance class System.Xml.Schema.XmlSchemaObjectCollection System.Xml.Schema.XmlSchema::get_Items()
0xbf231  ldloc.3
0xbf232  callvirt instance int32 System.Xml.Schema.XmlSchemaObjectCollection::Add(class System.Xml.Schema.XmlSchemaObject item)
0xbf237  pop
0xbf238  newobj   instance void System.Xml.Schema.XmlSchemaAttributeGroup::.ctor()
0xbf23d  stloc.s  8
0xbf23f  ldloc.s  8
0xbf241  ldstr    aSpecialattrs// "specialAttrs"
0xbf246  callvirt instance void System.Xml.Schema.XmlSchemaAttributeGroup::set_Name(string value)
0xbf24b  newobj   instance void System.Xml.Schema.XmlSchemaAttribute::.ctor()
0xbf250  stloc.s  9
0xbf252  ldloc.s  9
0xbf254  ldstr    aLang// "lang"
0xbf259  ldstr    aHttpWwwW3OrgXm// "http://www.w3.org/XML/1998/namespace"
0xbf25e  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0xbf263  callvirt instance void System.Xml.Schema.XmlSchemaAttribute::set_RefName(class System.Xml.XmlQualifiedName value)
0xbf268  ldloc.s  8
0xbf26a  callvirt instance class System.Xml.Schema.XmlSchemaObjectCollection System.Xml.Schema.XmlSchemaAttributeGroup::get_Attributes()
0xbf26f  ldloc.s  9
0xbf271  callvirt instance int32 System.Xml.Schema.XmlSchemaObjectCollection::Add(class System.Xml.Schema.XmlSchemaObject item)
0xbf276  pop
0xbf277  newobj   instance void System.Xml.Schema.XmlSchemaAttribute::.ctor()
0xbf27c  stloc.s  0xA
0xbf27e  ldloc.s  0xA
0xbf280  ldstr    aSpace// "space"
0xbf285  ldstr    aHttpWwwW3OrgXm// "http://www.w3.org/XML/1998/namespace"
0xbf28a  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0xbf28f  callvirt instance void System.Xml.Schema.XmlSchemaAttribute::set_RefName(class System.Xml.XmlQualifiedName value)
0xbf294  ldloc.s  8
0xbf296  callvirt instance class System.Xml.Schema.XmlSchemaObjectCollection System.Xml.Schema.XmlSchemaAttributeGroup::get_Attributes()
0xbf29b  ldloc.s  0xA
0xbf29d  callvirt instance int32 System.Xml.Schema.XmlSchemaObjectCollection::Add(class System.Xml.Schema.XmlSchemaObject item)
0xbf2a2  pop
0xbf2a3  newobj   instance void System.Xml.Schema.XmlSchemaAttribute::.ctor()
0xbf2a8  stloc.s  0xB
0xbf2aa  ldloc.s  0xB
0xbf2ac  ldstr    aBase// "base"
0xbf2b1  ldstr    aHttpWwwW3OrgXm// "http://www.w3.org/XML/1998/namespace"
0xbf2b6  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0xbf2bb  callvirt instance void System.Xml.Schema.XmlSchemaAttribute::set_RefName(class System.Xml.XmlQualifiedName value)
0xbf2c0  ldloc.s  8
0xbf2c2  callvirt instance class System.Xml.Schema.XmlSchemaObjectCollection System.Xml.Schema.XmlSchemaAttributeGroup::get_Attributes()
0xbf2c7  ldloc.s  0xB
0xbf2c9  callvirt instance int32 System.Xml.Schema.XmlSchemaObjectCollection::Add(class System.Xml.Schema.XmlSchemaObject item)
0xbf2ce  pop
0xbf2cf  ldloc.0
0xbf2d0  callvirt instance class System.Xml.Schema.XmlSchemaObjectCollection System.Xml.Schema.XmlSchema::get_Items()
0xbf2d5  ldloc.s  8
0xbf2d7  callvirt instance int32 System.Xml.Schema.XmlSchemaObjectCollection::Add(class System.Xml.Schema.XmlSchemaObject item)
0xbf2dc  pop
0xbf2dd  ldloc.0
0xbf2de  ldc.i4.1
0xbf2df  callvirt instance void System.Xml.Schema.XmlSchema::set_IsPreprocessed(bool value)
0xbf2e4  ldloc.0
0xbf2e5  newobj   instance void System.Xml.NameTable::.ctor()
0xbf2ea  ldnull
0xbf2eb  ldnull
0xbf2ec  callvirt instance void System.Xml.Schema.XmlSchema::CompileSchemaInSet(class System.Xml.XmlNameTable nameTable, class System.Xml.Schema.ValidationEventHandler eventHandler, class System.Xml.Schema.XmlSchemaCompilationSettings compilationSettings)
0xbf2f1  ldsflda  class System.Xml.Schema.XmlSchema System.Xml.Schema.Preprocessor::builtInSchemaForXmlNS
0xbf2f6  ldloc.0
0xbf2f7  ldnull
0xbf2f8  call     T0x2B000140
0xbf2fd  pop
0xbf2fe  ldsfld   class System.Xml.Schema.XmlSchema System.Xml.Schema.Preprocessor::builtInSchemaForXmlNS
0xbf303  ret
```
