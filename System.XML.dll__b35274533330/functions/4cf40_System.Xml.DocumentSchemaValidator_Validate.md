# System.Xml.DocumentSchemaValidator::Validate

- ea: `0x4cf40`
- end: `0x4d09d`
- name: `System.Xml.DocumentSchemaValidator::Validate`
- size: `349`
- prototype: ``
- caller_count: `2`
- callee_count: `21`
- tags: `registry_config`

## callers

- `0x48010`
- `0x4c3f0`

## callees

- `0x13380`
- `0x4cf40`
- `0x4d210`
- `0x4d290`
- `0x4d890`
- `0x4d980`
- `0x51160`
- `0x51170`
- `0x51ee0`
- `0x524e0`
- `0x622f0`
- `0xbd560`
- `0xbd570`
- `0xbd580`
- `0xd2a50`
- `0xd2b20`
- `0xd3a10`
- `0xd4230`
- `0xd4920`
- `0xd6f00`
- `0xd8110`

## string_xrefs

- `0x4cffc`: `XmlDocument_NoNodeSchemaInfo`
- `0x4d031`: `XmlDocument_NoNodeSchemaInfo`
- `0x4d03e`: `XmlDocument_ValidateInvalidNodeType`

## pseudocode

```c

```

## disassembly

```asm
0x4cf40  ldnull
0x4cf41  stloc.0
0x4cf42  ldc.i4.s 0x10
0x4cf44  stloc.1
0x4cf45  ldarg.0
0x4cf46  ldarg.1
0x4cf47  stfld    class System.Xml.XmlNode System.Xml.DocumentSchemaValidator::startNode
0x4cf4c  ldarg.1
0x4cf4d  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlNode::get_NodeType()
0x4cf52  stloc.s  4
0x4cf54  ldloc.s  4
0x4cf56  ldc.i4.2
0x4cf57  bgt.s    loc_4CF6B
0x4cf59  ldloc.s  4
0x4cf5b  ldc.i4.1
0x4cf5c  beq.s    loc_4CF88
0x4cf5e  ldloc.s  4
0x4cf60  ldc.i4.2
0x4cf61  beq      loc_4D009
0x4cf66  br       loc_4D03E
0x4cf6b  ldloc.s  4
0x4cf6d  ldc.i4.s 9
0x4cf6f  beq.s    loc_4CF7F
0x4cf71  ldloc.s  4
0x4cf73  ldc.i4.s 0xB
0x4cf75  beq      loc_4D04F
0x4cf7a  br       loc_4D03E
0x4cf7f  ldloc.1
0x4cf80  ldc.i4.8
0x4cf81  or
0x4cf82  stloc.1
0x4cf83  br       loc_4D04F
0x4cf88  ldarg.1
0x4cf89  callvirt instance class System.Xml.Schema.IXmlSchemaInfo System.Xml.XmlNode::get_SchemaInfo()
0x4cf8e  stloc.2
0x4cf8f  ldloc.2
0x4cf90  callvirt instance class System.Xml.Schema.XmlSchemaElement System.Xml.Schema.IXmlSchemaInfo::get_SchemaElement()
0x4cf95  stloc.3
0x4cf96  ldloc.3
0x4cf97  brfalse.s loc_4CFC9
0x4cf99  ldloc.3
0x4cf9a  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaElement::get_RefName()
0x4cf9f  callvirt instance bool System.Xml.XmlQualifiedName::get_IsEmpty()
0x4cfa4  brtrue.s loc_4CFC2
0x4cfa6  ldarg.0
0x4cfa7  ldfld    class System.Xml.Schema.XmlSchemaSet System.Xml.DocumentSchemaValidator::schemas
0x4cfac  callvirt instance class System.Xml.Schema.XmlSchemaObjectTable System.Xml.Schema.XmlSchemaSet::get_GlobalElements()
0x4cfb1  ldloc.3
0x4cfb2  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaElement::get_QualifiedName()
0x4cfb7  callvirt instance class System.Xml.Schema.XmlSchemaObject System.Xml.Schema.XmlSchemaObjectTable::get_Item(class System.Xml.XmlQualifiedName name)
0x4cfbc  stloc.0
0x4cfbd  br       loc_4D04F
0x4cfc2  ldloc.3
0x4cfc3  stloc.0
0x4cfc4  br       loc_4D04F
0x4cfc9  ldloc.2
0x4cfca  callvirt instance class System.Xml.Schema.XmlSchemaType System.Xml.Schema.IXmlSchemaInfo::get_SchemaType()
0x4cfcf  stloc.0
0x4cfd0  ldloc.0
0x4cfd1  brtrue.s loc_4D04F
0x4cfd3  ldarg.1
0x4cfd4  callvirt instance class System.Xml.XmlNode System.Xml.XmlNode::get_ParentNode()
0x4cfd9  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlNode::get_NodeType()
0x4cfde  ldc.i4.s 9
0x4cfe0  bne.un.s loc_4CFEC
0x4cfe2  ldarg.1
0x4cfe3  callvirt instance class System.Xml.XmlNode System.Xml.XmlNode::get_ParentNode()
0x4cfe8  starg.s  1
0x4cfea  br.s     loc_4D04F
0x4cfec  ldarg.0
0x4cfed  ldarg.1
0x4cfee  isinst   System.Xml.XmlElement
0x4cff3  call     instance class System.Xml.Schema.XmlSchemaObject System.Xml.DocumentSchemaValidator::FindSchemaInfo(class System.Xml.XmlElement elementToValidate)
0x4cff8  stloc.0
0x4cff9  ldloc.0
0x4cffa  brtrue.s loc_4D04F
0x4cffc  ldstr    aXmldocumentNon// "XmlDocument_NoNodeSchemaInfo"
0x4d001  ldnull
0x4d002  ldarg.1
0x4d003  newobj   instance void System.Xml.Schema.XmlSchemaValidationException::.ctor(string res, string[] args, object sourceNode)
0x4d008  throw
0x4d009  ldarg.1
0x4d00a  callvirt instance valuetype System.Xml.XPath.XPathNodeType System.Xml.XmlNode::get_XPNodeType()
0x4d00f  ldc.i4.3
0x4d010  beq.s    loc_4D03E
0x4d012  ldarg.1
0x4d013  callvirt instance class System.Xml.Schema.IXmlSchemaInfo System.Xml.XmlNode::get_SchemaInfo()
0x4d018  callvirt instance class System.Xml.Schema.XmlSchemaAttribute System.Xml.Schema.IXmlSchemaInfo::get_SchemaAttribute()
0x4d01d  stloc.0
0x4d01e  ldloc.0
0x4d01f  brtrue.s loc_4D04F
0x4d021  ldarg.0
0x4d022  ldarg.1
0x4d023  isinst   System.Xml.XmlAttribute
0x4d028  call     instance class System.Xml.Schema.XmlSchemaAttribute System.Xml.DocumentSchemaValidator::FindSchemaInfo(class System.Xml.XmlAttribute attributeToValidate)
0x4d02d  stloc.0
0x4d02e  ldloc.0
0x4d02f  brtrue.s loc_4D04F
0x4d031  ldstr    aXmldocumentNon// "XmlDocument_NoNodeSchemaInfo"
0x4d036  ldnull
0x4d037  ldarg.1
0x4d038  newobj   instance void System.Xml.Schema.XmlSchemaValidationException::.ctor(string res, string[] args, object sourceNode)
0x4d03d  throw
0x4d03e  ldstr    aXmldocumentVal// "XmlDocument_ValidateInvalidNodeType"
0x4d043  ldnull
0x4d044  call     string System.Xml.Res::GetString(string name, object[] args)
0x4d049  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x4d04e  throw
0x4d04f  ldarg.0
0x4d050  ldc.i4.1
0x4d051  stfld    bool System.Xml.DocumentSchemaValidator::isValid
0x4d056  ldarg.0
0x4d057  ldloc.0
0x4d058  ldloc.1
0x4d059  call     instance void System.Xml.DocumentSchemaValidator::CreateValidator(class System.Xml.Schema.XmlSchemaObject partialValidationType, valuetype System.Xml.Schema.XmlSchemaValidationFlags validationFlags)
0x4d05e  ldarg.0
0x4d05f  ldfld    bool System.Xml.DocumentSchemaValidator::psviAugmentation
0x4d064  brfalse.s loc_4D084
0x4d066  ldarg.0
0x4d067  ldfld    class System.Xml.Schema.XmlSchemaInfo System.Xml.DocumentSchemaValidator::schemaInfo
0x4d06c  brtrue.s loc_4D079
0x4d06e  ldarg.0
0x4d06f  newobj   instance void System.Xml.Schema.XmlSchemaInfo::.ctor()
0x4d074  stfld    class System.Xml.Schema.XmlSchemaInfo System.Xml.DocumentSchemaValidator::schemaInfo
0x4d079  ldarg.0
0x4d07a  newobj   instance void System.Xml.Schema.XmlSchemaInfo::.ctor()
0x4d07f  stfld    class System.Xml.Schema.XmlSchemaInfo System.Xml.DocumentSchemaValidator::attributeSchemaInfo
0x4d084  ldarg.0
0x4d085  ldarg.1
0x4d086  call     instance void System.Xml.DocumentSchemaValidator::ValidateNode(class System.Xml.XmlNode node)
0x4d08b  ldarg.0
0x4d08c  ldfld    class System.Xml.Schema.XmlSchemaValidator System.Xml.DocumentSchemaValidator::validator
0x4d091  callvirt instance void System.Xml.Schema.XmlSchemaValidator::EndValidation()
0x4d096  ldarg.0
0x4d097  ldfld    bool System.Xml.DocumentSchemaValidator::isValid
0x4d09c  ret
```
