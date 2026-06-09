# System.Xml.Serialization.XmlSchemaExporter::ExportStructMapping

- ea: `0x80620`
- end: `0x808ce`
- name: `System.Xml.Serialization.XmlSchemaExporter::ExportStructMapping`
- size: `686`
- prototype: ``
- caller_count: `4`
- callee_count: `39`
- tags: `registry_config`

## callers

- `0x7f500`
- `0x7f5b0`
- `0x80620`
- `0x80b90`

## callees

- `0x132e0`
- `0x622f0`
- `0x68c10`
- `0x68c30`
- `0x68c50`
- `0x68c70`
- `0x68cd0`
- `0x68fb0`
- `0x69100`
- `0x69130`
- `0x69150`
- `0x69170`
- `0x69b20`
- `0x72b80`
- `0x72d60`
- `0x72e50`
- `0x7f270`
- `0x7f340`
- `0x7f3f0`
- `0x80620`
- `0x808d0`
- `0x80b90`
- `0x80d00`
- `0x821c0`
- `0xd1500`
- `0xd1540`
- `0xd1570`
- `0xd15f0`
- `0xd1890`
- `0xd1900`
- `0xd19a0`
- `0xd2170`
- `0xd2ac0`
- `0xd2af0`
- `0xd64f0`
- `0xd6520`
- `0xd6580`
- `0xd6af0`
- `0xd6b00`

## string_xrefs

- `0x80650`: `XmlCircularReference2`
- `0x806b1`: `XmlCannotIncludeInSchema`
- `0x80757`: `XmlAnonymousBaseType`

## pseudocode

```c

```

## disassembly

```asm
0x80620  ldarg.1
0x80621  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x80626  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsRoot()
0x8062b  brfalse.s loc_8063A
0x8062d  ldarg.0
0x8062e  ldc.i4.1
0x8062f  stfld    bool System.Xml.Serialization.XmlSchemaExporter::needToExportRoot
0x80634  ldsfld   class System.Xml.XmlQualifiedName System.Xml.XmlQualifiedName::Empty
0x80639  ret
0x8063a  ldarg.1
0x8063b  callvirt instance bool System.Xml.Serialization.TypeMapping::get_IsAnonymousType()
0x80640  brfalse.s loc_80691
0x80642  ldarg.0
0x80643  ldfld    class [mscorlib]System.Collections.Hashtable System.Xml.Serialization.XmlSchemaExporter::references
0x80648  ldarg.1
0x80649  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x8064e  brfalse.s loc_80684
0x80650  ldstr    aXmlcircularref// "XmlCircularReference2"
0x80655  ldc.i4.3
0x80656  newarr   [mscorlib]System.Object
0x8065b  dup
0x8065c  ldc.i4.0
0x8065d  ldarg.1
0x8065e  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x80663  callvirt instance string System.Xml.Serialization.TypeDesc::get_Name()
0x80668  stelem.ref
0x80669  dup
0x8066a  ldc.i4.1
0x8066b  ldstr    aAnonymoustype// "AnonymousType"
0x80670  stelem.ref
0x80671  dup
0x80672  ldc.i4.2
0x80673  ldstr    aFalse// "false"
0x80678  stelem.ref
0x80679  call     string System.Xml.Res::GetString(string name, object[] args)
0x8067e  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x80683  throw
0x80684  ldarg.0
0x80685  ldfld    class [mscorlib]System.Collections.Hashtable System.Xml.Serialization.XmlSchemaExporter::references
0x8068a  ldarg.1
0x8068b  ldarg.1
0x8068c  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x80691  ldarg.0
0x80692  ldfld    class [mscorlib]System.Collections.Hashtable System.Xml.Serialization.XmlSchemaExporter::types
0x80697  ldarg.1
0x80698  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x8069d  castclass System.Xml.Schema.XmlSchemaComplexType
0x806a2  stloc.0
0x806a3  ldloc.0
0x806a4  brtrue   loc_8087B
0x806a9  ldarg.1
0x806aa  callvirt instance bool System.Xml.Serialization.TypeMapping::get_IncludeInSchema()
0x806af  brtrue.s loc_806D5
0x806b1  ldstr    aXmlcannotinclu// "XmlCannotIncludeInSchema"
0x806b6  ldc.i4.1
0x806b7  newarr   [mscorlib]System.Object
0x806bc  dup
0x806bd  ldc.i4.0
0x806be  ldarg.1
0x806bf  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x806c4  callvirt instance string System.Xml.Serialization.TypeDesc::get_Name()
0x806c9  stelem.ref
0x806ca  call     string System.Xml.Res::GetString(string name, object[] args)
0x806cf  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x806d4  throw
0x806d5  ldarg.0
0x806d6  ldarg.1
0x806d7  ldarg.1
0x806d8  callvirt instance string System.Xml.Serialization.TypeMapping::get_Namespace()
0x806dd  call     instance void System.Xml.Serialization.XmlSchemaExporter::CheckForDuplicateType(class System.Xml.Serialization.TypeMapping mapping, string newNamespace)
0x806e2  newobj   instance void System.Xml.Schema.XmlSchemaComplexType::.ctor()
0x806e7  stloc.0
0x806e8  ldarg.1
0x806e9  callvirt instance bool System.Xml.Serialization.TypeMapping::get_IsAnonymousType()
0x806ee  brtrue.s loc_80717
0x806f0  ldloc.0
0x806f1  ldarg.1
0x806f2  callvirt instance string System.Xml.Serialization.TypeMapping::get_TypeName()
0x806f7  callvirt instance void System.Xml.Schema.XmlSchemaType::set_Name(string value)
0x806fc  ldarg.0
0x806fd  ldloc.0
0x806fe  ldarg.1
0x806ff  callvirt instance string System.Xml.Serialization.TypeMapping::get_Namespace()
0x80704  ldarg.2
0x80705  call     instance void System.Xml.Serialization.XmlSchemaExporter::AddSchemaItem(class System.Xml.Schema.XmlSchemaObject item, string ns, string referencingNs)
0x8070a  ldarg.0
0x8070b  ldfld    class [mscorlib]System.Collections.Hashtable System.Xml.Serialization.XmlSchemaExporter::types
0x80710  ldarg.1
0x80711  ldloc.0
0x80712  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x80717  ldloc.0
0x80718  ldarg.1
0x80719  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x8071e  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsAbstract()
0x80723  callvirt instance void System.Xml.Schema.XmlSchemaComplexType::set_IsAbstract(bool value)
0x80728  ldarg.1
0x80729  callvirt instance bool System.Xml.Serialization.StructMapping::get_IsOpenModel()
0x8072e  stloc.1
0x8072f  ldarg.1
0x80730  callvirt instance class System.Xml.Serialization.StructMapping System.Xml.Serialization.StructMapping::get_BaseMapping()
0x80735  brfalse  loc_80838
0x8073a  ldarg.1
0x8073b  callvirt instance class System.Xml.Serialization.StructMapping System.Xml.Serialization.StructMapping::get_BaseMapping()
0x80740  callvirt instance bool System.Xml.Serialization.TypeMapping::get_IncludeInSchema()
0x80745  brfalse  loc_80838
0x8074a  ldarg.1
0x8074b  callvirt instance class System.Xml.Serialization.StructMapping System.Xml.Serialization.StructMapping::get_BaseMapping()
0x80750  callvirt instance bool System.Xml.Serialization.TypeMapping::get_IsAnonymousType()
0x80755  brfalse.s loc_8079E
0x80757  ldstr    aXmlanonymousba// "XmlAnonymousBaseType"
0x8075c  ldc.i4.4
0x8075d  newarr   [mscorlib]System.Object
0x80762  dup
0x80763  ldc.i4.0
0x80764  ldarg.1
0x80765  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x8076a  callvirt instance string System.Xml.Serialization.TypeDesc::get_Name()
0x8076f  stelem.ref
0x80770  dup
0x80771  ldc.i4.1
0x80772  ldarg.1
0x80773  callvirt instance class System.Xml.Serialization.StructMapping System.Xml.Serialization.StructMapping::get_BaseMapping()
0x80778  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x8077d  callvirt instance string System.Xml.Serialization.TypeDesc::get_Name()
0x80782  stelem.ref
0x80783  dup
0x80784  ldc.i4.2
0x80785  ldstr    aAnonymoustype// "AnonymousType"
0x8078a  stelem.ref
0x8078b  dup
0x8078c  ldc.i4.3
0x8078d  ldstr    aFalse// "false"
0x80792  stelem.ref
0x80793  call     string System.Xml.Res::GetString(string name, object[] args)
0x80798  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x8079d  throw
0x8079e  ldarg.1
0x8079f  callvirt instance bool System.Xml.Serialization.StructMapping::get_HasSimpleContent()
0x807a4  brfalse.s loc_807DB
0x807a6  newobj   instance void System.Xml.Schema.XmlSchemaSimpleContent::.ctor()
0x807ab  stloc.2
0x807ac  newobj   instance void System.Xml.Schema.XmlSchemaSimpleContentExtension::.ctor()
0x807b1  stloc.3
0x807b2  ldloc.3
0x807b3  ldarg.0
0x807b4  ldarg.1
0x807b5  callvirt instance class System.Xml.Serialization.StructMapping System.Xml.Serialization.StructMapping::get_BaseMapping()
0x807ba  ldarg.1
0x807bb  callvirt instance string System.Xml.Serialization.TypeMapping::get_Namespace()
0x807c0  ldnull
0x807c1  call     instance class System.Xml.XmlQualifiedName System.Xml.Serialization.XmlSchemaExporter::ExportStructMapping(class System.Xml.Serialization.StructMapping mapping, string ns, class System.Xml.Schema.XmlSchemaElement element)
0x807c6  callvirt instance void System.Xml.Schema.XmlSchemaSimpleContentExtension::set_BaseTypeName(class System.Xml.XmlQualifiedName value)
0x807cb  ldloc.2
0x807cc  ldloc.3
0x807cd  callvirt instance void System.Xml.Schema.XmlSchemaContentModel::set_Content(class System.Xml.Schema.XmlSchemaContent value)
0x807d2  ldloc.0
0x807d3  ldloc.2
0x807d4  callvirt instance void System.Xml.Schema.XmlSchemaComplexType::set_ContentModel(class System.Xml.Schema.XmlSchemaContentModel value)
0x807d9  br.s     loc_80836
0x807db  newobj   instance void System.Xml.Schema.XmlSchemaComplexContentExtension::.ctor()
0x807e0  stloc.s  4
0x807e2  ldloc.s  4
0x807e4  ldarg.0
0x807e5  ldarg.1
0x807e6  callvirt instance class System.Xml.Serialization.StructMapping System.Xml.Serialization.StructMapping::get_BaseMapping()
0x807eb  ldarg.1
0x807ec  callvirt instance string System.Xml.Serialization.TypeMapping::get_Namespace()
0x807f1  ldnull
0x807f2  call     instance class System.Xml.XmlQualifiedName System.Xml.Serialization.XmlSchemaExporter::ExportStructMapping(class System.Xml.Serialization.StructMapping mapping, string ns, class System.Xml.Schema.XmlSchemaElement element)
0x807f7  callvirt instance void System.Xml.Schema.XmlSchemaComplexContentExtension::set_BaseTypeName(class System.Xml.XmlQualifiedName value)
0x807fc  newobj   instance void System.Xml.Schema.XmlSchemaComplexContent::.ctor()
0x80801  stloc.s  5
0x80803  ldloc.s  5
0x80805  ldloc.s  4
0x80807  callvirt instance void System.Xml.Schema.XmlSchemaContentModel::set_Content(class System.Xml.Schema.XmlSchemaContent value)
0x8080c  ldloc.s  5
0x8080e  ldarg.0
0x8080f  ldfld    class [mscorlib]System.Collections.Hashtable System.Xml.Serialization.XmlSchemaExporter::types
0x80814  ldarg.1
0x80815  callvirt instance class System.Xml.Serialization.StructMapping System.Xml.Serialization.StructMapping::get_BaseMapping()
0x8081a  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x8081f  castclass System.Xml.Schema.XmlSchemaComplexType
0x80824  call     bool System.Xml.Serialization.XmlSchemaImporter::IsMixed(class System.Xml.Schema.XmlSchemaType type)
0x80829  callvirt instance void System.Xml.Schema.XmlSchemaComplexContent::set_IsMixed(bool value)
0x8082e  ldloc.0
0x8082f  ldloc.s  5
0x80831  callvirt instance void System.Xml.Schema.XmlSchemaComplexType::set_ContentModel(class System.Xml.Schema.XmlSchemaContentModel value)
0x80836  ldc.i4.0
0x80837  stloc.1
0x80838  ldarg.0
0x80839  ldloc.0
0x8083a  ldarg.1
0x8083b  callvirt instance class System.Xml.Serialization.MemberMapping[] System.Xml.Serialization.StructMapping::get_Members()
0x80840  ldarg.1
0x80841  callvirt instance string System.Xml.Serialization.TypeMapping::get_TypeName()
0x80846  ldarg.1
0x80847  callvirt instance string System.Xml.Serialization.TypeMapping::get_Namespace()
0x8084c  ldarg.1
0x8084d  callvirt instance bool System.Xml.Serialization.StructMapping::get_HasSimpleContent()
0x80852  ldloc.1
0x80853  call     instance void System.Xml.Serialization.XmlSchemaExporter::ExportTypeMembers(class System.Xml.Schema.XmlSchemaComplexType type, class System.Xml.Serialization.MemberMapping[] members, string name, string ns, bool hasSimpleContent, bool openModel)
0x80858  ldarg.0
0x80859  ldarg.1
0x8085a  call     instance void System.Xml.Serialization.XmlSchemaExporter::ExportDerivedMappings(class System.Xml.Serialization.StructMapping mapping)
0x8085f  ldarg.1
0x80860  callvirt instance class System.Xml.Serialization.MemberMapping System.Xml.Serialization.StructMapping::get_XmlnsMember()
0x80865  brfalse.s loc_80888
0x80867  ldarg.0
0x80868  ldloc.0
0x80869  ldarg.1
0x8086a  callvirt instance class System.Xml.Serialization.MemberMapping System.Xml.Serialization.StructMapping::get_XmlnsMember()
0x8086f  callvirt instance string System.Xml.Serialization.MemberMapping::get_Name()
0x80874  call     instance void System.Xml.Serialization.XmlSchemaExporter::AddXmlnsAnnotation(class System.Xml.Schema.XmlSchemaComplexType type, string xmlnsMemberName)
0x80879  br.s     loc_80888
0x8087b  ldarg.0
0x8087c  ldarg.1
0x8087d  callvirt instance string System.Xml.Serialization.TypeMapping::get_Namespace()
0x80882  ldarg.2
0x80883  call     instance void System.Xml.Serialization.XmlSchemaExporter::AddSchemaImport(string ns, string referencingNs)
0x80888  ldarg.1
0x80889  callvirt instance bool System.Xml.Serialization.TypeMapping::get_IsAnonymousType()
0x8088e  brfalse.s loc_808AD
0x80890  ldarg.0
0x80891  ldfld    class [mscorlib]System.Collections.Hashtable System.Xml.Serialization.XmlSchemaExporter::references
0x80896  ldarg.1
0x80897  ldnull
0x80898  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x8089d  ldarg.3
0x8089e  brfalse.s loc_808A7
0x808a0  ldarg.3
0x808a1  ldloc.0
0x808a2  callvirt instance void System.Xml.Schema.XmlSchemaElement::set_SchemaType(class System.Xml.Schema.XmlSchemaType value)
0x808a7  ldsfld   class System.Xml.XmlQualifiedName System.Xml.XmlQualifiedName::Empty
0x808ac  ret
0x808ad  ldloc.0
0x808ae  callvirt instance string System.Xml.Schema.XmlSchemaType::get_Name()
0x808b3  ldarg.1
0x808b4  callvirt instance string System.Xml.Serialization.TypeMapping::get_Namespace()
0x808b9  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0x808be  stloc.s  6
0x808c0  ldarg.3
0x808c1  brfalse.s loc_808CB
0x808c3  ldarg.3
0x808c4  ldloc.s  6
0x808c6  callvirt instance void System.Xml.Schema.XmlSchemaElement::set_SchemaTypeName(class System.Xml.XmlQualifiedName value)
0x808cb  ldloc.s  6
0x808cd  ret
```
