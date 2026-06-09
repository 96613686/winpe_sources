# Microsoft.EventViewer.SnapIn.EventViewerExtension::.ctor

- ea: `0x1340`
- end: `0x13ec`
- name: `Microsoft.EventViewer.SnapIn.EventViewerExtension::.ctor`
- size: `172`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x10`
- `0x11b0`
- `0x1290`
- `0x1340`
- `0x86e0`

## string_xrefs

- `0x134c`: `EventViewerExtension`
- `0x13e1`: `EventViewerExtension`

## pseudocode

```c

```

## disassembly

```asm
0x1340  ldarg.0
0x1341  call     instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.NamespaceExtension::.ctor()
0x1346  call     void Microsoft.EventViewer.SnapIn.EventViewerSnapIn::InitializeTrace()
0x134b  ldarg.0
0x134c  ldstr    aEventviewerext// "EventViewerExtension"
0x1351  call     void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.TimeTrace::StartMethod(object, string)
0x1356  call     void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::EnableSecurityPrilige()
0x135b  ldarg.0
0x135c  ldstr    aMmcSnapinMachi// "MMC_SNAPIN_MACHINE_NAME"
0x1361  newobj   instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SharedDataItem::.ctor(string)
0x1366  stfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SharedDataItem Microsoft.EventViewer.SnapIn.EventViewerExtension::publishedDataItem
0x136b  ldarg.0
0x136c  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.PrimaryScopeNode [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.NamespaceExtension::get_PrimaryNode()
0x1371  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SharedData [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.PrimaryScopeNode::get_SharedData()
0x1376  ldarg.0
0x1377  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SharedDataItem Microsoft.EventViewer.SnapIn.EventViewerExtension::publishedDataItem
0x137c  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SharedData::Add(class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SharedDataItem)
0x1381  ldarg.0
0x1382  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.PrimaryScopeNode [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.NamespaceExtension::get_PrimaryNode()
0x1387  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SharedData [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.PrimaryScopeNode::get_SharedData()
0x138c  ldstr    aRmtOcSystemRes// "RMT_OC_SYSTEM_RESOURCE_MANAGER"
0x1391  newobj   instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SharedDataItem::.ctor(string)
0x1396  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SharedData::Add(class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SharedDataItem)
0x139b  ldarg.0
0x139c  call     void Microsoft.EventViewer.SnapIn.ViewerCommon::AddImages(class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase snapin)
0x13a1  ldarg.0
0x13a2  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.Console [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase::get_Console()
0x13a7  ldarg.0
0x13a8  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.MMCConsole::.ctor(class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.Console console, class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInBase snapin)
0x13ad  call     void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::set_Console(class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.IUIConsole)
0x13b2  leave.s  loc_13E0
0x13b4  stloc.0
0x13b5  ldstr    aEventviewersna_0// "EventViewerSnapIn"
0x13ba  ldnull
0x13bb  ldstr    aErrorException// "Error: Exception in ctor.\n{0}"
0x13c0  ldc.i4.1
0x13c1  newarr   [mscorlib]System.Object
0x13c6  dup
0x13c7  ldc.i4.0
0x13c8  ldloc.0
0x13c9  callvirt instance string [mscorlib]System.Object::ToString()
0x13ce  stelem.ref
0x13cf  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x13d4  call     void [System]System.Diagnostics.Trace::WriteLine(string, string)
0x13d9  call     void Microsoft.EventViewer.SnapIn.EventViewerSnapIn::ShutdownTrace()
0x13de  rethrow
0x13e0  ldarg.0
0x13e1  ldstr    aEventviewerext// "EventViewerExtension"
0x13e6  call     void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.TimeTrace::EndMethod(object, string)
0x13eb  ret
```
