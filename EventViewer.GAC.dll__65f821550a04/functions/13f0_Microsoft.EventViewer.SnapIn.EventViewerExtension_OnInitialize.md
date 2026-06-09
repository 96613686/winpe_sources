# Microsoft.EventViewer.SnapIn.EventViewerExtension::OnInitialize

- ea: `0x13f0`
- end: `0x1568`
- name: `Microsoft.EventViewer.SnapIn.EventViewerExtension::OnInitialize`
- size: `376`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x3b0`
- `0x13f0`
- `0x4520`
- `0x8690`
- `0xa7b0`

## pseudocode

```c

```

## disassembly

```asm
0x13f0  ldarg.0
0x13f1  ldstr    aOninitialize// "OnInitialize"
0x13f6  call     void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.TimeTrace::StartMethod(object, string)
0x13fb  call     void Microsoft.EventViewer.SnapIn.EventViewerSnapIn::SetRegistryForHelpChmFiles()
0x1400  ldarg.0
0x1401  call     instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInBase::OnInitialize()
0x1406  ldarg.0
0x1407  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.PrimaryScopeNode [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.NamespaceExtension::get_PrimaryNode()
0x140c  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SharedData [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.PrimaryScopeNode::get_SharedData()
0x1411  ldstr    aRmtOcSystemRes// "RMT_OC_SYSTEM_RESOURCE_MANAGER"
0x1416  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SharedDataItem [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SharedData::GetItem(string)
0x141b  stloc.2
0x141c  ldloc.2
0x141d  brfalse.s loc_1457
0x141f  ldloc.2
0x1420  callvirt instance unsigned int8[] [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SharedDataItemBase::GetData()
0x1425  brfalse.s loc_1457
0x1427  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_Unicode()
0x142c  ldloc.2
0x142d  callvirt instance unsigned int8[] [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SharedDataItemBase::GetData()
0x1432  callvirt instance string [mscorlib]System.Text.Encoding::GetString(unsigned int8[])
0x1437  stloc.3
0x1438  ldloc.3
0x1439  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x143e  brtrue.s loc_1457
0x1440  ldloc.3
0x1441  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x1446  ldstr    aFalse// "false"
0x144b  call     bool [mscorlib]System.String::Equals(string, string)
0x1450  brfalse.s loc_1457
0x1452  leave    loc_1567
0x1457  leave.s  loc_145C
0x1459  pop
0x145a  leave.s  loc_145C
0x145c  ldarg.0
0x145d  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.PrimaryScopeNode [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.NamespaceExtension::get_PrimaryNode()
0x1462  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SharedData [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.PrimaryScopeNode::get_SharedData()
0x1467  ldstr    aMmcSnapinMachi// "MMC_SNAPIN_MACHINE_NAME"
0x146c  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SharedDataItem [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SharedData::GetItem(string)
0x1471  stloc.0
0x1472  ldsfld   string [mscorlib]System.String::Empty
0x1477  stloc.1
0x1478  ldloc.0
0x1479  brfalse.s loc_14CA
0x147b  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_Unicode()
0x1480  ldloc.0
0x1481  callvirt instance unsigned int8[] [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SharedDataItemBase::GetData()
0x1486  callvirt instance string [mscorlib]System.Text.Encoding::GetString(unsigned int8[])
0x148b  stloc.1
0x148c  ldloc.1
0x148d  brfalse.s loc_14A7
0x148f  ldloc.1
0x1490  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1495  ldc.i4.0
0x1496  ble.s    loc_14A7
0x1498  ldloc.1
0x1499  ldc.i4.0
0x149a  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x149f  brtrue.s loc_14A7
0x14a1  ldsfld   string [mscorlib]System.String::Empty
0x14a6  stloc.1
0x14a7  ldloc.1
0x14a8  brfalse.s loc_14CA
0x14aa  ldloc.1
0x14ab  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x14b0  brtrue.s loc_14CA
0x14b2  ldloc.1
0x14b3  ldc.i4.0
0x14b4  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x14b9  stloc.s  4
0x14bb  ldloc.s  4
0x14bd  ldc.i4.0
0x14be  blt.s    loc_14CA
0x14c0  ldloc.1
0x14c1  ldc.i4.0
0x14c2  ldloc.s  4
0x14c4  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x14c9  stloc.1
0x14ca  leave.s  loc_14D5
0x14cc  pop
0x14cd  ldsfld   string [mscorlib]System.String::Empty
0x14d2  stloc.1
0x14d3  leave.s  loc_14D5
0x14d5  ldarg.0
0x14d6  ldloc.1
0x14d7  ldnull
0x14d8  ldnull
0x14d9  ldnull
0x14da  newobj   instance void Microsoft.EventViewer.SnapIn.MMCRootNode::.ctor(string remotecomputerName, string userDomain, string userName, class [mscorlib]System.Security.SecureString encryptedPassword)
0x14df  stfld    class Microsoft.EventViewer.SnapIn.MMCRootNode Microsoft.EventViewer.SnapIn.EventViewerExtension::rootNode
0x14e4  ldarg.0
0x14e5  ldfld    class Microsoft.EventViewer.SnapIn.MMCRootNode Microsoft.EventViewer.SnapIn.EventViewerExtension::rootNode
0x14ea  ldstr    aEventviewerChm// "eventviewer.chm::/html/4229f239-16a6-4e"...
0x14ef  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::set_HelpTopic(string)
0x14f4  ldarg.0
0x14f5  ldfld    class Microsoft.EventViewer.SnapIn.MMCRootNode Microsoft.EventViewer.SnapIn.EventViewerExtension::rootNode
0x14fa  call     string Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ViewerName()
0x14ff  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Node::set_DisplayName(string)
0x1504  ldarg.0
0x1505  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.PrimaryScopeNode [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.NamespaceExtension::get_PrimaryNode()
0x150a  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNodeCollection [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.PrimaryScopeNode::get_Children()
0x150f  ldarg.0
0x1510  ldfld    class Microsoft.EventViewer.SnapIn.MMCRootNode Microsoft.EventViewer.SnapIn.EventViewerExtension::rootNode
0x1515  callvirt instance int32 [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNodeCollection::Add(class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode)
0x151a  pop
0x151b  ldarg.0
0x151c  ldarg.0
0x151d  ldftn    instance void Microsoft.EventViewer.SnapIn.EventViewerExtension::ShowEventViewerHelpTopic(string helpTopicGuid)
0x1523  newobj   instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ShowHelpTopicDelegate::.ctor(object, native int)
0x1528  stfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ShowHelpTopicDelegate Microsoft.EventViewer.SnapIn.EventViewerExtension::showHelpTopicDelegate
0x152d  ldarg.0
0x152e  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ShowHelpTopicDelegate Microsoft.EventViewer.SnapIn.EventViewerExtension::showHelpTopicDelegate
0x1533  call     void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::AddShowEventViewerHelpTopicDelegate(class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ShowHelpTopicDelegate)
0x1538  leave.s  loc_155C
0x153a  stloc.s  5
0x153c  call     string Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ViewerName()
0x1541  ldloc.s  5
0x1543  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1548  ldarg.0
0x1549  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.Console [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase::get_Console()
0x154e  call     void Microsoft.EventViewer.SnapIn.ViewerCommon::DisplayError(string caption, string text, class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.Console con)
0x1553  ldarg.0
0x1554  ldc.i4.0
0x1555  stfld    bool Microsoft.EventViewer.SnapIn.EventViewerExtension::initializationSucceeded
0x155a  leave.s  loc_155C
0x155c  ldarg.0
0x155d  ldstr    aOninitialize// "OnInitialize"
0x1562  call     void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.TimeTrace::EndMethod(object, string)
0x1567  ret
```
