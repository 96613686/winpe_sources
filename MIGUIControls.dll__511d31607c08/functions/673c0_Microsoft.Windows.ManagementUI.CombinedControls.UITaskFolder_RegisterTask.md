# Microsoft.Windows.ManagementUI.CombinedControls.UITaskFolder::RegisterTask

- ea: `0x673c0`
- end: `0x676b3`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.UITaskFolder::RegisterTask`
- size: `755`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x65050`

## callees

- `0x12ed0`
- `0x12f50`
- `0x13440`
- `0x5d760`
- `0x5d840`
- `0x5d9d0`
- `0x5ebb0`
- `0x5ed70`
- `0x5edc0`
- `0x5f170`
- `0x645c0`
- `0x64600`
- `0x64680`
- `0x646e0`
- `0x673c0`
- `0x67bb0`
- `0x67ec0`
- `0x83c20`
- `0x83d30`
- `0xa01b0`

## string_xrefs

- `0x67644`: `ApplicationTaskScheduler`
- `0x67662`: `ApplicationTaskScheduler`
- `0x675a5`: `MessageTaskAccessException`
- `0x675bb`: `MessageTaskAccessEditException`
- `0x67518`: `MessageNeedBatchPrivilege`
- `0x67556`: `MessageTaskCredmanException`
- `0x6756f`: `MessageTaskCredmanEditException`

## pseudocode

```c

```

## disassembly

```asm
0x673c0  ldc.i4.0
0x673c1  stloc.0
0x673c2  ldc.i4.0
0x673c3  stloc.1
0x673c4  ldnull
0x673c5  stloc.2
0x673c6  ldsfld   string [mscorlib]System.String::Empty
0x673cb  stloc.3
0x673cc  ldloca.s 4
0x673ce  initobj  Microsoft.Windows.ManagementUI.CombinedControls.SecureStringVariant
0x673d4  ldarg.s  5
0x673d6  ldnull
0x673d7  stind.ref
0x673d8  ldarg.2
0x673d9  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_User()
0x673de  callvirt instance valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskLogonType Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser::get_UserLogonType()
0x673e3  stloc.1
0x673e4  ldarg.2
0x673e5  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_XmlText()
0x673ea  stloc.3
0x673eb  ldarg.3
0x673ec  brfalse  loc_676B1
0x673f1  ldc.i4.2
0x673f2  stloc.s  5
0x673f4  ldarg.s  4
0x673f6  brtrue.s loc_673FB
0x673f8  ldc.i4.4
0x673f9  stloc.s  5
0x673fb  nop
0x673fc  ldc.i4.0
0x673fd  stloc.s  6
0x673ff  ldc.i4.0
0x67400  stloc.s  7
0x67402  ldc.i4.1
0x67403  ldloc.1
0x67404  beq.s    loc_6740D
0x67406  ldc.i4.6
0x67407  ldloc.1
0x67408  bne.un   loc_67630
0x6740d  ldarg.2
0x6740e  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_User()
0x67413  stloc.s  8
0x67415  ldloc.s  8
0x67417  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser::get_IsGroupManagedServiceAccount()
0x6741c  brtrue   loc_67630
0x67421  ldarg.s  6
0x67423  callvirt instance native int [System.Windows.Forms]System.Windows.Forms.IWin32Window::get_Handle()
0x67428  ldloca.s 8
0x6742a  call     bool CredMan::PromptUserForPassword(native int parentHandle, class Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser& uiUser)
0x6742f  brfalse.s loc_67452
0x67431  ldarg.2
0x67432  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_User()
0x67437  callvirt instance class [mscorlib]System.Security.SecureString Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser::get_EncryptedPassword()
0x6743c  brfalse.s loc_6744A
0x6743e  ldarg.2
0x6743f  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_User()
0x67444  callvirt instance class [mscorlib]System.Security.SecureString Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser::get_EncryptedPassword()
0x67449  stloc.2
0x6744a  ldc.i4.1
0x6744b  stloc.s  6
0x6744d  br       loc_67630
0x67452  ldc.i4.1
0x67453  stloc.s  7
0x67455  br       loc_67630
0x6745a  ldc.i4.0
0x6745b  stloc.s  9
0x6745d  ldnull
0x6745e  stloc.s  0xB
0x67460  ldloca.s 4
0x67462  ldc.i4.0
0x67463  stfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.SecureStringVariant::type
0x67468  ldloca.s 4
0x6746a  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x6746f  stfld    native int Microsoft.Windows.ManagementUI.CombinedControls.SecureStringVariant::StringVal
0x67474  ldloc.2
0x67475  brfalse.s loc_67490
0x67477  ldloca.s 4
0x67479  ldc.i4.8
0x6747a  stfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.SecureStringVariant::type
0x6747f  ldloc.2
0x67480  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::SecureStringToBSTR(class [mscorlib]System.Security.SecureString)
0x67485  stloc.s  0xC
0x67487  ldloca.s 4
0x67489  ldloc.s  0xC
0x6748b  stfld    native int Microsoft.Windows.ManagementUI.CombinedControls.SecureStringVariant::StringVal
0x67490  ldarg.0
0x67491  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ITaskFolder Microsoft.Windows.ManagementUI.CombinedControls.UITaskFolder::secureITaskFolder
0x67496  ldarg.2
0x67497  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_Name()
0x6749c  ldloc.3
0x6749d  ldloc.s  5
0x6749f  ldarg.2
0x674a0  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_User()
0x674a5  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser::get_NameToUse()
0x674aa  ldloc.s  4
0x674ac  ldloc.1
0x674ad  ldnull
0x674ae  ldloca.s 0xB
0x674b0  callvirt instance unsigned int32 Microsoft.Windows.ManagementUI.CombinedControls.ITaskFolder::RegisterTask([in] [hasfieldmarshal] string name, [in] [hasfieldmarshal] string xmlText, valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskCreation flags, [in] [hasfieldmarshal] object userId, [in] [hasfieldmarshal] valuetype Microsoft.Windows.ManagementUI.CombinedControls.SecureStringVariant password, valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskLogonType logonType, [in] [hasfieldmarshal] object sddl, [out] class Microsoft.Windows.ManagementUI.CombinedControls.IRegisteredTask& registeredTask)
0x674b5  stloc.s  0xA
0x674b7  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x674bc  ldloc.s  4
0x674be  ldfld    native int Microsoft.Windows.ManagementUI.CombinedControls.SecureStringVariant::StringVal
0x674c3  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x674c8  brfalse.s loc_674E2
0x674ca  ldloc.s  4
0x674cc  ldfld    native int Microsoft.Windows.ManagementUI.CombinedControls.SecureStringVariant::StringVal
0x674d1  call     void [mscorlib]System.Runtime.InteropServices.Marshal::ZeroFreeBSTR(native int)
0x674d6  ldloca.s 4
0x674d8  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x674dd  stfld    native int Microsoft.Windows.ManagementUI.CombinedControls.SecureStringVariant::StringVal
0x674e2  ldloc.s  0xB
0x674e4  brfalse.s loc_6752E
0x674e6  ldarg.2
0x674e7  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_ActualSecurityDescriptor()
0x674ec  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x674f1  brtrue.s loc_67502
0x674f3  ldloc.s  0xB
0x674f5  ldarg.2
0x674f6  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_ActualSecurityDescriptor()
0x674fb  ldc.i4.s 0x10
0x674fd  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.IRegisteredTask::SetSecurityDescriptor(string sddl, int32 flags)
0x67502  ldc.i4.1
0x67503  stloc.0
0x67504  ldarg.s  5
0x67506  ldloc.s  0xB
0x67508  stind.ref
0x67509  ldc.i4   0x4131C
0x6750e  ldloc.s  0xA
0x67510  bne.un   loc_67637
0x67515  ldarg.0
0x67516  ldarg.s  6
0x67518  ldstr    aMessageneedbat// "MessageNeedBatchPrivilege"
0x6751d  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x67522  ldarg.s  7
0x67524  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::ShowErrorMessage(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string errorMessage, bool showToUser)
0x67529  br       loc_67637
0x6752e  ldc.i4   0x80070005
0x67533  ldloc.s  0xA
0x67535  beq.s    loc_6754C
0x67537  ldc.i4   0x8007052E
0x6753c  ldloc.s  0xA
0x6753e  beq.s    loc_6754C
0x67540  ldc.i4   0x80041314
0x67545  ldloc.s  0xA
0x67547  bne.un   loc_675D3
0x6754c  ldloc.s  6
0x6754e  brfalse.s loc_67585
0x67550  ldarg.1
0x67551  brtrue.s loc_6756C
0x67553  ldarg.0
0x67554  ldarg.s  6
0x67556  ldstr    aMessagetaskcre_0// "MessageTaskCredmanException"
0x6755b  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x67560  ldarg.s  7
0x67562  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::ShowErrorMessage(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string errorMessage, bool showToUser)
0x67567  br       loc_67637
0x6756c  ldarg.0
0x6756d  ldarg.s  6
0x6756f  ldstr    aMessagetaskcre_1// "MessageTaskCredmanEditException"
0x67574  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x67579  ldarg.s  7
0x6757b  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::ShowErrorMessage(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string errorMessage, bool showToUser)
0x67580  br       loc_67637
0x67585  ldarg.0
0x67586  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::get_UITaskService()
0x6758b  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_ComputerName()
0x67590  call     bool Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::CurrentUserIsAdmin(string computerName)
0x67595  brtrue.s loc_675CE
0x67597  ldc.i4.4
0x67598  ldloc.1
0x67599  beq.s    loc_6759F
0x6759b  ldc.i4.5
0x6759c  ldloc.1
0x6759d  bne.un.s loc_675CE
0x6759f  ldarg.1
0x675a0  brtrue.s loc_675B8
0x675a2  ldarg.0
0x675a3  ldarg.s  6
0x675a5  ldstr    aMessagetaskacc// "MessageTaskAccessException"
0x675aa  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x675af  ldarg.s  7
0x675b1  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::ShowErrorMessage(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string errorMessage, bool showToUser)
0x675b6  br.s     loc_67637
0x675b8  ldarg.0
0x675b9  ldarg.s  6
0x675bb  ldstr    aMessagetaskacc_0// "MessageTaskAccessEditException"
0x675c0  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x675c5  ldarg.s  7
0x675c7  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::ShowErrorMessage(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string errorMessage, bool showToUser)
0x675cc  br.s     loc_67637
0x675ce  ldc.i4.1
0x675cf  stloc.s  9
0x675d1  br.s     loc_675F8
0x675d3  ldc.i4   0x80070002
0x675d8  ldloc.s  0xA
0x675da  bne.un.s loc_675E2
0x675dc  newobj   instance void [mscorlib]System.IO.FileNotFoundException::.ctor()
0x675e1  throw
0x675e2  ldarg.0
0x675e3  ldarg.s  6
0x675e5  ldloc.s  0xA
0x675e7  ldarg.s  7
0x675e9  ldc.i4.1
0x675ea  ldarg.2
0x675eb  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_Name()
0x675f0  call     instance bool Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::ProcessExternalErrors(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parentWindow, unsigned int32 errorCode, bool showToUser, bool showUnknownErrorsToUser, string taskName)
0x675f5  pop
0x675f6  br.s     loc_67637
0x675f8  ldloc.s  9
0x675fa  brfalse.s loc_67630
0x675fc  ldarg.2
0x675fd  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_User()
0x67602  stloc.s  0xD
0x67604  ldarg.s  6
0x67606  callvirt instance native int [System.Windows.Forms]System.Windows.Forms.IWin32Window::get_Handle()
0x6760b  ldloca.s 0xD
0x6760d  call     bool CredMan::PromptUserForPassword(native int parentHandle, class Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser& uiUser)
0x67612  brfalse.s loc_67637
0x67614  ldarg.2
0x67615  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_User()
0x6761a  callvirt instance class [mscorlib]System.Security.SecureString Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser::get_EncryptedPassword()
0x6761f  brfalse.s loc_6762D
0x67621  ldarg.2
0x67622  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_User()
0x67627  callvirt instance class [mscorlib]System.Security.SecureString Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser::get_EncryptedPassword()
0x6762c  stloc.2
0x6762d  ldc.i4.1
0x6762e  stloc.s  6
0x67630  ldloc.s  7
0x67632  brfalse  loc_6745A
0x67637  leave.s  loc_676B1
0x67639  stloc.s  0xE
0x6763b  ldarg.s  6
0x6763d  ldloc.s  0xE
0x6763f  callvirt instance string [mscorlib]System.Exception::get_Message()
0x67644  ldstr    aApplicationtas// "ApplicationTaskScheduler"
0x67649  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x6764e  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string errorString, string caption)
0x67653  leave.s  loc_676B1
0x67655  pop
0x67656  ldarg.s  6
0x67658  ldstr    aMessagefoldern// "MessageFolderNotFound"
0x6765d  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x67662  ldstr    aApplicationtas// "ApplicationTaskScheduler"
0x67667  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x6766c  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string errorString, string caption)
0x67671  leave.s  loc_676B1
0x67673  throw
0x67674  stloc.s  0xF
0x67676  ldarg.0
0x67677  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::get_UITaskService()
0x6767c  ldloc.s  0xF
0x6767e  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::ProcessServiceErrors(class [mscorlib]System.Exception e)
0x67683  leave.s  loc_676B1
0x67685  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x6768a  ldloc.s  4
0x6768c  ldfld    native int Microsoft.Windows.ManagementUI.CombinedControls.SecureStringVariant::StringVal
0x67691  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x67696  brfalse.s loc_676B0
0x67698  ldloc.s  4
0x6769a  ldfld    native int Microsoft.Windows.ManagementUI.CombinedControls.SecureStringVariant::StringVal
0x6769f  call     void [mscorlib]System.Runtime.InteropServices.Marshal::ZeroFreeBSTR(native int)
0x676a4  ldloca.s 4
0x676a6  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x676ab  stfld    native int Microsoft.Windows.ManagementUI.CombinedControls.SecureStringVariant::StringVal
0x676b0  endfinally
0x676b1  ldloc.0
0x676b2  ret
```
