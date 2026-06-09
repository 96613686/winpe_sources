# System.Xml.Serialization.SoapSchemaExporter::ExportArrayMapping

- ea: `0x704a0`
- end: `0x70637`
- name: `System.Xml.Serialization.SoapSchemaExporter::ExportArrayMapping`
- size: `407`
- prototype: ``
- caller_count: `1`
- callee_count: `29`
- tags: `registry_config`

## callers

- `0x70370`

## callees

- `0x132e0`
- `0x13310`
- `0x13320`
- `0x13380`
- `0x49600`
- `0x51120`
- `0x68600`
- `0x68c10`
- `0x68c30`
- `0x68dc0`
- `0x68e40`
- `0x70170`
- `0x70190`
- `0x70210`
- `0x70280`
- `0x70370`
- `0x704a0`
- `0xd0380`
- `0xd0950`
- `0xd0b50`
- `0xd1540`
- `0xd1630`
- `0xd1670`
- `0xd16b0`
- `0xd1890`
- `0xd19a0`
- `0xd2170`
- `0xd3f00`
- `0xd6b00`

## string_xrefs

- `0x70558`: `http://www.w3.org/2001/XMLSchema`
- `0x705f8`: `http://www.w3.org/2001/XMLSchema`
- `0x7050a`: `http://schemas.xmlsoap.org/soap/encoding/`
- `0x7051b`: `http://schemas.xmlsoap.org/wsdl/`
- `0x7057e`: `http://schemas.xmlsoap.org/wsdl/`

## pseudocode

```c

```

## disassembly

```asm
0x704a0  br.s     loc_704AA
0x704a2  ldarg.1
0x704a3  callvirt instance class System.Xml.Serialization.ArrayMapping System.Xml.Serialization.ArrayMapping::get_Next()
0x704a8  starg.s  1
0x704aa  ldarg.1
0x704ab  callvirt instance class System.Xml.Serialization.ArrayMapping System.Xml.Serialization.ArrayMapping::get_Next()
0x704b0  brtrue.s loc_704A2
0x704b2  ldarg.0
0x704b3  ldfld    class [mscorlib]System.Collections.Hashtable System.Xml.Serialization.SoapSchemaExporter::types
0x704b8  ldarg.1
0x704b9  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x704be  castclass System.Xml.Schema.XmlSchemaComplexType
0x704c3  stloc.0
0x704c4  ldloc.0
0x704c5  brtrue   loc_70618
0x704ca  ldarg.0
0x704cb  ldarg.1
0x704cc  callvirt instance string System.Xml.Serialization.TypeMapping::get_TypeName()
0x704d1  ldarg.1
0x704d2  callvirt instance string System.Xml.Serialization.TypeMapping::get_Namespace()
0x704d7  call     instance void System.Xml.Serialization.SoapSchemaExporter::CheckForDuplicateType(string newTypeName, string newNamespace)
0x704dc  newobj   instance void System.Xml.Schema.XmlSchemaComplexType::.ctor()
0x704e1  stloc.0
0x704e2  ldloc.0
0x704e3  ldarg.1
0x704e4  callvirt instance string System.Xml.Serialization.TypeMapping::get_TypeName()
0x704e9  callvirt instance void System.Xml.Schema.XmlSchemaType::set_Name(string value)
0x704ee  ldarg.0
0x704ef  ldfld    class [mscorlib]System.Collections.Hashtable System.Xml.Serialization.SoapSchemaExporter::types
0x704f4  ldarg.1
0x704f5  ldloc.0
0x704f6  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x704fb  ldarg.0
0x704fc  ldloc.0
0x704fd  ldarg.1
0x704fe  callvirt instance string System.Xml.Serialization.TypeMapping::get_Namespace()
0x70503  ldarg.2
0x70504  call     instance void System.Xml.Serialization.SoapSchemaExporter::AddSchemaItem(class System.Xml.Schema.XmlSchemaObject item, string ns, string referencingNs)
0x70509  ldarg.0
0x7050a  ldstr    aHttpSchemasXml// "http://schemas.xmlsoap.org/soap/encodin"...
0x7050f  ldarg.1
0x70510  callvirt instance string System.Xml.Serialization.TypeMapping::get_Namespace()
0x70515  call     instance void System.Xml.Serialization.SoapSchemaExporter::AddSchemaImport(string ns, string referencingNs)
0x7051a  ldarg.0
0x7051b  ldstr    aHttpSchemasXml_0// "http://schemas.xmlsoap.org/wsdl/"
0x70520  ldarg.1
0x70521  callvirt instance string System.Xml.Serialization.TypeMapping::get_Namespace()
0x70526  call     instance void System.Xml.Serialization.SoapSchemaExporter::AddSchemaImport(string ns, string referencingNs)
0x7052b  newobj   instance void System.Xml.Schema.XmlSchemaComplexContentRestriction::.ctor()
0x70530  stloc.1
0x70531  ldarg.0
0x70532  ldarg.1
0x70533  callvirt instance class System.Xml.Serialization.ElementAccessor[] System.Xml.Serialization.ArrayMapping::get_Elements()
0x70538  ldc.i4.0
0x70539  ldelem.ref
0x7053a  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x7053f  ldarg.1
0x70540  callvirt instance string System.Xml.Serialization.TypeMapping::get_Namespace()
0x70545  call     instance class System.Xml.XmlQualifiedName System.Xml.Serialization.SoapSchemaExporter::ExportTypeMapping(class System.Xml.Serialization.TypeMapping mapping, string ns)
0x7054a  stloc.2
0x7054b  ldloc.2
0x7054c  callvirt instance bool System.Xml.XmlQualifiedName::get_IsEmpty()
0x70551  brfalse.s loc_70563
0x70553  ldstr    aAnytype// "anyType"
0x70558  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x7055d  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0x70562  stloc.2
0x70563  newobj   instance void System.Xml.Schema.XmlSchemaAttribute::.ctor()
0x70568  stloc.3
0x70569  ldloc.3
0x7056a  ldsfld   class System.Xml.XmlQualifiedName System.Xml.Serialization.SoapSchemaExporter::ArrayTypeQName
0x7056f  callvirt instance void System.Xml.Schema.XmlSchemaAttribute::set_RefName(class System.Xml.XmlQualifiedName value)
0x70574  ldstr    aWsdl// "wsdl"
0x70579  ldstr    aArraytype// "arrayType"
0x7057e  ldstr    aHttpSchemasXml_0// "http://schemas.xmlsoap.org/wsdl/"
0x70583  ldarg.0
0x70584  call     instance class System.Xml.XmlDocument System.Xml.Serialization.SoapSchemaExporter::get_Document()
0x70589  newobj   instance void System.Xml.XmlAttribute::.ctor(string prefix, string localName, string namespaceURI, class System.Xml.XmlDocument doc)
0x7058e  stloc.s  4
0x70590  ldloc.s  4
0x70592  ldloc.2
0x70593  callvirt instance string System.Xml.XmlQualifiedName::get_Namespace()
0x70598  ldstr    asc_12804C// ":"
0x7059d  ldloc.2
0x7059e  callvirt instance string System.Xml.XmlQualifiedName::get_Name()
0x705a3  ldstr    asc_12E3FA// "[]"
0x705a8  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x705ad  callvirt instance void System.Xml.XmlNode::set_Value(string value)
0x705b2  ldloc.3
0x705b3  ldc.i4.1
0x705b4  newarr   System.Xml.XmlAttribute
0x705b9  dup
0x705ba  ldc.i4.0
0x705bb  ldloc.s  4
0x705bd  stelem.ref
0x705be  callvirt instance void System.Xml.Schema.XmlSchemaAnnotated::set_UnhandledAttributes(class System.Xml.XmlAttribute[] value)
0x705c3  ldloc.1
0x705c4  callvirt instance class System.Xml.Schema.XmlSchemaObjectCollection System.Xml.Schema.XmlSchemaComplexContentRestriction::get_Attributes()
0x705c9  ldloc.3
0x705ca  callvirt instance int32 System.Xml.Schema.XmlSchemaObjectCollection::Add(class System.Xml.Schema.XmlSchemaObject item)
0x705cf  pop
0x705d0  ldloc.1
0x705d1  ldsfld   class System.Xml.XmlQualifiedName System.Xml.Serialization.SoapSchemaExporter::ArrayQName
0x705d6  callvirt instance void System.Xml.Schema.XmlSchemaComplexContentRestriction::set_BaseTypeName(class System.Xml.XmlQualifiedName value)
0x705db  newobj   instance void System.Xml.Schema.XmlSchemaComplexContent::.ctor()
0x705e0  stloc.s  5
0x705e2  ldloc.s  5
0x705e4  ldloc.1
0x705e5  callvirt instance void System.Xml.Schema.XmlSchemaContentModel::set_Content(class System.Xml.Schema.XmlSchemaContent value)
0x705ea  ldloc.0
0x705eb  ldloc.s  5
0x705ed  callvirt instance void System.Xml.Schema.XmlSchemaComplexType::set_ContentModel(class System.Xml.Schema.XmlSchemaContentModel value)
0x705f2  ldloc.2
0x705f3  callvirt instance string System.Xml.XmlQualifiedName::get_Namespace()
0x705f8  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x705fd  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x70602  brfalse.s loc_70625
0x70604  ldarg.0
0x70605  ldloc.2
0x70606  callvirt instance string System.Xml.XmlQualifiedName::get_Namespace()
0x7060b  ldarg.1
0x7060c  callvirt instance string System.Xml.Serialization.TypeMapping::get_Namespace()
0x70611  call     instance void System.Xml.Serialization.SoapSchemaExporter::AddSchemaImport(string ns, string referencingNs)
0x70616  br.s     loc_70625
0x70618  ldarg.0
0x70619  ldarg.1
0x7061a  callvirt instance string System.Xml.Serialization.TypeMapping::get_Namespace()
0x7061f  ldarg.2
0x70620  call     instance void System.Xml.Serialization.SoapSchemaExporter::AddSchemaImport(string ns, string referencingNs)
0x70625  ldarg.1
0x70626  callvirt instance string System.Xml.Serialization.TypeMapping::get_TypeName()
0x7062b  ldarg.1
0x7062c  callvirt instance string System.Xml.Serialization.TypeMapping::get_Namespace()
0x70631  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0x70636  ret
```
