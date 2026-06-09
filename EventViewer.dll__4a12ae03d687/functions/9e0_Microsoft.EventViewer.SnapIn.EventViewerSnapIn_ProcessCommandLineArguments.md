# Microsoft.EventViewer.SnapIn.EventViewerSnapIn::ProcessCommandLineArguments

- ea: `0x9e0`
- end: `0x1007`
- name: `Microsoft.EventViewer.SnapIn.EventViewerSnapIn::ProcessCommandLineArguments`
- size: `1575`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x5f0`

## callees

- `0x8d0`
- `0x9e0`
- `0x1010`
- `0x1170`
- `0x1a00`
- `0x3050`
- `0x31d0`
- `0x3460`
- `0x3530`
- `0x3d70`
- `0x9120`
- `0xa7b0`
- `0xa970`

## string_xrefs

- `0x9e1`: `ProcessCommandLineArguments`
- `0xffb`: `ProcessCommandLineArguments`
- `0xb0b`: `/COMPUTER:`
- `0xb4a`: `/COMPUTER:`
- `0xb2e`: `-COMPUTER:`
- `0xb8b`: `Computer {0} is not localhost.`
- `0xba9`: `Computer {0} is localhost.`
- `0xbc8`: `Computer {0} is not localhost (or dns failed).`
- `0xe88`: `ProcessCommandLineArguments: Calling AddViewNode`
- `0xf01`: `ProcessCommandLineArguments: AddViewNode failed.`
- `0xf1d`: `ProcessCommandLineArguments: Loading log file {0}.`
- `0xfb1`: `ProcessCommandLineArguments: Got a node to select`
- `0xfca`: `ProcessCommandLineArguments: No node to select`

## pseudocode

```c

```

## disassembly

```asm
0x9e0  ldarg.0
0x9e1  ldstr    aProcesscommand// "ProcessCommandLineArguments"
0x9e6  call     void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.TimeTrace::StartMethod(object, string)
0x9eb  ldsfld   string [mscorlib]System.String::Empty
0x9f0  stloc.0
0x9f1  ldsfld   string [mscorlib]System.String::Empty
0x9f6  stloc.1
0x9f7  ldsfld   string [mscorlib]System.String::Empty
0x9fc  stloc.2
0x9fd  ldsfld   string [mscorlib]System.String::Empty
0xa02  stloc.3
0xa03  ldsfld   string [mscorlib]System.String::Empty
0xa08  stloc.s  4
0xa0a  ldc.i4.0
0xa0b  stloc.s  5
0xa0d  ldc.i4.s 0x25
0xa0f  call     string [mscorlib]System.Environment::GetFolderPath(valuetype [mscorlib]System.Environment/SpecialFolder)
0xa14  ldsfld   char [mscorlib]System.IO.Path::DirectorySeparatorChar
0xa19  stloc.s  7
0xa1b  ldloca.s 7
0xa1d  call     instance string [mscorlib]System.Char::ToString()
0xa22  ldstr    aEventvwrMsc// "eventvwr.msc"
0xa27  call     string [mscorlib]System.String::Concat(string, string, string)
0xa2c  stloc.s  6
0xa2e  call     string[] [mscorlib]System.Environment::GetCommandLineArgs()
0xa33  stloc.s  8
0xa35  ldc.i4.0
0xa36  stloc.s  9
0xa38  br       loc_D02
0xa3d  ldloc.s  8
0xa3f  ldloc.s  9
0xa41  ldelem.ref
0xa42  stloc.s  0xA
0xa44  ldloc.s  0xA
0xa46  ldloc.s  6
0xa48  ldc.i4.5
0xa49  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0xa4e  brtrue.s loc_A57
0xa50  ldarg.0
0xa51  ldc.i4.1
0xa52  stfld    bool Microsoft.EventViewer.SnapIn.EventViewerSnapIn::remoteMachineOverridden
0xa57  ldloc.s  0xA
0xa59  ldstr    aEventvwrMsc// "eventvwr.msc"
0xa5e  ldc.i4.5
0xa5f  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0xa64  brtrue.s loc_A9A
0xa66  ldloc.s  0xA
0xa68  newobj   instance void [mscorlib]System.IO.FileInfo::.ctor(string)
0xa6d  callvirt instance bool [mscorlib]System.IO.FileSystemInfo::get_Exists()
0xa72  brtrue.s loc_A7D
0xa74  ldarg.0
0xa75  ldc.i4.1
0xa76  stfld    bool Microsoft.EventViewer.SnapIn.EventViewerSnapIn::remoteMachineOverridden
0xa7b  br.s     loc_A9A
0xa7d  ldloc.s  0xA
0xa7f  newobj   instance void [mscorlib]System.IO.FileInfo::.ctor(string)
0xa84  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0xa89  ldloc.s  6
0xa8b  ldc.i4.5
0xa8c  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0xa91  brtrue.s loc_A9A
0xa93  ldarg.0
0xa94  ldc.i4.1
0xa95  stfld    bool Microsoft.EventViewer.SnapIn.EventViewerSnapIn::remoteMachineOverridden
0xa9a  ldloc.s  0xA
0xa9c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xaa1  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0xaa6  ldstr    aC// "/c:"
0xaab  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xab0  call     instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0xab5  ldc.i4.0
0xab6  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0xabb  brtrue.s loc_AE0
0xabd  ldloc.s  0xA
0xabf  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xac4  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0xac9  ldstr    aC_0// "-c:"
0xace  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xad3  call     instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0xad8  ldc.i4.0
0xad9  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0xade  brfalse.s loc_AF5
0xae0  ldloc.s  0xA
0xae2  ldstr    aC// "/c:"
0xae7  call     instance int32 [mscorlib]System.String::get_Length()
0xaec  callvirt instance string [mscorlib]System.String::Substring(int32)
0xaf1  stloc.0
0xaf2  ldc.i4.1
0xaf3  stloc.s  5
0xaf5  ldloc.s  0xA
0xaf7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xafc  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0xb01  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xb06  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0xb0b  ldstr    aComputer// "/COMPUTER:"
0xb10  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xb15  call     instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0xb1a  ldc.i4.0
0xb1b  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0xb20  brtrue.s loc_B48
0xb22  ldloc.s  0xA
0xb24  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xb29  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0xb2e  ldstr    aComputer_0// "-COMPUTER:"
0xb33  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xb38  call     instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0xb3d  ldc.i4.0
0xb3e  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0xb43  brfalse  loc_BEB
0xb48  ldloc.s  0xA
0xb4a  ldstr    aComputer// "/COMPUTER:"
0xb4f  call     instance int32 [mscorlib]System.String::get_Length()
0xb54  callvirt instance string [mscorlib]System.String::Substring(int32)
0xb59  stloc.s  0xB
0xb5b  ldsfld   string [mscorlib]System.String::Empty
0xb60  call     class [System]System.Net.IPHostEntry [System]System.Net.Dns::GetHostEntry(string)
0xb65  ldloc.s  0xB
0xb67  call     class [System]System.Net.IPHostEntry [System]System.Net.Dns::GetHostEntry(string)
0xb6c  stloc.s  0xC
0xb6e  callvirt instance string [System]System.Net.IPHostEntry::get_HostName()
0xb73  ldloc.s  0xC
0xb75  callvirt instance string [System]System.Net.IPHostEntry::get_HostName()
0xb7a  ldc.i4.5
0xb7b  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xb80  brtrue.s loc_BA7
0xb82  ldloc.s  0xB
0xb84  stloc.s  4
0xb86  ldc.i4.1
0xb87  stloc.s  5
0xb89  ldarg.0
0xb8a  ldnull
0xb8b  ldstr    aComputer0IsNot// "Computer {0} is not localhost."
0xb90  ldc.i4.1
0xb91  newarr   [mscorlib]System.Object
0xb96  dup
0xb97  ldc.i4.0
0xb98  ldloc.s  0xB
0xb9a  stelem.ref
0xb9b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xba0  call     void [System]System.Diagnostics.Trace::WriteLine(object, string)
0xba5  br.s     loc_BC3
0xba7  ldarg.0
0xba8  ldnull
0xba9  ldstr    aComputer0IsLoc// "Computer {0} is localhost."
0xbae  ldc.i4.1
0xbaf  newarr   [mscorlib]System.Object
0xbb4  dup
0xbb5  ldc.i4.0
0xbb6  ldloc.s  0xB
0xbb8  stelem.ref
0xbb9  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xbbe  call     void [System]System.Diagnostics.Trace::WriteLine(object, string)
0xbc3  leave.s  loc_BEB
0xbc5  pop
0xbc6  ldarg.0
0xbc7  ldnull
0xbc8  ldstr    aComputer0IsNot_0// "Computer {0} is not localhost (or dns f"...
0xbcd  ldc.i4.1
0xbce  newarr   [mscorlib]System.Object
0xbd3  dup
0xbd4  ldc.i4.0
0xbd5  ldloc.s  0xB
0xbd7  stelem.ref
0xbd8  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xbdd  call     void [System]System.Diagnostics.Trace::WriteLine(object, string)
0xbe2  ldloc.s  0xB
0xbe4  stloc.s  4
0xbe6  ldc.i4.1
0xbe7  stloc.s  5
0xbe9  leave.s  loc_BEB
0xbeb  ldloc.s  0xA
0xbed  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xbf2  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0xbf7  ldstr    aL// "/l:"
0xbfc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xc01  call     instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0xc06  ldc.i4.0
0xc07  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0xc0c  brtrue.s loc_C31
0xc0e  ldloc.s  0xA
0xc10  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xc15  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0xc1a  ldstr    aL_0// "-l:"
0xc1f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xc24  call     instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0xc29  ldc.i4.0
0xc2a  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0xc2f  brfalse.s loc_C46
0xc31  ldloc.s  0xA
0xc33  ldstr    aL// "/l:"
0xc38  call     instance int32 [mscorlib]System.String::get_Length()
0xc3d  callvirt instance string [mscorlib]System.String::Substring(int32)
0xc42  stloc.3
0xc43  ldc.i4.1
0xc44  stloc.s  5
0xc46  ldloc.s  0xA
0xc48  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xc4d  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0xc52  ldstr    aF// "/f:"
0xc57  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xc5c  call     instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0xc61  ldc.i4.0
0xc62  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0xc67  brtrue.s loc_C8C
0xc69  ldloc.s  0xA
0xc6b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xc70  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0xc75  ldstr    aF_0// "-f:"
0xc7a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xc7f  call     instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0xc84  ldc.i4.0
0xc85  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0xc8a  brfalse.s loc_CA1
0xc8c  ldloc.s  0xA
0xc8e  ldstr    aF// "/f:"
0xc93  call     instance int32 [mscorlib]System.String::get_Length()
0xc98  callvirt instance string [mscorlib]System.String::Substring(int32)
0xc9d  stloc.1
0xc9e  ldc.i4.1
0xc9f  stloc.s  5
0xca1  ldloc.s  0xA
0xca3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xca8  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0xcad  ldstr    aV// "/v:"
0xcb2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xcb7  call     instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0xcbc  ldc.i4.0
0xcbd  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0xcc2  brtrue.s loc_CE7
0xcc4  ldloc.s  0xA
0xcc6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xccb  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0xcd0  ldstr    aV_0// "-v:"
0xcd5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xcda  call     instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0xcdf  ldc.i4.0
0xce0  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0xce5  brfalse.s loc_CFC
0xce7  ldloc.s  0xA
0xce9  ldstr    aV// "/v:"
0xcee  call     instance int32 [mscorlib]System.String::get_Length()
0xcf3  callvirt instance string [mscorlib]System.String::Substring(int32)
0xcf8  stloc.2
0xcf9  ldc.i4.1
0xcfa  stloc.s  5
0xcfc  ldloc.s  9
0xcfe  ldc.i4.1
0xcff  add
0xd00  stloc.s  9
0xd02  ldloc.s  9
0xd04  ldloc.s  8
0xd06  ldlen
0xd07  conv.i4
0xd08  blt      loc_A3D
0xd0d  ldloc.s  5
0xd0f  brfalse  loc_FD4
0xd14  ldarg.0
0xd15  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapIn::get_RootNode()
0xd1a  castclass Microsoft.EventViewer.SnapIn.MMCRootNode
0xd1f  stloc.s  0xD
0xd21  ldloc.s  4
0xd23  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xd28  brtrue.s loc_D4B
0xd2a  ldarg.0
0xd2b  ldc.i4.1
0xd2c  stfld    bool Microsoft.EventViewer.SnapIn.EventViewerSnapIn::remoteMachineOverridden
0xd31  ldarg.0
0xd32  ldloc.s  4
0xd34  stfld    string Microsoft.EventViewer.SnapIn.EventViewerSnapIn::remoteMachineName
0xd39  ldarg.0
0xd3a  ldc.i4.1
0xd3b  call     instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase::set_IsModified(bool)
0xd40  ldarg.0
0xd41  ldc.i4.1
0xd42  ldc.i4.1
0xd43  call     instance bool Microsoft.EventViewer.SnapIn.EventViewerSnapIn::RefreshViewer(bool expandNodeFlag, bool snapinInitialized)
0xd48  pop
0xd49  br.s     loc_D52
0xd4b  ldloc.s  0xD
0xd4d  callvirt instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::ExpandNode()
0xd52  ldc.i4.0
0xd53  stloc.s  0xE
0xd55  ldnull
0xd56  stloc.s  0xF
0xd58  ldloc.s  0xD
0xd5a  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNodeCollection [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_Children()
0xd5f  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0xd64  ldc.i4.1
0xd65  ble      loc_FD4
0xd6a  ldloc.s  0xD
0xd6c  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNodeCollection [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_Children()
0xd71  ldc.i4.0
0xd72  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNodeCollection::get_Item(int32)
0xd77  castclass Microsoft.EventViewer.SnapIn.ViewerRootNode
0xd7c  stloc.s  0x10
0xd7e  ldloc.1
0xd7f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xd84  brtrue   loc_E2E
0xd89  ldloc.3
0xd8a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
  ... truncated ...
```
