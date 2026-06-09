# Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::GetEvent

- ea: `0x426f0`
- end: `0x42777`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::GetEvent`
- size: `135`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x420e0`

## callees

- `0x12860`
- `0x13510`
- `0x3aea0`
- `0x3afa0`
- `0x3cc00`
- `0x426f0`
- `0x4d1a0`
- `0x4d1b0`

## string_xrefs

- `0x4271c`: `Failed to create bookmark in background fetch`
- `0x42739`: `Failed to update bookmark in background fetch`

## pseudocode

```c

```

## disassembly

```asm
0x426f0  ldarg.3
0x426f1  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x426f6  stind.i
0x426f7  ldc.i4.0
0x426f8  stloc.0
0x426f9  ldarg.2
0x426fa  brfalse.s loc_42744
0x426fc  ldarg.3
0x426fd  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x42702  call     native int Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::CreateBookMarkBuffer(native int buff)
0x42707  stind.i
0x42708  ldarg.3
0x42709  ldind.i
0x4270a  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x4270f  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x42714  brfalse.s loc_42729
0x42716  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x4271b  stloc.0
0x4271c  ldstr    aFailedToCreate// "Failed to create bookmark in background"...
0x42721  ldloc.0
0x42722  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x42727  br.s     loc_42744
0x42729  ldarg.3
0x4272a  ldind.i
0x4272b  ldarg.1
0x4272c  call     bool Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::UpdateBookMark(native int bookMark, native int eventHandle)
0x42731  brtrue.s loc_42744
0x42733  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x42738  stloc.0
0x42739  ldstr    aFailedToUpdate// "Failed to update bookmark in background"...
0x4273e  ldloc.0
0x4273f  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x42744  ldarg.1
0x42745  ldarg.0
0x42746  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::context
0x4274b  ldarg.0
0x4274c  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::safeLiteRecordContext
0x42751  callvirt instance native int Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle::get_Handle()
0x42756  call     class Microsoft.Windows.ManagementUI.CombinedControls.LiteEventRecord Microsoft.Windows.ManagementUI.CombinedControls.CrimsonEvent::GetLiteRecord(native int evtPtr, class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext vwrCtx, native int liteRecordContext)
0x4275b  stloc.1
0x4275c  ldloc.1
0x4275d  ldarg.1
0x4275e  stfld    native int Microsoft.Windows.ManagementUI.CombinedControls.LiteEventRecord::EventHandle
0x42763  ldarg.1
0x42764  ldloc.1
0x42765  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.CrimsonEvent::.ctor(native int hEvent, class Microsoft.Windows.ManagementUI.CombinedControls.LiteEventRecord evtRec)
0x4276a  dup
0x4276b  ldarg.0
0x4276c  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::context
0x42771  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.CrimsonEvent::set_Context(class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext value)
0x42776  ret
```
