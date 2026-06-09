# Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::DeterminePastTaskActivityFromTaskSchedulerEvents

- ea: `0x7ddf0`
- end: `0x7e13d`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::DeterminePastTaskActivityFromTaskSchedulerEvents`
- size: `845`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callers

- `0x7dcd0`

## callees

- `0x12860`
- `0x12ed0`
- `0x32ea0`
- `0x33e70`
- `0x38820`
- `0x4d110`
- `0x4d140`
- `0x4d150`
- `0x4d1c0`
- `0x67c80`
- `0x68220`
- `0x685f0`
- `0x7ddf0`
- `0x7e140`
- `0x7e7e0`
- `0x7efa0`
- `0xa2740`

## string_xrefs

- `0x7df05`: `Microsoft-Windows-TaskScheduler/Operational`
- `0x7e0e0`: `JobsServiceException`
- `0x7dec9`: `) and TimeCreated[@SystemTime>='`

## pseudocode

```c

```

## disassembly

```asm
0x7ddf0  ldarg.0
0x7ddf1  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class PastTaskActivityData> Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::pastTaskActivityDictionary
0x7ddf6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class PastTaskActivityData>::Clear()
0x7ddfb  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x7de00  stloc.0
0x7de01  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x7de06  stloc.1
0x7de07  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x7de0c  stloc.2
0x7de0d  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x7de12  stloc.3
0x7de13  ldarg.0
0x7de14  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::secondThreadTaskService
0x7de19  ldarg.0
0x7de1a  ldfld    class [System]System.ComponentModel.BackgroundWorker Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::dataReaderThread
0x7de1f  ldarg.1
0x7de20  ldarg.0
0x7de21  ldflda   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Windows.ManagementUI.CombinedControls.UITask> Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::allTasksDictionary
0x7de26  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::GetAllTasksDictionary(object sender, class [System]System.ComponentModel.DoWorkEventArgs e, [out] class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Windows.ManagementUI.CombinedControls.UITask>& taskList)
0x7de2b  brfalse  loc_7E0E0
0x7de30  ldarg.0
0x7de31  ldfld    class [System]System.ComponentModel.BackgroundWorker Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::dataReaderThread
0x7de36  callvirt instance bool [System]System.ComponentModel.BackgroundWorker::get_CancellationPending()
0x7de3b  brtrue   loc_7E0F0
0x7de40  ldarg.0
0x7de41  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::secondThreadTaskService
0x7de46  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UIEventLogService Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_EventLogService()
0x7de4b  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext Microsoft.Windows.ManagementUI.CombinedControls.UIEventLogService::get_Context()
0x7de50  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::get_Session()
0x7de55  callvirt instance native int Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle::get_Handle()
0x7de5a  stloc.0
0x7de5b  ldc.i4.s 0x10
0x7de5d  newarr   [mscorlib]System.Int32
0x7de62  dup
0x7de63  ldtoken  valuetype __StaticArrayInitTypeSize=64 <PrivateImplementationDetails>::'9AC9FA158AA17BE30A91C0AA2F6CD9B6DA8084C9A41A58F420520944DE39313B'
0x7de68  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::InitializeArray(class [mscorlib]System.Array, valuetype [mscorlib]System.RuntimeFieldHandle)
0x7de6d  stloc.s  5
0x7de6f  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x7de74  stloc.s  6
0x7de76  ldloc.s  6
0x7de78  ldstr    aSystem_1// "*[System[("
0x7de7d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x7de82  pop
0x7de83  ldc.i4.0
0x7de84  stloc.s  0xA
0x7de86  br.s     loc_7DEBF
0x7de88  ldloc.s  6
0x7de8a  ldstr    aEventid_1// "EventID="
0x7de8f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x7de94  pop
0x7de95  ldloc.s  6
0x7de97  ldloc.s  5
0x7de99  ldloc.s  0xA
0x7de9b  ldelem.i4
0x7de9c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(int32)
0x7dea1  pop
0x7dea2  ldloc.s  0xA
0x7dea4  ldc.i4.1
0x7dea5  add
0x7dea6  ldloc.s  5
0x7dea8  ldlen
0x7dea9  conv.i4
0x7deaa  bge.s    loc_7DEB9
0x7deac  ldloc.s  6
0x7deae  ldstr    aOr// " or "
0x7deb3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x7deb8  pop
0x7deb9  ldloc.s  0xA
0x7debb  ldc.i4.1
0x7debc  add
0x7debd  stloc.s  0xA
0x7debf  ldloc.s  0xA
0x7dec1  ldloc.s  5
0x7dec3  ldlen
0x7dec4  conv.i4
0x7dec5  blt.s    loc_7DE88
0x7dec7  ldloc.s  6
0x7dec9  ldstr    aAndTimecreated_0// ") and TimeCreated[@SystemTime>='"
0x7dece  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x7ded3  pop
0x7ded4  ldloc.s  6
0x7ded6  ldarg.0
0x7ded7  ldflda   valuetype [mscorlib]System.DateTime Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::refreshTime
0x7dedc  ldarg.0
0x7dedd  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::pastTaskActivityControl
0x7dee2  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.Windows.ManagementUI.CombinedControls.PastTaskActivitySummaryControl::get_UserChosenTimeSpan()
0x7dee7  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::Subtract(valuetype [mscorlib]System.TimeSpan)
0x7deec  call     string Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::GetCrimsonDateTime(valuetype [mscorlib]System.DateTime dt)
0x7def1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x7def6  pop
0x7def7  ldloc.s  6
0x7def9  ldstr    asc_B7262// "']]]"
0x7defe  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x7df03  pop
0x7df04  ldloc.0
0x7df05  ldstr    aMicrosoftWindo_1// "Microsoft-Windows-TaskScheduler/Operati"...
0x7df0a  ldloc.s  6
0x7df0c  callvirt instance string [mscorlib]System.Object::ToString()
0x7df11  ldc.i4   0x101
0x7df16  call     native int Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::QueryLog(native int session, [hasfieldmarshal] string path, [hasfieldmarshal] string query, int32 flags)
0x7df1b  stloc.1
0x7df1c  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x7df21  stloc.s  4
0x7df23  ldloc.1
0x7df24  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x7df29  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x7df2e  brfalse.s loc_7DF6F
0x7df30  ldnull
0x7df31  ldstr    aCrimsonexcepti// "CrimsonException"
0x7df36  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7df3b  ldc.i4.1
0x7df3c  newarr   [mscorlib]System.Object
0x7df41  dup
0x7df42  ldc.i4.0
0x7df43  ldloca.s 4
0x7df45  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7df4a  ldtoken  [mscorlib]System.Int32
0x7df4f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7df54  callvirt instance object [mscorlib]System.Globalization.CultureInfo::GetFormat(class [mscorlib]System.Type)
0x7df59  castclass [mscorlib]System.IFormatProvider
0x7df5e  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x7df63  stelem.ref
0x7df64  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x7df69  newobj   instance void ReadingDataFailedException::.ctor(string errorMsg)
0x7df6e  throw
0x7df6f  ldc.i4   0x400
0x7df74  stloc.s  7
0x7df76  ldloc.s  7
0x7df78  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::AllocHGlobal(int32)
0x7df7d  stloc.3
0x7df7e  ldc.i4   0x100
0x7df83  newarr   [mscorlib]System.IntPtr
0x7df88  stloc.s  8
0x7df8a  ldc.i4.0
0x7df8b  stloc.s  9
0x7df8d  br       loc_7E0CE
0x7df92  ldloc.1
0x7df93  ldc.i4   0x100
0x7df98  ldloc.s  8
0x7df9a  ldc.i4.m1
0x7df9b  ldc.i4.0
0x7df9c  ldloca.s 9
0x7df9e  call     bool Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::GetNextBatch(native int queryHandle, int32 eventSize, [hasfieldmarshal] native int[] events, int32 timeout, int32 flags, int32& returned)
0x7dfa3  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x7dfa8  stloc.s  4
0x7dfaa  brfalse  loc_7E081
0x7dfaf  ldc.i4.0
0x7dfb0  stloc.s  0xB
0x7dfb2  br       loc_7E076
0x7dfb7  ldc.i4.1
0x7dfb8  ldc.i4.1
0x7dfb9  newarr   [mscorlib]System.String
0x7dfbe  dup
0x7dfbf  ldc.i4.0
0x7dfc0  ldstr    aEventSystemEve// "Event/System/EventID"
0x7dfc5  stelem.ref
0x7dfc6  ldc.i4.0
0x7dfc7  call     native int Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::CreateRenderContext(int32 countOfValues, string[] valuePaths, int32 flags)
0x7dfcc  stloc.2
0x7dfcd  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x7dfd2  stloc.s  4
0x7dfd4  ldloc.2
0x7dfd5  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x7dfda  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x7dfdf  brfalse.s loc_7E020
0x7dfe1  ldnull
0x7dfe2  ldstr    aCrimsonexcepti// "CrimsonException"
0x7dfe7  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7dfec  ldc.i4.1
0x7dfed  newarr   [mscorlib]System.Object
0x7dff2  dup
0x7dff3  ldc.i4.0
0x7dff4  ldloca.s 4
0x7dff6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7dffb  ldtoken  [mscorlib]System.Int32
0x7e000  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7e005  callvirt instance object [mscorlib]System.Globalization.CultureInfo::GetFormat(class [mscorlib]System.Type)
0x7e00a  castclass [mscorlib]System.IFormatProvider
0x7e00f  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x7e014  stelem.ref
0x7e015  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x7e01a  newobj   instance void ReadingDataFailedException::.ctor(string errorMsg)
0x7e01f  throw
0x7e020  ldarg.0
0x7e021  ldloc.s  8
0x7e023  ldloc.s  0xB
0x7e025  ldelem.i
0x7e026  ldloc.2
0x7e027  ldloca.s 3
0x7e029  ldloca.s 7
0x7e02b  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::RenderCrimsonEvent(native int hEvent, native int evtRenderContext, native int& buffer, int32& bufferSize)
0x7e030  ldloc.3
0x7e031  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x7e036  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7e03b  call     object [mscorlib]System.Runtime.InteropServices.Marshal::PtrToStructure(native int, class [mscorlib]System.Type)
0x7e040  unbox.any Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x7e045  call     object Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::VariantToObject(valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventVariant var)
0x7e04a  unbox.any [mscorlib]System.UInt16
0x7e04f  stloc.s  0xC
0x7e051  ldarg.0
0x7e052  ldloc.s  0xC
0x7e054  ldloc.s  8
0x7e056  ldloc.s  0xB
0x7e058  ldelem.i
0x7e059  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::ProcessTaskSchedulerEvent(unsigned int16 eventID, native int hEvent)
0x7e05e  ldloc.s  8
0x7e060  ldloc.s  0xB
0x7e062  ldelem.i
0x7e063  call     bool Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::CloseHandle(native int eventHandle)
0x7e068  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x7e06d  stloc.s  4
0x7e06f  pop
0x7e070  ldloc.s  0xB
0x7e072  ldc.i4.1
0x7e073  add
0x7e074  stloc.s  0xB
0x7e076  ldloc.s  0xB
0x7e078  ldloc.s  9
0x7e07a  blt      loc_7DFB7
0x7e07f  br.s     loc_7E0CE
0x7e081  ldloc.s  4
0x7e083  ldc.i4   0x103
0x7e088  bne.un.s loc_7E08F
0x7e08a  leave    loc_7E13C
0x7e08f  ldnull
0x7e090  ldstr    aCrimsonexcepti// "CrimsonException"
0x7e095  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7e09a  ldc.i4.1
0x7e09b  newarr   [mscorlib]System.Object
0x7e0a0  dup
0x7e0a1  ldc.i4.0
0x7e0a2  ldloca.s 4
0x7e0a4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7e0a9  ldtoken  [mscorlib]System.Int32
0x7e0ae  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7e0b3  callvirt instance object [mscorlib]System.Globalization.CultureInfo::GetFormat(class [mscorlib]System.Type)
0x7e0b8  castclass [mscorlib]System.IFormatProvider
0x7e0bd  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x7e0c2  stelem.ref
0x7e0c3  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x7e0c8  newobj   instance void ReadingDataFailedException::.ctor(string errorMsg)
0x7e0cd  throw
0x7e0ce  ldarg.0
0x7e0cf  ldfld    class [System]System.ComponentModel.BackgroundWorker Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::dataReaderThread
0x7e0d4  callvirt instance bool [System]System.ComponentModel.BackgroundWorker::get_CancellationPending()
0x7e0d9  brfalse  loc_7DF92
0x7e0de  leave.s  loc_7E13C
0x7e0e0  ldstr    aJobsserviceexc// "JobsServiceException"
0x7e0e5  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7e0ea  newobj   instance void ReadingDataFailedException::.ctor(string errorMsg)
0x7e0ef  throw
0x7e0f0  leave.s  loc_7E13C
0x7e0f2  ldloc.1
0x7e0f3  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x7e0f8  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x7e0fd  brfalse.s loc_7E10D
0x7e0ff  ldloc.1
0x7e100  call     bool Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::CloseHandle(native int eventHandle)
0x7e105  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x7e10a  stloc.s  4
0x7e10c  pop
0x7e10d  ldloc.2
0x7e10e  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x7e113  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x7e118  brfalse.s loc_7E128
0x7e11a  ldloc.2
0x7e11b  call     bool Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::CloseHandle(native int eventHandle)
0x7e120  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x7e125  stloc.s  4
0x7e127  pop
0x7e128  ldloc.3
0x7e129  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x7e12e  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x7e133  brfalse.s loc_7E13B
0x7e135  ldloc.3
0x7e136  call     void [mscorlib]System.Runtime.InteropServices.Marshal::FreeHGlobal(native int)
0x7e13b  endfinally
0x7e13c  ret
```
