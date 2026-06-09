# SubscriptionProcessing::StartWecService

- ea: `0xa59a0`
- end: `0xa5aac`
- name: `SubscriptionProcessing::StartWecService`
- size: `268`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0xa5b50`

## callees

- `0x34d0`
- `0x12ed0`
- `0x13440`
- `0x13510`
- `0xa59a0`

## string_xrefs

- `0xa5a13`: `In StartWecService() : Unable to Call quick config.`
- `0xa5a7a`: `WecServiceStartError`

## pseudocode

```c

```

## disassembly

```asm
0xa59a0  ldc.i4.0
0xa59a1  stloc.0
0xa59a2  ldsfld   string SubscriptionProcessing::WecServiceName
0xa59a7  newobj   instance void [System.ServiceProcess]System.ServiceProcess.ServiceController::.ctor(string)
0xa59ac  stloc.1
0xa59ad  ldloc.1
0xa59ae  callvirt instance valuetype [System.ServiceProcess]System.ServiceProcess.ServiceControllerStatus [System.ServiceProcess]System.ServiceProcess.ServiceController::get_Status()
0xa59b3  stloc.2
0xa59b4  ldloca.s 2
0xa59b6  ldc.i4.1
0xa59b7  box      [System.ServiceProcess]System.ServiceProcess.ServiceControllerStatus
0xa59bc  constrained. [System.ServiceProcess]System.ServiceProcess.ServiceControllerStatus
0xa59c2  callvirt instance bool [mscorlib]System.Object::Equals(object)
0xa59c7  brtrue.s loc_A59E5
0xa59c9  ldloc.1
0xa59ca  callvirt instance valuetype [System.ServiceProcess]System.ServiceProcess.ServiceControllerStatus [System.ServiceProcess]System.ServiceProcess.ServiceController::get_Status()
0xa59cf  stloc.2
0xa59d0  ldloca.s 2
0xa59d2  ldc.i4.3
0xa59d3  box      [System.ServiceProcess]System.ServiceProcess.ServiceControllerStatus
0xa59d8  constrained. [System.ServiceProcess]System.ServiceProcess.ServiceControllerStatus
0xa59de  callvirt instance bool [mscorlib]System.Object::Equals(object)
0xa59e3  brfalse.s loc_A59FF
0xa59e5  ldloc.1
0xa59e6  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceController::Start()
0xa59eb  ldloca.s 3
0xa59ed  ldc.i4.0
0xa59ee  ldc.i4.0
0xa59ef  ldarg.1
0xa59f0  call     instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0xa59f5  ldloc.1
0xa59f6  ldc.i4.4
0xa59f7  ldloc.3
0xa59f8  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceController::WaitForStatus(valuetype [System.ServiceProcess]System.ServiceProcess.ServiceControllerStatus, valuetype [mscorlib]System.TimeSpan)
0xa59fd  ldc.i4.1
0xa59fe  stloc.0
0xa59ff  ldloc.1
0xa5a00  callvirt instance void [System]System.ComponentModel.Component::Dispose()
0xa5a05  call     bool Microsoft.WindowsEventCollection.Private.ECNativeMethods::EcQuickConfig()
0xa5a0a  brtrue.s loc_A5A1F
0xa5a0c  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0xa5a11  stloc.s  4
0xa5a13  ldstr    aInStartwecserv// "In StartWecService() : Unable to Call q"...
0xa5a18  ldloc.s  4
0xa5a1a  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0xa5a1f  leave    loc_A5AAA
0xa5a24  stloc.s  5
0xa5a26  ldc.i4.1
0xa5a27  stloc.s  6
0xa5a29  ldloc.s  5
0xa5a2b  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0xa5a30  isinst   [System]System.ComponentModel.Win32Exception
0xa5a35  brfalse.s loc_A5A6F
0xa5a37  ldloc.s  5
0xa5a39  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0xa5a3e  castclass [System]System.ComponentModel.Win32Exception
0xa5a43  callvirt instance int32 [System]System.ComponentModel.Win32Exception::get_NativeErrorCode()
0xa5a48  ldc.i4.5
0xa5a49  bne.un.s loc_A5A6F
0xa5a4b  ldarg.0
0xa5a4c  ldfld    class [System.Windows.Forms]System.Windows.Forms.IWin32Window SubscriptionProcessing::parentWindow
0xa5a51  ldloc.s  5
0xa5a53  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0xa5a58  callvirt instance string [mscorlib]System.Exception::get_Message()
0xa5a5d  ldstr    aViewername// "ViewerName"
0xa5a62  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0xa5a67  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string errorString, string caption)
0xa5a6c  ldc.i4.0
0xa5a6d  stloc.s  6
0xa5a6f  ldloc.s  6
0xa5a71  brfalse.s loc_A5AA8
0xa5a73  ldarg.0
0xa5a74  ldfld    class [System.Windows.Forms]System.Windows.Forms.IWin32Window SubscriptionProcessing::parentWindow
0xa5a79  ldnull
0xa5a7a  ldstr    aWecservicestar// "WecServiceStartError"
0xa5a7f  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0xa5a84  ldc.i4.1
0xa5a85  newarr   [mscorlib]System.Object
0xa5a8a  dup
0xa5a8b  ldc.i4.0
0xa5a8c  ldloc.s  5
0xa5a8e  callvirt instance string [mscorlib]System.Exception::get_Message()
0xa5a93  stelem.ref
0xa5a94  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa5a99  ldstr    aViewername// "ViewerName"
0xa5a9e  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0xa5aa3  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string errorString, string caption)
0xa5aa8  leave.s  loc_A5AAA
0xa5aaa  ldloc.0
0xa5aab  ret
```
