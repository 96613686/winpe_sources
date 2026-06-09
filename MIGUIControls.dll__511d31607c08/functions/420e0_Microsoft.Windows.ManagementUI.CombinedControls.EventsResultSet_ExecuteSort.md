# Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::ExecuteSort

- ea: `0x420e0`
- end: `0x42623`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::ExecuteSort`
- size: `1347`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x41f60`

## callees

- `0x12840`
- `0x12860`
- `0x12920`
- `0x13510`
- `0x1cd50`
- `0x1ce20`
- `0x3aed0`
- `0x3d5b0`
- `0x3dab0`
- `0x3dac0`
- `0x3e220`
- `0x3e7a0`
- `0x3f150`
- `0x3f210`
- `0x420e0`
- `0x42630`
- `0x426f0`
- `0x42780`
- `0x427f0`
- `0x44e30`
- `0x45500`
- `0x4d110`

## string_xrefs

- `0x4211c`: `SortFetchingEvents-InsideSort`
- `0x422c1`: `SortFetchingEvents-InsideSort`

## pseudocode

```c

```

## disassembly

```asm
0x420e0  ldc.i4.0
0x420e1  stloc.0
0x420e2  ldc.i4.0
0x420e3  conv.i8
0x420e4  stloc.1
0x420e5  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x420ea  stloc.2
0x420eb  ldsfld   unsigned int64 Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::SortFetchBatchSize
0x420f0  conv.i4
0x420f1  stloc.s  5
0x420f3  ldc.i4.1
0x420f4  newarr   [mscorlib]System.IntPtr
0x420f9  stloc.s  6
0x420fb  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<native int>::.ctor()
0x42100  stloc.s  7
0x42102  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<unsigned int64>::.ctor()
0x42107  stloc.s  8
0x42109  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<native int>::.ctor()
0x4210e  stloc.s  9
0x42110  ldc.i4.0
0x42111  stloc.s  0xC
0x42113  ldarg.0
0x42114  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::isQueryForwardOnly
0x42119  stloc.s  0xD
0x4211b  ldarg.0
0x4211c  ldstr    aSortfetchingev// "SortFetchingEvents-InsideSort"
0x42121  call     void Microsoft.Windows.ManagementUI.CombinedControls.TimeTrace::StartMethod(object thisObject, string methodName)
0x42126  ldarg.2
0x42127  brfalse.s loc_42144
0x42129  ldnull
0x4212a  stloc.s  6
0x4212c  ldarg.0
0x4212d  ldloca.s 5
0x4212f  call     instance native int[] Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::FetchNextBatchFromSortingResults(int32& fetchSize)
0x42134  stloc.s  6
0x42136  ldloc.s  5
0x42138  ldsfld   unsigned int64 Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::SortFetchBatchSize
0x4213d  conv.i4
0x4213e  bge.s    loc_421A3
0x42140  ldc.i4.1
0x42141  stloc.0
0x42142  br.s     loc_421A3
0x42144  ldarg.0
0x42145  ldfld    class [mscorlib]System.Collections.Generic.List`1<native int> Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::eventToBookMarkMapping
0x4214a  brfalse  loc_422C0
0x4214f  ldarg.0
0x42150  ldfld    class [mscorlib]System.Collections.Generic.List`1<native int> Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::eventToBookMarkMapping
0x42155  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<native int>::get_Count()
0x4215a  brfalse  loc_422C0
0x4215f  ldarg.0
0x42160  ldfld    class [mscorlib]System.Collections.Generic.List`1<native int> Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::eventToBookMarkMapping
0x42165  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<native int>::get_Count()
0x4216a  newarr   [mscorlib]System.IntPtr
0x4216f  stloc.s  6
0x42171  ldc.i4.0
0x42172  stloc.s  0xC
0x42174  br.s     loc_4218E
0x42176  ldloc.s  6
0x42178  ldloc.s  0xC
0x4217a  ldarg.0
0x4217b  ldfld    class [mscorlib]System.Collections.Generic.List`1<native int> Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::eventToBookMarkMapping
0x42180  ldloc.s  0xC
0x42182  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<native int>::get_Item(!!T0)
0x42187  stelem.i
0x42188  ldloc.s  0xC
0x4218a  ldc.i4.1
0x4218b  add
0x4218c  stloc.s  0xC
0x4218e  ldloc.s  0xC
0x42190  ldarg.0
0x42191  ldfld    class [mscorlib]System.Collections.Generic.List`1<native int> Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::eventToBookMarkMapping
0x42196  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<native int>::get_Count()
0x4219b  blt.s    loc_42176
0x4219d  ldloc.s  0xC
0x4219f  stloc.s  5
0x421a1  ldc.i4.1
0x421a2  stloc.0
0x421a3  ldloc.s  6
0x421a5  brfalse  loc_422A9
0x421aa  ldc.i4.0
0x421ab  stloc.s  0xC
0x421ad  br       loc_422A0
0x421b2  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x421b7  stloc.s  0xA
0x421b9  ldarg.2
0x421ba  brtrue.s loc_421CC
0x421bc  ldarg.0
0x421bd  ldloc.1
0x421be  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.IEventBase Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::GetEventAt(unsigned int64 index)
0x421c3  isinst   Microsoft.Windows.ManagementUI.CombinedControls.CrimsonEvent
0x421c8  stloc.s  4
0x421ca  br.s     loc_421DC
0x421cc  ldarg.0
0x421cd  ldloc.s  6
0x421cf  ldloc.s  0xC
0x421d1  ldelem.i
0x421d2  ldarg.3
0x421d3  ldloca.s 0xA
0x421d5  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.CrimsonEvent Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::GetEvent(native int hEvent, bool fetchBookMark, [out] native int& bookMark)
0x421da  stloc.s  4
0x421dc  ldloc.s  4
0x421de  brfalse  loc_42293
0x421e3  ldloca.s 0xB
0x421e5  initobj  Microsoft.Windows.ManagementUI.CombinedControls.SortKeysItem
0x421eb  ldloca.s 0xB
0x421ed  ldloc.1
0x421ee  stfld    unsigned int64 Microsoft.Windows.ManagementUI.CombinedControls.SortKeysItem::evtIndex
0x421f3  ldloca.s 0xB
0x421f5  ldloc.s  4
0x421f7  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.LiteEventRecord Microsoft.Windows.ManagementUI.CombinedControls.CrimsonEvent::get_LiteRecord()
0x421fc  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.LiteEventRecord Microsoft.Windows.ManagementUI.CombinedControls.SortKeysItem::eventRecord
0x42201  ldloca.s 0xB
0x42203  ldarg.0
0x42204  ldloc.s  4
0x42206  call     instance object Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::GetProperty(class Microsoft.Windows.ManagementUI.CombinedControls.CrimsonEvent evt)
0x4220b  stfld    object Microsoft.Windows.ManagementUI.CombinedControls.SortKeysItem::sortkeyVal
0x42210  ldarg.3
0x42211  brfalse.s loc_4221C
0x42213  ldloc.s  9
0x42215  ldloc.s  0xA
0x42217  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<native int>::Add(var<u1>)
0x4221c  ldloc.s  0xD
0x4221e  brtrue.s loc_42277
0x42220  ldloc.s  4
0x42222  callvirt instance native int Microsoft.Windows.ManagementUI.CombinedControls.CrimsonEvent::get_EventHandle()
0x42227  call     bool Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::CloseHandle(native int eventHandle)
0x4222c  brtrue.s loc_42266
0x4222e  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x42233  stloc.s  0xE
0x42235  ldstr    aUnableToCloseT_1// "Unable to close the event handle for in"...
0x4223a  ldloca.s 1
0x4223c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x42241  ldtoken  [mscorlib]System.Int64
0x42246  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4224b  callvirt instance object [mscorlib]System.Globalization.CultureInfo::GetFormat(class [mscorlib]System.Type)
0x42250  castclass [mscorlib]System.IFormatProvider
0x42255  call     instance string [mscorlib]System.UInt64::ToString(class [mscorlib]System.IFormatProvider)
0x4225a  call     string [mscorlib]System.String::Concat(string, string)
0x4225f  ldloc.s  0xE
0x42261  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x42266  ldloc.s  0xB
0x42268  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.LiteEventRecord Microsoft.Windows.ManagementUI.CombinedControls.SortKeysItem::eventRecord
0x4226d  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x42272  stfld    native int Microsoft.Windows.ManagementUI.CombinedControls.LiteEventRecord::EventHandle
0x42277  ldloc.s  4
0x42279  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x4227e  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.CrimsonEvent::set_EventHandle(native int value)
0x42283  ldloc.2
0x42284  ldloc.s  0xB
0x42286  box      Microsoft.Windows.ManagementUI.CombinedControls.SortKeysItem
0x4228b  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x42290  pop
0x42291  br.s     loc_42295
0x42293  ldc.i4.1
0x42294  stloc.0
0x42295  ldloc.1
0x42296  ldc.i4.1
0x42297  conv.i8
0x42298  add
0x42299  stloc.1
0x4229a  ldloc.s  0xC
0x4229c  ldc.i4.1
0x4229d  add
0x4229e  stloc.s  0xC
0x422a0  ldloc.s  0xC
0x422a2  ldloc.s  5
0x422a4  blt      loc_421B2
0x422a9  ldloc.0
0x422aa  brtrue.s loc_422C0
0x422ac  ldarg.1
0x422ad  brfalse  loc_42126
0x422b2  ldarg.1
0x422b3  brfalse.s loc_422C0
0x422b5  ldarg.1
0x422b6  callvirt instance bool [System]System.ComponentModel.BackgroundWorker::get_CancellationPending()
0x422bb  brfalse  loc_42126
0x422c0  ldarg.0
0x422c1  ldstr    aSortfetchingev// "SortFetchingEvents-InsideSort"
0x422c6  call     void Microsoft.Windows.ManagementUI.CombinedControls.TimeTrace::EndMethod(object thisObject, string methodName)
0x422cb  call     void Microsoft.Windows.ManagementUI.CombinedControls.CrimsonEvent::ReleaseStaticVariablesUsedForFetchingSortParams()
0x422d0  ldarg.1
0x422d1  brfalse.s loc_422EF
0x422d3  ldarg.1
0x422d4  brfalse  loc_425FD
0x422d9  ldarg.1
0x422da  callvirt instance bool [System]System.ComponentModel.BackgroundWorker::get_CancellationPending()
0x422df  brtrue   loc_425FD
0x422e4  ldarg.0
0x422e5  ldfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::errorInSorting
0x422ea  brtrue   loc_425FD
0x422ef  ldloc.2
0x422f0  ldarg.0
0x422f1  callvirt instance void [mscorlib]System.Collections.ArrayList::Sort(class [mscorlib]System.Collections.IComparer)
0x422f6  ldarg.0
0x422f7  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x422fc  stfld    class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::eventGroups
0x42301  ldarg.0
0x42302  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::itemToGroupMapping
0x42307  callvirt instance void [mscorlib]System.Collections.Hashtable::Clear()
0x4230c  ldarg.0
0x4230d  ldarg.s  4
0x4230f  brtrue.s loc_42318
0x42311  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ResultColumn::.ctor()
0x42316  br.s     loc_4231E
0x42318  ldarg.0
0x42319  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ResultColumn Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::currentSortCol
0x4231e  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.ResultColumn Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::currentGroupColumn
0x42323  ldsfld   string [mscorlib]System.String::Empty
0x42328  stloc.s  0xF
0x4232a  ldnull
0x4232b  stloc.s  0x10
0x4232d  ldloc.2
0x4232e  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x42333  newarr   Microsoft.Windows.ManagementUI.CombinedControls.LiteEventRecord
0x42338  stloc.s  0x11
0x4233a  ldsfld   string [mscorlib]System.String::Empty
0x4233f  stloc.s  0x12
0x42341  ldc.i4.0
0x42342  stloc.s  0x13
0x42344  ldc.i4.0
0x42345  conv.i8
0x42346  stloc.1
0x42347  br       loc_424AD
0x4234c  ldarg.0
0x4234d  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::curSortAsc
0x42352  brfalse.s loc_4237B
0x42354  ldloc.2
0x42355  ldloc.1
0x42356  conv.i4
0x42357  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x4235c  unbox.any Microsoft.Windows.ManagementUI.CombinedControls.SortKeysItem
0x42361  stloc.3
0x42362  ldloc.s  0x11
0x42364  ldloc.1
0x42365  conv.ovf.i8.un
0x42366  ldloc.2
0x42367  ldloc.1
0x42368  conv.i4
0x42369  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x4236e  unbox    Microsoft.Windows.ManagementUI.CombinedControls.SortKeysItem
0x42373  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.LiteEventRecord Microsoft.Windows.ManagementUI.CombinedControls.SortKeysItem::eventRecord
0x42378  stelem.ref
0x42379  br.s     loc_423B2
0x4237b  ldloc.2
0x4237c  ldloc.2
0x4237d  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x42382  ldloc.1
0x42383  conv.i4
0x42384  sub
0x42385  ldc.i4.1
0x42386  sub
0x42387  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x4238c  unbox.any Microsoft.Windows.ManagementUI.CombinedControls.SortKeysItem
0x42391  stloc.3
0x42392  ldloc.s  0x11
0x42394  ldloc.1
0x42395  conv.ovf.i8.un
0x42396  ldloc.2
0x42397  ldloc.2
0x42398  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x4239d  ldloc.1
0x4239e  conv.i4
0x4239f  sub
0x423a0  ldc.i4.1
0x423a1  sub
0x423a2  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x423a7  unbox    Microsoft.Windows.ManagementUI.CombinedControls.SortKeysItem
0x423ac  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.LiteEventRecord Microsoft.Windows.ManagementUI.CombinedControls.SortKeysItem::eventRecord
0x423b1  stelem.ref
0x423b2  ldarg.s  4
0x423b4  brfalse  loc_4245E
0x423b9  ldloc.3
0x423ba  ldfld    object Microsoft.Windows.ManagementUI.CombinedControls.SortKeysItem::sortkeyVal
0x423bf  brfalse.s loc_423F5
0x423c1  ldloc.3
0x423c2  ldfld    object Microsoft.Windows.ManagementUI.CombinedControls.SortKeysItem::sortkeyVal
0x423c7  isinst   [mscorlib]System.DateTime
0x423cc  brfalse.s loc_423E6
0x423ce  ldloc.3
0x423cf  ldfld    object Microsoft.Windows.ManagementUI.CombinedControls.SortKeysItem::sortkeyVal
0x423d4  unbox.any [mscorlib]System.DateTime
0x423d9  stloc.s  0x14
0x423db  ldloca.s 0x14
0x423dd  call     instance string [mscorlib]System.DateTime::ToLongDateString()
0x423e2  stloc.s  0xF
0x423e4  br.s     loc_423FC
0x423e6  ldloc.3
0x423e7  ldfld    object Microsoft.Windows.ManagementUI.CombinedControls.SortKeysItem::sortkeyVal
0x423ec  callvirt instance string [mscorlib]System.Object::ToString()
0x423f1  stloc.s  0xF
0x423f3  br.s     loc_423FC
0x423f5  ldstr    asc_AA3F4// ""
0x423fa  stloc.s  0xF
0x423fc  ldloc.s  0x10
0x423fe  brfalse.s loc_4240C
0x42400  ldloc.s  0x12
0x42402  ldloc.s  0xF
0x42404  ldc.i4.1
0x42405  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x4240a  brfalse.s loc_4243C
  ... truncated ...
```
