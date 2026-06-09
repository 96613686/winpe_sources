# Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::.cctor

- ea: `0x45f70`
- end: `0x46065`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::.cctor`
- size: `245`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x37100`
- `0x4bfb0`

## string_xrefs

- `0x45fac`: `Settings.Xml`
- `0x46055`: `RecentViews.xml`

## pseudocode

```c

```

## disassembly

```asm
0x45f70  ldstr    aViews// "Views"
0x45f75  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::ViewsFolderName
0x45f7a  ldstr    aApplicationvie// "ApplicationViewsRootNode"
0x45f7f  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::AdminViewsFolderName
0x45f84  ldstr    aExternallogs// "ExternalLogs"
0x45f89  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::ExternalLogsFolderName
0x45f8e  ldstr    aView// "View_"
0x45f93  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::ViewFileNamePrefix
0x45f98  ldstr    aLog// "Log_"
0x45f9d  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::ExternalLogFileNamePrefix
0x45fa2  ldstr    aChannel_0// "Channel_"
0x45fa7  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::ChannelFileNamePrefix
0x45fac  ldstr    aSettingsXml// "Settings.Xml"
0x45fb1  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::ViewerConfigFileName
0x45fb6  ldc.i4.s 0x64
0x45fb8  stsfld   int32 Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::MaximumViewNameLength
0x45fbd  ldc.i4   0x104
0x45fc2  stsfld   int32 Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::MaximumPathLength
0x45fc7  ldc.i4.s 0x3C
0x45fc9  stsfld   int32 Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::DefaultPreviewSize
0x45fce  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Windows.ManagementUI.CombinedControls.RecentViewsData>::.ctor()
0x45fd3  stsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Windows.ManagementUI.CombinedControls.RecentViewsData> Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::recentViewsDataArrayList
0x45fd8  ldnull
0x45fd9  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::recentViewsFile
0x45fde  ldc.i4.s 0x1E
0x45fe0  ldc.i4.4
0x45fe1  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::.ctor(valuetype Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers id, valuetype Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus stat)
0x45fe6  stsfld   class Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::directChannelVisibleAction
0x45feb  ldc.i4.1
0x45fec  stsfld   bool Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::previewVisible
0x45ff1  ldsfld   int32 Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::DefaultPreviewSize
0x45ff6  stsfld   int32 Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::previewSize
0x45ffb  ldc.i4.s 0x23
0x45ffd  call     string [mscorlib]System.Environment::GetFolderPath(valuetype [mscorlib]System.Environment/SpecialFolder)
0x46002  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::MicrosoftFolderName
0x46007  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::LIN_EventViewer
0x4600c  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x46011  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x46016  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::recentViewsFile
0x4601b  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::recentViewsFile
0x46020  ldc.i4.s 0x23
0x46022  call     string [mscorlib]System.Environment::GetFolderPath(valuetype [mscorlib]System.Environment/SpecialFolder)
0x46027  ldc.i4.s 0x1C
0x46029  call     string [mscorlib]System.Environment::GetFolderPath(valuetype [mscorlib]System.Environment/SpecialFolder)
0x4602e  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x46033  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::recentViewsFile
0x46038  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::recentViewsFile
0x4603d  call     class [mscorlib]System.IO.DirectoryInfo Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::CreateDirectory(string path)
0x46042  pop
0x46043  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::recentViewsFile
0x46048  ldsfld   char [mscorlib]System.IO.Path::DirectorySeparatorChar
0x4604d  stloc.0
0x4604e  ldloca.s 0
0x46050  call     instance string [mscorlib]System.Char::ToString()
0x46055  ldstr    aRecentviewsXml// "RecentViews.xml"
0x4605a  call     string [mscorlib]System.String::Concat(string, string, string)
0x4605f  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::recentViewsFile
0x46064  ret
```
