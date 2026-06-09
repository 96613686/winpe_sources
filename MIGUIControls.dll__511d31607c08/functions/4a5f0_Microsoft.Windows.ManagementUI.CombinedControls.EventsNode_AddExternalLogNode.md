# Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::AddExternalLogNode

- ea: `0x4a5f0`
- end: `0x4a7f6`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::AddExternalLogNode`
- size: `518`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `broker_com_uri`

## callees

- `0x12ed0`
- `0x13440`
- `0x14db0`
- `0x14e30`
- `0x33aa0`
- `0x37e70`
- `0x46530`
- `0x46600`
- `0x46610`
- `0x46620`
- `0x46880`
- `0x4a5f0`
- `0x4a800`
- `0x4a8e0`
- `0x4b3d0`
- `0x4c8f0`
- `0x4d630`
- `0x4dca0`
- `0x53a10`
- `0x53fd0`
- `0x54110`

## string_xrefs

- `0x4a7c2`: `Invalid File name/file path`
- `0x4a7dc`: `Invalid File name/file path`

## pseudocode

```c

```

## disassembly

```asm
0x4a5f0  ldnull
0x4a5f1  stloc.0
0x4a5f2  ldarg.0
0x4a5f3  ldloca.s 0
0x4a5f5  call     void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::GetExternalLogRootNode(class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode nd, [out] class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode& logRootNode)
0x4a5fa  ldnull
0x4a5fb  stloc.1
0x4a5fc  ldc.i4.0
0x4a5fd  stloc.2
0x4a5fe  ldc.i4.0
0x4a5ff  stloc.3
0x4a600  ldarg.1
0x4a601  call     bool [mscorlib]System.IO.File::Exists(string)
0x4a606  brtrue.s loc_4A641
0x4a608  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4a60d  ldtoken  [mscorlib]System.String
0x4a612  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4a617  callvirt instance object [mscorlib]System.Globalization.CultureInfo::GetFormat(class [mscorlib]System.Type)
0x4a61c  castclass [mscorlib]System.IFormatProvider
0x4a621  ldstr    aFilenotexister// "FileNotExistError"
0x4a626  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x4a62b  ldc.i4.1
0x4a62c  newarr   [mscorlib]System.Object
0x4a631  dup
0x4a632  ldc.i4.0
0x4a633  ldarg.1
0x4a634  stelem.ref
0x4a635  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4a63a  call     void Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::ShowErrorMessageBox(string message)
0x4a63f  ldloc.3
0x4a640  ret
0x4a641  ldloc.0
0x4a642  brtrue.s loc_4A64D
0x4a644  ldc.i4.1
0x4a645  stloc.2
0x4a646  ldc.i4.5
0x4a647  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::.ctor(valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventNodeType type)
0x4a64c  stloc.0
0x4a64d  nop
0x4a64e  ldarg.3
0x4a64f  ldloc.0
0x4a650  ldarg.1
0x4a651  ldsfld   string [mscorlib]System.String::Empty
0x4a656  ldsfld   string [mscorlib]System.String::Empty
0x4a65b  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::GetChildNode(string channel, string query, string name)
0x4a660  stind.ref
0x4a661  ldarg.3
0x4a662  ldind.ref
0x4a663  brtrue   loc_4A708
0x4a668  ldarg.1
0x4a669  call     string [mscorlib]System.IO.Path::GetFileNameWithoutExtension(string)
0x4a66e  stloc.s  4
0x4a670  ldloc.s  4
0x4a672  stloc.s  5
0x4a674  ldc.i4.0
0x4a675  stloc.s  6
0x4a677  br.s     loc_4A6D2
0x4a679  ldloc.s  6
0x4a67b  ldc.i4.1
0x4a67c  add
0x4a67d  stloc.s  6
0x4a67f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4a684  ldtoken  [mscorlib]System.String
0x4a689  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4a68e  callvirt instance object [mscorlib]System.Globalization.CultureInfo::GetFormat(class [mscorlib]System.Type)
0x4a693  castclass [mscorlib]System.IFormatProvider
0x4a698  ldstr    a01_1// "{0}_{1}"
0x4a69d  ldc.i4.2
0x4a69e  newarr   [mscorlib]System.Object
0x4a6a3  dup
0x4a6a4  ldc.i4.0
0x4a6a5  ldloc.s  4
0x4a6a7  stelem.ref
0x4a6a8  dup
0x4a6a9  ldc.i4.1
0x4a6aa  ldloca.s 6
0x4a6ac  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4a6b1  ldtoken  [mscorlib]System.Int32
0x4a6b6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4a6bb  callvirt instance object [mscorlib]System.Globalization.CultureInfo::GetFormat(class [mscorlib]System.Type)
0x4a6c0  castclass [mscorlib]System.IFormatProvider
0x4a6c5  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x4a6ca  stelem.ref
0x4a6cb  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4a6d0  stloc.s  5
0x4a6d2  ldloc.0
0x4a6d3  ldloc.s  5
0x4a6d5  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::IsDuplicateNode(string newNodeName)
0x4a6da  brtrue.s loc_4A679
0x4a6dc  ldloc.0
0x4a6dd  ldarg.1
0x4a6de  ldloc.s  5
0x4a6e0  ldsfld   string [mscorlib]System.String::Empty
0x4a6e5  call     bool Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::get_HasWritePermissionToAllUsers()
0x4a6ea  ldsfld   string [mscorlib]System.String::Empty
0x4a6ef  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::AddExternalLogNode(string filePath, string name, string nodePath, bool allUsersExternalLog, string description)
0x4a6f4  ldloc.0
0x4a6f5  ldarg.1
0x4a6f6  ldsfld   string [mscorlib]System.String::Empty
0x4a6fb  ldsfld   string [mscorlib]System.String::Empty
0x4a700  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::GetChildNode(string channel, string query, string name)
0x4a705  stloc.1
0x4a706  br.s     loc_4A70B
0x4a708  ldarg.3
0x4a709  ldind.ref
0x4a70a  stloc.1
0x4a70b  ldarg.2
0x4a70c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4a711  brtrue.s loc_4A778
0x4a713  ldarg.2
0x4a714  ldstr    asc_AB580// "*"
0x4a719  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4a71e  brtrue.s loc_4A778
0x4a720  ldloc.1
0x4a721  brfalse.s loc_4A778
0x4a723  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig::.ctor()
0x4a728  stloc.s  7
0x4a72a  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.EventQuery::.ctor()
0x4a72f  stloc.s  8
0x4a731  ldarg.1
0x4a732  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x4a737  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::ExternalFilePrefix
0x4a73c  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x4a741  ldc.i4.0
0x4a742  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x4a747  brtrue.s loc_4A756
0x4a749  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::ExternalFilePrefix
0x4a74e  ldarg.1
0x4a74f  call     string [mscorlib]System.String::Concat(string, string)
0x4a754  starg.s  1
0x4a756  ldloc.s  8
0x4a758  ldarg.1
0x4a759  ldarg.2
0x4a75a  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventQuery::AddSelector(string path, string selector)
0x4a75f  ldloc.s  7
0x4a761  ldloc.s  8
0x4a763  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig::set_Query(class Microsoft.Windows.ManagementUI.CombinedControls.EventQuery value)
0x4a768  ldloc.s  7
0x4a76a  ldc.i4.1
0x4a76b  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig::set_UserQuery(bool value)
0x4a770  ldloc.1
0x4a771  ldloc.s  7
0x4a773  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::set_Filter(class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig value)
0x4a778  ldloc.2
0x4a779  brfalse.s loc_4A7BC
0x4a77b  ldloc.0
0x4a77c  ldc.i4.3
0x4a77d  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::set_NodeState(valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventNodeState value)
0x4a782  ldarg.0
0x4a783  stloc.s  9
0x4a785  br.s     loc_4A790
0x4a787  ldloc.s  9
0x4a789  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_ParentNode()
0x4a78e  stloc.s  9
0x4a790  ldloc.s  9
0x4a792  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_ParentNode()
0x4a797  brtrue.s loc_4A787
0x4a799  ldloc.0
0x4a79a  ldloc.s  9
0x4a79c  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::set_ParentNode(class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode value)
0x4a7a1  ldloc.s  9
0x4a7a3  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.IItemsDictionary Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::get_SubNode()
0x4a7a8  ldloc.0
0x4a7a9  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::get_Name()
0x4a7ae  ldloc.0
0x4a7af  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x4a7b4  ldloc.s  9
0x4a7b6  ldc.i4.1
0x4a7b7  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::set_NodeState(valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventNodeState value)
0x4a7bc  ldc.i4.1
0x4a7bd  stloc.3
0x4a7be  leave.s  loc_4A7F4
0x4a7c0  pop
0x4a7c1  ldnull
0x4a7c2  ldstr    aInvalidFileNam// "Invalid File name/file path"
0x4a7c7  ldstr    aViewername// "ViewerName"
0x4a7cc  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x4a7d1  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string errorString, string caption)
0x4a7d6  ldc.i4.0
0x4a7d7  stloc.3
0x4a7d8  leave.s  loc_4A7F4
0x4a7da  pop
0x4a7db  ldnull
0x4a7dc  ldstr    aInvalidFileNam// "Invalid File name/file path"
0x4a7e1  ldstr    aViewername// "ViewerName"
0x4a7e6  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x4a7eb  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string errorString, string caption)
0x4a7f0  ldc.i4.0
0x4a7f1  stloc.3
0x4a7f2  leave.s  loc_4A7F4
0x4a7f4  ldloc.3
0x4a7f5  ret
```
