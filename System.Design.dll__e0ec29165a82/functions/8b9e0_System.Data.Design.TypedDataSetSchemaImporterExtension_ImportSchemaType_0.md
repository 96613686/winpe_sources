# System.Data.Design.TypedDataSetSchemaImporterExtension::ImportSchemaType_0

- ea: `0x8b9e0`
- end: `0x8bcd5`
- name: `System.Data.Design.TypedDataSetSchemaImporterExtension::ImportSchemaType_0`
- size: `757`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x72810`
- `0x8b9e0`
- `0x8bce0`
- `0x8bda0`
- `0x8be20`

## string_xrefs

- `0x8baaf`: `http://www.w3.org/2001/XMLSchema`
- `0x8bac5`: `urn:schemas-microsoft-com:xml-diffgram-v1`

## pseudocode

```c

```

## disassembly

```asm
0x8b9e0  ldarg.1
0x8b9e1  brtrue.s loc_8B9E5
0x8b9e3  ldnull
0x8b9e4  ret
0x8b9e5  ldarg.2
0x8b9e6  isinst   [System.Xml]System.Xml.Schema.XmlSchemaElement
0x8b9eb  brtrue.s loc_8B9EF
0x8b9ed  ldnull
0x8b9ee  ret
0x8b9ef  ldarg.2
0x8b9f0  castclass [System.Xml]System.Xml.Schema.XmlSchemaElement
0x8b9f5  stloc.0
0x8b9f6  ldloc.0
0x8b9f7  call     bool System.Data.Design.TypedDataSetSchemaImporterExtension::IsDataSet(class [System.Xml]System.Xml.Schema.XmlSchemaElement e)
0x8b9fc  brfalse.s loc_8BA2D
0x8b9fe  ldarg.0
0x8b9ff  ldfld    class [mscorlib]System.Collections.Hashtable System.Data.Design.TypedDataSetSchemaImporterExtension::importedTypes
0x8ba04  ldarg.1
0x8ba05  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x8ba0a  brfalse.s loc_8BA1E
0x8ba0c  ldarg.0
0x8ba0d  ldfld    class [mscorlib]System.Collections.Hashtable System.Data.Design.TypedDataSetSchemaImporterExtension::importedTypes
0x8ba12  ldarg.1
0x8ba13  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x8ba18  castclass [mscorlib]System.String
0x8ba1d  ret
0x8ba1e  ldarg.0
0x8ba1f  ldloc.0
0x8ba20  ldarg.3
0x8ba21  ldarg.s  5
0x8ba23  ldarg.s  6
0x8ba25  ldarg.s  8
0x8ba27  call     instance string System.Data.Design.TypedDataSetSchemaImporterExtension::GenerateTypedDataSet(class [System.Xml]System.Xml.Schema.XmlSchemaElement element, class [System.Xml]System.Xml.Serialization.XmlSchemas schemas, class [System]System.CodeDom.CodeCompileUnit compileUnit, class [System]System.CodeDom.CodeNamespace mainNamespace, class [System]System.CodeDom.Compiler.CodeDomProvider codeProvider)
0x8ba2c  ret
0x8ba2d  ldarg.1
0x8ba2e  isinst   [System.Xml]System.Xml.Schema.XmlSchemaComplexType
0x8ba33  brfalse  loc_8BCD3
0x8ba38  ldarg.1
0x8ba39  castclass [System.Xml]System.Xml.Schema.XmlSchemaComplexType
0x8ba3e  stloc.1
0x8ba3f  ldloc.1
0x8ba40  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaParticle [System.Xml]System.Xml.Schema.XmlSchemaComplexType::get_Particle()
0x8ba45  isinst   [System.Xml]System.Xml.Schema.XmlSchemaSequence
0x8ba4a  brfalse  loc_8BBDF
0x8ba4f  ldloc.1
0x8ba50  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaParticle [System.Xml]System.Xml.Schema.XmlSchemaComplexType::get_Particle()
0x8ba55  castclass [System.Xml]System.Xml.Schema.XmlSchemaSequence
0x8ba5a  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection [System.Xml]System.Xml.Schema.XmlSchemaGroupBase::get_Items()
0x8ba5f  stloc.2
0x8ba60  ldloc.2
0x8ba61  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x8ba66  ldc.i4.2
0x8ba67  bne.un   loc_8BBDF
0x8ba6c  ldloc.2
0x8ba6d  ldc.i4.0
0x8ba6e  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaObject [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection::get_Item(int32)
0x8ba73  isinst   [System.Xml]System.Xml.Schema.XmlSchemaAny
0x8ba78  brfalse  loc_8BBDF
0x8ba7d  ldloc.2
0x8ba7e  ldc.i4.1
0x8ba7f  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaObject [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection::get_Item(int32)
0x8ba84  isinst   [System.Xml]System.Xml.Schema.XmlSchemaAny
0x8ba89  brfalse  loc_8BBDF
0x8ba8e  ldloc.2
0x8ba8f  ldc.i4.0
0x8ba90  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaObject [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection::get_Item(int32)
0x8ba95  castclass [System.Xml]System.Xml.Schema.XmlSchemaAny
0x8ba9a  stloc.3
0x8ba9b  ldloc.2
0x8ba9c  ldc.i4.1
0x8ba9d  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaObject [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection::get_Item(int32)
0x8baa2  castclass [System.Xml]System.Xml.Schema.XmlSchemaAny
0x8baa7  stloc.s  4
0x8baa9  ldloc.3
0x8baaa  callvirt instance string [System.Xml]System.Xml.Schema.XmlSchemaAny::get_Namespace()
0x8baaf  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2001/XMLSchema"
0x8bab4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8bab9  brfalse  loc_8BBDF
0x8babe  ldloc.s  4
0x8bac0  callvirt instance string [System.Xml]System.Xml.Schema.XmlSchemaAny::get_Namespace()
0x8bac5  ldstr    aUrnSchemasMicr_0// "urn:schemas-microsoft-com:xml-diffgram-"...
0x8baca  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8bacf  brfalse  loc_8BBDF
0x8bad4  ldnull
0x8bad5  stloc.s  5
0x8bad7  ldnull
0x8bad8  stloc.s  6
0x8bada  ldloc.1
0x8badb  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection [System.Xml]System.Xml.Schema.XmlSchemaComplexType::get_Attributes()
0x8bae0  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaObjectEnumerator [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection::GetEnumerator()
0x8bae5  stloc.s  7
0x8bae7  br.s     loc_8BB45
0x8bae9  ldloc.s  7
0x8baeb  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaObject [System.Xml]System.Xml.Schema.XmlSchemaObjectEnumerator::get_Current()
0x8baf0  castclass [System.Xml]System.Xml.Schema.XmlSchemaAttribute
0x8baf5  stloc.s  8
0x8baf7  ldloc.s  8
0x8baf9  callvirt instance string [System.Xml]System.Xml.Schema.XmlSchemaAttribute::get_Name()
0x8bafe  ldstr    aNamespace_0// "namespace"
0x8bb03  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8bb08  brfalse.s loc_8BB1A
0x8bb0a  ldloc.s  8
0x8bb0c  callvirt instance string [System.Xml]System.Xml.Schema.XmlSchemaAttribute::get_FixedValue()
0x8bb11  callvirt instance string [mscorlib]System.String::Trim()
0x8bb16  stloc.s  5
0x8bb18  br.s     loc_8BB3B
0x8bb1a  ldloc.s  8
0x8bb1c  callvirt instance string [System.Xml]System.Xml.Schema.XmlSchemaAttribute::get_Name()
0x8bb21  ldstr    aTabletypename// "tableTypeName"
0x8bb26  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8bb2b  brfalse.s loc_8BB3B
0x8bb2d  ldloc.s  8
0x8bb2f  callvirt instance string [System.Xml]System.Xml.Schema.XmlSchemaAttribute::get_FixedValue()
0x8bb34  callvirt instance string [mscorlib]System.String::Trim()
0x8bb39  stloc.s  6
0x8bb3b  ldloc.s  5
0x8bb3d  brfalse.s loc_8BB45
0x8bb3f  ldloc.s  6
0x8bb41  brfalse.s loc_8BB45
0x8bb43  leave.s  loc_8BB65
0x8bb45  ldloc.s  7
0x8bb47  callvirt instance bool [System.Xml]System.Xml.Schema.XmlSchemaObjectEnumerator::MoveNext()
0x8bb4c  brtrue.s loc_8BAE9
0x8bb4e  leave.s  loc_8BB65
0x8bb50  ldloc.s  7
0x8bb52  isinst   [mscorlib]System.IDisposable
0x8bb57  stloc.s  9
0x8bb59  ldloc.s  9
0x8bb5b  brfalse.s loc_8BB64
0x8bb5d  ldloc.s  9
0x8bb5f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8bb64  endfinally
0x8bb65  ldloc.s  5
0x8bb67  brtrue.s loc_8BB6B
0x8bb69  ldnull
0x8bb6a  ret
0x8bb6b  ldarg.3
0x8bb6c  ldloc.s  5
0x8bb6e  callvirt instance class [mscorlib]System.Collections.IList [System.Xml]System.Xml.Serialization.XmlSchemas::GetSchemas(string)
0x8bb73  stloc.s  0xA
0x8bb75  ldloc.s  0xA
0x8bb77  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x8bb7c  ldc.i4.1
0x8bb7d  beq.s    loc_8BB81
0x8bb7f  ldnull
0x8bb80  ret
0x8bb81  ldloc.s  0xA
0x8bb83  ldc.i4.0
0x8bb84  callvirt instance object [mscorlib]System.Collections.IList::get_Item(int32)
0x8bb89  isinst   [System.Xml]System.Xml.Schema.XmlSchema
0x8bb8e  stloc.s  0xB
0x8bb90  ldloc.s  0xB
0x8bb92  brfalse.s loc_8BB9D
0x8bb94  ldloc.s  0xB
0x8bb96  callvirt instance string [System.Xml]System.Xml.Schema.XmlSchema::get_Id()
0x8bb9b  brtrue.s loc_8BB9F
0x8bb9d  ldnull
0x8bb9e  ret
0x8bb9f  ldarg.0
0x8bba0  ldloc.s  0xB
0x8bba2  ldarg.3
0x8bba3  call     instance class [System.Xml]System.Xml.Schema.XmlSchemaElement System.Data.Design.TypedDataSetSchemaImporterExtension::FindDataSetElement(class [System.Xml]System.Xml.Schema.XmlSchema schema, class [System.Xml]System.Xml.Serialization.XmlSchemas schemas)
0x8bba8  stloc.s  0xC
0x8bbaa  ldloc.s  0xC
0x8bbac  brfalse.s loc_8BBDD
0x8bbae  ldarg.0
0x8bbaf  ldloc.s  0xC
0x8bbb1  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaType [System.Xml]System.Xml.Schema.XmlSchemaElement::get_SchemaType()
0x8bbb6  ldloc.s  0xC
0x8bbb8  ldarg.3
0x8bbb9  ldarg.s  4
0x8bbbb  ldarg.s  5
0x8bbbd  ldarg.s  6
0x8bbbf  ldarg.s  7
0x8bbc1  ldarg.s  8
0x8bbc3  callvirt instance string [System.Xml]System.Xml.Serialization.Advanced.SchemaImporterExtension::ImportSchemaType(class [System.Xml]System.Xml.Schema.XmlSchemaType, class [System.Xml]System.Xml.Schema.XmlSchemaObject, class [System.Xml]System.Xml.Serialization.XmlSchemas, class [System.Xml]System.Xml.Serialization.XmlSchemaImporter, class [System]System.CodeDom.CodeCompileUnit, class [System]System.CodeDom.CodeNamespace, valuetype [System.Xml]System.Xml.Serialization.CodeGenerationOptions, class [System]System.CodeDom.Compiler.CodeDomProvider)
0x8bbc8  stloc.s  0xD
0x8bbca  ldloc.s  6
0x8bbcc  brtrue.s loc_8BBD1
0x8bbce  ldloc.s  0xD
0x8bbd0  ret
0x8bbd1  ldarg.s  8
0x8bbd3  ldloc.s  0xD
0x8bbd5  ldloc.s  6
0x8bbd7  call     string System.Data.Design.CodeGenHelper::GetTypeName(class [System]System.CodeDom.Compiler.CodeDomProvider codeProvider, string string1, string string2)
0x8bbdc  ret
0x8bbdd  ldnull
0x8bbde  ret
0x8bbdf  ldloc.1
0x8bbe0  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaParticle [System.Xml]System.Xml.Schema.XmlSchemaComplexType::get_Particle()
0x8bbe5  isinst   [System.Xml]System.Xml.Schema.XmlSchemaSequence
0x8bbea  brtrue.s loc_8BBFC
0x8bbec  ldloc.1
0x8bbed  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaParticle [System.Xml]System.Xml.Schema.XmlSchemaComplexType::get_Particle()
0x8bbf2  isinst   [System.Xml]System.Xml.Schema.XmlSchemaAll
0x8bbf7  brfalse  loc_8BCD3
0x8bbfc  ldloc.1
0x8bbfd  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaParticle [System.Xml]System.Xml.Schema.XmlSchemaComplexType::get_Particle()
0x8bc02  castclass [System.Xml]System.Xml.Schema.XmlSchemaGroupBase
0x8bc07  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection [System.Xml]System.Xml.Schema.XmlSchemaGroupBase::get_Items()
0x8bc0c  stloc.s  0xE
0x8bc0e  ldloc.s  0xE
0x8bc10  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x8bc15  ldc.i4.1
0x8bc16  bne.un   loc_8BCD3
0x8bc1b  ldloc.s  0xE
0x8bc1d  ldc.i4.0
0x8bc1e  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaObject [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection::get_Item(int32)
0x8bc23  isinst   [System.Xml]System.Xml.Schema.XmlSchemaAny
0x8bc28  brtrue.s loc_8BC2C
0x8bc2a  ldnull
0x8bc2b  ret
0x8bc2c  ldloc.s  0xE
0x8bc2e  ldc.i4.0
0x8bc2f  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaObject [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection::get_Item(int32)
0x8bc34  castclass [System.Xml]System.Xml.Schema.XmlSchemaAny
0x8bc39  stloc.s  0xF
0x8bc3b  ldloc.s  0xF
0x8bc3d  callvirt instance string [System.Xml]System.Xml.Schema.XmlSchemaAny::get_Namespace()
0x8bc42  brtrue.s loc_8BC46
0x8bc44  ldnull
0x8bc45  ret
0x8bc46  ldloc.s  0xF
0x8bc48  callvirt instance string [System.Xml]System.Xml.Schema.XmlSchemaAny::get_Namespace()
0x8bc4d  ldc.i4.s 0x23
0x8bc4f  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x8bc54  ldc.i4.0
0x8bc55  blt.s    loc_8BC59
0x8bc57  ldnull
0x8bc58  ret
0x8bc59  ldloc.s  0xF
0x8bc5b  callvirt instance string [System.Xml]System.Xml.Schema.XmlSchemaAny::get_Namespace()
0x8bc60  ldc.i4.s 0x20
0x8bc62  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x8bc67  ldc.i4.0
0x8bc68  blt.s    loc_8BC6C
0x8bc6a  ldnull
0x8bc6b  ret
0x8bc6c  ldarg.3
0x8bc6d  ldloc.s  0xF
0x8bc6f  callvirt instance string [System.Xml]System.Xml.Schema.XmlSchemaAny::get_Namespace()
0x8bc74  callvirt instance class [mscorlib]System.Collections.IList [System.Xml]System.Xml.Serialization.XmlSchemas::GetSchemas(string)
0x8bc79  stloc.s  0x10
0x8bc7b  ldloc.s  0x10
0x8bc7d  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x8bc82  ldc.i4.1
0x8bc83  beq.s    loc_8BC87
0x8bc85  ldnull
0x8bc86  ret
0x8bc87  ldloc.s  0x10
0x8bc89  ldc.i4.0
0x8bc8a  callvirt instance object [mscorlib]System.Collections.IList::get_Item(int32)
0x8bc8f  isinst   [System.Xml]System.Xml.Schema.XmlSchema
0x8bc94  stloc.s  0x11
0x8bc96  ldloc.s  0x11
0x8bc98  brtrue.s loc_8BC9C
0x8bc9a  ldnull
0x8bc9b  ret
0x8bc9c  ldloc.s  0x11
0x8bc9e  callvirt instance string [System.Xml]System.Xml.Schema.XmlSchema::get_Id()
0x8bca3  brtrue.s loc_8BCA7
0x8bca5  ldnull
0x8bca6  ret
0x8bca7  ldarg.0
0x8bca8  ldloc.s  0x11
0x8bcaa  ldarg.3
0x8bcab  call     instance class [System.Xml]System.Xml.Schema.XmlSchemaElement System.Data.Design.TypedDataSetSchemaImporterExtension::FindDataSetElement(class [System.Xml]System.Xml.Schema.XmlSchema schema, class [System.Xml]System.Xml.Serialization.XmlSchemas schemas)
0x8bcb0  stloc.s  0x12
0x8bcb2  ldloc.s  0x12
0x8bcb4  brfalse.s loc_8BCD1
0x8bcb6  ldarg.0
0x8bcb7  ldloc.s  0x12
0x8bcb9  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaType [System.Xml]System.Xml.Schema.XmlSchemaElement::get_SchemaType()
0x8bcbe  ldloc.s  0x12
0x8bcc0  ldarg.3
0x8bcc1  ldarg.s  4
0x8bcc3  ldarg.s  5
0x8bcc5  ldarg.s  6
0x8bcc7  ldarg.s  7
0x8bcc9  ldarg.s  8
0x8bccb  callvirt instance string [System.Xml]System.Xml.Serialization.Advanced.SchemaImporterExtension::ImportSchemaType(class [System.Xml]System.Xml.Schema.XmlSchemaType, class [System.Xml]System.Xml.Schema.XmlSchemaObject, class [System.Xml]System.Xml.Serialization.XmlSchemas, class [System.Xml]System.Xml.Serialization.XmlSchemaImporter, class [System]System.CodeDom.CodeCompileUnit, class [System]System.CodeDom.CodeNamespace, valuetype [System.Xml]System.Xml.Serialization.CodeGenerationOptions, class [System]System.CodeDom.Compiler.CodeDomProvider)
0x8bcd0  ret
0x8bcd1  ldnull
0x8bcd2  ret
0x8bcd3  ldnull
0x8bcd4  ret
```
