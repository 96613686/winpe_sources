# Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::UpdateAfterSortFinished

- ea: `0x2fec0`
- end: `0x30119`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::UpdateAfterSortFinished`
- size: `601`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2fea0`

## callees

- `0x12ed0`
- `0x13610`
- `0x13ce0`
- `0x1c9e0`
- `0x1ca50`
- `0x1cd50`
- `0x1ce20`
- `0x2d060`
- `0x2d220`
- `0x2d540`
- `0x2d590`
- `0x2da50`
- `0x2f0d0`
- `0x2f130`
- `0x2fec0`
- `0x30260`
- `0x31650`
- `0x31660`
- `0x33aa0`
- `0x39070`
- `0x3f640`
- `0x3f660`
- `0x3f6a0`
- `0x3f6b0`
- `0x3fb80`
- `0x3fdb0`
- `0x41620`

## string_xrefs

- `0x2fec1`: `UpdateAfterSortFinished`
- `0x3010d`: `UpdateAfterSortFinished`

## pseudocode

```c

```

## disassembly

```asm
0x2fec0  ldarg.0
0x2fec1  ldstr    aUpdateaftersor// "UpdateAfterSortFinished"
0x2fec6  call     void Microsoft.Windows.ManagementUI.CombinedControls.TimeTrace::StartMethod(object thisObject, string methodName)
0x2fecb  ldarg.0
0x2fecc  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::stopAndResumeButton
0x2fed1  ldc.i4.0
0x2fed2  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::EnableControl(class [System.Windows.Forms]System.Windows.Forms.Control ctl, bool enable)
0x2fed7  ldarg.0
0x2fed8  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Cursor [System.Windows.Forms]System.Windows.Forms.Control::get_Cursor()
0x2fedd  stloc.0
0x2fede  ldarg.0
0x2fedf  call     class [System.Windows.Forms]System.Windows.Forms.Cursor [System.Windows.Forms]System.Windows.Forms.Cursors::get_WaitCursor()
0x2fee4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Cursor(class [System.Windows.Forms]System.Windows.Forms.Cursor)
0x2fee9  ldarg.0
0x2feea  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ListViewEx Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::mainListView
0x2feef  callvirt instance valuetype Microsoft.Windows.ManagementUI.CombinedControls.ListViewPoint Microsoft.Windows.ManagementUI.CombinedControls.ListViewEx::GetCurrentScrollPosition()
0x2fef4  stloc.1
0x2fef5  ldarg.0
0x2fef6  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::res
0x2fefb  callvirt instance int32 Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::get_SortError()
0x2ff00  brfalse.s loc_2FF3A
0x2ff02  ldarg.0
0x2ff03  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::res
0x2ff08  callvirt instance int32 Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::get_SortError()
0x2ff0d  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor(int32)
0x2ff12  callvirt instance string [mscorlib]System.Exception::get_Message()
0x2ff17  call     void Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::ShowErrorMessageBox(string message)
0x2ff1c  ldarg.0
0x2ff1d  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::res
0x2ff22  ldc.i4.0
0x2ff23  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::set_SortError(int32 value)
0x2ff28  ldarg.0
0x2ff29  ldc.i4.1
0x2ff2a  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::set_AsynchronousState(valuetype AsyncState value)
0x2ff2f  ldarg.0
0x2ff30  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::UpdateColumnImage()
0x2ff35  leave    loc_30118
0x2ff3a  ldc.i4.m1
0x2ff3b  stloc.2
0x2ff3c  ldarg.0
0x2ff3d  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ListViewEx Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::mainListView
0x2ff42  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::BeginUpdate()
0x2ff47  ldarg.0
0x2ff48  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::GetSelectedEventKey()
0x2ff4d  ldarg.0
0x2ff4e  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::lstCache
0x2ff53  callvirt instance void [mscorlib]System.Collections.Hashtable::Clear()
0x2ff58  ldarg.0
0x2ff59  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::res
0x2ff5e  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::get_Grouped()
0x2ff63  brfalse.s loc_2FFB4
0x2ff65  ldarg.0
0x2ff66  ldflda   valuetype Microsoft.Windows.ManagementUI.CombinedControls.ViewConfig Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::viewConfig
0x2ff6b  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.ViewConfig::Sorted
0x2ff70  brfalse.s loc_2FFB4
0x2ff72  ldarg.0
0x2ff73  ldflda   valuetype Microsoft.Windows.ManagementUI.CombinedControls.ViewConfig Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::viewConfig
0x2ff78  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ResultColumn Microsoft.Windows.ManagementUI.CombinedControls.ViewConfig::SortColumn
0x2ff7d  ldarg.0
0x2ff7e  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::res
0x2ff83  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.ResultColumn Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::get_GroupColumn()
0x2ff88  beq.s    loc_2FFB4
0x2ff8a  ldarg.0
0x2ff8b  ldc.i4.4
0x2ff8c  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::set_AsynchronousState(valuetype AsyncState value)
0x2ff91  ldarg.0
0x2ff92  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::res
0x2ff97  ldarg.0
0x2ff98  ldflda   valuetype Microsoft.Windows.ManagementUI.CombinedControls.ViewConfig Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::viewConfig
0x2ff9d  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ResultColumn Microsoft.Windows.ManagementUI.CombinedControls.ViewConfig::SortColumn
0x2ffa2  ldarg.0
0x2ffa3  ldflda   valuetype Microsoft.Windows.ManagementUI.CombinedControls.ViewConfig Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::viewConfig
0x2ffa8  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.ViewConfig::SortAsc
0x2ffad  ldc.i4.0
0x2ffae  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::Sort(class Microsoft.Windows.ManagementUI.CombinedControls.ResultColumn column, bool ascending, bool createGroups)
0x2ffb3  pop
0x2ffb4  ldarg.0
0x2ffb5  ldflda   valuetype Microsoft.Windows.ManagementUI.CombinedControls.ViewConfig Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::viewConfig
0x2ffba  initobj  Microsoft.Windows.ManagementUI.CombinedControls.ViewConfig
0x2ffc0  ldarg.0
0x2ffc1  ldc.i4.0
0x2ffc2  stfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::cacheStart
0x2ffc7  ldarg.0
0x2ffc8  ldc.i4.0
0x2ffc9  stfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::cacheEnd
0x2ffce  ldarg.0
0x2ffcf  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::UpdateColumnImage()
0x2ffd4  ldarg.0
0x2ffd5  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ListViewEx Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::mainListView
0x2ffda  ldarg.0
0x2ffdb  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::res
0x2ffe0  callvirt instance unsigned int64 Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::get_Count()
0x2ffe5  conv.i4
0x2ffe6  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::SetListViewRowCount(class [System.Windows.Forms]System.Windows.Forms.ListView lv, int32 count)
0x2ffeb  ldarg.0
0x2ffec  ldc.i4.1
0x2ffed  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::set_AsynchronousState(valuetype AsyncState value)
0x2fff2  ldarg.0
0x2fff3  ldfld    class [System.Windows.Forms]System.Windows.Forms.SplitContainer Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::previewPaneSplitter
0x2fff8  callvirt instance class [System.Windows.Forms]System.Windows.Forms.SplitterPanel [System.Windows.Forms]System.Windows.Forms.SplitContainer::get_Panel1()
0x2fffd  ldarg.0
0x2fffe  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::tableLayoutPanel1
0x30003  callvirt instance bool [System.Windows.Forms]System.Windows.Forms.Control::Contains(class [System.Windows.Forms]System.Windows.Forms.Control)
0x30008  brtrue.s loc_30046
0x3000a  ldarg.0
0x3000b  ldnull
0x3000c  ldstr    aDescriptionbar// "DescriptionBarForEventCount"
0x30011  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x30016  ldc.i4.1
0x30017  newarr   [mscorlib]System.Object
0x3001c  dup
0x3001d  ldc.i4.0
0x3001e  ldarg.0
0x3001f  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ListViewEx Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::mainListView
0x30024  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.ListView::get_VirtualListSize()
0x30029  stloc.3
0x3002a  ldloca.s 3
0x3002c  ldstr    aN// "N"
0x30031  call     class [mscorlib]System.Globalization.NumberFormatInfo Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::get_NumberFormat()
0x30036  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x3003b  stelem.ref
0x3003c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x30041  stfld    string Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::message
0x30046  ldarg.0
0x30047  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::res
0x3004c  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::get_Grouped()
0x30051  brfalse.s loc_3005B
0x30053  ldarg.0
0x30054  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::RefreshGroups()
0x30059  br.s     loc_30061
0x3005b  ldarg.0
0x3005c  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::RefreshListView()
0x30061  ldarg.0
0x30062  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.PropertyDialogHashtableKey Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::keyOfEventToBeSelected
0x30067  brfalse.s loc_30094
0x30069  ldarg.0
0x3006a  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::res
0x3006f  ldarg.0
0x30070  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.PropertyDialogHashtableKey Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::keyOfEventToBeSelected
0x30075  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.PropertyDialogHashtableKey::get_Channel()
0x3007a  ldarg.0
0x3007b  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.PropertyDialogHashtableKey Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::keyOfEventToBeSelected
0x30080  callvirt instance unsigned int64 Microsoft.Windows.ManagementUI.CombinedControls.PropertyDialogHashtableKey::get_RecordId()
0x30085  ldc.i4.m1
0x30086  callvirt instance int32 Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::GetIndexOfEvent(string channel, unsigned int64 recordId, int32 currentIndex)
0x3008b  stloc.2
0x3008c  ldloc.2
0x3008d  ldc.i4.0
0x3008e  bge.s    loc_30096
0x30090  ldc.i4.0
0x30091  stloc.2
0x30092  br.s     loc_30096
0x30094  ldc.i4.0
0x30095  stloc.2
0x30096  ldarg.0
0x30097  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ListViewEx Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::mainListView
0x3009c  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.ListView::get_VirtualListSize()
0x300a1  ldc.i4.0
0x300a2  ble.s    loc_300AB
0x300a4  ldarg.0
0x300a5  ldloc.2
0x300a6  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::GetEventAndRefreshProperties(int32 Index)
0x300ab  ldarg.0
0x300ac  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ListViewEx Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::mainListView
0x300b1  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.ListView::get_VirtualListSize()
0x300b6  ldloc.2
0x300b7  blt.s    loc_300D9
0x300b9  ldarg.0
0x300ba  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ListViewEx Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::mainListView
0x300bf  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.ListView::get_VirtualListSize()
0x300c4  brfalse.s loc_300D9
0x300c6  ldarg.0
0x300c7  ldloc.2
0x300c8  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::SelectEventItem(int32 index)
0x300cd  ldarg.0
0x300ce  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ListViewEx Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::mainListView
0x300d3  ldloc.2
0x300d4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::EnsureVisible(int32)
0x300d9  ldarg.0
0x300da  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ListViewEx Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::mainListView
0x300df  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::EndUpdate()
0x300e4  ldarg.0
0x300e5  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::FireUpdateDescriptionEvent()
0x300ea  leave.s  loc_30118
0x300ec  ldarg.0
0x300ed  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ListViewEx Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::mainListView
0x300f2  ldloc.1
0x300f3  ldfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.ListViewPoint::x
0x300f8  ldc.i4.0
0x300f9  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ListViewEx::SetScrollPosition(int32 x, int32 y)
0x300fe  ldarg.0
0x300ff  ldnull
0x30100  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.PropertyDialogHashtableKey Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::keyOfEventToBeSelected
0x30105  ldarg.0
0x30106  ldloc.0
0x30107  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Cursor(class [System.Windows.Forms]System.Windows.Forms.Cursor)
0x3010c  ldarg.0
0x3010d  ldstr    aUpdateaftersor// "UpdateAfterSortFinished"
0x30112  call     void Microsoft.Windows.ManagementUI.CombinedControls.TimeTrace::EndMethod(object thisObject, string methodName)
0x30117  endfinally
0x30118  ret
```
