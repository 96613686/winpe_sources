# Microsoft.Windows.ManagementUI.CombinedControls.UITask::SetActions

- ea: `0x65e90`
- end: `0x6608d`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.UITask::SetActions`
- size: `509`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `service_task, broker_com_uri`

## callers

- `0x64a80`

## callees

- `0x12ed0`
- `0x133f0`
- `0x13430`
- `0x5d760`
- `0x5f840`
- `0x5f860`
- `0x5fa10`
- `0x5faf0`
- `0x5fd80`
- `0x5ffc0`
- `0x60110`
- `0x60120`
- `0x645c0`
- `0x64640`
- `0x65c70`
- `0x65c90`
- `0x65e90`
- `0x67c50`
- `0x67e80`
- `0x85380`
- `0x853c0`
- `0x85400`
- `0x85890`

## string_xrefs

- `0x66013`: `MessageTaskDoesNotExist`

## pseudocode

```c

```

## disassembly

```asm
0x65e90  ldarg.1
0x65e91  ldind.ref
0x65e92  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.IActionCollection Microsoft.Windows.ManagementUI.CombinedControls.ITaskDefinition::get_Actions()
0x65e97  stloc.0
0x65e98  ldarg.0
0x65e99  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UIActionList Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_ActionList()
0x65e9e  callvirt instance class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.UIActionList::get_ActionsList()
0x65ea3  ldstr    aErroractionmes// "ErrorActionMessage"
0x65ea8  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x65ead  call     bool Microsoft.Windows.ManagementUI.CombinedControls.UITask::ListValid(class [mscorlib]System.Collections.ArrayList list, string message)
0x65eb2  stloc.1
0x65eb3  ldloc.1
0x65eb4  brfalse  loc_6608B
0x65eb9  ldloc.0
0x65eba  ldarg.0
0x65ebb  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UIActionList Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_ActionList()
0x65ec0  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UIActionList::get_Context()
0x65ec5  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.IActionCollection::set_Context(string value)
0x65eca  ldc.i4.0
0x65ecb  stloc.2
0x65ecc  ldc.i4.0
0x65ecd  stloc.3
0x65ece  br       loc_65FE8
0x65ed3  ldarg.0
0x65ed4  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UIActionList Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_ActionList()
0x65ed9  callvirt instance class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.UIActionList::get_ActionsList()
0x65ede  ldloc.3
0x65edf  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x65ee4  castclass Microsoft.Windows.ManagementUI.CombinedControls.UIAction
0x65ee9  stloc.s  4
0x65eeb  ldc.i4.0
0x65eec  stloc.1
0x65eed  ldarg.2
0x65eee  brtrue.s loc_65F04
0x65ef0  ldloc.0
0x65ef1  ldloc.s  4
0x65ef3  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UIAction::get_Id()
0x65ef8  call     int32 Microsoft.Windows.ManagementUI.CombinedControls.UITask::FindActionIndex(class Microsoft.Windows.ManagementUI.CombinedControls.IActionCollection actionCollection, string taskName)
0x65efd  stloc.2
0x65efe  ldloc.2
0x65eff  brtrue.s loc_65F04
0x65f01  ldc.i4.1
0x65f02  starg.s  2
0x65f04  ldloc.s  4
0x65f06  callvirt instance valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskActionType Microsoft.Windows.ManagementUI.CombinedControls.UIAction::get_ActionType()
0x65f0b  brtrue.s loc_65F3E
0x65f0d  ldarg.2
0x65f0e  brtrue.s loc_65F20
0x65f10  ldloc.0
0x65f11  ldloc.2
0x65f12  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.IAction Microsoft.Windows.ManagementUI.CombinedControls.IActionCollection::GetItem([hasfieldmarshal] int32)
0x65f17  castclass Microsoft.Windows.ManagementUI.CombinedControls.IExecAction
0x65f1c  stloc.s  5
0x65f1e  br.s     loc_65F2E
0x65f20  ldloc.0
0x65f21  ldc.i4.0
0x65f22  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.IAction Microsoft.Windows.ManagementUI.CombinedControls.IActionCollection::Create([hasfieldmarshal] valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskActionType)
0x65f27  castclass Microsoft.Windows.ManagementUI.CombinedControls.IExecAction
0x65f2c  stloc.s  5
0x65f2e  ldloc.s  4
0x65f30  ldloca.s 5
0x65f32  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UIAction::GetExe(class Microsoft.Windows.ManagementUI.CombinedControls.IExecAction& action)
0x65f37  ldc.i4.1
0x65f38  stloc.1
0x65f39  br       loc_65FE4
0x65f3e  ldloc.s  4
0x65f40  callvirt instance valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskActionType Microsoft.Windows.ManagementUI.CombinedControls.UIAction::get_ActionType()
0x65f45  ldc.i4.5
0x65f46  bne.un.s loc_65F76
0x65f48  ldarg.2
0x65f49  brtrue.s loc_65F5B
0x65f4b  ldloc.0
0x65f4c  ldloc.2
0x65f4d  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.IAction Microsoft.Windows.ManagementUI.CombinedControls.IActionCollection::GetItem([hasfieldmarshal] int32)
0x65f52  castclass Microsoft.Windows.ManagementUI.CombinedControls.IComHandlerAction
0x65f57  stloc.s  6
0x65f59  br.s     loc_65F69
0x65f5b  ldloc.0
0x65f5c  ldc.i4.5
0x65f5d  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.IAction Microsoft.Windows.ManagementUI.CombinedControls.IActionCollection::Create([hasfieldmarshal] valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskActionType)
0x65f62  castclass Microsoft.Windows.ManagementUI.CombinedControls.IComHandlerAction
0x65f67  stloc.s  6
0x65f69  ldloc.s  4
0x65f6b  ldloca.s 6
0x65f6d  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UIAction::PutComHandlerToIComHandlerAction(class Microsoft.Windows.ManagementUI.CombinedControls.IComHandlerAction& action)
0x65f72  ldc.i4.1
0x65f73  stloc.1
0x65f74  br.s     loc_65FE4
0x65f76  ldloc.s  4
0x65f78  callvirt instance valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskActionType Microsoft.Windows.ManagementUI.CombinedControls.UIAction::get_ActionType()
0x65f7d  ldc.i4.6
0x65f7e  bne.un.s loc_65FAE
0x65f80  ldarg.2
0x65f81  brtrue.s loc_65F93
0x65f83  ldloc.0
0x65f84  ldloc.2
0x65f85  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.IAction Microsoft.Windows.ManagementUI.CombinedControls.IActionCollection::GetItem([hasfieldmarshal] int32)
0x65f8a  castclass Microsoft.Windows.ManagementUI.CombinedControls.IEmailAction
0x65f8f  stloc.s  7
0x65f91  br.s     loc_65FA1
0x65f93  ldloc.0
0x65f94  ldc.i4.6
0x65f95  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.IAction Microsoft.Windows.ManagementUI.CombinedControls.IActionCollection::Create([hasfieldmarshal] valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskActionType)
0x65f9a  castclass Microsoft.Windows.ManagementUI.CombinedControls.IEmailAction
0x65f9f  stloc.s  7
0x65fa1  ldloc.s  4
0x65fa3  ldloca.s 7
0x65fa5  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UIAction::PutEmailDataToIEmailAction(class Microsoft.Windows.ManagementUI.CombinedControls.IEmailAction& action)
0x65faa  ldc.i4.1
0x65fab  stloc.1
0x65fac  br.s     loc_65FE4
0x65fae  ldloc.s  4
0x65fb0  callvirt instance valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskActionType Microsoft.Windows.ManagementUI.CombinedControls.UIAction::get_ActionType()
0x65fb5  ldc.i4.7
0x65fb6  bne.un.s loc_65FE4
0x65fb8  ldarg.2
0x65fb9  brtrue.s loc_65FCB
0x65fbb  ldloc.0
0x65fbc  ldloc.2
0x65fbd  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.IAction Microsoft.Windows.ManagementUI.CombinedControls.IActionCollection::GetItem([hasfieldmarshal] int32)
0x65fc2  castclass Microsoft.Windows.ManagementUI.CombinedControls.IShowMessageAction
0x65fc7  stloc.s  8
0x65fc9  br.s     loc_65FD9
0x65fcb  ldloc.0
0x65fcc  ldc.i4.7
0x65fcd  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.IAction Microsoft.Windows.ManagementUI.CombinedControls.IActionCollection::Create([hasfieldmarshal] valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskActionType)
0x65fd2  castclass Microsoft.Windows.ManagementUI.CombinedControls.IShowMessageAction
0x65fd7  stloc.s  8
0x65fd9  ldloc.s  4
0x65fdb  ldloca.s 8
0x65fdd  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UIAction::PutMessageToIShowMessageAction(class Microsoft.Windows.ManagementUI.CombinedControls.IShowMessageAction& action)
0x65fe2  ldc.i4.1
0x65fe3  stloc.1
0x65fe4  ldloc.3
0x65fe5  ldc.i4.1
0x65fe6  add
0x65fe7  stloc.3
0x65fe8  ldloc.3
0x65fe9  ldarg.0
0x65fea  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UIActionList Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_ActionList()
0x65fef  callvirt instance class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.UIActionList::get_ActionsList()
0x65ff4  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x65ff9  blt      loc_65ED3
0x65ffe  leave    loc_6608B
0x66003  stloc.s  9
0x66005  ldarg.0
0x66006  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::get_UITaskService()
0x6600b  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_IsShuttingDown()
0x66010  brtrue.s loc_6603E
0x66012  ldnull
0x66013  ldstr    aMessagetaskdoe// "MessageTaskDoesNotExist"
0x66018  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x6601d  ldc.i4.2
0x6601e  newarr   [mscorlib]System.Object
0x66023  dup
0x66024  ldc.i4.0
0x66025  ldarg.0
0x66026  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_Name()
0x6602b  stelem.ref
0x6602c  dup
0x6602d  ldc.i4.1
0x6602e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x66033  stelem.ref
0x66034  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x66039  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(string errorString)
0x6603e  ldloc.s  9
0x66040  callvirt instance string [mscorlib]System.Exception::get_Message()
0x66045  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::SystemError(string errorString)
0x6604a  leave.s  loc_6608B
0x6604c  ldarg.0
0x6604d  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::get_UITaskService()
0x66052  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_IsShuttingDown()
0x66057  brtrue.s loc_66068
0x66059  ldstr    aMessagefoldern// "MessageFolderNotFound"
0x6605e  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x66063  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(string errorString)
0x66068  callvirt instance string [mscorlib]System.Exception::get_Message()
0x6606d  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::SystemError(string errorString)
0x66072  leave.s  loc_6608B
0x66074  stloc.s  0xA
0x66076  ldarg.0
0x66077  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::get_UITaskService()
0x6607c  ldloc.s  0xA
0x6607e  ldarg.0
0x6607f  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_Name()
0x66084  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::ProcessServiceErrors(class [mscorlib]System.Exception e, string taskName)
0x66089  leave.s  loc_6608B
0x6608b  ldloc.1
0x6608c  ret
```
