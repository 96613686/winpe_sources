# Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::GetResultConfig

- ea: `0x48b20`
- end: `0x48dae`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::GetResultConfig`
- size: `654`
- prototype: ``
- caller_count: `6`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x46e70`
- `0x4b890`
- `0x4b9f0`
- `0x4bbc0`
- `0x4c020`
- `0x4c600`

## callees

- `0x13430`
- `0x14db0`
- `0x16310`
- `0x16350`
- `0x16370`
- `0x37e70`
- `0x46600`
- `0x48b20`
- `0x49420`
- `0x4ca30`

## string_xrefs

- `0x48bb8`: `XMl file invalid`
- `0x48c7b`: `XMl file invalid`
- `0x48d01`: `XMl file invalid`

## pseudocode

```c

```

## disassembly

```asm
0x48b20  ldc.i4.1
0x48b21  stloc.0
0x48b22  ldarg.0
0x48b23  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::resultConfig
0x48b28  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x48b2d  brfalse  loc_48D41
0x48b32  ldarg.1
0x48b33  brtrue   loc_48D0F
0x48b38  ldarg.0
0x48b39  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::nodePathInConfig
0x48b3e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x48b43  brfalse  loc_48CE9
0x48b48  ldc.i4.0
0x48b49  stloc.0
0x48b4a  ldarg.0
0x48b4b  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_ParentNode()
0x48b50  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::GetConfigPathForNode()
0x48b55  stloc.1
0x48b56  ldloc.1
0x48b57  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x48b5c  brtrue   loc_48D0F
0x48b61  ldloc.1
0x48b62  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x48b67  brfalse  loc_48D0F
0x48b6c  ldloc.1
0x48b6d  newobj   instance void [mscorlib]System.IO.DirectoryInfo::.ctor(string)
0x48b72  callvirt instance class [mscorlib]System.IO.FileInfo[] [mscorlib]System.IO.DirectoryInfo::GetFiles()
0x48b77  stloc.2
0x48b78  ldc.i4.0
0x48b79  stloc.s  4
0x48b7b  br       loc_48C0F
0x48b80  ldloc.2
0x48b81  ldloc.s  4
0x48b83  ldelem.ref
0x48b84  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x48b89  call     string [mscorlib]System.IO.Path::GetExtension(string)
0x48b8e  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::ViewerConfigExtension
0x48b93  ldc.i4.5
0x48b94  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x48b99  brtrue.s loc_48C09
0x48b9b  call     class [System.Xml]System.Xml.XmlDocument Microsoft.Windows.ManagementUI.CombinedControls.XmlConfigHelper::CreateXmlDocument()
0x48ba0  starg.s  1
0x48ba2  ldc.i4.0
0x48ba3  stloc.0
0x48ba4  ldarg.1
0x48ba5  ldloc.2
0x48ba6  ldloc.s  4
0x48ba8  ldelem.ref
0x48ba9  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x48bae  call     void Microsoft.Windows.ManagementUI.CombinedControls.XmlConfigHelper::Load(class [System.Xml]System.Xml.XmlDocument doc, string uri)
0x48bb3  ldc.i4.1
0x48bb4  stloc.0
0x48bb5  leave.s  loc_48BC6
0x48bb7  pop
0x48bb8  ldstr    aXmlFileInvalid// "XMl file invalid"
0x48bbd  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::SystemError(string errorString)
0x48bc2  ldc.i4.0
0x48bc3  stloc.0
0x48bc4  leave.s  loc_48BC6
0x48bc6  ldloc.0
0x48bc7  brfalse.s loc_48C04
0x48bc9  ldarg.1
0x48bca  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x48bcf  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::NameNode
0x48bd4  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x48bd9  stloc.3
0x48bda  ldloc.3
0x48bdb  brfalse.s loc_48C04
0x48bdd  ldloc.3
0x48bde  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x48be3  ldarg.0
0x48be4  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::get_Name()
0x48be9  ldc.i4.0
0x48bea  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x48bef  brtrue.s loc_48C04
0x48bf1  ldc.i4.1
0x48bf2  stloc.0
0x48bf3  ldarg.0
0x48bf4  ldloc.2
0x48bf5  ldloc.s  4
0x48bf7  ldelem.ref
0x48bf8  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x48bfd  stfld    string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::nodePathInConfig
0x48c02  br.s     loc_48C19
0x48c04  ldnull
0x48c05  starg.s  1
0x48c07  ldc.i4.0
0x48c08  stloc.0
0x48c09  ldloc.s  4
0x48c0b  ldc.i4.1
0x48c0c  add
0x48c0d  stloc.s  4
0x48c0f  ldloc.s  4
0x48c11  ldloc.2
0x48c12  ldlen
0x48c13  conv.i4
0x48c14  blt      loc_48B80
0x48c19  ldloc.1
0x48c1a  call     string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::GetUsersConfigDirectoryForGivenAllUserPath(string path)
0x48c1f  stloc.1
0x48c20  call     bool Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::get_HasWritePermissionToAllUsers()
0x48c25  brtrue   loc_48D0F
0x48c2a  ldloc.1
0x48c2b  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x48c30  brfalse  loc_48D0F
0x48c35  ldarg.0
0x48c36  ldsfld   string [mscorlib]System.String::Empty
0x48c3b  stfld    string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::nodePathInConfig
0x48c40  call     class [System.Xml]System.Xml.XmlDocument Microsoft.Windows.ManagementUI.CombinedControls.XmlConfigHelper::CreateXmlDocument()
0x48c45  stloc.s  5
0x48c47  ldloc.1
0x48c48  newobj   instance void [mscorlib]System.IO.DirectoryInfo::.ctor(string)
0x48c4d  callvirt instance class [mscorlib]System.IO.FileInfo[] [mscorlib]System.IO.DirectoryInfo::GetFiles()
0x48c52  stloc.2
0x48c53  ldloc.0
0x48c54  stloc.s  6
0x48c56  ldc.i4.0
0x48c57  stloc.0
0x48c58  ldc.i4.0
0x48c59  stloc.s  7
0x48c5b  br.s     loc_48CD7
0x48c5d  ldc.i4.0
0x48c5e  stloc.0
0x48c5f  call     class [System.Xml]System.Xml.XmlDocument Microsoft.Windows.ManagementUI.CombinedControls.XmlConfigHelper::CreateXmlDocument()
0x48c64  stloc.s  5
0x48c66  ldloc.s  5
0x48c68  ldloc.2
0x48c69  ldloc.s  7
0x48c6b  ldelem.ref
0x48c6c  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x48c71  call     void Microsoft.Windows.ManagementUI.CombinedControls.XmlConfigHelper::Load(class [System.Xml]System.Xml.XmlDocument doc, string uri)
0x48c76  ldc.i4.1
0x48c77  stloc.0
0x48c78  leave.s  loc_48C89
0x48c7a  pop
0x48c7b  ldstr    aXmlFileInvalid// "XMl file invalid"
0x48c80  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::SystemError(string errorString)
0x48c85  ldc.i4.0
0x48c86  stloc.0
0x48c87  leave.s  loc_48C89
0x48c89  ldloc.0
0x48c8a  brfalse.s loc_48CCC
0x48c8c  ldloc.s  5
0x48c8e  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x48c93  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::NameNode
0x48c98  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x48c9d  stloc.3
0x48c9e  ldloc.3
0x48c9f  brfalse.s loc_48CCC
0x48ca1  ldloc.3
0x48ca2  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x48ca7  ldarg.0
0x48ca8  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::get_Name()
0x48cad  ldc.i4.4
0x48cae  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x48cb3  brtrue.s loc_48CCC
0x48cb5  ldc.i4.1
0x48cb6  stloc.0
0x48cb7  ldarg.0
0x48cb8  ldloc.2
0x48cb9  ldloc.s  7
0x48cbb  ldelem.ref
0x48cbc  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x48cc1  stfld    string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::nodePathInConfig
0x48cc6  ldloc.s  5
0x48cc8  starg.s  1
0x48cca  br.s     loc_48CE1
0x48ccc  ldnull
0x48ccd  stloc.s  5
0x48ccf  ldc.i4.0
0x48cd0  stloc.0
0x48cd1  ldloc.s  7
0x48cd3  ldc.i4.1
0x48cd4  add
0x48cd5  stloc.s  7
0x48cd7  ldloc.s  7
0x48cd9  ldloc.2
0x48cda  ldlen
0x48cdb  conv.i4
0x48cdc  blt      loc_48C5D
0x48ce1  ldloc.0
0x48ce2  brtrue.s loc_48D0F
0x48ce4  ldloc.s  6
0x48ce6  stloc.0
0x48ce7  br.s     loc_48D0F
0x48ce9  call     class [System.Xml]System.Xml.XmlDocument Microsoft.Windows.ManagementUI.CombinedControls.XmlConfigHelper::CreateXmlDocument()
0x48cee  starg.s  1
0x48cf0  ldarg.1
0x48cf1  ldarg.0
0x48cf2  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::nodePathInConfig
0x48cf7  call     void Microsoft.Windows.ManagementUI.CombinedControls.XmlConfigHelper::Load(class [System.Xml]System.Xml.XmlDocument doc, string uri)
0x48cfc  ldc.i4.1
0x48cfd  stloc.0
0x48cfe  leave.s  loc_48D0F
0x48d00  pop
0x48d01  ldstr    aXmlFileInvalid// "XMl file invalid"
0x48d06  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::SystemError(string errorString)
0x48d0b  ldc.i4.0
0x48d0c  stloc.0
0x48d0d  leave.s  loc_48D0F
0x48d0f  ldloc.0
0x48d10  brfalse  loc_48DAC
0x48d15  ldarg.1
0x48d16  brfalse  loc_48DAC
0x48d1b  ldarg.1
0x48d1c  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x48d21  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::ResultViewConfig
0x48d26  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x48d2b  stloc.s  8
0x48d2d  ldloc.s  8
0x48d2f  brfalse.s loc_48D3E
0x48d31  ldarg.0
0x48d32  ldloc.s  8
0x48d34  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x48d39  stfld    string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::resultConfig
0x48d3e  ldloc.s  8
0x48d40  ret
0x48d41  call     class [System.Xml]System.Xml.XmlDocument Microsoft.Windows.ManagementUI.CombinedControls.XmlConfigHelper::CreateXmlDocument()
0x48d46  stloc.s  9
0x48d48  ldloc.s  9
0x48d4a  ldarg.0
0x48d4b  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::resultConfig
0x48d50  call     void Microsoft.Windows.ManagementUI.CombinedControls.XmlConfigHelper::LoadXml(class [System.Xml]System.Xml.XmlDocument doc, string xml)
0x48d55  ldloc.s  9
0x48d57  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x48d5c  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::PreviewConfigNode
0x48d61  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x48d66  stloc.s  0xA
0x48d68  ldloc.s  0xA
0x48d6a  brfalse.s loc_48D8D
0x48d6c  ldloc.s  0xA
0x48d6e  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x48d73  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::VisibleAttr
0x48d78  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x48d7d  brtrue.s loc_48D87
0x48d7f  ldc.i4.0
0x48d80  stsfld   bool Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::previewVisible
0x48d85  br.s     loc_48D8D
0x48d87  ldc.i4.1
0x48d88  stsfld   bool Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::previewVisible
0x48d8d  ldarg.1
0x48d8e  brfalse.s loc_48DA4
0x48d90  ldarg.1
0x48d91  ldloc.s  9
0x48d93  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x48d98  ldc.i4.1
0x48d99  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlDocument::ImportNode(class [System.Xml]System.Xml.XmlNode, bool)
0x48d9e  castclass [System.Xml]System.Xml.XmlElement
0x48da3  ret
0x48da4  ldloc.s  9
0x48da6  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x48dab  ret
0x48dac  ldnull
0x48dad  ret
```
