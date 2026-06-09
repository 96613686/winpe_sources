# Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.ContentTypeExportHelper::FixUpContentType

- ea: `0xa780`
- end: `0xaabc`
- name: `Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.ContentTypeExportHelper::FixUpContentType`
- size: `828`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x9f50`

## callees

- `0xa780`

## string_xrefs

- `0xa83b`: `XmlDocument`
- `0xa867`: `NamespaceURI`
- `0xa8cb`: `urn:deployment-manifest-schema`
- `0xa8fd`: `urn:deployment-manifest-schema`

## pseudocode

```c

```

## disassembly

```asm
0xa780  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0xa785  stloc.0
0xa786  ldarg.0
0xa787  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_SchemaXmlWithResourceTokens()
0xa78c  newobj   instance void [mscorlib]System.IO.StringReader::.ctor(string)
0xa791  newobj   instance void [System.Xml]System.Xml.XmlTextReader::.ctor(class [mscorlib]System.IO.TextReader)
0xa796  stloc.1
0xa797  ldloc.1
0xa798  ldc.i4.0
0xa799  callvirt instance void [System.Xml]System.Xml.XmlTextReader::set_DtdProcessing(valuetype [System.Xml]System.Xml.DtdProcessing)
0xa79e  ldloc.0
0xa79f  ldloc.1
0xa7a0  callvirt instance void [System.Xml]System.Xml.XmlDocument::Load(class [System.Xml]System.Xml.XmlReader)
0xa7a5  leave.s  loc_A7B1
0xa7a7  ldloc.1
0xa7a8  brfalse.s loc_A7B0
0xa7aa  ldloc.1
0xa7ab  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa7b0  endfinally
0xa7b1  ldloc.0
0xa7b2  ldstr    aParentwebid// "ParentWebId"
0xa7b7  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0xa7bc  stloc.2
0xa7bd  ldloc.2
0xa7be  ldarg.0
0xa7bf  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_ParentWeb()
0xa7c4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_ID()
0xa7c9  stloc.s  0xB
0xa7cb  ldloca.s 0xB
0xa7cd  ldstr    aD// "D"
0xa7d2  call     instance string [mscorlib]System.Guid::ToString(string)
0xa7d7  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0xa7dc  ldloc.0
0xa7dd  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0xa7e2  ldloc.2
0xa7e3  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlElement::SetAttributeNode(class [System.Xml]System.Xml.XmlAttribute)
0xa7e8  pop
0xa7e9  ldloc.0
0xa7ea  ldstr    aScope// "Scope"
0xa7ef  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0xa7f4  stloc.3
0xa7f5  ldloc.3
0xa7f6  ldarg.0
0xa7f7  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_Scope()
0xa7fc  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0xa801  ldloc.0
0xa802  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0xa807  ldloc.3
0xa808  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlElement::SetAttributeNode(class [System.Xml]System.Xml.XmlAttribute)
0xa80d  pop
0xa80e  ldloc.0
0xa80f  ldstr    aNextchildbyte// "NextChildByte"
0xa814  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0xa819  stloc.s  4
0xa81b  ldloc.s  4
0xa81d  ldstr    a0_0// "0"
0xa822  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0xa827  ldloc.0
0xa828  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0xa82d  ldloc.s  4
0xa82f  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlElement::SetAttributeNode(class [System.Xml]System.Xml.XmlAttribute)
0xa834  pop
0xa835  ldloc.0
0xa836  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0xa83b  ldstr    aXmldocument// "XmlDocument"
0xa840  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlElement::GetElementsByTagName(string)
0xa845  stloc.s  5
0xa847  ldloc.s  5
0xa849  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0xa84e  stloc.s  0xC
0xa850  br.s     loc_A8A5
0xa852  ldloc.s  0xC
0xa854  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xa859  castclass [System.Xml]System.Xml.XmlNode
0xa85e  stloc.s  6
0xa860  ldloc.s  6
0xa862  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xa867  ldstr    aNamespaceuri// "NamespaceURI"
0xa86c  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xa871  stloc.s  7
0xa873  ldloc.s  7
0xa875  brfalse.s loc_A8A5
0xa877  ldloc.s  7
0xa879  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xa87e  brfalse.s loc_A8A5
0xa880  ldloc.s  7
0xa882  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xa887  ldstr    aMicrosoftShare_1// "Microsoft.SharePoint.Taxonomy.ContentTy"...
0xa88c  ldc.i4.4
0xa88d  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xa892  brfalse.s loc_A8A5
0xa894  ldloc.s  6
0xa896  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0xa89b  ldloc.s  6
0xa89d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0xa8a2  pop
0xa8a3  br.s     loc_A8AE
0xa8a5  ldloc.s  0xC
0xa8a7  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xa8ac  brtrue.s loc_A852
0xa8ae  leave.s  loc_A8C5
0xa8b0  ldloc.s  0xC
0xa8b2  isinst   [mscorlib]System.IDisposable
0xa8b7  stloc.s  0xD
0xa8b9  ldloc.s  0xD
0xa8bb  brfalse.s loc_A8C4
0xa8bd  ldloc.s  0xD
0xa8bf  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa8c4  endfinally
0xa8c5  ldloc.0
0xa8c6  ldstr    aEventreceivers// "EventReceivers"
0xa8cb  ldstr    aUrnDeploymentM// "urn:deployment-manifest-schema"
0xa8d0  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string)
0xa8d5  stloc.s  8
0xa8d7  ldarg.0
0xa8d8  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPEventReceiverDefinitionCollection [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_EventReceivers()
0xa8dd  callvirt instance class [mscorlib]System.Collections.IEnumerator [Microsoft.SharePoint]Microsoft.SharePoint.SPBaseCollection::GetEnumerator()
0xa8e2  stloc.s  0xE
0xa8e4  br       loc_AA84
0xa8e9  ldloc.s  0xE
0xa8eb  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xa8f0  castclass [Microsoft.SharePoint]Microsoft.SharePoint.SPEventReceiverDefinition
0xa8f5  stloc.s  9
0xa8f7  ldloc.0
0xa8f8  ldstr    aEventreceiver// "EventReceiver"
0xa8fd  ldstr    aUrnDeploymentM// "urn:deployment-manifest-schema"
0xa902  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string)
0xa907  stloc.s  0xA
0xa909  ldloc.s  0xA
0xa90b  ldstr    aId// "Id"
0xa910  ldloc.s  9
0xa912  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPEventReceiverDefinition::get_Id()
0xa917  stloc.s  0xF
0xa919  ldloca.s 0xF
0xa91b  constrained. [mscorlib]System.Guid
0xa921  callvirt instance string [mscorlib]System.Object::ToString()
0xa926  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0xa92b  ldloc.s  0xA
0xa92d  ldstr    aName// "Name"
0xa932  ldloc.s  9
0xa934  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPEventReceiverDefinition::get_Name()
0xa939  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0xa93e  ldloc.s  0xA
0xa940  ldstr    aWebid// "WebId"
0xa945  ldloc.s  9
0xa947  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPEventReceiverDefinition::get_WebId()
0xa94c  stloc.s  0x10
0xa94e  ldloca.s 0x10
0xa950  constrained. [mscorlib]System.Guid
0xa956  callvirt instance string [mscorlib]System.Object::ToString()
0xa95b  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0xa960  ldloc.s  0xA
0xa962  ldstr    aHostid// "HostId"
0xa967  ldloc.s  9
0xa969  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPEventReceiverDefinition::get_HostId()
0xa96e  stloc.s  0x11
0xa970  ldloca.s 0x11
0xa972  constrained. [mscorlib]System.Guid
0xa978  callvirt instance string [mscorlib]System.Object::ToString()
0xa97d  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0xa982  ldloc.s  0xA
0xa984  ldstr    aHosttype// "HostType"
0xa989  ldloc.s  9
0xa98b  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPEventHostType [Microsoft.SharePoint]Microsoft.SharePoint.SPEventReceiverDefinition::get_HostType()
0xa990  box      [Microsoft.SharePoint]Microsoft.SharePoint.SPEventHostType
0xa995  callvirt instance string [mscorlib]System.Object::ToString()
0xa99a  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0xa99f  ldloc.s  0xA
0xa9a1  ldstr    aSynchronizatio// "Synchronization"
0xa9a6  ldloc.s  9
0xa9a8  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPEventReceiverSynchronization [Microsoft.SharePoint]Microsoft.SharePoint.SPEventReceiverDefinition::get_Synchronization()
0xa9ad  box      [Microsoft.SharePoint]Microsoft.SharePoint.SPEventReceiverSynchronization
0xa9b2  callvirt instance string [mscorlib]System.Object::ToString()
0xa9b7  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0xa9bc  ldloc.s  0xA
0xa9be  ldstr    aType// "Type"
0xa9c3  ldloc.s  9
0xa9c5  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPEventReceiverType [Microsoft.SharePoint]Microsoft.SharePoint.SPEventReceiverDefinition::get_Type()
0xa9ca  box      [Microsoft.SharePoint]Microsoft.SharePoint.SPEventReceiverType
0xa9cf  callvirt instance string [mscorlib]System.Object::ToString()
0xa9d4  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0xa9d9  ldloc.s  0xA
0xa9db  ldstr    aSequencenumber// "SequenceNumber"
0xa9e0  ldloc.s  9
0xa9e2  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.SPEventReceiverDefinition::get_SequenceNumber()
0xa9e7  stloc.s  0x12
0xa9e9  ldloca.s 0x12
0xa9eb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa9f0  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xa9f5  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0xa9fa  ldloc.s  0xA
0xa9fc  ldstr    aUrl// "Url"
0xaa01  ldloc.s  9
0xaa03  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPEventReceiverDefinition::get_Url()
0xaa08  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0xaa0d  ldloc.s  0xA
0xaa0f  ldstr    aAssembly// "Assembly"
0xaa14  ldloc.s  9
0xaa16  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPEventReceiverDefinition::get_Assembly()
0xaa1b  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0xaa20  ldloc.s  0xA
0xaa22  ldstr    aClass// "Class"
0xaa27  ldloc.s  9
0xaa29  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPEventReceiverDefinition::get_Class()
0xaa2e  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0xaa33  ldloc.s  0xA
0xaa35  ldstr    aData// "Data"
0xaa3a  ldloc.s  9
0xaa3c  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPEventReceiverDefinition::get_Data()
0xaa41  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0xaa46  ldloc.s  0xA
0xaa48  ldstr    aFilter// "Filter"
0xaa4d  ldloc.s  9
0xaa4f  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPEventReceiverDefinition::get_Filter()
0xaa54  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0xaa59  ldloc.s  0xA
0xaa5b  ldstr    aCredential// "Credential"
0xaa60  ldloc.s  9
0xaa62  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.SPEventReceiverDefinition::get_Credential()
0xaa67  stloc.s  0x13
0xaa69  ldloca.s 0x13
0xaa6b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xaa70  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xaa75  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0xaa7a  ldloc.s  8
0xaa7c  ldloc.s  0xA
0xaa7e  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0xaa83  pop
0xaa84  ldloc.s  0xE
0xaa86  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xaa8b  brtrue   loc_A8E9
0xaa90  leave.s  loc_AAA7
0xaa92  ldloc.s  0xE
0xaa94  isinst   [mscorlib]System.IDisposable
0xaa99  stloc.s  0x14
0xaa9b  ldloc.s  0x14
0xaa9d  brfalse.s loc_AAA6
0xaa9f  ldloc.s  0x14
0xaaa1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xaaa6  endfinally
0xaaa7  ldloc.0
0xaaa8  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0xaaad  ldloc.s  8
0xaaaf  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0xaab4  pop
0xaab5  ldloc.0
0xaab6  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0xaabb  ret
```
