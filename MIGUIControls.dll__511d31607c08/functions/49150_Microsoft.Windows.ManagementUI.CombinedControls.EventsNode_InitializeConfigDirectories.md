# Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::InitializeConfigDirectories

- ea: `0x49150`
- end: `0x49418`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::InitializeConfigDirectories`
- size: `712`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x46820`

## callees

- `0x1b4c0`
- `0x1b4f0`
- `0x49150`
- `0x4bfb0`
- `0x4cc80`

## string_xrefs

- `0x492e8`: `ViewerConfigPath = '{0}'`
- `0x49307`: `ViewerViewsFolderPath = '{0}'`
- `0x49326`: `ViewerAdminViewsPath = '{0}'`
- `0x49345`: `ViewerExternalLogsPath = '{0}'`
- `0x49379`: `*.xml`
- `0x493ca`: `*.xml`
- `0x493f7`: `*.xml`

## pseudocode

```c

```

## disassembly

```asm
0x49150  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::ViewerConfigPath
0x49155  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4915a  brtrue.s loc_4915D
0x4915c  ret
0x4915d  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x49162  stloc.0
0x49163  ldloc.0
0x49164  ldc.i4.s 0x23
0x49166  call     string [mscorlib]System.Environment::GetFolderPath(valuetype [mscorlib]System.Environment/SpecialFolder)
0x4916b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x49170  pop
0x49171  ldloc.0
0x49172  ldsfld   char [mscorlib]System.IO.Path::DirectorySeparatorChar
0x49177  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x4917c  pop
0x4917d  ldloc.0
0x4917e  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::MicrosoftFolderName
0x49183  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x49188  pop
0x49189  ldloc.0
0x4918a  ldsfld   char [mscorlib]System.IO.Path::DirectorySeparatorChar
0x4918f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x49194  pop
0x49195  ldloc.0
0x49196  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::LIN_EventViewer
0x4919b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x491a0  pop
0x491a1  ldloc.0
0x491a2  callvirt instance string [mscorlib]System.Object::ToString()
0x491a7  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::ViewerConfigPath
0x491ac  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::ViewerConfigPath
0x491b1  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x491b6  brtrue   loc_4927E
0x491bb  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::ViewerConfigPath
0x491c0  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::ViewerViewsFolderPath
0x491c5  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::ViewerConfigPath
0x491ca  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::ViewerAdminViewsPath
0x491cf  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::ViewerConfigPath
0x491d4  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::ViewerExternalLogsPath
0x491d9  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::ViewerConfigPath
0x491de  call     class [mscorlib]System.IO.DirectoryInfo Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::CreateDirectory(string path)
0x491e3  stloc.1
0x491e4  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::ViewerConfigPath
0x491e9  ldsfld   char [mscorlib]System.IO.Path::DirectorySeparatorChar
0x491ee  stloc.2
0x491ef  ldloca.s 2
0x491f1  call     instance string [mscorlib]System.Char::ToString()
0x491f6  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::ExternalLogsFolderName
0x491fb  call     string [mscorlib]System.String::Concat(string, string, string)
0x49200  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::ViewerExternalLogsPath
0x49205  ldloc.1
0x49206  brfalse.s loc_49234
0x49208  ldloc.1
0x49209  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::ViewsFolderName
0x4920e  callvirt instance class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.DirectoryInfo::CreateSubdirectory(string)
0x49213  dup
0x49214  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x49219  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::ViewerViewsFolderPath
0x4921e  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::AdminViewsFolderName
0x49223  callvirt instance class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.DirectoryInfo::CreateSubdirectory(string)
0x49228  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x4922d  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::ViewerAdminViewsPath
0x49232  br.s     loc_49276
0x49234  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::ViewerConfigPath
0x49239  ldsfld   char [mscorlib]System.IO.Path::DirectorySeparatorChar
0x4923e  stloc.3
0x4923f  ldloca.s 3
0x49241  call     instance string [mscorlib]System.Int32::ToString()
0x49246  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::ViewsFolderName
0x4924b  call     string [mscorlib]System.String::Concat(string, string, string)
0x49250  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::ViewerViewsFolderPath
0x49255  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::ViewerConfigPath
0x4925a  ldsfld   char [mscorlib]System.IO.Path::DirectorySeparatorChar
0x4925f  stloc.3
0x49260  ldloca.s 3
0x49262  call     instance string [mscorlib]System.Int32::ToString()
0x49267  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::AdminViewsFolderName
0x4926c  call     string [mscorlib]System.String::Concat(string, string, string)
0x49271  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::ViewerAdminViewsPath
0x49276  leave.s  loc_492E6
0x49278  pop
0x49279  leave.s  loc_492E6
0x4927b  pop
0x4927c  leave.s  loc_492E6
0x4927e  ldloc.0
0x4927f  ldsfld   char [mscorlib]System.IO.Path::DirectorySeparatorChar
0x49284  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x49289  pop
0x4928a  ldloc.0
0x4928b  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::ViewsFolderName
0x49290  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x49295  callvirt instance string [mscorlib]System.Object::ToString()
0x4929a  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::ViewerViewsFolderPath
0x4929f  ldloc.0
0x492a0  ldsfld   char [mscorlib]System.IO.Path::DirectorySeparatorChar
0x492a5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x492aa  pop
0x492ab  ldloc.0
0x492ac  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::AdminViewsFolderName
0x492b1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x492b6  callvirt instance string [mscorlib]System.Object::ToString()
0x492bb  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::ViewerAdminViewsPath
0x492c0  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::ViewerConfigPath
0x492c5  ldsfld   char [mscorlib]System.IO.Path::DirectorySeparatorChar
0x492ca  stloc.2
0x492cb  ldloca.s 2
0x492cd  call     instance string [mscorlib]System.Char::ToString()
0x492d2  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::ExternalLogsFolderName
0x492d7  call     string [mscorlib]System.String::Concat(string, string, string)
0x492dc  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::ViewerExternalLogsPath
0x492e1  call     void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::InitialiePreviewSizeFromConfigFile()
0x492e6  ldarg.0
0x492e7  ldnull
0x492e8  ldstr    aViewerconfigpa// "ViewerConfigPath = '{0}'"
0x492ed  ldc.i4.1
0x492ee  newarr   [mscorlib]System.Object
0x492f3  dup
0x492f4  ldc.i4.0
0x492f5  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::ViewerConfigPath
0x492fa  stelem.ref
0x492fb  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x49300  call     void [System]System.Diagnostics.Trace::WriteLine(object, string)
0x49305  ldarg.0
0x49306  ldnull
0x49307  ldstr    aViewerviewsfol// "ViewerViewsFolderPath = '{0}'"
0x4930c  ldc.i4.1
0x4930d  newarr   [mscorlib]System.Object
0x49312  dup
0x49313  ldc.i4.0
0x49314  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::ViewerViewsFolderPath
0x49319  stelem.ref
0x4931a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4931f  call     void [System]System.Diagnostics.Trace::WriteLine(object, string)
0x49324  ldarg.0
0x49325  ldnull
0x49326  ldstr    aVieweradminvie// "ViewerAdminViewsPath = '{0}'"
0x4932b  ldc.i4.1
0x4932c  newarr   [mscorlib]System.Object
0x49331  dup
0x49332  ldc.i4.0
0x49333  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::ViewerAdminViewsPath
0x49338  stelem.ref
0x49339  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4933e  call     void [System]System.Diagnostics.Trace::WriteLine(object, string)
0x49343  ldarg.0
0x49344  ldnull
0x49345  ldstr    aViewerexternal// "ViewerExternalLogsPath = '{0}'"
0x4934a  ldc.i4.1
0x4934b  newarr   [mscorlib]System.Object
0x49350  dup
0x49351  ldc.i4.0
0x49352  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::ViewerExternalLogsPath
0x49357  stelem.ref
0x49358  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4935d  call     void [System]System.Diagnostics.Trace::WriteLine(object, string)
0x49362  call     bool Microsoft.Windows.ManagementUI.CombinedControls.SnapInFeedback::OptedIn()
0x49367  brfalse  loc_49417
0x4936c  ldc.i4.0
0x4936d  stloc.s  4
0x4936f  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::ViewerViewsFolderPath
0x49374  newobj   instance void [mscorlib]System.IO.DirectoryInfo::.ctor(string)
0x49379  ldstr    aXml_1// "*.xml"
0x4937e  ldc.i4.1
0x4937f  callvirt instance class [mscorlib]System.IO.FileInfo[] [mscorlib]System.IO.DirectoryInfo::GetFiles(string, valuetype [mscorlib]System.IO.SearchOption)
0x49384  stloc.s  7
0x49386  ldc.i4.0
0x49387  stloc.3
0x49388  br.s     loc_493A5
0x4938a  ldloc.s  7
0x4938c  ldloc.3
0x4938d  ldelem.ref
0x4938e  stloc.s  8
0x49390  ldloc.s  8
0x49392  callvirt instance valuetype [mscorlib]System.IO.FileAttributes [mscorlib]System.IO.FileSystemInfo::get_Attributes()
0x49397  ldc.i4.1
0x49398  and
0x49399  brtrue.s loc_493A1
0x4939b  ldloc.s  4
0x4939d  ldc.i4.1
0x4939e  add
0x4939f  stloc.s  4
0x493a1  ldloc.3
0x493a2  ldc.i4.1
0x493a3  add
0x493a4  stloc.3
0x493a5  ldloc.3
0x493a6  ldloc.s  7
0x493a8  ldlen
0x493a9  conv.i4
0x493aa  blt.s    loc_4938A
0x493ac  leave.s  loc_493B1
0x493ae  pop
0x493af  leave.s  loc_493B1
0x493b1  ldc.i4   0xEEB
0x493b6  ldloc.s  4
0x493b8  call     void Microsoft.Windows.ManagementUI.CombinedControls.SnapInFeedback::SetGlobalDatapoint(valuetype Microsoft.Windows.ManagementUI.CombinedControls.FeedbackDatapoint datapoint, unsigned int32 value)
0x493bd  ldc.i4.0
0x493be  stloc.s  5
0x493c0  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::ViewerExternalLogsPath
0x493c5  newobj   instance void [mscorlib]System.IO.DirectoryInfo::.ctor(string)
0x493ca  ldstr    aXml_1// "*.xml"
0x493cf  ldc.i4.1
0x493d0  callvirt instance class [mscorlib]System.IO.FileInfo[] [mscorlib]System.IO.DirectoryInfo::GetFiles(string, valuetype [mscorlib]System.IO.SearchOption)
0x493d5  ldlen
0x493d6  conv.i4
0x493d7  stloc.s  5
0x493d9  leave.s  loc_493DE
0x493db  pop
0x493dc  leave.s  loc_493DE
0x493de  ldc.i4   0xEE1
0x493e3  ldloc.s  5
0x493e5  call     void Microsoft.Windows.ManagementUI.CombinedControls.SnapInFeedback::SetGlobalDatapoint(valuetype Microsoft.Windows.ManagementUI.CombinedControls.FeedbackDatapoint datapoint, unsigned int32 value)
0x493ea  ldc.i4.0
0x493eb  stloc.s  6
0x493ed  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionFilterFileUtil::FilterDirPath
0x493f2  newobj   instance void [mscorlib]System.IO.DirectoryInfo::.ctor(string)
0x493f7  ldstr    aXml_1// "*.xml"
0x493fc  ldc.i4.1
0x493fd  callvirt instance class [mscorlib]System.IO.FileInfo[] [mscorlib]System.IO.DirectoryInfo::GetFiles(string, valuetype [mscorlib]System.IO.SearchOption)
0x49402  ldlen
0x49403  conv.i4
0x49404  stloc.s  6
0x49406  leave.s  loc_4940B
0x49408  pop
0x49409  leave.s  loc_4940B
0x4940b  ldc.i4   0xEE2
0x49410  ldloc.s  6
0x49412  call     void Microsoft.Windows.ManagementUI.CombinedControls.SnapInFeedback::SetGlobalDatapoint(valuetype Microsoft.Windows.ManagementUI.CombinedControls.FeedbackDatapoint datapoint, unsigned int32 value)
0x49417  ret
```
