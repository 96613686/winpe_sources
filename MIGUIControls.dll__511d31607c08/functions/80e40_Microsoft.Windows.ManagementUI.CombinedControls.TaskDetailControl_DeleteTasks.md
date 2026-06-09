# Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::DeleteTasks

- ea: `0x80e40`
- end: `0x81042`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::DeleteTasks`
- size: `514`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x82200`
- `0x82590`

## callees

- `0x12ed0`
- `0x13280`
- `0x645c0`
- `0x676c0`
- `0x7cd60`
- `0x7cf40`
- `0x80370`
- `0x80930`
- `0x80e40`

## string_xrefs

- `0x80ec2`: `ApplicationTaskScheduler`
- `0x80e9f`: `UserQuestionDeleteTask`
- `0x80eb4`: `UserQuestionDeleteMultipleTasks`

## pseudocode

```c

```

## disassembly

```asm
0x80e40  ldc.i4.1
0x80e41  stloc.0
0x80e42  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x80e47  stloc.1
0x80e48  ldarg.0
0x80e49  call     instance class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::get_SelectedTasks()
0x80e4e  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x80e53  stloc.2
0x80e54  br.s     loc_80E6F
0x80e56  ldloc.2
0x80e57  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x80e5c  castclass Microsoft.Windows.ManagementUI.CombinedControls.UITask
0x80e61  stloc.3
0x80e62  ldloc.1
0x80e63  ldloc.3
0x80e64  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_Name()
0x80e69  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x80e6e  pop
0x80e6f  ldloc.2
0x80e70  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x80e75  brtrue.s loc_80E56
0x80e77  leave.s  loc_80E8D
0x80e79  ldloc.2
0x80e7a  isinst   [mscorlib]System.IDisposable
0x80e7f  stloc.s  4
0x80e81  ldloc.s  4
0x80e83  brfalse.s loc_80E8C
0x80e85  ldloc.s  4
0x80e87  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x80e8c  endfinally
0x80e8d  ldloc.1
0x80e8e  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x80e93  ldc.i4.0
0x80e94  ble      loc_81035
0x80e99  ldc.i4.1
0x80e9a  stloc.s  5
0x80e9c  ldarg.1
0x80e9d  brfalse.s loc_80ED7
0x80e9f  ldstr    aUserquestionde// "UserQuestionDeleteTask"
0x80ea4  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x80ea9  stloc.s  6
0x80eab  ldloc.1
0x80eac  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x80eb1  ldc.i4.1
0x80eb2  ble.s    loc_80EC0
0x80eb4  ldstr    aUserquestionde_0// "UserQuestionDeleteMultipleTasks"
0x80eb9  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x80ebe  stloc.s  6
0x80ec0  ldloc.s  6
0x80ec2  ldstr    aApplicationtas// "ApplicationTaskScheduler"
0x80ec7  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x80ecc  call     valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult Microsoft.Windows.ManagementUI.CombinedControls.QueryMessage::QueryUser(string message, string caption)
0x80ed1  ldc.i4.6
0x80ed2  beq.s    loc_80ED7
0x80ed4  ldc.i4.0
0x80ed5  stloc.s  5
0x80ed7  ldloc.s  5
0x80ed9  brfalse  loc_81035
0x80ede  ldc.i4.0
0x80edf  stloc.s  7
0x80ee1  ldarg.0
0x80ee2  ldfld    object Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::listViewMainSyncRoot
0x80ee7  stloc.s  8
0x80ee9  ldc.i4.0
0x80eea  stloc.s  9
0x80eec  ldloc.s  8
0x80eee  ldloca.s 9
0x80ef0  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x80ef5  ldloc.1
0x80ef6  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x80efb  stloc.2
0x80efc  br.s     loc_80F58
0x80efe  ldloc.2
0x80eff  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x80f04  castclass [mscorlib]System.String
0x80f09  stloc.s  0xA
0x80f0b  ldarg.0
0x80f0c  ldloc.s  0xA
0x80f0e  call     instance int32 Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::FindTaskInList(string taskName)
0x80f13  stloc.s  7
0x80f15  ldarg.0
0x80f16  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase Microsoft.Windows.ManagementUI.CombinedControls.BaseResultsControl::get_DataModel()
0x80f1b  castclass Microsoft.Windows.ManagementUI.CombinedControls.UITaskFolder
0x80f20  ldloc.s  0xA
0x80f22  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.UITaskFolder::DeleteTask(string taskName)
0x80f27  brfalse.s loc_80F3D
0x80f29  ldarg.0
0x80f2a  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::listViewMain
0x80f2f  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ListView/ListViewItemCollection [System.Windows.Forms]System.Windows.Forms.ListView::get_Items()
0x80f34  ldloc.s  7
0x80f36  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView/ListViewItemCollection::RemoveAt(int32)
0x80f3b  br.s     loc_80F3F
0x80f3d  ldc.i4.0
0x80f3e  stloc.0
0x80f3f  leave.s  loc_80F58
0x80f41  pop
0x80f42  ldarg.0
0x80f43  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::listViewMain
0x80f48  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ListView/ListViewItemCollection [System.Windows.Forms]System.Windows.Forms.ListView::get_Items()
0x80f4d  ldloc.s  7
0x80f4f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView/ListViewItemCollection::RemoveAt(int32)
0x80f54  ldc.i4.0
0x80f55  stloc.0
0x80f56  leave.s  loc_80F58
0x80f58  ldloc.2
0x80f59  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x80f5e  brtrue.s loc_80EFE
0x80f60  leave.s  loc_80F76
0x80f62  ldloc.2
0x80f63  isinst   [mscorlib]System.IDisposable
0x80f68  stloc.s  4
0x80f6a  ldloc.s  4
0x80f6c  brfalse.s loc_80F75
0x80f6e  ldloc.s  4
0x80f70  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x80f75  endfinally
0x80f76  leave.s  loc_80F84
0x80f78  ldloc.s  9
0x80f7a  brfalse.s loc_80F83
0x80f7c  ldloc.s  8
0x80f7e  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x80f83  endfinally
0x80f84  ldarg.0
0x80f85  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::listViewMain
0x80f8a  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ListView/ListViewItemCollection [System.Windows.Forms]System.Windows.Forms.ListView::get_Items()
0x80f8f  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.ListView/ListViewItemCollection::get_Count()
0x80f94  ldc.i4.1
0x80f95  bne.un.s loc_80FE0
0x80f97  ldarg.0
0x80f98  ldfld    object Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::listViewMainSyncRoot
0x80f9d  stloc.s  8
0x80f9f  ldc.i4.0
0x80fa0  stloc.s  9
0x80fa2  ldloc.s  8
0x80fa4  ldloca.s 9
0x80fa6  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x80fab  ldarg.0
0x80fac  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::listViewMain
0x80fb1  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ListView/SelectedListViewItemCollection [System.Windows.Forms]System.Windows.Forms.ListView::get_SelectedItems()
0x80fb6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView/SelectedListViewItemCollection::Clear()
0x80fbb  ldarg.0
0x80fbc  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::listViewMain
0x80fc1  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ListView/ListViewItemCollection [System.Windows.Forms]System.Windows.Forms.ListView::get_Items()
0x80fc6  ldc.i4.0
0x80fc7  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ListViewItem [System.Windows.Forms]System.Windows.Forms.ListView/ListViewItemCollection::get_Item(int32)
0x80fcc  ldc.i4.1
0x80fcd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListViewItem::set_Selected(bool)
0x80fd2  leave.s  loc_81035
0x80fd4  ldloc.s  9
0x80fd6  brfalse.s loc_80FDF
0x80fd8  ldloc.s  8
0x80fda  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x80fdf  endfinally
0x80fe0  ldloc.s  7
0x80fe2  ldc.i4.0
0x80fe3  ble.s    loc_81035
0x80fe5  ldloc.s  7
0x80fe7  ldc.i4.1
0x80fe8  sub
0x80fe9  stloc.s  7
0x80feb  ldarg.0
0x80fec  ldfld    object Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::listViewMainSyncRoot
0x80ff1  stloc.s  8
0x80ff3  ldc.i4.0
0x80ff4  stloc.s  9
0x80ff6  ldloc.s  8
0x80ff8  ldloca.s 9
0x80ffa  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x80fff  ldarg.0
0x81000  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::listViewMain
0x81005  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ListView/SelectedListViewItemCollection [System.Windows.Forms]System.Windows.Forms.ListView::get_SelectedItems()
0x8100a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView/SelectedListViewItemCollection::Clear()
0x8100f  ldarg.0
0x81010  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::listViewMain
0x81015  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ListView/ListViewItemCollection [System.Windows.Forms]System.Windows.Forms.ListView::get_Items()
0x8101a  ldloc.s  7
0x8101c  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ListViewItem [System.Windows.Forms]System.Windows.Forms.ListView/ListViewItemCollection::get_Item(int32)
0x81021  ldc.i4.1
0x81022  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListViewItem::set_Selected(bool)
0x81027  leave.s  loc_81035
0x81029  ldloc.s  9
0x8102b  brfalse.s loc_81034
0x8102d  ldloc.s  8
0x8102f  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x81034  endfinally
0x81035  leave.s  loc_81040
0x81037  pop
0x81038  ldarg.0
0x81039  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.BaseResultsControl::HandleServiceUnavailableException()
0x8103e  leave.s  loc_81040
0x81040  ldloc.0
0x81041  ret
```
