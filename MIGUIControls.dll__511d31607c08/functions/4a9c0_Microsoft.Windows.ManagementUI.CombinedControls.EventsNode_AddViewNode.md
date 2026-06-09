# Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::AddViewNode

- ea: `0x4a9c0`
- end: `0x4abc7`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::AddViewNode`
- size: `519`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

## callees

- `0x12ed0`
- `0x16310`
- `0x16370`
- `0x33aa0`
- `0x37e70`
- `0x4a8e0`
- `0x4a9c0`
- `0x4ae40`
- `0x4b350`
- `0x4c8f0`
- `0x4d650`
- `0x4d840`
- `0x4dfa0`
- `0x53a10`
- `0x53b00`
- `0x53fc0`
- `0x53fd0`
- `0x54010`
- `0x54040`
- `0x54110`

## string_xrefs

- `0x4aa9f`: `CommandLineViewName`
- `0x4aac1`: `InvalidConfigFileError`
- `0x4ab80`: `InvalidConfigFileError`
- `0x4ab9c`: `InvalidConfigFileError`
- `0x4abb4`: `InvalidConfigFileError`
- `0x4ab8e`: `PathTooLongError`

## pseudocode

```c

```

## disassembly

```asm
0x4a9c0  call     class [System.Xml]System.Xml.XmlDocument Microsoft.Windows.ManagementUI.CombinedControls.XmlConfigHelper::CreateXmlDocument()
0x4a9c5  stloc.0
0x4a9c6  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig::.ctor()
0x4a9cb  stloc.1
0x4a9cc  ldc.i4.0
0x4a9cd  stloc.2
0x4a9ce  ldsfld   string [mscorlib]System.String::Empty
0x4a9d3  stloc.3
0x4a9d4  ldarg.1
0x4a9d5  call     bool [mscorlib]System.IO.File::Exists(string)
0x4a9da  brtrue.s loc_4AA14
0x4a9dc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4a9e1  ldtoken  [mscorlib]System.String
0x4a9e6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4a9eb  callvirt instance object [mscorlib]System.Globalization.CultureInfo::GetFormat(class [mscorlib]System.Type)
0x4a9f0  castclass [mscorlib]System.IFormatProvider
0x4a9f5  ldstr    aFilenotexister// "FileNotExistError"
0x4a9fa  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x4a9ff  ldc.i4.1
0x4aa00  newarr   [mscorlib]System.Object
0x4aa05  dup
0x4aa06  ldc.i4.0
0x4aa07  ldarg.1
0x4aa08  stelem.ref
0x4aa09  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4aa0e  stloc.3
0x4aa0f  br       loc_4ABA9
0x4aa14  nop
0x4aa15  ldloc.0
0x4aa16  ldarg.1
0x4aa17  call     void Microsoft.Windows.ManagementUI.CombinedControls.XmlConfigHelper::Load(class [System.Xml]System.Xml.XmlDocument doc, string uri)
0x4aa1c  ldsfld   string [mscorlib]System.String::Empty
0x4aa21  stloc.s  4
0x4aa23  ldc.i4.1
0x4aa24  stloc.s  5
0x4aa26  ldsfld   string [mscorlib]System.String::Empty
0x4aa2b  stloc.s  6
0x4aa2d  ldarg.0
0x4aa2e  ldloca.s 7
0x4aa30  call     void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::GetViewRootNode(class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode nd, [out] class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode& viewRootNode)
0x4aa35  ldloc.0
0x4aa36  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x4aa3b  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::QueryConfig
0x4aa40  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x4aa45  stloc.s  8
0x4aa47  ldloc.s  8
0x4aa49  brfalse.s loc_4AA6F
0x4aa4b  ldloc.1
0x4aa4c  ldloc.s  8
0x4aa4e  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig::InitializeForXml(class [System.Xml]System.Xml.XmlElement qryElem)
0x4aa53  ldloc.1
0x4aa54  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig::get_Name()
0x4aa59  stloc.s  6
0x4aa5b  ldloc.1
0x4aa5c  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig::get_Name()
0x4aa61  ldstr    a0_1// "_{0}"
0x4aa66  call     string [mscorlib]System.String::Concat(string, string)
0x4aa6b  stloc.s  4
0x4aa6d  br.s     loc_4AAB2
0x4aa6f  ldloc.0
0x4aa70  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x4aa75  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x4aa7a  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::QUERYLISTNODE
0x4aa7f  ldc.i4.0
0x4aa80  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x4aa85  brtrue.s loc_4AAB2
0x4aa87  ldloc.1
0x4aa88  ldc.i4.1
0x4aa89  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig::set_UserQuery(bool value)
0x4aa8e  ldloc.1
0x4aa8f  ldloc.0
0x4aa90  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x4aa95  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.EventQuery::.ctor(class [System.Xml]System.Xml.XmlElement evtQry)
0x4aa9a  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig::set_Query(class Microsoft.Windows.ManagementUI.CombinedControls.EventQuery value)
0x4aa9f  ldstr    aCommandlinevie// "CommandLineViewName"
0x4aaa4  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x4aaa9  stloc.s  4
0x4aaab  ldsfld   string [mscorlib]System.String::Empty
0x4aab0  stloc.s  6
0x4aab2  ldloc.1
0x4aab3  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.EventQuery Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig::get_Query()
0x4aab8  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.EventQuery::IsEmpty()
0x4aabd  brfalse.s loc_4AAD1
0x4aabf  ldc.i4.0
0x4aac0  stloc.2
0x4aac1  ldstr    aInvalidconfigf// "InvalidConfigFileError"
0x4aac6  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x4aacb  stloc.3
0x4aacc  br       loc_4AB7D
0x4aad1  ldc.i4.1
0x4aad2  stloc.2
0x4aad3  ldarg.2
0x4aad4  ldloc.s  7
0x4aad6  ldloc.1
0x4aad7  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.EventQuery Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig::get_Query()
0x4aadc  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.EventQuery::get_Channel()
0x4aae1  ldloc.1
0x4aae2  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.EventQuery Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig::get_Query()
0x4aae7  callvirt instance string [mscorlib]System.Object::ToString()
0x4aaec  ldloc.s  6
0x4aaee  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::GetChildNode(string channel, string query, string name)
0x4aaf3  stind.ref
0x4aaf4  ldarg.2
0x4aaf5  ldind.ref
0x4aaf6  brtrue   loc_4AB7D
0x4aafb  br.s     loc_4AB4E
0x4aafd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4ab02  ldtoken  [mscorlib]System.String
0x4ab07  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4ab0c  callvirt instance object [mscorlib]System.Globalization.CultureInfo::GetFormat(class [mscorlib]System.Type)
0x4ab11  castclass [mscorlib]System.IFormatProvider
0x4ab16  ldloc.s  4
0x4ab18  ldc.i4.1
0x4ab19  newarr   [mscorlib]System.Object
0x4ab1e  dup
0x4ab1f  ldc.i4.0
0x4ab20  ldloca.s 5
0x4ab22  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4ab27  ldtoken  [mscorlib]System.Int32
0x4ab2c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4ab31  callvirt instance object [mscorlib]System.Globalization.CultureInfo::GetFormat(class [mscorlib]System.Type)
0x4ab36  castclass [mscorlib]System.IFormatProvider
0x4ab3b  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x4ab40  stelem.ref
0x4ab41  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4ab46  stloc.s  6
0x4ab48  ldloc.s  5
0x4ab4a  ldc.i4.1
0x4ab4b  add
0x4ab4c  stloc.s  5
0x4ab4e  ldloc.s  6
0x4ab50  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4ab55  brtrue.s loc_4AAFD
0x4ab57  ldloc.s  7
0x4ab59  ldloc.s  6
0x4ab5b  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::IsDuplicateNode(string newNodeName)
0x4ab60  brtrue.s loc_4AAFD
0x4ab62  ldloc.1
0x4ab63  ldloc.s  6
0x4ab65  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig::set_Name(string value)
0x4ab6a  ldloc.s  7
0x4ab6c  ldloc.1
0x4ab6d  ldsfld   string [mscorlib]System.String::Empty
0x4ab72  ldc.i4.1
0x4ab73  call     bool Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::get_HasWritePermissionToAllUsers()
0x4ab78  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::AddViewNode(class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig qryConfig, string path, bool customView, bool allUserQuery)
0x4ab7d  leave.s  loc_4ABA9
0x4ab7f  pop
0x4ab80  ldstr    aInvalidconfigf// "InvalidConfigFileError"
0x4ab85  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x4ab8a  stloc.3
0x4ab8b  leave.s  loc_4ABA9
0x4ab8d  pop
0x4ab8e  ldstr    aPathtoolongerr// "PathTooLongError"
0x4ab93  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x4ab98  stloc.3
0x4ab99  leave.s  loc_4ABA9
0x4ab9b  pop
0x4ab9c  ldstr    aInvalidconfigf// "InvalidConfigFileError"
0x4aba1  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x4aba6  stloc.3
0x4aba7  leave.s  loc_4ABA9
0x4aba9  ldloc.2
0x4abaa  brtrue.s loc_4ABC5
0x4abac  ldloc.3
0x4abad  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4abb2  brfalse.s loc_4ABBF
0x4abb4  ldstr    aInvalidconfigf// "InvalidConfigFileError"
0x4abb9  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x4abbe  stloc.3
0x4abbf  ldloc.3
0x4abc0  call     void Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::ShowErrorMessageBox(string message)
0x4abc5  ldloc.2
0x4abc6  ret
```
