# Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::GetInstanceStartTime

- ea: `0x6d200`
- end: `0x6d414`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::GetInstanceStartTime`
- size: `532`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callers

- `0x6cff0`

## callees

- `0x12ed0`
- `0x13440`
- `0x1b7c0`
- `0x1b850`
- `0x344c0`
- `0x38840`
- `0x3a9e0`
- `0x3f6d0`
- `0x3f760`
- `0x3f920`
- `0x3fb80`
- `0x3fbb0`
- `0x41730`
- `0x41740`
- `0x67c80`
- `0x67ca0`
- `0x685f0`
- `0x6d200`

## string_xrefs

- `0x6d3de`: `ApplicationTaskScheduler`
- `0x6d3fa`: `ApplicationTaskScheduler`
- `0x6d266`: `Microsoft-Windows-TaskScheduler/Operational`
- `0x6d3d4`: `MessageTaskCrimsonServiceNotRunning`
- `0x6d3f0`: `MessageTaskAccessViewStartTimes`

## pseudocode

```c

```

## disassembly

```asm
0x6d200  ldc.i4.0
0x6d201  stloc.0
0x6d202  ldnull
0x6d203  stloc.1
0x6d204  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x6d209  stloc.2
0x6d20a  ldloc.2
0x6d20b  ldstr    aEventdataDataN// "*[EventData/Data[@Name='InstanceId']=\""
0x6d210  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x6d215  pop
0x6d216  ldloc.2
0x6d217  ldarg.1
0x6d218  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x6d21d  pop
0x6d21e  ldloc.2
0x6d21f  ldstr    aAndSystemEvent// "\" and System/EventID=100]"
0x6d224  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x6d229  pop
0x6d22a  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::.ctor()
0x6d22f  stloc.3
0x6d230  ldloc.3
0x6d231  ldc.i4.0
0x6d232  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::set_ShowPartialQueryErrors(bool value)
0x6d237  ldloc.3
0x6d238  ldc.i4.1
0x6d239  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::set_ExecutePartialQuery(bool value)
0x6d23e  ldloc.3
0x6d23f  ldarg.0
0x6d240  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::service
0x6d245  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UIEventLogService Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_EventLogService()
0x6d24a  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext Microsoft.Windows.ManagementUI.CombinedControls.UIEventLogService::get_Context()
0x6d24f  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::set_Context(class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext value)
0x6d254  ldarg.0
0x6d255  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::service
0x6d25a  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UIEventLogService Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_EventLogService()
0x6d25f  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext Microsoft.Windows.ManagementUI.CombinedControls.UIEventLogService::get_Context()
0x6d264  stloc.1
0x6d265  ldloc.3
0x6d266  ldstr    aMicrosoftWindo_1// "Microsoft-Windows-TaskScheduler/Operati"...
0x6d26b  ldloc.2
0x6d26c  callvirt instance string [mscorlib]System.Object::ToString()
0x6d271  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::Initialize(string channelPath, string Query)
0x6d276  brfalse  loc_6D3AD
0x6d27b  ldloc.3
0x6d27c  callvirt instance unsigned int64 Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::get_Count()
0x6d281  ldc.i4.0
0x6d282  conv.i8
0x6d283  ble.un   loc_6D3AD
0x6d288  ldloc.3
0x6d289  ldc.i4.0
0x6d28a  conv.i8
0x6d28b  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.IEventBase Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::GetAt(unsigned int64 index)
0x6d290  stloc.s  4
0x6d292  ldloc.s  4
0x6d294  brfalse  loc_6D3AD
0x6d299  ldarg.3
0x6d29a  ldloc.s  4
0x6d29c  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Windows.ManagementUI.CombinedControls.IEventBase::get_TimeGenerated()
0x6d2a1  stloc.s  7
0x6d2a3  ldloca.s 7
0x6d2a5  call     instance string [mscorlib]System.DateTime::ToString()
0x6d2aa  stind.ref
0x6d2ab  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x6d2b0  stloc.s  7
0x6d2b2  ldloca.s 7
0x6d2b4  ldloc.s  4
0x6d2b6  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Windows.ManagementUI.CombinedControls.IEventBase::get_TimeGenerated()
0x6d2bb  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::Subtract(valuetype [mscorlib]System.DateTime)
0x6d2c0  stloc.s  5
0x6d2c2  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x6d2c7  stloc.s  6
0x6d2c9  ldloc.s  6
0x6d2cb  ldloca.s 5
0x6d2cd  call     instance int32 [mscorlib]System.TimeSpan::get_Hours()
0x6d2d2  stloc.s  8
0x6d2d4  ldloca.s 8
0x6d2d6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6d2db  ldtoken  [mscorlib]System.Int32
0x6d2e0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6d2e5  callvirt instance object [mscorlib]System.Globalization.CultureInfo::GetFormat(class [mscorlib]System.Type)
0x6d2ea  castclass [mscorlib]System.IFormatProvider
0x6d2ef  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x6d2f4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x6d2f9  pop
0x6d2fa  ldloc.s  6
0x6d2fc  ldstr    aHourseparator// "HourSeparator"
0x6d301  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x6d306  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x6d30b  pop
0x6d30c  ldloc.s  6
0x6d30e  ldloca.s 5
0x6d310  call     instance int32 [mscorlib]System.TimeSpan::get_Minutes()
0x6d315  stloc.s  8
0x6d317  ldloca.s 8
0x6d319  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6d31e  ldtoken  [mscorlib]System.Int32
0x6d323  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6d328  callvirt instance object [mscorlib]System.Globalization.CultureInfo::GetFormat(class [mscorlib]System.Type)
0x6d32d  castclass [mscorlib]System.IFormatProvider
0x6d332  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x6d337  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x6d33c  pop
0x6d33d  ldloc.s  6
0x6d33f  ldstr    aMinuteseparato// "MinuteSeparator"
0x6d344  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x6d349  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x6d34e  pop
0x6d34f  ldloc.s  6
0x6d351  ldloca.s 5
0x6d353  call     instance int32 [mscorlib]System.TimeSpan::get_Seconds()
0x6d358  stloc.s  8
0x6d35a  ldloca.s 8
0x6d35c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6d361  ldtoken  [mscorlib]System.Int32
0x6d366  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6d36b  callvirt instance object [mscorlib]System.Globalization.CultureInfo::GetFormat(class [mscorlib]System.Type)
0x6d370  castclass [mscorlib]System.IFormatProvider
0x6d375  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x6d37a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x6d37f  pop
0x6d380  ldloc.s  6
0x6d382  ldstr    aSecondseparato// "SecondSeparator"
0x6d387  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x6d38c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x6d391  pop
0x6d392  ldarg.2
0x6d393  ldloc.s  6
0x6d395  callvirt instance string [mscorlib]System.Object::ToString()
0x6d39a  stind.ref
0x6d39b  ldarg.s  4
0x6d39d  ldloc.1
0x6d39e  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::get_RemoteComputer()
0x6d3a3  ldloc.s  4
0x6d3a5  call     string Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::GetUserId(string computerName, class Microsoft.Windows.ManagementUI.CombinedControls.IEventBase evt)
0x6d3aa  stind.ref
0x6d3ab  ldc.i4.1
0x6d3ac  stloc.0
0x6d3ad  leave.s  loc_6D412
0x6d3af  stloc.s  9
0x6d3b1  ldarg.0
0x6d3b2  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::service
0x6d3b7  ldc.i4.0
0x6d3b8  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::set_IsConnectedToCrimson(bool value)
0x6d3bd  ldarg.0
0x6d3be  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::accessMessageHasBeenDisplayed
0x6d3c3  brtrue.s loc_6D410
0x6d3c5  ldloc.s  9
0x6d3c7  callvirt instance int32 Microsoft.Windows.ManagementUI.CombinedControls.UIException::get_ErrorNumber()
0x6d3cc  call     bool Microsoft.Windows.ManagementUI.CombinedControls.UIException::ServiceNotAvailableError(int32 error)
0x6d3d1  brfalse.s loc_6D3EF
0x6d3d3  ldarg.0
0x6d3d4  ldstr    aMessagetaskcri// "MessageTaskCrimsonServiceNotRunning"
0x6d3d9  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x6d3de  ldstr    aApplicationtas// "ApplicationTaskScheduler"
0x6d3e3  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x6d3e8  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string errorString, string caption)
0x6d3ed  br.s     loc_6D409
0x6d3ef  ldarg.0
0x6d3f0  ldstr    aMessagetaskacc_5// "MessageTaskAccessViewStartTimes"
0x6d3f5  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x6d3fa  ldstr    aApplicationtas// "ApplicationTaskScheduler"
0x6d3ff  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x6d404  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string errorString, string caption)
0x6d409  ldarg.0
0x6d40a  ldc.i4.1
0x6d40b  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::accessMessageHasBeenDisplayed
0x6d410  leave.s  loc_6D412
0x6d412  ldloc.0
0x6d413  ret
```
