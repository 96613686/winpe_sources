# Microsoft.Windows.ManagementUI.CombinedControls.UITaskEventSubscription::SubscribeToTaskSchedulerChannel

- ea: `0x85a60`
- end: `0x85b28`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.UITaskEventSubscription::SubscribeToTaskSchedulerChannel`
- size: `200`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x859f0`

## callees

- `0x12840`
- `0x13510`
- `0x4d350`
- `0x4d360`
- `0x85a50`
- `0x85a60`
- `0xa2320`

## string_xrefs

- `0x85a60`: `Microsoft-Windows-TaskScheduler/Operational`
- `0x85aae`: `Unable to open the session `

## pseudocode

```c

```

## disassembly

```asm
0x85a60  ldstr    aMicrosoftWindo_1// "Microsoft-Windows-TaskScheduler/Operati"...
0x85a65  stloc.0
0x85a66  ldstr    aSystemEventid1// "*[System[(EventID=100 or EventID=101 or"...
0x85a6b  stloc.1
0x85a6c  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::PrepareConstrainedRegions()
0x85a71  leave    loc_85B27
0x85a76  ldloca.s 2
0x85a78  initobj  EventRPCLogin
0x85a7e  ldarg.0
0x85a7f  ldarg.1
0x85a80  call     instance bool Microsoft.Windows.ManagementUI.CombinedControls.UITaskEventSubscription::ValidComputerName(string computerName)
0x85a85  brfalse.s loc_85A8F
0x85a87  ldloca.s 2
0x85a89  ldarg.1
0x85a8a  call     instance void EventRPCLogin::SetServer(string inServer)
0x85a8f  ldc.i4.1
0x85a90  ldloca.s 2
0x85a92  ldc.i4.0
0x85a93  ldc.i4.0
0x85a94  call     native int Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::EventOpenSession(valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventLoginClass loginClass, valuetype EventRPCLogin& Login, int32 timeout, int32 flags)
0x85a99  stloc.3
0x85a9a  ldloc.3
0x85a9b  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x85aa0  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x85aa5  brfalse.s loc_85AC3
0x85aa7  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x85aac  stloc.s  4
0x85aae  ldstr    aUnableToOpenTh_0// "Unable to open the session "
0x85ab3  ldloc.0
0x85ab4  ldloc.1
0x85ab5  call     string [mscorlib]System.String::Concat(string, string, string)
0x85aba  ldloc.s  4
0x85abc  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x85ac1  br.s     loc_85B26
0x85ac3  ldarg.0
0x85ac4  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle Microsoft.Windows.ManagementUI.CombinedControls.UITaskEventSubscription::handleTaskSchedulerSession
0x85ac9  ldloc.3
0x85aca  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle::InitHandle(native int crimsonHandle)
0x85acf  ldloc.3
0x85ad0  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x85ad5  ldloc.0
0x85ad6  ldloc.1
0x85ad7  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x85adc  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x85ae1  ldarg.0
0x85ae2  ldfld    class SubEventQueryCallback Microsoft.Windows.ManagementUI.CombinedControls.UITaskEventSubscription::activeCallback
0x85ae7  ldc.i4.1
0x85ae8  call     native int Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::EventSubscribe(native int session, native int signalEvent, [hasfieldmarshal] string channelPath, [hasfieldmarshal] string query, native int bookMark, native int context, class SubEventQueryCallback eventCallback, int32 flags)
0x85aed  stloc.s  5
0x85aef  ldloc.s  5
0x85af1  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x85af6  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x85afb  brfalse.s loc_85B19
0x85afd  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x85b02  stloc.s  6
0x85b04  ldstr    aUnableToSubscr// "Unable to subscribe "
0x85b09  ldloc.0
0x85b0a  ldloc.1
0x85b0b  call     string [mscorlib]System.String::Concat(string, string, string)
0x85b10  ldloc.s  6
0x85b12  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x85b17  br.s     loc_85B26
0x85b19  ldarg.0
0x85b1a  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle Microsoft.Windows.ManagementUI.CombinedControls.UITaskEventSubscription::handleTaskSchedulerSubscription
0x85b1f  ldloc.s  5
0x85b21  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle::InitHandle(native int crimsonHandle)
0x85b26  endfinally
0x85b27  ret
```
