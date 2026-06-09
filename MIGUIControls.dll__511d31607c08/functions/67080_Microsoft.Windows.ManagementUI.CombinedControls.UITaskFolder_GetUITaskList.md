# Microsoft.Windows.ManagementUI.CombinedControls.UITaskFolder::GetUITaskList

- ea: `0x67080`
- end: `0x671b6`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.UITaskFolder::GetUITaskList`
- size: `310`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x671c0`
- `0x816a0`

## callees

- `0x12ed0`
- `0x133f0`
- `0x5d760`
- `0x5d7f0`
- `0x645c0`
- `0x64870`
- `0x66b70`
- `0x66b80`
- `0x66ba0`
- `0x66bd0`
- `0x66ff0`
- `0x67080`
- `0x67c50`
- `0x67ec0`
- `0x83d10`

## string_xrefs

- `0x6711c`: `AccessTaskDenied`

## pseudocode

```c

```

## disassembly

```asm
0x67080  ldnull
0x67081  stloc.0
0x67082  ldnull
0x67083  stloc.1
0x67084  ldc.i4.0
0x67085  stloc.s  4
0x67087  ldarg.1
0x67088  isinst   [System]System.ComponentModel.BackgroundWorker
0x6708d  stloc.s  5
0x6708f  ldc.i4.0
0x67090  stloc.s  6
0x67092  ldarg.0
0x67093  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::IsValid()
0x67098  brfalse  loc_6719D
0x6709d  ldloc.s  5
0x6709f  brfalse.s loc_670AD
0x670a1  ldloc.s  5
0x670a3  callvirt instance bool [System]System.ComponentModel.BackgroundWorker::get_CancellationPending()
0x670a8  brtrue   loc_6719D
0x670ad  nop
0x670ae  ldarg.s  4
0x670b0  brfalse.s loc_670B5
0x670b2  ldc.i4.1
0x670b3  stloc.s  4
0x670b5  ldarg.0
0x670b6  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ITaskFolder Microsoft.Windows.ManagementUI.CombinedControls.UITaskFolder::secureITaskFolder
0x670bb  ldloc.s  4
0x670bd  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.IRegisteredTaskCollection Microsoft.Windows.ManagementUI.CombinedControls.ITaskFolder::GetTasks(valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskEnumFlags flags)
0x670c2  stloc.1
0x670c3  ldarg.0
0x670c4  ldloc.1
0x670c5  call     class Microsoft.Windows.ManagementUI.CombinedControls.UITaskList Microsoft.Windows.ManagementUI.CombinedControls.UITaskList::GetUITaskList(class Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase parent, class Microsoft.Windows.ManagementUI.CombinedControls.IRegisteredTaskCollection secureInterface)
0x670ca  stloc.0
0x670cb  ldloc.0
0x670cc  ldnull
0x670cd  cgt.un
0x670cf  ldarg.3
0x670d0  and
0x670d1  brfalse  loc_67158
0x670d6  ldc.i4.0
0x670d7  stloc.s  6
0x670d9  ldloc.0
0x670da  callvirt instance int32 Microsoft.Windows.ManagementUI.CombinedControls.UITaskList::get_Count()
0x670df  ldc.i4.1
0x670e0  sub
0x670e1  stloc.3
0x670e2  br.s     loc_67154
0x670e4  ldloc.0
0x670e5  ldloc.3
0x670e6  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.UITaskList::get_Item(int32 index)
0x670eb  stloc.2
0x670ec  ldloc.2
0x670ed  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.UITask::LoadFromTaskDefinition()
0x670f2  brtrue.s loc_670FB
0x670f4  ldloc.0
0x670f5  ldloc.3
0x670f6  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskList::RemoveAt(int32 index)
0x670fb  ldc.i4.s 0x64
0x670fd  ldloc.s  6
0x670ff  ldc.i4.1
0x67100  add
0x67101  dup
0x67102  stloc.s  6
0x67104  bne.un.s loc_67118
0x67106  ldloc.s  5
0x67108  brfalse.s loc_67115
0x6710a  ldloc.s  5
0x6710c  callvirt instance bool [System]System.ComponentModel.BackgroundWorker::get_CancellationPending()
0x67111  brfalse.s loc_67115
0x67113  leave.s  loc_67158
0x67115  ldc.i4.0
0x67116  stloc.s  6
0x67118  leave.s  loc_67150
0x6711a  pop
0x6711b  ldnull
0x6711c  ldstr    aAccesstaskdeni// "AccessTaskDenied"
0x67121  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x67126  ldc.i4.2
0x67127  newarr   [mscorlib]System.Object
0x6712c  dup
0x6712d  ldc.i4.0
0x6712e  ldloc.2
0x6712f  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_Name()
0x67134  stelem.ref
0x67135  dup
0x67136  ldc.i4.1
0x67137  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x6713c  stelem.ref
0x6713d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x67142  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(string errorString)
0x67147  ldloc.0
0x67148  ldloc.3
0x67149  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskList::RemoveAt(int32 index)
0x6714e  leave.s  loc_67150
0x67150  ldloc.3
0x67151  ldc.i4.1
0x67152  sub
0x67153  stloc.3
0x67154  ldloc.3
0x67155  ldc.i4.0
0x67156  bge.s    loc_670E4
0x67158  leave.s  loc_6719D
0x6715a  stloc.s  7
0x6715c  ldarg.0
0x6715d  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::get_UITaskService()
0x67162  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_IsShuttingDown()
0x67167  brtrue.s loc_67175
0x67169  ldloc.s  7
0x6716b  callvirt instance string [mscorlib]System.Exception::get_Message()
0x67170  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(string errorString)
0x67175  leave.s  loc_6719D
0x67177  stloc.s  8
0x67179  ldsfld   string [mscorlib]System.String::Empty
0x6717e  ldarg.0
0x6717f  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.UITaskFolder::get_Name()
0x67184  ldloc.s  8
0x67186  newobj   instance void [mscorlib]System.IO.FileNotFoundException::.ctor(string, string, class [mscorlib]System.Exception)
0x6718b  throw
0x6718c  stloc.s  9
0x6718e  ldarg.0
0x6718f  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::get_UITaskService()
0x67194  ldloc.s  9
0x67196  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::ProcessServiceErrors(class [mscorlib]System.Exception e)
0x6719b  leave.s  loc_6719D
0x6719d  ldloc.s  5
0x6719f  brfalse.s loc_671B4
0x671a1  ldarg.2
0x671a2  brfalse.s loc_671B4
0x671a4  ldloc.s  5
0x671a6  callvirt instance bool [System]System.ComponentModel.BackgroundWorker::get_CancellationPending()
0x671ab  brfalse.s loc_671B4
0x671ad  ldarg.2
0x671ae  ldc.i4.1
0x671af  callvirt instance void [System]System.ComponentModel.CancelEventArgs::set_Cancel(bool)
0x671b4  ldloc.0
0x671b5  ret
```
