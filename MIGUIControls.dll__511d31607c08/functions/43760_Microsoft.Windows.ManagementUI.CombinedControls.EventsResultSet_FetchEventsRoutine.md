# Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::FetchEventsRoutine

- ea: `0x43760`
- end: `0x43a60`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::FetchEventsRoutine`
- size: `768`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callees

- `0x12860`
- `0x13510`
- `0x35010`
- `0x36630`
- `0x42dd0`
- `0x43760`
- `0x4d110`
- `0x4d160`
- `0x4d1a0`
- `0x4d1b0`

## string_xrefs

- `0x43968`: `Failed to create bookmark in background fetch`
- `0x43861`: `Failed to update bookmark in background fetch`
- `0x4398b`: `Failed to update bookmark in background fetch`

## pseudocode

```c

```

## disassembly

```asm
0x43760  call     void Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::EnableSecurityPrilige()
0x43765  ldarg.0
0x43766  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::reverseFetch
0x4376b  brfalse.s loc_43774
0x4376d  ldc.i4   0x200
0x43772  br.s     loc_43779
0x43774  ldc.i4   0x100
0x43779  ldarg.0
0x4377a  ldfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::queryFlags
0x4377f  or
0x43780  stloc.0
0x43781  ldarg.1
0x43782  isinst   [System]System.ComponentModel.BackgroundWorker
0x43787  stloc.1
0x43788  ldarg.2
0x43789  brtrue.s loc_43792
0x4378b  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x43790  br.s     loc_4379D
0x43792  ldarg.2
0x43793  callvirt instance object [System]System.ComponentModel.DoWorkEventArgs::get_Argument()
0x43798  unbox.any [mscorlib]System.IntPtr
0x4379d  stloc.2
0x4379e  ldc.i4.0
0x4379f  stloc.3
0x437a0  ldc.i4   0xFF
0x437a5  newarr   [mscorlib]System.IntPtr
0x437aa  stloc.s  4
0x437ac  ldloc.1
0x437ad  ldc.i4.0
0x437ae  callvirt instance void [System]System.ComponentModel.BackgroundWorker::ReportProgress(int32)
0x437b3  br       loc_43A41
0x437b8  ldarg.0
0x437b9  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::safeQueryHandle
0x437be  stloc.s  5
0x437c0  ldc.i4.0
0x437c1  stloc.s  6
0x437c3  ldloc.s  5
0x437c5  ldloca.s 6
0x437c7  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x437cc  ldc.i4.0
0x437cd  stloc.s  7
0x437cf  ldc.i4.0
0x437d0  stloc.s  8
0x437d2  ldarg.0
0x437d3  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::resultPositionChanged
0x437d8  brfalse  loc_438A7
0x437dd  ldloc.2
0x437de  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x437e3  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x437e8  brfalse  loc_438A7
0x437ed  ldarg.0
0x437ee  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::isQueryForwardOnly
0x437f3  brtrue   loc_438A7
0x437f8  ldarg.0
0x437f9  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::safeQueryHandle
0x437fe  callvirt instance native int Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle::get_Handle()
0x43803  ldc.i4.0
0x43804  conv.i8
0x43805  ldloc.2
0x43806  ldc.i4.0
0x43807  ldc.i4.4
0x43808  call     bool Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::SeekToEvent(native int queryHandle, int64 pos, native int bookMarkToSet, int32 timeOut, [hasfieldmarshal] valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventSeekFlags flags)
0x4380d  brtrue.s loc_43824
0x4380f  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x43814  stloc.s  7
0x43816  ldstr    aUnableToSeekTo_0// "Unable to seek to the last fetched book"...
0x4381b  ldloc.s  7
0x4381d  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x43822  br.s     loc_438A0
0x43824  ldarg.0
0x43825  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::safeQueryHandle
0x4382a  callvirt instance native int Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle::get_Handle()
0x4382f  ldc.i4.1
0x43830  ldloc.s  4
0x43832  ldc.i4.0
0x43833  ldloca.s 8
0x43835  call     int32 Microsoft.Windows.ManagementUI.CombinedControls.CEventsCommon::GetNextBatchOfEvents(native int qryHandle, int32 numberOfEventsToFetch, native int[] eventHandles, int32 fetchDirection, int32& returnedEventsCount)
0x4383a  stloc.s  7
0x4383c  ldloc.s  7
0x4383e  brfalse.s loc_4384E
0x43840  ldstr    aUnableToGetThe// "Unable to Get the next event after seek"...
0x43845  ldloc.s  7
0x43847  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x4384c  br.s     loc_438A0
0x4384e  ldloc.2
0x4384f  ldloc.s  4
0x43851  ldc.i4.0
0x43852  ldelem.i
0x43853  call     bool Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::UpdateBookMark(native int bookMark, native int eventHandle)
0x43858  brtrue.s loc_4386F
0x4385a  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x4385f  stloc.s  7
0x43861  ldstr    aFailedToUpdate// "Failed to update bookmark in background"...
0x43866  ldloc.s  7
0x43868  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x4386d  br.s     loc_43882
0x4386f  ldloc.3
0x43870  ldc.i4.0
0x43871  ble.s    loc_43882
0x43873  ldarg.0
0x43874  ldfld    class [mscorlib]System.Collections.Generic.List`1<native int> Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::eventToBookMarkMapping
0x43879  ldloc.3
0x4387a  ldc.i4.1
0x4387b  sub
0x4387c  ldloc.2
0x4387d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<native int>::set_Item(int32, var<u1>)
0x43882  ldloc.s  4
0x43884  ldc.i4.0
0x43885  ldelem.i
0x43886  call     bool Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::CloseHandle(native int eventHandle)
0x4388b  brtrue.s loc_438A0
0x4388d  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x43892  stloc.s  7
0x43894  ldstr    aUnableToCloseT_2// "Unable to close the event handle for be"...
0x43899  ldloc.s  7
0x4389b  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x438a0  ldarg.0
0x438a1  ldc.i4.0
0x438a2  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::resultPositionChanged
0x438a7  ldarg.0
0x438a8  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::safeQueryHandle
0x438ad  callvirt instance native int Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle::get_Handle()
0x438b2  ldc.i4   0xFF
0x438b7  ldloc.s  4
0x438b9  ldloc.0
0x438ba  ldloca.s 8
0x438bc  call     int32 Microsoft.Windows.ManagementUI.CombinedControls.CEventsCommon::GetNextBatchOfEvents(native int qryHandle, int32 numberOfEventsToFetch, native int[] eventHandles, int32 fetchDirection, int32& returnedEventsCount)
0x438c1  stloc.s  7
0x438c3  ldloc.s  7
0x438c5  brfalse.s loc_43909
0x438c7  ldloc.s  7
0x438c9  ldc.i4   0x103
0x438ce  bne.un.s loc_438DC
0x438d0  ldarg.0
0x438d1  ldc.i4.1
0x438d2  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::endOfFile
0x438d7  ldc.i4.0
0x438d8  stloc.s  7
0x438da  br.s     loc_43909
0x438dc  ldarg.0
0x438dd  ldloc.s  7
0x438df  stfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::lastError
0x438e4  ldarg.0
0x438e5  ldloc.s  7
0x438e7  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor(int32)
0x438ec  callvirt instance string [mscorlib]System.Exception::get_Message()
0x438f1  stfld    string Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::strError
0x438f6  ldstr    aFailedToGetNex// "Failed to get next batch of events in b"...
0x438fb  ldloc.s  7
0x438fd  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x43902  ldarg.0
0x43903  ldc.i4.1
0x43904  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::endOfFile
0x43909  ldloc.s  7
0x4390b  brtrue   loc_43A27
0x43910  ldloc.s  8
0x43912  ldc.i4.0
0x43913  ble      loc_43A27
0x43918  ldc.i4.0
0x43919  stloc.s  9
0x4391b  br       loc_439E0
0x43920  ldarg.0
0x43921  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::isQueryForwardOnly
0x43926  brfalse.s loc_43947
0x43928  ldarg.0
0x43929  ldloc.s  4
0x4392b  ldloc.s  9
0x4392d  ldelem.i
0x4392e  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::AddToIndexArray(native int evt)
0x43933  ldarg.0
0x43934  ldarg.0
0x43935  ldfld    unsigned int64 Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::countOfItems
0x4393a  ldc.i4.1
0x4393b  conv.i8
0x4393c  add
0x4393d  stfld    unsigned int64 Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::countOfItems
0x43942  br       loc_439DA
0x43947  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x4394c  call     native int Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::CreateBookMarkBuffer(native int buff)
0x43951  stloc.s  0xA
0x43953  ldloc.s  0xA
0x43955  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x4395a  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x4395f  brfalse.s loc_43976
0x43961  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x43966  stloc.s  7
0x43968  ldstr    aFailedToCreate// "Failed to create bookmark in background"...
0x4396d  ldloc.s  7
0x4396f  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x43974  br.s     loc_439DA
0x43976  ldloc.s  0xA
0x43978  ldloc.s  4
0x4397a  ldloc.s  9
0x4397c  ldelem.i
0x4397d  call     bool Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::UpdateBookMark(native int bookMark, native int eventHandle)
0x43982  brtrue.s loc_43999
0x43984  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x43989  stloc.s  7
0x4398b  ldstr    aFailedToUpdate// "Failed to update bookmark in background"...
0x43990  ldloc.s  7
0x43992  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x43997  br.s     loc_439BB
0x43999  ldarg.0
0x4399a  ldloc.s  0xA
0x4399c  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::AddToIndexArray(native int evt)
0x439a1  ldarg.0
0x439a2  ldarg.0
0x439a3  ldfld    unsigned int64 Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::countOfItems
0x439a8  ldc.i4.1
0x439a9  conv.i8
0x439aa  add
0x439ab  stfld    unsigned int64 Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::countOfItems
0x439b0  ldloc.s  0xA
0x439b2  stloc.2
0x439b3  ldarg.0
0x439b4  ldfld    unsigned int64 Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::countOfItems
0x439b9  conv.i4
0x439ba  stloc.3
0x439bb  ldloc.s  4
0x439bd  ldloc.s  9
0x439bf  ldelem.i
0x439c0  call     bool Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::CloseHandle(native int eventHandle)
0x439c5  brtrue.s loc_439DA
0x439c7  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x439cc  stloc.s  7
0x439ce  ldstr    aUnableToCloseT_3// "Unable to close the event handle for in"...
0x439d3  ldloc.s  7
0x439d5  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x439da  ldloc.s  9
0x439dc  ldc.i4.1
0x439dd  add
0x439de  stloc.s  9
0x439e0  ldloc.s  9
0x439e2  ldloc.s  8
0x439e4  blt      loc_43920
0x439e9  ldloc.s  8
0x439eb  ldc.i4   0xFF
0x439f0  bge.s    loc_439F9
0x439f2  ldarg.0
0x439f3  ldc.i4.1
0x439f4  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::endOfFile
0x439f9  leave.s  loc_43A41
0x439fb  ldloc.1
0x439fc  callvirt instance bool [System]System.ComponentModel.BackgroundWorker::get_CancellationPending()
0x43a01  brtrue.s loc_43A26
0x43a03  ldarg.0
0x43a04  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::fetchCanceled
0x43a09  brtrue.s loc_43A26
0x43a0b  ldarg.0
0x43a0c  ldfld    unsigned int64 Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::countOfItems
0x43a11  ldc.i4   0x3FC
0x43a16  conv.i8
0x43a17  rem.un
0x43a18  ldsfld   unsigned int64 Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::InitialFetchSize
0x43a1d  bne.un.s loc_43A26
0x43a1f  ldloc.1
0x43a20  ldc.i4.0
0x43a21  callvirt instance void [System]System.ComponentModel.BackgroundWorker::ReportProgress(int32)
0x43a26  endfinally
0x43a27  leave.s  loc_43A41
0x43a29  ldarg.0
0x43a2a  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::safeQueryHandle
0x43a2f  call     void [mscorlib]System.Threading.Monitor::PulseAll(object)
0x43a34  endfinally
0x43a35  ldloc.s  6
0x43a37  brfalse.s loc_43A40
0x43a39  ldloc.s  5
0x43a3b  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x43a40  endfinally
0x43a41  ldarg.0
0x43a42  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::endOfFile
0x43a47  brtrue.s loc_43A54
0x43a49  ldloc.1
0x43a4a  callvirt instance bool [System]System.ComponentModel.BackgroundWorker::get_CancellationPending()
0x43a4f  brfalse  loc_437B8
0x43a54  leave.s  loc_43A5F
0x43a56  ldloc.1
0x43a57  ldc.i4.s 0x64
0x43a59  callvirt instance void [System]System.ComponentModel.BackgroundWorker::ReportProgress(int32)
0x43a5e  endfinally
0x43a5f  ret
```
