# Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::EndTask

- ea: `0x80b30`
- end: `0x80bd0`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::EndTask`
- size: `160`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x82260`

## callees

- `0x12ed0`
- `0x13280`
- `0x1b4d0`
- `0x7cf40`
- `0x80370`
- `0x80b30`
- `0x80bd0`

## string_xrefs

- `0x80b6e`: `ApplicationTaskScheduler`
- `0x80b55`: `UserQuestionEndTask`
- `0x80b62`: `UserQuestionEndTasks`

## pseudocode

```c

```

## disassembly

```asm
0x80b30  ldc.i4.1
0x80b31  stloc.0
0x80b32  ldc.i4   0x13EB
0x80b37  call     void Microsoft.Windows.ManagementUI.CombinedControls.SnapInFeedback::IncrementGlobalDatapoint(valuetype Microsoft.Windows.ManagementUI.CombinedControls.FeedbackDatapoint datapoint)
0x80b3c  ldarg.0
0x80b3d  call     instance class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::get_SelectedTasks()
0x80b42  stloc.1
0x80b43  ldloc.1
0x80b44  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x80b49  ldc.i4.0
0x80b4a  ble.s    loc_80BC1
0x80b4c  ldloc.1
0x80b4d  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x80b52  ldc.i4.1
0x80b53  bne.un.s loc_80B62
0x80b55  ldstr    aUserquestionen_0// "UserQuestionEndTask"
0x80b5a  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x80b5f  stloc.2
0x80b60  br.s     loc_80B6D
0x80b62  ldstr    aUserquestionen_1// "UserQuestionEndTasks"
0x80b67  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x80b6c  stloc.2
0x80b6d  ldloc.2
0x80b6e  ldstr    aApplicationtas// "ApplicationTaskScheduler"
0x80b73  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x80b78  call     valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult Microsoft.Windows.ManagementUI.CombinedControls.QueryMessage::QueryUser(string message, string caption)
0x80b7d  ldc.i4.6
0x80b7e  bne.un.s loc_80BC1
0x80b80  ldloc.1
0x80b81  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x80b86  stloc.3
0x80b87  br.s     loc_80BA3
0x80b89  ldloc.3
0x80b8a  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x80b8f  castclass Microsoft.Windows.ManagementUI.CombinedControls.UITask
0x80b94  stloc.s  4
0x80b96  ldarg.0
0x80b97  ldloc.s  4
0x80b99  ldc.i4.0
0x80b9a  call     instance bool Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::EndTask(class Microsoft.Windows.ManagementUI.CombinedControls.UITask task, bool queryUser)
0x80b9f  stloc.0
0x80ba0  ldloc.0
0x80ba1  brfalse.s loc_80BAB
0x80ba3  ldloc.3
0x80ba4  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x80ba9  brtrue.s loc_80B89
0x80bab  leave.s  loc_80BC1
0x80bad  ldloc.3
0x80bae  isinst   [mscorlib]System.IDisposable
0x80bb3  stloc.s  5
0x80bb5  ldloc.s  5
0x80bb7  brfalse.s loc_80BC0
0x80bb9  ldloc.s  5
0x80bbb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x80bc0  endfinally
0x80bc1  leave.s  loc_80BCE
0x80bc3  pop
0x80bc4  ldc.i4.0
0x80bc5  stloc.0
0x80bc6  ldarg.0
0x80bc7  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.BaseResultsControl::HandleServiceUnavailableException()
0x80bcc  leave.s  loc_80BCE
0x80bce  ldloc.0
0x80bcf  ret
```
