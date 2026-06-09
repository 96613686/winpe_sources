# Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::InitializeQueryNode

- ea: `0x4b9f0`
- end: `0x4bb27`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::InitializeQueryNode`
- size: `311`
- prototype: ``
- caller_count: `4`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4b000`
- `0x4b420`
- `0x8d260`
- `0x8f180`

## callees

- `0x13430`
- `0x14da0`
- `0x14de0`
- `0x16310`
- `0x16370`
- `0x46dd0`
- `0x46ea0`
- `0x48b20`
- `0x4b9f0`
- `0x4bc60`
- `0x53a10`
- `0x53b00`
- `0x54010`
- `0x54040`
- `0x54050`
- `0x54090`
- `0x540c0`
- `0x540d0`

## string_xrefs

- `0x4bb0a`: `Invalid config file. Xml format error`

## pseudocode

```c

```

## disassembly

```asm
0x4b9f0  call     class [System.Xml]System.Xml.XmlDocument Microsoft.Windows.ManagementUI.CombinedControls.XmlConfigHelper::CreateXmlDocument()
0x4b9f5  stloc.0
0x4b9f6  ldloc.0
0x4b9f7  ldarg.1
0x4b9f8  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x4b9fd  call     void Microsoft.Windows.ManagementUI.CombinedControls.XmlConfigHelper::Load(class [System.Xml]System.Xml.XmlDocument doc, string uri)
0x4ba02  ldloc.0
0x4ba03  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x4ba08  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::QueryConfig
0x4ba0d  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x4ba12  stloc.1
0x4ba13  ldloc.1
0x4ba14  brfalse.s loc_4BA5D
0x4ba16  ldarg.0
0x4ba17  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig::.ctor()
0x4ba1c  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::qry
0x4ba21  ldarg.0
0x4ba22  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::qry
0x4ba27  ldloc.1
0x4ba28  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig::InitializeForXml(class [System.Xml]System.Xml.XmlElement qryElem)
0x4ba2d  ldarg.0
0x4ba2e  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::qry
0x4ba33  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig::get_SortGroupConfigPresent()
0x4ba38  brtrue.s loc_4BA4C
0x4ba3a  ldarg.0
0x4ba3b  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::qry
0x4ba40  callvirt instance valuetype Microsoft.Windows.ManagementUI.CombinedControls.ViewConfig Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig::get_ViewConfig()
0x4ba45  ldfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.ViewConfig::SuppressQueryExecutionErrors
0x4ba4a  brfalse.s loc_4BA5D
0x4ba4c  ldarg.0
0x4ba4d  ldarg.0
0x4ba4e  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::qry
0x4ba53  callvirt instance valuetype Microsoft.Windows.ManagementUI.CombinedControls.ViewConfig Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig::get_ViewConfig()
0x4ba58  stfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.ViewConfig Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::viewConfig
0x4ba5d  ldarg.0
0x4ba5e  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::qry
0x4ba63  brtrue.s loc_4BA6C
0x4ba65  ldc.i4.0
0x4ba66  stloc.2
0x4ba67  leave    loc_4BB25
0x4ba6c  ldarg.0
0x4ba6d  ldloc.0
0x4ba6e  call     instance class [System.Xml]System.Xml.XmlElement Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::GetResultConfig(class [System.Xml]System.Xml.XmlDocument doc)
0x4ba73  pop
0x4ba74  ldarg.0
0x4ba75  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::qry
0x4ba7a  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig::get_Name()
0x4ba7f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4ba84  brfalse.s loc_4BA97
0x4ba86  ldarg.0
0x4ba87  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::qry
0x4ba8c  ldarg.1
0x4ba8d  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_Name()
0x4ba92  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig::set_Name(string value)
0x4ba97  ldarg.0
0x4ba98  ldarg.1
0x4ba99  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x4ba9e  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::set_LogFilePath(string value)
0x4baa3  ldarg.0
0x4baa4  ldarg.0
0x4baa5  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::qry
0x4baaa  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig::get_Name()
0x4baaf  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::set_Name(string value)
0x4bab4  ldarg.0
0x4bab5  ldarg.0
0x4bab6  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::qry
0x4babb  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig::get_LanguageNeutralName()
0x4bac0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4bac5  brtrue.s loc_4BAD4
0x4bac7  ldarg.0
0x4bac8  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::qry
0x4bacd  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig::get_LanguageNeutralName()
0x4bad2  br.s     loc_4BADF
0x4bad4  ldarg.0
0x4bad5  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::qry
0x4bada  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig::get_Name()
0x4badf  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::set_LanguageNeutralName(string value)
0x4bae4  ldarg.0
0x4bae5  ldarg.0
0x4bae6  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::qry
0x4baeb  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig::get_Description()
0x4baf0  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::set_Description(string value)
0x4baf5  ldarg.0
0x4baf6  ldarg.1
0x4baf7  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x4bafc  stfld    string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::nodePathInConfig
0x4bb01  ldarg.0
0x4bb02  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::UpdateReadOnly()
0x4bb07  leave.s  loc_4BB23
0x4bb09  stloc.3
0x4bb0a  ldstr    aInvalidConfigF// "Invalid config file. Xml format error"
0x4bb0f  ldloc.3
0x4bb10  callvirt instance string [mscorlib]System.Exception::get_Message()
0x4bb15  call     string [mscorlib]System.String::Concat(string, string)
0x4bb1a  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::SystemError(string errorString)
0x4bb1f  ldc.i4.0
0x4bb20  stloc.2
0x4bb21  leave.s  loc_4BB25
0x4bb23  ldc.i4.1
0x4bb24  ret
0x4bb25  ldloc.2
0x4bb26  ret
```
