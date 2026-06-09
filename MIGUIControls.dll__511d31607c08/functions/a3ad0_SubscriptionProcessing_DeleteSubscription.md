# SubscriptionProcessing::DeleteSubscription

- ea: `0xa3ad0`
- end: `0xa3dad`
- name: `SubscriptionProcessing::DeleteSubscription`
- size: `733`
- prototype: ``
- caller_count: `2`
- callee_count: `20`
- tags: ``

## callers

- `0x8e0d0`
- `0xa4610`

## callees

- `0x8c0`
- `0x26a0`
- `0x12ed0`
- `0x13280`
- `0x13440`
- `0x8e490`
- `0x8e500`
- `0x8e570`
- `0x8e640`
- `0x8e650`
- `0x8fa60`
- `0x9cb90`
- `0xa3ad0`
- `0xa47f0`
- `0xa4870`
- `0xa49a0`
- `0xa4ae0`
- `0xa4b20`
- `0xa5050`
- `0xa58d0`

## string_xrefs

- `0xa3d55`: `MessageCannotDeleteSubscriptionWhileItIsBeingEdited`
- `0xa3d8c`: `MessageCannotDeleteSubscriptionWhileItIsBeingEditedInMultipleDelete`

## pseudocode

```c

```

## disassembly

```asm
0xa3ad0  ldc.i4.0
0xa3ad1  stloc.1
0xa3ad2  ldarg.0
0xa3ad3  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView SubscriptionProcessing::currentListView
0xa3ad8  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ListView/SelectedIndexCollection [System.Windows.Forms]System.Windows.Forms.ListView::get_SelectedIndices()
0xa3add  brfalse.s loc_A3AFE
0xa3adf  ldarg.0
0xa3ae0  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView SubscriptionProcessing::currentListView
0xa3ae5  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ListView/SelectedIndexCollection [System.Windows.Forms]System.Windows.Forms.ListView::get_SelectedIndices()
0xa3aea  brfalse.s loc_A3B00
0xa3aec  ldarg.0
0xa3aed  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView SubscriptionProcessing::currentListView
0xa3af2  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ListView/SelectedIndexCollection [System.Windows.Forms]System.Windows.Forms.ListView::get_SelectedIndices()
0xa3af7  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.ListView/SelectedIndexCollection::get_Count()
0xa3afc  brtrue.s loc_A3B00
0xa3afe  ldc.i4.0
0xa3aff  ret
0xa3b00  ldc.i4.0
0xa3b01  stloc.2
0xa3b02  ldc.i4.0
0xa3b03  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::.ctor(bool newSubscription)
0xa3b08  stloc.3
0xa3b09  ldloc.3
0xa3b0a  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::SetParentWindowForDialog()
0xa3b0f  ldc.i4.0
0xa3b10  stloc.s  4
0xa3b12  ldarg.0
0xa3b13  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView SubscriptionProcessing::currentListView
0xa3b18  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ListView/SelectedIndexCollection [System.Windows.Forms]System.Windows.Forms.ListView::get_SelectedIndices()
0xa3b1d  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.ListView/SelectedIndexCollection::get_Count()
0xa3b22  ldc.i4.1
0xa3b23  blt.s    loc_A3B3B
0xa3b25  call     string Microsoft.Windows.ManagementUI.CombinedControls.Resources.SubscriptionResources::get_ConfirmDeleteSubscriptionPrompt()
0xa3b2a  ldstr    aViewername// "ViewerName"
0xa3b2f  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0xa3b34  call     valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult Microsoft.Windows.ManagementUI.CombinedControls.QueryMessage::QueryUser(string message, string caption)
0xa3b39  stloc.s  4
0xa3b3b  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0xa3b40  stloc.s  5
0xa3b42  ldc.i4.0
0xa3b43  stloc.s  6
0xa3b45  ldarg.0
0xa3b46  call     instance int32 SubscriptionProcessing::get_SelectedIndex()
0xa3b4b  stloc.s  7
0xa3b4d  ldc.i4.0
0xa3b4e  stloc.s  8
0xa3b50  ldloc.s  4
0xa3b52  ldc.i4.6
0xa3b53  bne.un   loc_A3DA5
0xa3b58  ldarg.0
0xa3b59  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView SubscriptionProcessing::currentListView
0xa3b5e  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ListView/SelectedIndexCollection [System.Windows.Forms]System.Windows.Forms.ListView::get_SelectedIndices()
0xa3b63  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Windows.Forms]System.Windows.Forms.ListView/SelectedIndexCollection::GetEnumerator()
0xa3b68  stloc.s  9
0xa3b6a  br       loc_A3C27
0xa3b6f  ldloc.s  9
0xa3b71  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xa3b76  unbox.any [mscorlib]System.Int32
0xa3b7b  stloc.s  0xA
0xa3b7d  ldc.i4.0
0xa3b7e  stloc.s  8
0xa3b80  ldarg.0
0xa3b81  ldloc.s  0xA
0xa3b83  ldloca.s 0
0xa3b85  call     instance bool SubscriptionProcessing::GetSelectedSubscriptionAtIndex(int32 index, [out] class Microsoft.WindowsEventCollection.Subscription& subs)
0xa3b8a  brfalse  loc_A3C27
0xa3b8f  ldloc.0
0xa3b90  brfalse  loc_A3C27
0xa3b95  ldloc.3
0xa3b96  ldloc.0
0xa3b97  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::set_OriginalSubscription(class Microsoft.WindowsEventCollection.Subscription value)
0xa3b9c  ldsfld   string [mscorlib]System.String::Empty
0xa3ba1  stloc.s  0xB
0xa3ba3  ldloc.3
0xa3ba4  ldarg.0
0xa3ba5  ldfld    bool SubscriptionProcessing::channelReadOnly
0xa3baa  ldarg.0
0xa3bab  ldfld    string SubscriptionProcessing::logFileName
0xa3bb0  ldc.i4.0
0xa3bb1  ldloca.s 0xB
0xa3bb3  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::Initialize(bool channelPathReadOnly, string channelPath, bool flagStartStatusPolling, string& errorString)
0xa3bb8  pop
0xa3bb9  ldloc.3
0xa3bba  ldloc.0
0xa3bbb  callvirt instance string Microsoft.WindowsEventCollection.Subscription::get_Name()
0xa3bc0  ldc.i4.0
0xa3bc1  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::AlreadyLoaded(string subscriptionName, bool flagBringToFocus)
0xa3bc6  brfalse.s loc_A3BCD
0xa3bc8  ldc.i4.1
0xa3bc9  stloc.1
0xa3bca  ldc.i4.1
0xa3bcb  stloc.s  8
0xa3bcd  ldloc.s  8
0xa3bcf  brtrue.s loc_A3C27
0xa3bd1  ldarg.0
0xa3bd2  ldloc.0
0xa3bd3  callvirt instance string Microsoft.WindowsEventCollection.Subscription::get_Name()
0xa3bd8  call     instance bool SubscriptionProcessing::DeleteSubscription(string name)
0xa3bdd  brfalse.s loc_A3C27
0xa3bdf  ldloc.s  0xA
0xa3be1  ldc.i4.0
0xa3be2  blt.s    loc_A3C25
0xa3be4  ldarg.0
0xa3be5  ldarg.0
0xa3be6  ldarg.0
0xa3be7  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView SubscriptionProcessing::currentListView
0xa3bec  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ListView/ListViewItemCollection [System.Windows.Forms]System.Windows.Forms.ListView::get_Items()
0xa3bf1  ldloc.s  0xA
0xa3bf3  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ListViewItem [System.Windows.Forms]System.Windows.Forms.ListView/ListViewItemCollection::get_Item(int32)
0xa3bf8  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.ListViewItem::get_ImageIndex()
0xa3bfd  call     instance valuetype Microsoft.WindowsEventCollection.SourceCompositeStatus SubscriptionProcessing::GetCompositeStatusForImageIndex(int32 imageIndex)
0xa3c02  ldc.i4.0
0xa3c03  call     instance void SubscriptionProcessing::UpdateSummaryValue(valuetype Microsoft.WindowsEventCollection.SourceCompositeStatus status, bool increment)
0xa3c08  ldloc.s  5
0xa3c0a  ldarg.0
0xa3c0b  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView SubscriptionProcessing::currentListView
0xa3c10  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ListView/ListViewItemCollection [System.Windows.Forms]System.Windows.Forms.ListView::get_Items()
0xa3c15  ldloc.s  0xA
0xa3c17  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ListViewItem [System.Windows.Forms]System.Windows.Forms.ListView/ListViewItemCollection::get_Item(int32)
0xa3c1c  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xa3c21  pop
0xa3c22  ldc.i4.1
0xa3c23  stloc.s  6
0xa3c25  ldc.i4.1
0xa3c26  stloc.2
0xa3c27  ldloc.s  9
0xa3c29  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xa3c2e  brtrue   loc_A3B6F
0xa3c33  leave.s  loc_A3C4A
0xa3c35  ldloc.s  9
0xa3c37  isinst   [mscorlib]System.IDisposable
0xa3c3c  stloc.s  0xC
0xa3c3e  ldloc.s  0xC
0xa3c40  brfalse.s loc_A3C49
0xa3c42  ldloc.s  0xC
0xa3c44  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa3c49  endfinally
0xa3c4a  ldloc.s  6
0xa3c4c  brfalse  loc_A3D36
0xa3c51  ldarg.0
0xa3c52  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView SubscriptionProcessing::currentListView
0xa3c57  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ListView/ListViewItemCollection [System.Windows.Forms]System.Windows.Forms.ListView::get_Items()
0xa3c5c  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.ListView/ListViewItemCollection::get_Count()
0xa3c61  ldc.i4.0
0xa3c62  ble      loc_A3D36
0xa3c67  ldarg.0
0xa3c68  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView SubscriptionProcessing::currentListView
0xa3c6d  ldarg.0
0xa3c6e  ldftn    instance void SubscriptionProcessing::listView_SelectedIndexChanged(object sender, class [mscorlib]System.EventArgs e)
0xa3c74  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0xa3c79  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::remove_SelectedIndexChanged(class [mscorlib]System.EventHandler)
0xa3c7e  ldarg.0
0xa3c7f  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView SubscriptionProcessing::currentListView
0xa3c84  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::BeginUpdate()
0xa3c89  ldloc.s  5
0xa3c8b  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0xa3c90  stloc.s  9
0xa3c92  br.s     loc_A3CC6
0xa3c94  ldloc.s  9
0xa3c96  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xa3c9b  castclass [System.Windows.Forms]System.Windows.Forms.ListViewItem
0xa3ca0  stloc.s  0xD
0xa3ca2  ldarg.0
0xa3ca3  ldfld    class Microsoft.WindowsEventCollection.SubscriptionStatusMonitor SubscriptionProcessing::subscriptionStatusMonitor
0xa3ca8  ldloc.s  0xD
0xa3caa  callvirt instance string [System.Windows.Forms]System.Windows.Forms.ListViewItem::get_Text()
0xa3caf  callvirt instance void Microsoft.WindowsEventCollection.SubscriptionStatusMonitor::DeleteSubscriptionName(string name)
0xa3cb4  ldarg.0
0xa3cb5  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView SubscriptionProcessing::currentListView
0xa3cba  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ListView/ListViewItemCollection [System.Windows.Forms]System.Windows.Forms.ListView::get_Items()
0xa3cbf  ldloc.s  0xD
0xa3cc1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView/ListViewItemCollection::Remove(class [System.Windows.Forms]System.Windows.Forms.ListViewItem)
0xa3cc6  ldloc.s  9
0xa3cc8  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xa3ccd  brtrue.s loc_A3C94
0xa3ccf  leave.s  loc_A3CE6
0xa3cd1  ldloc.s  9
0xa3cd3  isinst   [mscorlib]System.IDisposable
0xa3cd8  stloc.s  0xC
0xa3cda  ldloc.s  0xC
0xa3cdc  brfalse.s loc_A3CE5
0xa3cde  ldloc.s  0xC
0xa3ce0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa3ce5  endfinally
0xa3ce6  ldarg.0
0xa3ce7  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView SubscriptionProcessing::currentListView
0xa3cec  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::EndUpdate()
0xa3cf1  leave.s  loc_A3D0B
0xa3cf3  ldarg.0
0xa3cf4  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView SubscriptionProcessing::currentListView
0xa3cf9  ldarg.0
0xa3cfa  ldftn    instance void SubscriptionProcessing::listView_SelectedIndexChanged(object sender, class [mscorlib]System.EventArgs e)
0xa3d00  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0xa3d05  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::add_SelectedIndexChanged(class [mscorlib]System.EventHandler)
0xa3d0a  endfinally
0xa3d0b  ldarg.0
0xa3d0c  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView SubscriptionProcessing::currentListView
0xa3d11  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ListView/ListViewItemCollection [System.Windows.Forms]System.Windows.Forms.ListView::get_Items()
0xa3d16  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.ListView/ListViewItemCollection::get_Count()
0xa3d1b  ldloc.s  7
0xa3d1d  ble.s    loc_A3D29
0xa3d1f  ldarg.0
0xa3d20  ldloc.s  7
0xa3d22  call     instance void SubscriptionProcessing::SelectIndex(int32 index)
0xa3d27  br.s     loc_A3D30
0xa3d29  ldarg.0
0xa3d2a  ldc.i4.0
0xa3d2b  call     instance void SubscriptionProcessing::SelectIndex(int32 index)
0xa3d30  ldarg.0
0xa3d31  call     instance void SubscriptionProcessing::FireSummaryInfoChangedEvent()
0xa3d36  ldloc.1
0xa3d37  brfalse.s loc_A3DA5
0xa3d39  ldloc.1
0xa3d3a  brfalse.s loc_A3D70
0xa3d3c  ldarg.0
0xa3d3d  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView SubscriptionProcessing::currentListView
0xa3d42  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ListView/SelectedIndexCollection [System.Windows.Forms]System.Windows.Forms.ListView::get_SelectedIndices()
0xa3d47  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.ListView/SelectedIndexCollection::get_Count()
0xa3d4c  ldc.i4.1
0xa3d4d  bne.un.s loc_A3D70
0xa3d4f  ldarg.0
0xa3d50  ldfld    class [System.Windows.Forms]System.Windows.Forms.IWin32Window SubscriptionProcessing::parentWindow
0xa3d55  ldstr    aMessagecannotd// "MessageCannotDeleteSubscriptionWhileItI"...
0xa3d5a  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0xa3d5f  ldstr    aViewername// "ViewerName"
0xa3d64  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0xa3d69  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string errorString, string caption)
0xa3d6e  br.s     loc_A3DA5
0xa3d70  ldloc.1
0xa3d71  brfalse.s loc_A3DA5
0xa3d73  ldarg.0
0xa3d74  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView SubscriptionProcessing::currentListView
0xa3d79  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ListView/SelectedIndexCollection [System.Windows.Forms]System.Windows.Forms.ListView::get_SelectedIndices()
0xa3d7e  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.ListView/SelectedIndexCollection::get_Count()
0xa3d83  ldc.i4.1
0xa3d84  ble.s    loc_A3DA5
0xa3d86  ldarg.0
0xa3d87  ldfld    class [System.Windows.Forms]System.Windows.Forms.IWin32Window SubscriptionProcessing::parentWindow
0xa3d8c  ldstr    aMessagecannotd_0// "MessageCannotDeleteSubscriptionWhileItI"...
0xa3d91  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0xa3d96  ldstr    aViewername// "ViewerName"
0xa3d9b  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0xa3da0  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string errorString, string caption)
0xa3da5  ldloc.3
0xa3da6  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::RemoveTaskFromList()
0xa3dab  ldloc.2
0xa3dac  ret
```
