# Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::AddSubNodes

- ea: `0x4b420`
- end: `0x4b849`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::AddSubNodes`
- size: `1065`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `broker_com_uri`

## callers

- `0x4bc80`

## callees

- `0x120f0`
- `0x12140`
- `0x12ed0`
- `0x13510`
- `0x14da0`
- `0x14db0`
- `0x14de0`
- `0x14e00`
- `0x14e30`
- `0x1afd0`
- `0x37e80`
- `0x46080`
- `0x46550`
- `0x46590`
- `0x46610`
- `0x46880`
- `0x46dd0`
- `0x4b420`
- `0x4b850`
- `0x4b890`
- `0x4b9f0`
- `0x4c730`
- `0x4c8f0`
- `0x4ca30`

## string_xrefs

- `0x4b531`: ` from NativeMethods.SHCreateItemFromParsingName`

## pseudocode

```c

```

## disassembly

```asm
0x4b420  ldc.i4.0
0x4b421  stloc.0
0x4b422  ldarg.2
0x4b423  ldc.i4.5
0x4b424  beq.s    loc_4B42A
0x4b426  ldc.i4.s 0xA
0x4b428  br.s     loc_4B42C
0x4b42a  ldc.i4.s 0xC
0x4b42c  stloc.1
0x4b42d  ldc.i4   0x1F4
0x4b432  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0x4b437  stloc.2
0x4b438  ldc.i4.0
0x4b439  stloc.3
0x4b43a  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x4b43f  stloc.s  4
0x4b441  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x4b446  stloc.s  5
0x4b448  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.IShellItem
0x4b44d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4b452  callvirt instance valuetype [mscorlib]System.Guid [mscorlib]System.Type::get_GUID()
0x4b457  stloc.s  6
0x4b459  ldc.i4   0x1F4
0x4b45e  stloc.s  7
0x4b460  ldc.i4.m1
0x4b461  stloc.s  8
0x4b463  ldarg.1
0x4b464  callvirt instance bool [mscorlib]System.IO.FileSystemInfo::get_Exists()
0x4b469  brfalse  loc_4B848
0x4b46e  ldc.i4.m1
0x4b46f  stloc.s  8
0x4b471  ldc.i4   0x1F4
0x4b476  stloc.s  7
0x4b478  ldsfld   string [mscorlib]System.String::Empty
0x4b47d  stloc.s  0xA
0x4b47f  ldarg.1
0x4b480  callvirt instance class [mscorlib]System.IO.DirectoryInfo[] [mscorlib]System.IO.DirectoryInfo::GetDirectories()
0x4b485  stloc.s  0xC
0x4b487  ldc.i4.0
0x4b488  stloc.s  0xD
0x4b48a  br       loc_4B673
0x4b48f  ldloc.s  0xC
0x4b491  ldloc.s  0xD
0x4b493  ldelem.ref
0x4b494  stloc.s  0xE
0x4b496  ldloc.s  0xE
0x4b498  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x4b49d  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::ViewerAdminViewsPath
0x4b4a2  ldc.i4.5
0x4b4a3  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x4b4a8  brfalse  loc_4B662
0x4b4ad  ldloc.s  0xE
0x4b4af  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x4b4b4  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::ViewerAdminViewsPath
0x4b4b9  call     string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::GetUsersConfigDirectoryForGivenAllUserPath(string path)
0x4b4be  ldc.i4.5
0x4b4bf  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x4b4c4  brfalse  loc_4B662
0x4b4c9  ldarg.0
0x4b4ca  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.IItemsDictionary Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::get_SubNode()
0x4b4cf  ldloc.s  0xE
0x4b4d1  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_Name()
0x4b4d6  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x4b4db  brfalse.s loc_4B4FD
0x4b4dd  ldarg.0
0x4b4de  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.IItemsDictionary Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::get_SubNode()
0x4b4e3  ldloc.s  0xE
0x4b4e5  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_Name()
0x4b4ea  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x4b4ef  castclass Microsoft.Windows.ManagementUI.CombinedControls.EventsNode
0x4b4f4  stloc.s  0xF
0x4b4f6  ldc.i4.1
0x4b4f7  stloc.0
0x4b4f8  br       loc_4B657
0x4b4fd  ldsfld   string [mscorlib]System.String::Empty
0x4b502  stloc.s  0xA
0x4b504  ldloc.s  0xE
0x4b506  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x4b50b  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x4b510  ldloca.s 6
0x4b512  ldloca.s 5
0x4b514  call     int32 Microsoft.Windows.ManagementUI.CombinedControls.NativeMethods::SHCreateItemFromParsingName([hasfieldmarshal] string path, native int bindCtx, valuetype [mscorlib]System.Guid& riid, [out] native int& ptrOut)
0x4b519  stloc.3
0x4b51a  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x4b51f  stloc.s  9
0x4b521  ldloc.s  9
0x4b523  brfalse.s loc_4B540
0x4b525  ldstr    aWin32Error// "Win32 error #: "
0x4b52a  ldloca.s 9
0x4b52c  call     instance string [mscorlib]System.Int32::ToString()
0x4b531  ldstr    aFromNativemeth_0// " from NativeMethods.SHCreateItemFromPar"...
0x4b536  call     string [mscorlib]System.String::Concat(string, string, string)
0x4b53b  call     void [System]System.Diagnostics.Trace::WriteLine(string)
0x4b540  ldloc.3
0x4b541  brfalse.s loc_4B550
0x4b543  ldstr    aUnableToGetThe_0// "Unable to get the locallized name for f"...
0x4b548  ldloc.3
0x4b549  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x4b54e  br.s     loc_4B59C
0x4b550  ldloc.s  5
0x4b552  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x4b557  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x4b55c  brfalse.s loc_4B59C
0x4b55e  ldloc.s  5
0x4b560  call     object [mscorlib]System.Runtime.InteropServices.Marshal::GetObjectForIUnknown(native int)
0x4b565  castclass Microsoft.Windows.ManagementUI.CombinedControls.IShellItem
0x4b56a  stloc.s  0x10
0x4b56c  ldloc.s  0x10
0x4b56e  brfalse.s loc_4B599
0x4b570  ldloc.s  0x10
0x4b572  ldc.i4.0
0x4b573  ldloca.s 4
0x4b575  callvirt instance int32 Microsoft.Windows.ManagementUI.CombinedControls.IShellItem::GetDisplayName([hasfieldmarshal] valuetype Microsoft.Windows.ManagementUI.CombinedControls.SIGDN sigdnName, [out] native int& strPtr)
0x4b57a  stloc.3
0x4b57b  ldloc.s  4
0x4b57d  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x4b582  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x4b587  brfalse.s loc_4B599
0x4b589  ldloc.s  4
0x4b58b  call     string [mscorlib]System.Runtime.InteropServices.Marshal::PtrToStringUni(native int)
0x4b590  stloc.s  0xA
0x4b592  ldloc.s  4
0x4b594  call     void [mscorlib]System.Runtime.InteropServices.Marshal::FreeCoTaskMem(native int)
0x4b599  ldnull
0x4b59a  stloc.s  0x10
0x4b59c  ldloc.s  0xA
0x4b59e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4b5a3  brfalse.s loc_4B5ED
0x4b5a5  ldloc.s  0xE
0x4b5a7  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_Name()
0x4b5ac  stloc.s  0xA
0x4b5ae  ldloc.s  0xE
0x4b5b0  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x4b5b5  ldloc.2
0x4b5b6  ldloc.s  7
0x4b5b8  ldloca.s 8
0x4b5ba  call     int32 Microsoft.Windows.ManagementUI.CombinedControls.NativeMethods::SHGetLocalizedName([hasfieldmarshal] string path, [out] [hasfieldmarshal] class [mscorlib]System.Text.StringBuilder moduleName, int32 len, int32& resourceIdentifier)
0x4b5bf  stloc.3
0x4b5c0  ldloc.3
0x4b5c1  brfalse.s loc_4B5D9
0x4b5c3  ldstr    aGetlocalizedna// "GetLocalizedName"
0x4b5c8  ldloc.3
0x4b5c9  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x4b5ce  ldloc.s  0xE
0x4b5d0  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_Name()
0x4b5d5  stloc.s  0xA
0x4b5d7  br.s     loc_4B5ED
0x4b5d9  ldarg.0
0x4b5da  ldloc.2
0x4b5db  callvirt instance string [mscorlib]System.Object::ToString()
0x4b5e0  stfld    string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::locallizedDllName
0x4b5e5  ldarg.0
0x4b5e6  ldloc.s  8
0x4b5e8  stfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::nameResId
0x4b5ed  ldloc.1
0x4b5ee  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::.ctor(valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventNodeType type)
0x4b5f3  stloc.s  0xF
0x4b5f5  ldloc.s  0xF
0x4b5f7  ldc.i4.1
0x4b5f8  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::set_CanDelete(bool value)
0x4b5fd  ldloc.s  0xF
0x4b5ff  ldloc.s  0xE
0x4b601  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_Name()
0x4b606  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::set_LanguageNeutralName(string value)
0x4b60b  ldloc.s  0xF
0x4b60d  ldloc.s  0xA
0x4b60f  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::set_LocalizedName(string value)
0x4b614  ldloc.s  0xF
0x4b616  ldloc.s  0xE
0x4b618  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x4b61d  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::set_LogFilePath(string value)
0x4b622  ldloc.s  0xF
0x4b624  ldarg.0
0x4b625  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::set_ParentNode(class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode value)
0x4b62a  ldloc.s  0xF
0x4b62c  ldloc.s  0xE
0x4b62e  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x4b633  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::set_NodePathForConfig(string value)
0x4b638  ldc.i4.0
0x4b639  stloc.0
0x4b63a  ldloc.s  5
0x4b63c  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x4b641  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x4b646  brfalse.s loc_4B657
0x4b648  ldloc.s  5
0x4b64a  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::Release(native int)
0x4b64f  pop
0x4b650  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x4b655  stloc.s  5
0x4b657  ldloc.0
0x4b658  brtrue.s loc_4B662
0x4b65a  ldarg.0
0x4b65b  ldloca.s 0xF
0x4b65d  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::AddChildNode(class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode& node)
0x4b662  ldc.i4   0x1F4
0x4b667  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0x4b66c  stloc.2
0x4b66d  ldloc.s  0xD
0x4b66f  ldc.i4.1
0x4b670  add
0x4b671  stloc.s  0xD
0x4b673  ldloc.s  0xD
0x4b675  ldloc.s  0xC
0x4b677  ldlen
0x4b678  conv.i4
0x4b679  blt      loc_4B48F
0x4b67e  ldarg.s  4
0x4b680  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4b685  brtrue.s loc_4B690
0x4b687  ldarg.0
0x4b688  ldarg.s  4
0x4b68a  ldc.i4.1
0x4b68b  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::AddQueryNodeFromXmlString(string xmlString, bool isBuiltInView)
0x4b690  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x4b695  stloc.s  0xB
0x4b697  ldarg.1
0x4b698  callvirt instance class [mscorlib]System.IO.FileInfo[] [mscorlib]System.IO.DirectoryInfo::GetFiles()
0x4b69d  stloc.s  0x11
0x4b69f  ldc.i4.0
0x4b6a0  stloc.s  0xD
0x4b6a2  br       loc_4B7FE
0x4b6a7  ldloc.s  0x11
0x4b6a9  ldloc.s  0xD
0x4b6ab  ldelem.ref
0x4b6ac  stloc.s  0x12
0x4b6ae  ldloc.s  0x12
0x4b6b0  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x4b6b5  call     string [mscorlib]System.IO.Path::GetExtension(string)
0x4b6ba  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::ViewerConfigExtension
0x4b6bf  ldc.i4.5
0x4b6c0  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x4b6c5  brtrue   loc_4B7F8
0x4b6ca  ldarg.2
0x4b6cb  ldc.i4.5
0x4b6cc  bne.un   loc_4B75D
0x4b6d1  ldc.i4.6
0x4b6d2  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::.ctor(valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventNodeType type)
0x4b6d7  stloc.s  0x13
0x4b6d9  ldloc.s  0x13
0x4b6db  ldloc.s  0x12
0x4b6dd  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::InitializeExteralLogNode(class [mscorlib]System.IO.FileInfo fileInfo)
0x4b6e2  ldloc.s  0x13
0x4b6e4  ldarg.0
0x4b6e5  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::set_ParentNode(class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode value)
0x4b6ea  ldloc.s  0x13
0x4b6ec  ldarg.3
0x4b6ed  ldc.i4.0
0x4b6ee  ceq
0x4b6f0  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::set_AllUserQuery(bool value)
0x4b6f5  ldarg.3
0x4b6f6  brfalse.s loc_4B74E
0x4b6f8  ldarg.0
0x4b6f9  ldloc.s  0x13
0x4b6fb  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::get_Name()
0x4b700  call     instance bool Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::IsDuplicateNode(string newNodeName)
0x4b705  brfalse.s loc_4B74E
0x4b707  ldloc.s  0x13
0x4b709  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4b70e  ldtoken  [mscorlib]System.String
0x4b713  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4b718  callvirt instance object [mscorlib]System.Globalization.CultureInfo::GetFormat(class [mscorlib]System.Type)
0x4b71d  castclass [mscorlib]System.IFormatProvider
0x4b722  ldstr    aModifiednodena// "ModifiedNodeName"
0x4b727  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x4b72c  ldc.i4.2
0x4b72d  newarr   [mscorlib]System.Object
0x4b732  dup
0x4b733  ldc.i4.0
0x4b734  ldloc.s  0x13
0x4b736  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::get_Name()
0x4b73b  stelem.ref
0x4b73c  dup
0x4b73d  ldc.i4.1
0x4b73e  call     string Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::get_CurrentUser()
0x4b743  stelem.ref
0x4b744  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4b749  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::set_Name(string value)
0x4b74e  ldloc.s  0xB
0x4b750  ldloc.s  0x13
0x4b752  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x4b757  pop
0x4b758  br       loc_4B7F8
0x4b75d  ldc.i4.s 9
0x4b75f  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::.ctor(valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventNodeType type)
0x4b764  stloc.s  0x14
0x4b766  ldloc.s  0x14
0x4b768  ldloc.s  0x12
0x4b76a  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::InitializeQueryNode(class [mscorlib]System.IO.FileInfo fileInfo)
0x4b76f  brfalse  loc_4B7F8
0x4b774  ldloc.s  0x14
0x4b776  ldarg.0
0x4b777  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::set_ParentNode(class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode value)
0x4b77c  ldloc.s  0x14
0x4b77e  ldloc.s  0x12
0x4b780  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x4b785  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::set_LogFilePath(string value)
0x4b78a  ldloc.s  0x14
0x4b78c  ldarg.3
0x4b78d  ldc.i4.0
0x4b78e  ceq
  ... truncated ...
```
