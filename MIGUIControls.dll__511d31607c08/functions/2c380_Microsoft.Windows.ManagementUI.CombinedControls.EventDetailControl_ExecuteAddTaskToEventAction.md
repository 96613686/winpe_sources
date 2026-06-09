# Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::ExecuteAddTaskToEventAction

- ea: `0x2c380`
- end: `0x2c523`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::ExecuteAddTaskToEventAction`
- size: `419`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `service_task, broker_com_uri`

## callers

- `0x2bed0`

## callees

- `0x12ed0`
- `0x1b4d0`
- `0x1cd50`
- `0x1ce20`
- `0x2b230`
- `0x2b7b0`
- `0x2c380`
- `0x2f1f0`
- `0x33aa0`
- `0x35480`
- `0x36330`
- `0x36340`
- `0x36390`
- `0x37140`
- `0x39020`
- `0x3a9d0`
- `0x3aa20`
- `0x3aa90`
- `0x3ab20`

## string_xrefs

- `0x2c381`: `ExecuteAddTaskToEventAction`
- `0x2c517`: `ExecuteAddTaskToEventAction`
- `0x2c3ba`: `TaskAttachError`
- `0x2c43e`: `TaskAttachError`

## pseudocode

```c

```

## disassembly

```asm
0x2c380  ldarg.0
0x2c381  ldstr    aExecuteaddtask// "ExecuteAddTaskToEventAction"
0x2c386  call     void Microsoft.Windows.ManagementUI.CombinedControls.TimeTrace::StartMethod(object thisObject, string methodName)
0x2c38b  ldc.i4.1
0x2c38c  stloc.0
0x2c38d  ldarg.0
0x2c38e  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::channel
0x2c393  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2c398  brtrue.s loc_2C3CB
0x2c39a  ldarg.0
0x2c39b  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::singleChannelQuery
0x2c3a0  brfalse.s loc_2C3CB
0x2c3a2  ldarg.0
0x2c3a3  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::channel
0x2c3a8  ldarg.0
0x2c3a9  call     instance native int Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::get_SessionPtr()
0x2c3ae  call     valuetype Microsoft.Windows.ManagementUI.CombinedControls.CrimsonChannelType Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::GetChannelType(string channelPath, native int session)
0x2c3b3  call     bool Microsoft.Windows.ManagementUI.CombinedControls.CEventsCommon::IsCrimsonDirectChannel(valuetype Microsoft.Windows.ManagementUI.CombinedControls.CrimsonChannelType channelType)
0x2c3b8  brfalse.s loc_2C3CB
0x2c3ba  ldstr    aTaskattacherro// "TaskAttachError"
0x2c3bf  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x2c3c4  call     void Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::ShowErrorMessageBox(string message)
0x2c3c9  ldc.i4.0
0x2c3ca  stloc.0
0x2c3cb  ldloc.0
0x2c3cc  brfalse  loc_2C516
0x2c3d1  ldarg.1
0x2c3d2  callvirt instance valuetype Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Status()
0x2c3d7  brtrue   loc_2C516
0x2c3dc  ldarg.0
0x2c3dd  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ListViewEx Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::mainListView
0x2c3e2  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ListView/SelectedIndexCollection [System.Windows.Forms]System.Windows.Forms.ListView::get_SelectedIndices()
0x2c3e7  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.ListView/SelectedIndexCollection::get_Count()
0x2c3ec  ldc.i4.0
0x2c3ed  ble      loc_2C516
0x2c3f2  ldarg.0
0x2c3f3  ldarg.0
0x2c3f4  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ListViewEx Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::mainListView
0x2c3f9  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ListView/SelectedIndexCollection [System.Windows.Forms]System.Windows.Forms.ListView::get_SelectedIndices()
0x2c3fe  ldc.i4.0
0x2c3ff  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.ListView/SelectedIndexCollection::get_Item(int32)
0x2c404  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.IEventBase Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::GetEventAt(int32 index)
0x2c409  isinst   Microsoft.Windows.ManagementUI.CombinedControls.ISystemEvent
0x2c40e  stloc.1
0x2c40f  ldloc.1
0x2c410  callvirt instance native int Microsoft.Windows.ManagementUI.CombinedControls.ISystemEvent::get_EventHandle()
0x2c415  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x2c41a  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x2c41f  brfalse  loc_2C516
0x2c424  ldloc.1
0x2c425  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.IEventBase::get_OriginalChannel()
0x2c42a  stloc.2
0x2c42b  ldloc.2
0x2c42c  ldarg.0
0x2c42d  call     instance native int Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::get_SessionPtr()
0x2c432  call     valuetype Microsoft.Windows.ManagementUI.CombinedControls.CrimsonChannelType Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::GetChannelType(string channelPath, native int session)
0x2c437  call     bool Microsoft.Windows.ManagementUI.CombinedControls.CEventsCommon::IsCrimsonDirectChannelOrExternalLog(valuetype Microsoft.Windows.ManagementUI.CombinedControls.CrimsonChannelType channelType)
0x2c43c  brfalse.s loc_2C454
0x2c43e  ldstr    aTaskattacherro// "TaskAttachError"
0x2c443  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x2c448  call     void Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::ShowErrorMessageBox(string message)
0x2c44d  ldc.i4.0
0x2c44e  stloc.0
0x2c44f  br       loc_2C516
0x2c454  ldloc.1
0x2c455  brfalse  loc_2C514
0x2c45a  ldc.i4.5
0x2c45b  newarr   [mscorlib]System.String
0x2c460  dup
0x2c461  ldc.i4.0
0x2c462  ldloc.2
0x2c463  stelem.ref
0x2c464  dup
0x2c465  ldc.i4.1
0x2c466  ldstr    asc_A80EC// "\\"
0x2c46b  stelem.ref
0x2c46c  dup
0x2c46d  ldc.i4.2
0x2c46e  ldloc.1
0x2c46f  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.IEventBase::get_Source()
0x2c474  stelem.ref
0x2c475  dup
0x2c476  ldc.i4.3
0x2c477  ldstr    asc_AABD4// "_"
0x2c47c  stelem.ref
0x2c47d  dup
0x2c47e  ldc.i4.4
0x2c47f  ldloc.1
0x2c480  callvirt instance unsigned int16 Microsoft.Windows.ManagementUI.CombinedControls.IEventBase::get_EventId()
0x2c485  stloc.s  6
0x2c487  ldloca.s 6
0x2c489  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2c48e  ldtoken  [mscorlib]System.UInt16
0x2c493  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2c498  callvirt instance object [mscorlib]System.Globalization.CultureInfo::GetFormat(class [mscorlib]System.Type)
0x2c49d  castclass [mscorlib]System.IFormatProvider
0x2c4a2  call     instance string [mscorlib]System.UInt16::ToString(class [mscorlib]System.IFormatProvider)
0x2c4a7  stelem.ref
0x2c4a8  call     string [mscorlib]System.String::Concat(string[])
0x2c4ad  stloc.3
0x2c4ae  ldloc.3
0x2c4af  call     string Microsoft.Windows.ManagementUI.CombinedControls.CEventsCommon::MakeNameDirectoryFileName(string name)
0x2c4b4  stloc.3
0x2c4b5  ldloc.1
0x2c4b6  callvirt instance unsigned int16 Microsoft.Windows.ManagementUI.CombinedControls.IEventBase::get_EventId()
0x2c4bb  stloc.s  6
0x2c4bd  ldloca.s 6
0x2c4bf  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2c4c4  ldtoken  [mscorlib]System.UInt16
0x2c4c9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2c4ce  callvirt instance object [mscorlib]System.Globalization.CultureInfo::GetFormat(class [mscorlib]System.Type)
0x2c4d3  castclass [mscorlib]System.IFormatProvider
0x2c4d8  call     instance string [mscorlib]System.UInt16::ToString(class [mscorlib]System.IFormatProvider)
0x2c4dd  stloc.s  4
0x2c4df  ldloc.1
0x2c4e0  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.IEventBase::get_Source()
0x2c4e5  stloc.s  5
0x2c4e7  ldarg.0
0x2c4e8  call     instance bool Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::get_IsOwnedByTaskScheduler()
0x2c4ed  ldarg.0
0x2c4ee  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::context
0x2c4f3  ldc.i4.0
0x2c4f4  ldsfld   string [mscorlib]System.String::Empty
0x2c4f9  ldloc.3
0x2c4fa  ldloc.2
0x2c4fb  ldloc.s  4
0x2c4fd  ldloc.s  5
0x2c4ff  call     bool Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::AttachTask(bool isTaskScheduler, class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext viewerContext, bool isAttachToCustomView, string queryXml, string taskName, string channel, string eventIdString, string evtSource)
0x2c504  stloc.0
0x2c505  ldloc.0
0x2c506  brfalse.s loc_2C516
0x2c508  ldc.i4   0xEE3
0x2c50d  call     void Microsoft.Windows.ManagementUI.CombinedControls.SnapInFeedback::IncrementGlobalDatapoint(valuetype Microsoft.Windows.ManagementUI.CombinedControls.FeedbackDatapoint datapoint)
0x2c512  br.s     loc_2C516
0x2c514  ldc.i4.0
0x2c515  stloc.0
0x2c516  ldarg.0
0x2c517  ldstr    aExecuteaddtask// "ExecuteAddTaskToEventAction"
0x2c51c  call     void Microsoft.Windows.ManagementUI.CombinedControls.TimeTrace::EndMethod(object thisObject, string methodName)
0x2c521  ldloc.0
0x2c522  ret
```
