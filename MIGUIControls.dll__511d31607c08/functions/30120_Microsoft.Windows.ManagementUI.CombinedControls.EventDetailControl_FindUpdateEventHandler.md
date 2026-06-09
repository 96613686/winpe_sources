# Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::FindUpdateEventHandler

- ea: `0x30120`
- end: `0x301a2`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::FindUpdateEventHandler`
- size: `130`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1cd50`
- `0x1ce20`
- `0x30120`
- `0x301b0`
- `0x3ee80`
- `0x3ffc0`
- `0x41170`

## string_xrefs

- `0x30121`: `FindUpdateEventHandler:`
- `0x30197`: `FindUpdateEventHandler:`

## pseudocode

```c

```

## disassembly

```asm
0x30120  ldarg.0
0x30121  ldstr    aFindupdateeven// "FindUpdateEventHandler:"
0x30126  call     void Microsoft.Windows.ManagementUI.CombinedControls.TimeTrace::StartMethod(object thisObject, string methodName)
0x3012b  ldarg.0
0x3012c  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::res
0x30131  brfalse.s loc_30177
0x30133  ldarg.0
0x30134  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::res
0x30139  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::get_FindCanceled()
0x3013e  brtrue.s loc_30177
0x30140  ldarg.0
0x30141  call     instance bool [System.Windows.Forms]System.Windows.Forms.Control::get_InvokeRequired()
0x30146  brfalse.s loc_3016B
0x30148  ldarg.0
0x30149  ldarg.0
0x3014a  ldfld    class UpdateFind Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::updateFindDelegate
0x3014f  ldc.i4.1
0x30150  newarr   [mscorlib]System.Object
0x30155  dup
0x30156  ldc.i4.0
0x30157  ldarg.2
0x30158  callvirt instance int32 Microsoft.Windows.ManagementUI.CombinedControls.FindItemEventArgs::get_IndexOfFoundItem()
0x3015d  box      [mscorlib]System.Int32
0x30162  stelem.ref
0x30163  call     instance class [mscorlib]System.IAsyncResult [System.Windows.Forms]System.Windows.Forms.Control::BeginInvoke(class [mscorlib]System.Delegate, object[])
0x30168  pop
0x30169  br.s     loc_30177
0x3016b  ldarg.0
0x3016c  ldarg.2
0x3016d  callvirt instance int32 Microsoft.Windows.ManagementUI.CombinedControls.FindItemEventArgs::get_IndexOfFoundItem()
0x30172  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::FindUpdate(int32 foundItemIndex)
0x30177  ldarg.0
0x30178  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::res
0x3017d  brfalse.s loc_30196
0x3017f  ldarg.0
0x30180  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::res
0x30185  ldarg.0
0x30186  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::FindUpdateEventHandler(object sender, class Microsoft.Windows.ManagementUI.CombinedControls.FindItemEventArgs e)
0x3018c  newobj   instance void class [mscorlib]System.EventHandler`1<class Microsoft.Windows.ManagementUI.CombinedControls.FindItemEventArgs>::.ctor(object, native int)
0x30191  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::remove_ItemFound(class [mscorlib]System.EventHandler`1<class Microsoft.Windows.ManagementUI.CombinedControls.FindItemEventArgs> value)
0x30196  ldarg.0
0x30197  ldstr    aFindupdateeven// "FindUpdateEventHandler:"
0x3019c  call     void Microsoft.Windows.ManagementUI.CombinedControls.TimeTrace::EndMethod(object thisObject, string methodName)
0x301a1  ret
```
