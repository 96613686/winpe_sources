# Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::FetchNextBatchWithBookMarksOrEvents

- ea: `0x430a0`
- end: `0x43248`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::FetchNextBatchWithBookMarksOrEvents`
- size: `424`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x41180`
- `0x413f0`

## callees

- `0x12860`
- `0x13510`
- `0x1cd50`
- `0x1ce20`
- `0x36630`
- `0x3f580`
- `0x42dd0`
- `0x430a0`
- `0x44710`
- `0x4d1a0`
- `0x4d1b0`

## string_xrefs

- `0x431b4`: `Unable to create bookmark `
- `0x431d4`: `Unable to update bookmark for the event `

## pseudocode

```c

```

## disassembly

```asm
0x430a0  ldarg.0
0x430a1  ldstr    aFetchnextbatch_0// "FetchNextBatchWithBookMarksOrEvents"
0x430a6  call     void Microsoft.Windows.ManagementUI.CombinedControls.TimeTrace::StartMethod(object thisObject, string methodName)
0x430ab  ldarg.1
0x430ac  ldind.i4
0x430ad  ldc.i4.0
0x430ae  bgt.s    loc_430B8
0x430b0  ldsfld   unsigned int64 Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::InitialFetchSize
0x430b5  conv.i4
0x430b6  br.s     loc_430BA
0x430b8  ldarg.1
0x430b9  ldind.i4
0x430ba  stloc.0
0x430bb  ldarg.1
0x430bc  ldc.i4.0
0x430bd  stind.i4
0x430be  ldloc.0
0x430bf  newarr   [mscorlib]System.IntPtr
0x430c4  stloc.1
0x430c5  ldc.i4.0
0x430c6  stloc.2
0x430c7  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x430cc  stloc.3
0x430cd  ldc.i4.0
0x430ce  stloc.s  4
0x430d0  ldarg.0
0x430d1  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::reverseFetch
0x430d6  brfalse.s loc_430DF
0x430d8  ldc.i4   0x200
0x430dd  br.s     loc_430E4
0x430df  ldc.i4   0x100
0x430e4  ldarg.0
0x430e5  ldfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::queryFlags
0x430ea  or
0x430eb  stloc.s  5
0x430ed  ldarg.0
0x430ee  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::safeQueryHandle
0x430f3  stloc.s  6
0x430f5  ldc.i4.0
0x430f6  stloc.s  7
0x430f8  ldloc.s  6
0x430fa  ldloca.s 7
0x430fc  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x43101  ldarg.0
0x43102  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::safeQueryHandle
0x43107  callvirt instance native int Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle::get_Handle()
0x4310c  ldloc.0
0x4310d  ldloc.1
0x4310e  ldloc.s  5
0x43110  ldarg.1
0x43111  call     int32 Microsoft.Windows.ManagementUI.CombinedControls.CEventsCommon::GetNextBatchOfEvents(native int qryHandle, int32 numberOfEventsToFetch, native int[] eventHandles, int32 fetchDirection, int32& returnedEventsCount)
0x43116  stloc.s  4
0x43118  ldloc.s  4
0x4311a  brfalse.s loc_4315B
0x4311c  ldloc.s  4
0x4311e  ldc.i4   0x103
0x43123  bne.un.s loc_4312E
0x43125  ldarg.0
0x43126  ldc.i4.1
0x43127  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::set_EndOfResult(bool value)
0x4312c  leave.s  loc_43169
0x4312e  ldarg.0
0x4312f  ldloc.s  4
0x43131  stfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::lastError
0x43136  ldarg.0
0x43137  ldloc.s  4
0x43139  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor(int32)
0x4313e  callvirt instance string [mscorlib]System.Exception::get_Message()
0x43143  stfld    string Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::strError
0x43148  ldarg.0
0x43149  ldc.i4.1
0x4314a  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::set_EndOfResult(bool value)
0x4314f  ldstr    aErrorGettingNe// "Error getting next batch of events"
0x43154  ldloc.s  4
0x43156  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x4315b  leave.s  loc_43169
0x4315d  ldloc.s  7
0x4315f  brfalse.s loc_43168
0x43161  ldloc.s  6
0x43163  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x43168  endfinally
0x43169  ldc.i4.0
0x4316a  stloc.2
0x4316b  br       loc_43221
0x43170  ldarg.0
0x43171  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::isQueryForwardOnly
0x43176  brfalse.s loc_43195
0x43178  ldarg.0
0x43179  ldloc.1
0x4317a  ldloc.2
0x4317b  ldelem.i
0x4317c  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::AddToIndexArray(native int evt)
0x43181  ldarg.0
0x43182  ldarg.0
0x43183  ldfld    unsigned int64 Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::countOfItems
0x43188  ldc.i4.1
0x43189  conv.i8
0x4318a  add
0x4318b  stfld    unsigned int64 Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::countOfItems
0x43190  br       loc_4321D
0x43195  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x4319a  call     native int Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::CreateBookMarkBuffer(native int buff)
0x4319f  stloc.3
0x431a0  ldloc.3
0x431a1  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x431a6  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x431ab  brfalse.s loc_431C2
0x431ad  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x431b2  stloc.s  4
0x431b4  ldstr    aUnableToCreate_0// "Unable to create bookmark "
0x431b9  ldloc.s  4
0x431bb  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x431c0  br.s     loc_4321D
0x431c2  ldloc.3
0x431c3  ldloc.1
0x431c4  ldloc.2
0x431c5  ldelem.i
0x431c6  call     bool Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::UpdateBookMark(native int bookMark, native int eventHandle)
0x431cb  brtrue.s loc_43207
0x431cd  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x431d2  stloc.s  4
0x431d4  ldstr    aUnableToUpdate// "Unable to update bookmark for the event"...
0x431d9  ldloca.s 2
0x431db  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x431e0  ldtoken  [mscorlib]System.Int32
0x431e5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x431ea  callvirt instance object [mscorlib]System.Globalization.CultureInfo::GetFormat(class [mscorlib]System.Type)
0x431ef  castclass [mscorlib]System.IFormatProvider
0x431f4  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x431f9  call     string [mscorlib]System.String::Concat(string, string)
0x431fe  ldloc.s  4
0x43200  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x43205  br.s     loc_4320E
0x43207  ldarg.0
0x43208  ldloc.3
0x43209  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::AddToIndexArray(native int evt)
0x4320e  ldarg.0
0x4320f  ldarg.0
0x43210  ldfld    unsigned int64 Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::countOfItems
0x43215  ldc.i4.1
0x43216  conv.i8
0x43217  add
0x43218  stfld    unsigned int64 Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::countOfItems
0x4321d  ldloc.2
0x4321e  ldc.i4.1
0x4321f  add
0x43220  stloc.2
0x43221  ldloc.2
0x43222  ldarg.1
0x43223  ldind.i4
0x43224  blt      loc_43170
0x43229  ldarg.1
0x4322a  ldind.i4
0x4322b  ldloc.0
0x4322c  bge.s    loc_43235
0x4322e  ldarg.0
0x4322f  ldc.i4.1
0x43230  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::set_EndOfResult(bool value)
0x43235  ldarg.0
0x43236  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::UpdateActions()
0x4323b  ldarg.0
0x4323c  ldstr    aFetchnextbatch_0// "FetchNextBatchWithBookMarksOrEvents"
0x43241  call     void Microsoft.Windows.ManagementUI.CombinedControls.TimeTrace::EndMethod(object thisObject, string methodName)
0x43246  ldloc.1
0x43247  ret
```
