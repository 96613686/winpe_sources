# Microsoft.SharePoint.Administration.SPAspConfigurationFile::ApplyActionToXmlDocument_0

- ea: `0x22e650`
- end: `0x22ec34`
- name: `Microsoft.SharePoint.Administration.SPAspConfigurationFile::ApplyActionToXmlDocument_0`
- size: `1508`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x22e540`

## callees

- `0x22e550`
- `0x22e5f0`
- `0x22e650`
- `0x22ef40`
- `0x472650`
- `0x93dae0`
- `0x957530`

## string_xrefs

- `0x22e85f`: `remove`
- `0x22e9e5`: `remove`
- `0x22e685`: `urn:schemas-microsoft-com:asm.v1`
- `0x22e70d`: `Action {0} from {1} has already been applied to the web.config and will be bypassed.`
- `0x22e741`: `The following error occured while processing {0} for existing web.config merge actions.  The action may be reapplied to the web.config, causing duplicate data: {1}`
- `0x22e77a`: `An action in {0} does not contain an id attribute with a unique guid value.  This action may be performed repeatedly, causing duplicate entries in the web.config.`
- `0x22e7a9`: `The action {0} in {1} cannot be performed because it is not an Xml element.`
- `0x22e7f7`: `The action {0} in {1} cannot be performed because it does not have a path attribute.`
- `0x22e87a`: `The action {0} in {1} cannot be performed because the path {2} does not exist. You can create the path node and rerun the merge to apply this action.`
- `0x22e8d4`: `The action {0} in {1} cannot be performed because the xml document does not support additions.`
- `0x22ea0c`: `The action {0} in {1} cannot be performed because the xml document does not support removing nodes.`
- `0x22ea5a`: `update`
- `0x22ea78`: `The action {0} in {1} cannot be performed because the xml document does not support updating nodes.`

## pseudocode

```c

```

## disassembly

```asm
0x22e650  ldarg.3
0x22e651  ldc.i4.1
0x22e652  and
0x22e653  ldc.i4.1
0x22e654  ceq
0x22e656  stloc.0
0x22e657  ldarg.3
0x22e658  ldc.i4.2
0x22e659  and
0x22e65a  ldc.i4.2
0x22e65b  ceq
0x22e65d  stloc.1
0x22e65e  ldarg.3
0x22e65f  ldc.i4.4
0x22e660  and
0x22e661  ldc.i4.4
0x22e662  ceq
0x22e664  stloc.2
0x22e665  ldarg.0
0x22e666  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x22e66b  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x22e670  stloc.3
0x22e671  ldarg.1
0x22e672  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlDocument::get_NameTable()
0x22e677  newobj   instance void [System.Xml]System.Xml.XmlNamespaceManager::.ctor(class [System.Xml]System.Xml.XmlNameTable)
0x22e67c  stloc.s  4
0x22e67e  ldloc.s  4
0x22e680  ldstr    aNs// "ns"
0x22e685  ldstr    aUrnSchemasMicr_0// "urn:schemas-microsoft-com:asm.v1"
0x22e68a  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x22e68f  ldarg.1
0x22e690  ldarg.2
0x22e691  ldc.i4.1
0x22e692  call     void Microsoft.SharePoint.Administration.SPAspConfigurationFile::CheckMergedActionsConfiguration(class [System.Xml]System.Xml.XmlDocument xd, string sourceFileName, bool createMergedActionsConfiguration)
0x22e697  ldarg.1
0x22e698  ldc.i4.1
0x22e699  call     class [System.Xml]System.Xml.XmlNode Microsoft.SharePoint.Administration.SPAspConfigurationFile::GetMergedActions(class [System.Xml]System.Xml.XmlDocument xd, bool createMergedActions)
0x22e69e  stloc.s  5
0x22e6a0  ldarg.1
0x22e6a1  call     class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, bool> Microsoft.SharePoint.Administration.SPAspConfigurationFile::ExtractMergedActionIds(class [System.Xml]System.Xml.XmlDocument doc)
0x22e6a6  stloc.s  6
0x22e6a8  ldloc.3
0x22e6a9  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x22e6ae  stloc.s  0x18
0x22e6b0  br       loc_22EC10
0x22e6b5  ldloc.s  0x18
0x22e6b7  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x22e6bc  castclass [System.Xml]System.Xml.XmlNode
0x22e6c1  stloc.s  7
0x22e6c3  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x22e6c8  stloc.s  8
0x22e6ca  ldloc.s  7
0x22e6cc  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x22e6d1  ldstr    aId// "id"
0x22e6d6  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x22e6db  stloc.s  9
0x22e6dd  ldloc.s  9
0x22e6df  brfalse  loc_22E76E
0x22e6e4  ldloc.s  9
0x22e6e6  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x22e6eb  stloc.s  0xA
0x22e6ed  ldloc.s  0xA
0x22e6ef  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x22e6f4  stloc.s  8
0x22e6f6  ldloc.s  6
0x22e6f8  ldloc.s  8
0x22e6fa  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, bool>::ContainsKey(var<u1>)
0x22e6ff  brfalse.s loc_22E731
0x22e701  ldc.i4   0x38383677
0x22e706  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x22e70b  ldc.i4.s 0x32
0x22e70d  ldstr    aAction0From1Ha// "Action {0} from {1} has already been ap"...
0x22e712  ldc.i4.2
0x22e713  newarr   [mscorlib]System.Object
0x22e718  stloc.s  0x19
0x22e71a  ldloc.s  0x19
0x22e71c  ldc.i4.0
0x22e71d  ldloc.s  0xA
0x22e71f  stelem.ref
0x22e720  ldloc.s  0x19
0x22e722  ldc.i4.1
0x22e723  ldarg.2
0x22e724  stelem.ref
0x22e725  ldloc.s  0x19
0x22e727  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x22e72c  leave    loc_22EC10
0x22e731  leave.s  loc_22E793
0x22e733  stloc.s  0xB
0x22e735  ldc.i4   0x38383678
0x22e73a  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x22e73f  ldc.i4.s 0x32
0x22e741  ldstr    aTheFollowingEr// "The following error occured while proce"...
0x22e746  ldc.i4.2
0x22e747  newarr   [mscorlib]System.Object
0x22e74c  stloc.s  0x1A
0x22e74e  ldloc.s  0x1A
0x22e750  ldc.i4.0
0x22e751  ldarg.2
0x22e752  stelem.ref
0x22e753  ldloc.s  0x1A
0x22e755  ldc.i4.1
0x22e756  ldloc.s  0xB
0x22e758  callvirt instance string [mscorlib]System.Exception::get_Message()
0x22e75d  stelem.ref
0x22e75e  ldloc.s  0x1A
0x22e760  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x22e765  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x22e76a  stloc.s  8
0x22e76c  leave.s  loc_22E793
0x22e76e  ldc.i4   0x38383679
0x22e773  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x22e778  ldc.i4.s 0x14
0x22e77a  ldstr    aAnActionIn0Doe// "An action in {0} does not contain an id"...
0x22e77f  ldc.i4.1
0x22e780  newarr   [mscorlib]System.Object
0x22e785  stloc.s  0x1B
0x22e787  ldloc.s  0x1B
0x22e789  ldc.i4.0
0x22e78a  ldarg.2
0x22e78b  stelem.ref
0x22e78c  ldloc.s  0x1B
0x22e78e  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x22e793  ldloc.s  7
0x22e795  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlNode::get_NodeType()
0x22e79a  ldc.i4.1
0x22e79b  beq.s    loc_22E7D8
0x22e79d  ldc.i4   0x64336D61
0x22e7a2  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x22e7a7  ldc.i4.s 0xA
0x22e7a9  ldstr    aTheAction0In1C// "The action {0} in {1} cannot be perform"...
0x22e7ae  ldc.i4.2
0x22e7af  newarr   [mscorlib]System.Object
0x22e7b4  stloc.s  0x1C
0x22e7b6  ldloc.s  0x1C
0x22e7b8  ldc.i4.0
0x22e7b9  ldloca.s 8
0x22e7bb  constrained. [mscorlib]System.Guid
0x22e7c1  callvirt instance string [mscorlib]System.Object::ToString()
0x22e7c6  stelem.ref
0x22e7c7  ldloc.s  0x1C
0x22e7c9  ldc.i4.1
0x22e7ca  ldarg.2
0x22e7cb  stelem.ref
0x22e7cc  ldloc.s  0x1C
0x22e7ce  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x22e7d3  br       loc_22EC10
0x22e7d8  ldloc.s  7
0x22e7da  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x22e7df  ldstr    aPath// "path"
0x22e7e4  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x22e7e9  brtrue.s loc_22E826
0x22e7eb  ldc.i4   0x64336D62
0x22e7f0  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x22e7f5  ldc.i4.s 0xA
0x22e7f7  ldstr    aTheAction0In1C_0// "The action {0} in {1} cannot be perform"...
0x22e7fc  ldc.i4.2
0x22e7fd  newarr   [mscorlib]System.Object
0x22e802  stloc.s  0x1D
0x22e804  ldloc.s  0x1D
0x22e806  ldc.i4.0
0x22e807  ldloca.s 8
0x22e809  constrained. [mscorlib]System.Guid
0x22e80f  callvirt instance string [mscorlib]System.Object::ToString()
0x22e814  stelem.ref
0x22e815  ldloc.s  0x1D
0x22e817  ldc.i4.1
0x22e818  ldarg.2
0x22e819  stelem.ref
0x22e81a  ldloc.s  0x1D
0x22e81c  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x22e821  br       loc_22EC10
0x22e826  ldloc.s  7
0x22e828  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x22e82d  ldstr    aPath// "path"
0x22e832  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x22e837  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x22e83c  stloc.s  0xC
0x22e83e  ldarg.1
0x22e83f  ldloc.s  0xC
0x22e841  ldloc.s  4
0x22e843  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0x22e848  stloc.s  0xD
0x22e84a  ldloc.s  0xD
0x22e84c  brfalse.s loc_22E858
0x22e84e  ldloc.s  0xD
0x22e850  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlNode::get_NodeType()
0x22e855  ldc.i4.1
0x22e856  beq.s    loc_22E8AF
0x22e858  ldloc.s  7
0x22e85a  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x22e85f  ldstr    aRemove_0// "remove"
0x22e864  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x22e869  brfalse  loc_22EB90
0x22e86e  ldc.i4   0x64336D63
0x22e873  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x22e878  ldc.i4.s 0xA
0x22e87a  ldstr    aTheAction0In1C_1// "The action {0} in {1} cannot be perform"...
0x22e87f  ldc.i4.3
0x22e880  newarr   [mscorlib]System.Object
0x22e885  stloc.s  0x1E
0x22e887  ldloc.s  0x1E
0x22e889  ldc.i4.0
0x22e88a  ldloca.s 8
0x22e88c  constrained. [mscorlib]System.Guid
0x22e892  callvirt instance string [mscorlib]System.Object::ToString()
0x22e897  stelem.ref
0x22e898  ldloc.s  0x1E
0x22e89a  ldc.i4.1
0x22e89b  ldarg.2
0x22e89c  stelem.ref
0x22e89d  ldloc.s  0x1E
0x22e89f  ldc.i4.2
0x22e8a0  ldloc.s  0xC
0x22e8a2  stelem.ref
0x22e8a3  ldloc.s  0x1E
0x22e8a5  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x22e8aa  br       loc_22EC10
0x22e8af  ldloc.s  7
0x22e8b1  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x22e8b6  ldstr    aAdd_0// "add"
0x22e8bb  call     bool [mscorlib]System.String::op_Equality(string, string)
0x22e8c0  brfalse  loc_22E9DE
0x22e8c5  ldloc.0
0x22e8c6  brtrue.s loc_22E903
0x22e8c8  ldc.i4   0x64336D64
0x22e8cd  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x22e8d2  ldc.i4.s 0xA
0x22e8d4  ldstr    aTheAction0In1C_2// "The action {0} in {1} cannot be perform"...
0x22e8d9  ldc.i4.2
0x22e8da  newarr   [mscorlib]System.Object
0x22e8df  stloc.s  0x1F
0x22e8e1  ldloc.s  0x1F
0x22e8e3  ldc.i4.0
0x22e8e4  ldloca.s 8
0x22e8e6  constrained. [mscorlib]System.Guid
0x22e8ec  callvirt instance string [mscorlib]System.Object::ToString()
0x22e8f1  stelem.ref
0x22e8f2  ldloc.s  0x1F
0x22e8f4  ldc.i4.1
0x22e8f5  ldarg.2
0x22e8f6  stelem.ref
0x22e8f7  ldloc.s  0x1F
0x22e8f9  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x22e8fe  br       loc_22EC10
0x22e903  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor()
0x22e908  stloc.s  0xE
0x22e90a  ldloc.s  0xD
0x22e90c  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x22e911  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x22e916  stloc.s  0x20
0x22e918  br.s     loc_22E945
0x22e91a  ldloc.s  0x20
0x22e91c  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x22e921  castclass [System.Xml]System.Xml.XmlNode
0x22e926  stloc.s  0xF
0x22e928  ldloc.s  0xF
0x22e92a  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x22e92f  callvirt instance int32 [System.Xml]System.Xml.XmlNamedNodeMap::get_Count()
0x22e934  brtrue.s loc_22E945
0x22e936  ldloc.s  0xE
0x22e938  ldloc.s  0xF
0x22e93a  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x22e93f  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x22e944  pop
0x22e945  ldloc.s  0x20
0x22e947  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x22e94c  brtrue.s loc_22E91A
0x22e94e  leave.s  loc_22E965
0x22e950  ldloc.s  0x20
0x22e952  isinst   [mscorlib]System.IDisposable
0x22e957  stloc.s  0x21
0x22e959  ldloc.s  0x21
0x22e95b  brfalse.s loc_22E964
0x22e95d  ldloc.s  0x21
0x22e95f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x22e964  endfinally
0x22e965  ldloc.s  7
0x22e967  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x22e96c  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x22e971  stloc.s  0x22
0x22e973  br.s     loc_22E9BB
0x22e975  ldloc.s  0x22
0x22e977  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x22e97c  castclass [System.Xml]System.Xml.XmlNode
0x22e981  stloc.s  0x10
0x22e983  ldloc.s  0x10
0x22e985  callvirt instance bool [System.Xml]System.Xml.XmlNode::get_HasChildNodes()
0x22e98a  brtrue.s loc_22E9AA
0x22e98c  ldloc.s  0x10
0x22e98e  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x22e993  callvirt instance int32 [System.Xml]System.Xml.XmlNamedNodeMap::get_Count()
0x22e998  brtrue.s loc_22E9AA
0x22e99a  ldloc.s  0xE
0x22e99c  ldloc.s  0x10
0x22e99e  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x22e9a3  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Contains(var<u1>)
0x22e9a8  brtrue.s loc_22E9BB
0x22e9aa  ldloc.s  0xD
0x22e9ac  ldarg.1
0x22e9ad  ldloc.s  0x10
  ... truncated ...
```
