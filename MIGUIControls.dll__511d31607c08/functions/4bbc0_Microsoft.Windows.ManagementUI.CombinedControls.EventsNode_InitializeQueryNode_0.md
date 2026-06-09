# Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::InitializeQueryNode_0

- ea: `0x4bbc0`
- end: `0x4bc60`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::InitializeQueryNode_0`
- size: `160`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4b850`
- `0x8eec0`

## callees

- `0x13430`
- `0x14de0`
- `0x16310`
- `0x16350`
- `0x46dd0`
- `0x46ea0`
- `0x48b20`
- `0x4bbc0`
- `0x4bc60`
- `0x53a10`
- `0x53b00`
- `0x54010`
- `0x540d0`

## string_xrefs

- `0x4bc48`: `Invalid config. Xml format error`

## pseudocode

```c

```

## disassembly

```asm
0x4bbc0  call     class [System.Xml]System.Xml.XmlDocument Microsoft.Windows.ManagementUI.CombinedControls.XmlConfigHelper::CreateXmlDocument()
0x4bbc5  stloc.0
0x4bbc6  ldarg.0
0x4bbc7  ldarg.2
0x4bbc8  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::_isBuiltInView
0x4bbcd  ldloc.0
0x4bbce  ldarg.1
0x4bbcf  call     void Microsoft.Windows.ManagementUI.CombinedControls.XmlConfigHelper::LoadXml(class [System.Xml]System.Xml.XmlDocument doc, string xml)
0x4bbd4  ldloc.0
0x4bbd5  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x4bbda  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::QueryConfig
0x4bbdf  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x4bbe4  stloc.1
0x4bbe5  ldloc.1
0x4bbe6  brfalse.s loc_4BBFF
0x4bbe8  ldarg.0
0x4bbe9  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig::.ctor()
0x4bbee  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::qry
0x4bbf3  ldarg.0
0x4bbf4  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::qry
0x4bbf9  ldloc.1
0x4bbfa  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig::InitializeForXml(class [System.Xml]System.Xml.XmlElement qryElem)
0x4bbff  ldarg.0
0x4bc00  ldloc.0
0x4bc01  call     instance class [System.Xml]System.Xml.XmlElement Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::GetResultConfig(class [System.Xml]System.Xml.XmlDocument doc)
0x4bc06  pop
0x4bc07  ldarg.0
0x4bc08  ldsfld   string [mscorlib]System.String::Empty
0x4bc0d  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::set_LogFilePath(string value)
0x4bc12  ldarg.0
0x4bc13  ldarg.0
0x4bc14  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::qry
0x4bc19  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig::get_Name()
0x4bc1e  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::set_Name(string value)
0x4bc23  ldarg.0
0x4bc24  ldarg.0
0x4bc25  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::qry
0x4bc2a  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig::get_Description()
0x4bc2f  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::set_Description(string value)
0x4bc34  ldarg.0
0x4bc35  ldsfld   string [mscorlib]System.String::Empty
0x4bc3a  stfld    string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::nodePathInConfig
0x4bc3f  ldarg.0
0x4bc40  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::UpdateReadOnly()
0x4bc45  leave.s  loc_4BC5F
0x4bc47  stloc.2
0x4bc48  ldstr    aInvalidConfigX// "Invalid config. Xml format error"
0x4bc4d  ldloc.2
0x4bc4e  callvirt instance string [mscorlib]System.Exception::get_Message()
0x4bc53  call     string [mscorlib]System.String::Concat(string, string)
0x4bc58  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::SystemError(string errorString)
0x4bc5d  leave.s  loc_4BC5F
0x4bc5f  ret
```
