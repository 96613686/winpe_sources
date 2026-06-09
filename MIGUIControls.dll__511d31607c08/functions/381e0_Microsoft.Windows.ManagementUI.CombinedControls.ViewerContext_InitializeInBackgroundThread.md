# Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::InitializeInBackgroundThread

- ea: `0x381e0`
- end: `0x3853d`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::InitializeInBackgroundThread`
- size: `861`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `broker_com_uri`

## callees

- `0x12110`
- `0x12800`
- `0x12830`
- `0x12cc0`
- `0x12ed0`
- `0x13510`
- `0x1b6a0`
- `0x1b710`
- `0x1b7a0`
- `0x1b7f0`
- `0x1b850`
- `0x1b920`
- `0x1cd50`
- `0x1ce20`
- `0x37fd0`
- `0x381e0`
- `0x386c0`
- `0x4d100`
- `0x4d110`
- `0x4d250`
- `0x4d410`

## string_xrefs

- `0x383fd`: `COMMON_ERROR_MESSAGE_ACCESS_DENIED`
- `0x38337`: `Unable to close temp handle on channel enum`

## pseudocode

```c

```

## disassembly

```asm
0x381e0  ldarg.0
0x381e1  ldstr    aInitialize// "Initialize"
0x381e6  call     void Microsoft.Windows.ManagementUI.CombinedControls.TimeTrace::StartMethod(object thisObject, string methodName)
0x381eb  ldarg.1
0x381ec  castclass object[]
0x381f1  dup
0x381f2  ldc.i4.0
0x381f3  ldelem.ref
0x381f4  castclass [mscorlib]System.String
0x381f9  stloc.0
0x381fa  dup
0x381fb  ldc.i4.1
0x381fc  ldelem.ref
0x381fd  castclass [mscorlib]System.String
0x38202  stloc.1
0x38203  dup
0x38204  ldc.i4.2
0x38205  ldelem.ref
0x38206  castclass [mscorlib]System.String
0x3820b  stloc.2
0x3820c  dup
0x3820d  ldc.i4.3
0x3820e  ldelem.ref
0x3820f  castclass [mscorlib]System.Security.SecureString
0x38214  stloc.3
0x38215  ldc.i4.4
0x38216  ldelem.ref
0x38217  unbox.any [mscorlib]System.Int32
0x3821c  pop
0x3821d  ldloca.s 4
0x3821f  initobj  Microsoft.Windows.ManagementUI.CombinedControls.EventLogin
0x38225  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x3822a  stloc.s  5
0x3822c  ldarg.0
0x3822d  ldnull
0x3822e  stfld    class [System]System.Net.IPAddress[] Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::addressOfHostComputer
0x38233  ldc.i4.0
0x38234  stloc.s  6
0x38236  ldloc.0
0x38237  ldarg.0
0x38238  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::remoteComputer
0x3823d  ldc.i4.0
0x3823e  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x38243  brfalse  loc_384A6
0x38248  ldarg.0
0x38249  ldloc.0
0x3824a  stfld    string Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::remoteComputer
0x3824f  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x38254  pop
0x38255  ldarg.0
0x38256  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::remoteComputer
0x3825b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x38260  brtrue   loc_3849F
0x38265  ldarg.0
0x38266  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::ModifyRemoteComputer()
0x3826b  ldloca.s 4
0x3826d  ldarg.0
0x3826e  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::remoteComputer
0x38273  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::StringToCoTaskMemUni(string)
0x38278  stfld    native int Microsoft.Windows.ManagementUI.CombinedControls.EventLogin::Server
0x3827d  ldloc.2
0x3827e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x38283  brtrue.s loc_382AF
0x38285  ldloca.s 4
0x38287  ldloc.1
0x38288  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::StringToCoTaskMemUni(string)
0x3828d  stfld    native int Microsoft.Windows.ManagementUI.CombinedControls.EventLogin::Domain
0x38292  ldloca.s 4
0x38294  ldloc.2
0x38295  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::StringToCoTaskMemUni(string)
0x3829a  stfld    native int Microsoft.Windows.ManagementUI.CombinedControls.EventLogin::User
0x3829f  ldloc.3
0x382a0  brfalse.s loc_382AF
0x382a2  ldloca.s 4
0x382a4  ldloc.3
0x382a5  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::SecureStringToCoTaskMemUnicode(class [mscorlib]System.Security.SecureString)
0x382aa  stfld    native int Microsoft.Windows.ManagementUI.CombinedControls.EventLogin::Password
0x382af  ldloc.s  4
0x382b1  box      Microsoft.Windows.ManagementUI.CombinedControls.EventLogin
0x382b6  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::SizeOf(object)
0x382bb  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::AllocHGlobal(int32)
0x382c0  stloc.s  5
0x382c2  ldloc.s  4
0x382c4  box      Microsoft.Windows.ManagementUI.CombinedControls.EventLogin
0x382c9  ldloc.s  5
0x382cb  ldc.i4.1
0x382cc  call     void [mscorlib]System.Runtime.InteropServices.Marshal::StructureToPtr(object, native int, bool)
0x382d1  ldc.i4.0
0x382d2  stloc.s  7
0x382d4  ldc.i4.1
0x382d5  ldloc.s  5
0x382d7  ldc.i4.0
0x382d8  ldc.i4.0
0x382d9  call     native int Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::OpenSession([hasfieldmarshal] valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventLoginClass loginclass, native int login, int32 timeout, int32 flags)
0x382de  stloc.s  8
0x382e0  ldloc.s  8
0x382e2  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x382e7  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x382ec  brfalse.s loc_382F5
0x382ee  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x382f3  stloc.s  6
0x382f5  ldloc.s  8
0x382f7  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x382fc  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x38301  brfalse.s loc_38356
0x38303  ldloc.s  8
0x38305  ldc.i4.0
0x38306  call     native int Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::OpenChannelEnum(native int session, int32 flags)
0x3830b  stloc.s  9
0x3830d  ldloc.s  9
0x3830f  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x38314  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x38319  brfalse.s loc_38327
0x3831b  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x38320  stloc.s  6
0x38322  ldc.i4.1
0x38323  stloc.s  7
0x38325  br.s     loc_38359
0x38327  ldloc.s  9
0x38329  call     bool Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::CloseHandle(native int eventHandle)
0x3832e  brtrue.s loc_38343
0x38330  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x38335  stloc.s  6
0x38337  ldstr    aUnableToCloseT_0// "Unable to close temp handle on channel "...
0x3833c  ldloc.s  6
0x3833e  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x38343  ldarg.0
0x38344  ldarg.0
0x38345  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::remoteComputer
0x3834a  call     bool Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::IsLocalComputerContext(string computerName)
0x3834f  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::islocalComputer
0x38354  br.s     loc_38359
0x38356  ldc.i4.1
0x38357  stloc.s  7
0x38359  ldloc.s  7
0x3835b  brfalse  loc_38448
0x38360  ldc.i4.0
0x38361  stloc.s  0xA
0x38363  ldloc.s  6
0x38365  brfalse.s loc_3836F
0x38367  ldloc.0
0x38368  call     bool Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::ProcessToCheckIfLegacyMachine(string machineName)
0x3836d  stloc.s  0xA
0x3836f  ldloc.s  0xA
0x38371  brfalse.s loc_38383
0x38373  ldarg.0
0x38374  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.LegacyEventLogUIException::.ctor()
0x38379  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.UIException Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::exceptionInConnectingThread
0x3837e  leave    loc_384A6
0x38383  ldarg.0
0x38384  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle::.ctor()
0x38389  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::safeSession
0x3838e  ldloc.s  6
0x38390  call     bool Microsoft.Windows.ManagementUI.CombinedControls.UIException::ServiceNotAvailableError(int32 error)
0x38395  brfalse.s loc_383E7
0x38397  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3839c  ldtoken  [mscorlib]System.String
0x383a1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x383a6  callvirt instance object [mscorlib]System.Globalization.CultureInfo::GetFormat(class [mscorlib]System.Type)
0x383ab  castclass [mscorlib]System.IFormatProvider
0x383b0  ldstr    aNoremoteserver// "NoRemoteServerError"
0x383b5  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x383ba  ldc.i4.2
0x383bb  newarr   [mscorlib]System.Object
0x383c0  dup
0x383c1  ldc.i4.0
0x383c2  ldarg.0
0x383c3  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::remoteComputer
0x383c8  stelem.ref
0x383c9  dup
0x383ca  ldc.i4.1
0x383cb  ldloc.s  6
0x383cd  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor(int32)
0x383d2  callvirt instance string [mscorlib]System.Exception::get_Message()
0x383d7  stelem.ref
0x383d8  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x383dd  ldc.i4.1
0x383de  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.UIException::.ctor(string message, valuetype Microsoft.Windows.ManagementUI.CombinedControls.ExceptionAction initialAction)
0x383e3  stloc.s  0xB
0x383e5  br.s     loc_38436
0x383e7  ldloc.s  6
0x383e9  conv.i8
0x383ea  ldc.i4   0x6D9
0x383ef  conv.i8
0x383f0  bne.un.s loc_38425
0x383f2  ldloc.2
0x383f3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x383f8  brtrue.s loc_383FD
0x383fa  ldloc.3
0x383fb  brtrue.s loc_38411
0x383fd  ldstr    aCommonErrorMes// "COMMON_ERROR_MESSAGE_ACCESS_DENIED"
0x38402  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x38407  ldc.i4.1
0x38408  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.UIException::.ctor(string message, valuetype Microsoft.Windows.ManagementUI.CombinedControls.ExceptionAction initialAction)
0x3840d  stloc.s  0xB
0x3840f  br.s     loc_38436
0x38411  ldstr    aConnectasnotsu// "ConnectAsNotSupport"
0x38416  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x3841b  ldc.i4.1
0x3841c  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.UIException::.ctor(string message, valuetype Microsoft.Windows.ManagementUI.CombinedControls.ExceptionAction initialAction)
0x38421  stloc.s  0xB
0x38423  br.s     loc_38436
0x38425  ldloc.s  6
0x38427  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.UIException::.ctor(int32 win32Error)
0x3842c  stloc.s  0xB
0x3842e  ldloc.s  0xB
0x38430  ldc.i4.1
0x38431  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UIException::set_ActionForException(valuetype Microsoft.Windows.ManagementUI.CombinedControls.ExceptionAction value)
0x38436  ldloc.s  0xB
0x38438  ldc.i4.1
0x38439  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UIException::set_RefreshConsole(bool value)
0x3843e  ldarg.0
0x3843f  ldloc.s  0xB
0x38441  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.UIException Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::exceptionInConnectingThread
0x38446  leave.s  loc_384A6
0x38448  ldarg.0
0x38449  ldloc.s  8
0x3844b  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle::.ctor(native int crimsonHandle)
0x38450  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::safeSession
0x38455  leave.s  loc_384A6
0x38457  ldloca.s 4
0x38459  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.EventLogin::Dispose()
0x3845e  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x38463  ldloc.s  5
0x38465  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x3846a  brfalse.s loc_3849E
0x3846c  ldloc.s  5
0x3846e  ldloc.s  4
0x38470  box      Microsoft.Windows.ManagementUI.CombinedControls.EventLogin
0x38475  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::SizeOf(object)
0x3847a  call     void Microsoft.Windows.ManagementUI.CombinedControls.NativeMethods::SecureZeroMemory(native int handle, unsigned int32 length)
0x3847f  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x38484  stloc.s  6
0x38486  ldloc.s  5
0x38488  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.EventLogin
0x3848d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x38492  call     void [mscorlib]System.Runtime.InteropServices.Marshal::DestroyStructure(native int, class [mscorlib]System.Type)
0x38497  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x3849c  stloc.s  6
0x3849e  endfinally
0x3849f  ldarg.0
0x384a0  ldc.i4.1
0x384a1  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::islocalComputer
0x384a6  ldarg.0
0x384a7  ldc.i4.1
0x384a8  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::initialized
0x384ad  leave    loc_3853C
0x384b2  ldarg.0
0x384b3  ldfld    object Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::connectingSyncObj
0x384b8  call     void [mscorlib]System.Threading.Monitor::Enter(object)
0x384bd  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x384c2  callvirt instance valuetype [mscorlib]System.Threading.ThreadState [mscorlib]System.Threading.Thread::get_ThreadState()
0x384c7  ldc.i4   0x100
0x384cc  and
0x384cd  brtrue.s loc_3851A
0x384cf  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x384d4  callvirt instance valuetype [mscorlib]System.Threading.ThreadState [mscorlib]System.Threading.Thread::get_ThreadState()
0x384d9  ldc.i4   0x80
0x384de  and
0x384df  brtrue.s loc_3851A
0x384e1  ldarg.0
0x384e2  ldc.i4.0
0x384e3  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::isConnecting
0x384e8  ldarg.0
0x384e9  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ConnectingToRemoteWaitForm Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::waitForm
0x384ee  brfalse.s loc_3851A
0x384f0  ldarg.0
0x384f1  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ConnectingToRemoteWaitForm Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::waitForm
0x384f6  ldarg.0
0x384f7  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::CloseWaitForm(object sender, class [mscorlib]System.EventArgs e)
0x384fd  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x38502  ldc.i4.2
0x38503  newarr   [mscorlib]System.Object
0x38508  dup
0x38509  ldc.i4.0
0x3850a  ldarg.0
0x3850b  stelem.ref
0x3850c  dup
0x3850d  ldc.i4.1
0x3850e  ldsfld   class [mscorlib]System.EventArgs [mscorlib]System.EventArgs::Empty
0x38513  stelem.ref
0x38514  callvirt instance class [mscorlib]System.IAsyncResult [System.Windows.Forms]System.Windows.Forms.Control::BeginInvoke(class [mscorlib]System.Delegate, object[])
0x38519  pop
0x3851a  ldarg.0
0x3851b  ldfld    object Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::connectingSyncObj
0x38520  call     void [mscorlib]System.Threading.Monitor::Pulse(object)
0x38525  ldarg.0
0x38526  ldfld    object Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::connectingSyncObj
0x3852b  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x38530  ldarg.0
0x38531  ldstr    aInitialize// "Initialize"
0x38536  call     void Microsoft.Windows.ManagementUI.CombinedControls.TimeTrace::EndMethod(object thisObject, string methodName)
0x3853b  endfinally
0x3853c  ret
```
