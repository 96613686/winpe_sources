# Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::AttachTask

- ea: `0x35480`
- end: `0x3569e`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::AttachTask`
- size: `542`
- prototype: ``
- caller_count: `2`
- callee_count: `36`
- tags: `service_task, broker_com_uri`

## callers

- `0x2c380`
- `0x475e0`

## callees

- `0x12ed0`
- `0x12f00`
- `0x12fe0`
- `0x14ed0`
- `0x14ef0`
- `0x14f10`
- `0x14f70`
- `0x14fb0`
- `0x14fd0`
- `0x14ff0`
- `0x15020`
- `0x15050`
- `0x15060`
- `0x1b4c0`
- `0x1b4d0`
- `0x33aa0`
- `0x35480`
- `0x37920`
- `0x37940`
- `0x37960`
- `0x38840`
- `0x5f840`
- `0x60110`
- `0x645c0`
- `0x64640`
- `0x66e60`
- `0x66e80`
- `0x67020`
- `0x67820`
- `0x67bf0`
- `0x67d70`
- `0x874d0`
- `0x874f0`
- `0x87760`
- `0x877a0`
- `0x87950`

## string_xrefs

- `0x354ca`: `EventViewerTaskFolderName`
- `0x355c3`: `SuccessTaskCreated`
- `0x3568b`: `MessageTaskCreateServiceException`

## pseudocode

```c

```

## disassembly

```asm
0x35480  ldc.i4.0
0x35481  stloc.0
0x35482  ldarg.1
0x35483  brfalse.s loc_354A5
0x35485  ldarg.1
0x35486  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::get_RemoteComputer()
0x3548b  ldarg.1
0x3548c  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::get_UserName()
0x35491  ldarg.1
0x35492  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::get_UserDomain()
0x35497  ldarg.1
0x35498  callvirt instance class [mscorlib]System.Security.SecureString Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::get_EncryptedPassword()
0x3549d  call     class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::CreateUITaskService(string computerName, string user, string domain, class [mscorlib]System.Security.SecureString encryptedPassword)
0x354a2  stloc.1
0x354a3  br.s     loc_354B3
0x354a5  ldsfld   string [mscorlib]System.String::Empty
0x354aa  ldnull
0x354ab  ldnull
0x354ac  ldnull
0x354ad  call     class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::CreateUITaskService(string computerName, string user, string domain, class [mscorlib]System.Security.SecureString encryptedPassword)
0x354b2  stloc.1
0x354b3  ldloc.1
0x354b4  brfalse  loc_35688
0x354b9  ldnull
0x354ba  stloc.2
0x354bb  ldloc.1
0x354bc  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskFolder Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_RootTaskFolder()
0x354c1  stloc.2
0x354c2  ldloc.2
0x354c3  brfalse  loc_35688
0x354c8  ldnull
0x354c9  stloc.3
0x354ca  ldstr    aEventviewertas// "EventViewerTaskFolderName"
0x354cf  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x354d4  stloc.s  4
0x354d6  ldloc.2
0x354d7  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskFolderList Microsoft.Windows.ManagementUI.CombinedControls.UITaskFolder::get_ChildFolderList()
0x354dc  ldloc.s  4
0x354de  callvirt instance int32 Microsoft.Windows.ManagementUI.CombinedControls.UITaskFolderList::GetFolderIndex(string inName)
0x354e3  stloc.s  5
0x354e5  ldloc.s  5
0x354e7  ldc.i4.m1
0x354e8  bne.un.s loc_354F5
0x354ea  ldloc.2
0x354eb  ldloc.s  4
0x354ed  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskFolder Microsoft.Windows.ManagementUI.CombinedControls.UITaskFolder::CreateFolder(string folderName)
0x354f2  stloc.3
0x354f3  br.s     loc_35503
0x354f5  ldloc.2
0x354f6  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskFolderList Microsoft.Windows.ManagementUI.CombinedControls.UITaskFolder::get_ChildFolderList()
0x354fb  ldloc.s  5
0x354fd  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskFolder Microsoft.Windows.ManagementUI.CombinedControls.UITaskFolderList::get_Item(int32 index)
0x35502  stloc.3
0x35503  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::.ctor()
0x35508  stloc.s  6
0x3550a  ldarg.2
0x3550b  brfalse.s loc_3551C
0x3550d  ldloc.s  6
0x3550f  ldloc.3
0x35510  ldarg.s  4
0x35512  ldarg.3
0x35513  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::Initialize(class Microsoft.Windows.ManagementUI.CombinedControls.UITaskFolder folder, string taskName, string subscription)
0x35518  stloc.s  7
0x3551a  br.s     loc_3552E
0x3551c  ldloc.s  6
0x3551e  ldloc.3
0x3551f  ldarg.s  4
0x35521  ldarg.s  5
0x35523  ldarg.s  6
0x35525  ldarg.s  7
0x35527  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::Initialize(class Microsoft.Windows.ManagementUI.CombinedControls.UITaskFolder folder, string taskName, string channel, string eventID, string eventSource)
0x3552c  stloc.s  7
0x3552e  ldloc.s  7
0x35530  brfalse  loc_35688
0x35535  ldloc.s  6
0x35537  ldc.i4.1
0x35538  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::ChildControlDataEntered(bool requiredDataExists)
0x3553d  call     class Microsoft.Windows.ManagementUI.CombinedControls.IUIConsole Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::get_Console()
0x35542  ldloc.s  6
0x35544  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult Microsoft.Windows.ManagementUI.CombinedControls.IUIConsole::ShowDialog(class [System.Windows.Forms]System.Windows.Forms.Form frm)
0x35549  ldc.i4.1
0x3554a  bne.un   loc_35688
0x3554f  ldloc.s  6
0x35551  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::get_CurrentTask()
0x35556  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_Name()
0x3555b  starg.s  4
0x3555d  ldarg.0
0x3555e  brtrue   loc_355EF
0x35563  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::.ctor()
0x35568  stloc.s  8
0x3556a  ldloc.s  8
0x3556c  ldc.i4.0
0x3556d  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Buttons(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxButtons value)
0x35572  ldloc.s  8
0x35574  ldc.i4.s 0x40
0x35576  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Icon(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxIcon value)
0x3557b  ldloc.s  8
0x3557d  ldc.i4.0
0x3557e  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_DefaultButton(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxDefaultButton value)
0x35583  ldloc.s  8
0x35585  call     valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxOptions Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::get_MessageOptions()
0x3558a  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Options(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxOptions value)
0x3558f  ldloc.s  8
0x35591  ldstr    aViewername// "ViewerName"
0x35596  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x3559b  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Caption(string value)
0x355a0  ldloc.s  8
0x355a2  ldc.i4.0
0x355a3  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_ShowHelp(bool value)
0x355a8  ldloc.s  8
0x355aa  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x355af  ldtoken  [mscorlib]System.String
0x355b4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x355b9  callvirt instance object [mscorlib]System.Globalization.CultureInfo::GetFormat(class [mscorlib]System.Type)
0x355be  castclass [mscorlib]System.IFormatProvider
0x355c3  ldstr    aSuccesstaskcre// "SuccessTaskCreated"
0x355c8  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x355cd  ldc.i4.1
0x355ce  newarr   [mscorlib]System.Object
0x355d3  dup
0x355d4  ldc.i4.0
0x355d5  ldarg.s  4
0x355d7  stelem.ref
0x355d8  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x355dd  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Text(string value)
0x355e2  call     class Microsoft.Windows.ManagementUI.CombinedControls.IUIConsole Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::get_Console()
0x355e7  ldloc.s  8
0x355e9  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult Microsoft.Windows.ManagementUI.CombinedControls.IUIConsole::ShowDialog(class Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams msgParams)
0x355ee  pop
0x355ef  call     bool Microsoft.Windows.ManagementUI.CombinedControls.SnapInFeedback::OptedIn()
0x355f4  brfalse  loc_35686
0x355f9  ldloc.s  6
0x355fb  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::get_CurrentTask()
0x35600  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UIActionList Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_ActionList()
0x35605  brfalse.s loc_35686
0x35607  ldloc.s  6
0x35609  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::get_CurrentTask()
0x3560e  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UIActionList Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_ActionList()
0x35613  callvirt instance class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.UIActionList::get_ActionsList()
0x35618  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x3561d  stloc.s  9
0x3561f  br.s     loc_35666
0x35621  ldloc.s  9
0x35623  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x35628  castclass Microsoft.Windows.ManagementUI.CombinedControls.UIAction
0x3562d  callvirt instance valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskActionType Microsoft.Windows.ManagementUI.CombinedControls.UIAction::get_ActionType()
0x35632  stloc.s  0xA
0x35634  ldloc.s  0xA
0x35636  brfalse.s loc_35644
0x35638  ldloc.s  0xA
0x3563a  ldc.i4.6
0x3563b  beq.s    loc_35650
0x3563d  ldloc.s  0xA
0x3563f  ldc.i4.7
0x35640  beq.s    loc_3565C
0x35642  br.s     loc_35666
0x35644  ldc.i4   0x13D8
0x35649  call     void Microsoft.Windows.ManagementUI.CombinedControls.SnapInFeedback::IncrementGlobalDatapoint(valuetype Microsoft.Windows.ManagementUI.CombinedControls.FeedbackDatapoint datapoint)
0x3564e  br.s     loc_35666
0x35650  ldc.i4   0x13D9
0x35655  call     void Microsoft.Windows.ManagementUI.CombinedControls.SnapInFeedback::IncrementGlobalDatapoint(valuetype Microsoft.Windows.ManagementUI.CombinedControls.FeedbackDatapoint datapoint)
0x3565a  br.s     loc_35666
0x3565c  ldc.i4   0x13DA
0x35661  call     void Microsoft.Windows.ManagementUI.CombinedControls.SnapInFeedback::IncrementGlobalDatapoint(valuetype Microsoft.Windows.ManagementUI.CombinedControls.FeedbackDatapoint datapoint)
0x35666  ldloc.s  9
0x35668  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x3566d  brtrue.s loc_35621
0x3566f  leave.s  loc_35686
0x35671  ldloc.s  9
0x35673  isinst   [mscorlib]System.IDisposable
0x35678  stloc.s  0xB
0x3567a  ldloc.s  0xB
0x3567c  brfalse.s loc_35685
0x3567e  ldloc.s  0xB
0x35680  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x35685  endfinally
0x35686  ldc.i4.1
0x35687  stloc.0
0x35688  leave.s  loc_3569C
0x3568a  pop
0x3568b  ldstr    aMessagetaskcre// "MessageTaskCreateServiceException"
0x35690  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x35695  call     void Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::ShowErrorMessageBox(string message)
0x3569a  leave.s  loc_3569C
0x3569c  ldloc.0
0x3569d  ret
```
