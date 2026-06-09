# Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::EndTask_0

- ea: `0x80bd0`
- end: `0x80c15`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::EndTask_0`
- size: `69`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x80b30`

## callees

- `0x12ed0`
- `0x13280`
- `0x133f0`
- `0x656f0`
- `0x80bd0`
- `0x80c20`

## string_xrefs

- `0x80bdf`: `ApplicationTaskScheduler`
- `0x80bd5`: `UserQuestionEndTask`
- `0x80c04`: `MessageNoEndTask`

## pseudocode

```c

```

## disassembly

```asm
0x80bd0  ldc.i4.1
0x80bd1  stloc.0
0x80bd2  ldarg.2
0x80bd3  brfalse.s loc_80BF1
0x80bd5  ldstr    aUserquestionen_0// "UserQuestionEndTask"
0x80bda  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x80bdf  ldstr    aApplicationtas// "ApplicationTaskScheduler"
0x80be4  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x80be9  call     valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult Microsoft.Windows.ManagementUI.CombinedControls.QueryMessage::QueryUser(string message, string caption)
0x80bee  ldc.i4.6
0x80bef  bne.un.s loc_80BF8
0x80bf1  ldarg.1
0x80bf2  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.UITask::EndTask()
0x80bf7  stloc.0
0x80bf8  ldloc.0
0x80bf9  brfalse.s loc_80C04
0x80bfb  ldarg.0
0x80bfc  ldarg.1
0x80bfd  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::UpdateTaskStatus(class Microsoft.Windows.ManagementUI.CombinedControls.UITask task)
0x80c02  br.s     loc_80C13
0x80c04  ldstr    aMessagenoendta// "MessageNoEndTask"
0x80c09  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x80c0e  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(string errorString)
0x80c13  ldloc.0
0x80c14  ret
```
