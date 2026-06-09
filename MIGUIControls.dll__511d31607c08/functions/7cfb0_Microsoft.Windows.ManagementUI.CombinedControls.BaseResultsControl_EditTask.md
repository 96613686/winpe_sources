# Microsoft.Windows.ManagementUI.CombinedControls.BaseResultsControl::EditTask

- ea: `0x7cfb0`
- end: `0x7d0a6`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.BaseResultsControl::EditTask`
- size: `246`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x817c0`

## callees

- `0x12ed0`
- `0x13000`
- `0x5d760`
- `0x67010`
- `0x67bb0`
- `0x6bca0`
- `0x6bd00`
- `0x6bd20`
- `0x6c000`
- `0x7ce50`
- `0x7cf40`
- `0x7cfb0`

## string_xrefs

- `0x7d028`: `LocalComputer`
- `0x7d04d`: `TitleModifyTask`

## pseudocode

```c

```

## disassembly

```asm
0x7cfb0  ldnull
0x7cfb1  stloc.0
0x7cfb2  ldarg.1
0x7cfb3  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UITaskFolder::get_Path()
0x7cfb8  stloc.1
0x7cfb9  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.UITaskFolder::RootFolder
0x7cfbe  ldarg.1
0x7cfbf  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UITaskFolder::get_Path()
0x7cfc4  ldc.i4.1
0x7cfc5  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x7cfca  brtrue.s loc_7CFE0
0x7cfcc  ldloc.1
0x7cfcd  ldsfld   char [mscorlib]System.IO.Path::DirectorySeparatorChar
0x7cfd2  stloc.3
0x7cfd3  ldloca.s 3
0x7cfd5  call     instance string [mscorlib]System.Char::ToString()
0x7cfda  call     string [mscorlib]System.String::Concat(string, string)
0x7cfdf  stloc.1
0x7cfe0  ldloc.1
0x7cfe1  ldarg.2
0x7cfe2  call     string [mscorlib]System.String::Concat(string, string)
0x7cfe7  stloc.1
0x7cfe8  ldarg.1
0x7cfe9  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::get_UITaskService()
0x7cfee  stloc.0
0x7cfef  ldloc.0
0x7cff0  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_ComputerName()
0x7cff5  ldloc.1
0x7cff6  call     class Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::GetDialog(string systemName, string taskPath)
0x7cffb  stloc.2
0x7cffc  ldloc.2
0x7cffd  brtrue   loc_7D09F
0x7d002  ldloc.0
0x7d003  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_ComputerName()
0x7d008  stloc.s  4
0x7d00a  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::.ctor()
0x7d00f  stloc.2
0x7d010  ldloc.s  4
0x7d012  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x7d017  brtrue.s loc_7D028
0x7d019  ldloc.s  4
0x7d01b  ldstr    asc_A98C0// "."
0x7d020  ldc.i4.5
0x7d021  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x7d026  brfalse.s loc_7D034
0x7d028  ldstr    aLocalcomputer// "LocalComputer"
0x7d02d  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7d032  stloc.s  4
0x7d034  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x7d039  ldtoken  [mscorlib]System.String
0x7d03e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7d043  callvirt instance object [mscorlib]System.Globalization.CultureInfo::GetFormat(class [mscorlib]System.Type)
0x7d048  castclass [mscorlib]System.IFormatProvider
0x7d04d  ldstr    aTitlemodifytas// "TitleModifyTask"
0x7d052  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7d057  ldc.i4.2
0x7d058  newarr   [mscorlib]System.Object
0x7d05d  dup
0x7d05e  ldc.i4.0
0x7d05f  ldarg.2
0x7d060  stelem.ref
0x7d061  dup
0x7d062  ldc.i4.1
0x7d063  ldloc.s  4
0x7d065  stelem.ref
0x7d066  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x7d06b  stloc.s  5
0x7d06d  ldloc.2
0x7d06e  ldarg.1
0x7d06f  ldarg.2
0x7d070  ldloc.s  5
0x7d072  ldc.i4.1
0x7d073  ldarg.0
0x7d074  ldnull
0x7d075  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::Initialize(class Microsoft.Windows.ManagementUI.CombinedControls.UITaskFolder folder, string taskName, string title, valuetype UserChoice userAction, class Microsoft.Windows.ManagementUI.CombinedControls.BaseResultsControl inOwnerView, string inXmlText)
0x7d07a  stloc.s  6
0x7d07c  ldloc.s  6
0x7d07e  brtrue.s loc_7D08A
0x7d080  ldarg.0
0x7d081  ldc.i4.0
0x7d082  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.BaseResultsControl::RefreshData(bool firstTime)
0x7d087  pop
0x7d088  br.s     loc_7D094
0x7d08a  ldloc.s  6
0x7d08c  brfalse.s loc_7D094
0x7d08e  ldloc.2
0x7d08f  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::ShowModelessDialog(class [System.Windows.Forms]System.Windows.Forms.Form dialog)
0x7d094  leave.s  loc_7D0A5
0x7d096  pop
0x7d097  ldarg.0
0x7d098  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.BaseResultsControl::HandleServiceUnavailableException()
0x7d09d  leave.s  loc_7D0A5
0x7d09f  ldloc.2
0x7d0a0  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::BringChildOrSelfToFront()
0x7d0a5  ret
```
