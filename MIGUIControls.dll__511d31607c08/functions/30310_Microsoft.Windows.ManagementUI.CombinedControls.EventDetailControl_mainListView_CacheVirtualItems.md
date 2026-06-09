# Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::mainListView_CacheVirtualItems

- ea: `0x30310`
- end: `0x30339`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::mainListView_CacheVirtualItems`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1cd50`
- `0x1ce20`
- `0x2d250`

## string_xrefs

- `0x30311`: `mainListView_CacheVirtualItems`
- `0x3032e`: `mainListView_CacheVirtualItems`

## pseudocode

```c

```

## disassembly

```asm
0x30310  ldarg.0
0x30311  ldstr    aMainlistviewCa// "mainListView_CacheVirtualItems"
0x30316  call     void Microsoft.Windows.ManagementUI.CombinedControls.TimeTrace::StartMethod(object thisObject, string methodName)
0x3031b  ldarg.0
0x3031c  ldarg.2
0x3031d  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.CacheVirtualItemsEventArgs::get_StartIndex()
0x30322  ldarg.2
0x30323  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.CacheVirtualItemsEventArgs::get_EndIndex()
0x30328  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::CacheHint(int32 startIndex, int32 endIndex)
0x3032d  ldarg.0
0x3032e  ldstr    aMainlistviewCa// "mainListView_CacheVirtualItems"
0x30333  call     void Microsoft.Windows.ManagementUI.CombinedControls.TimeTrace::EndMethod(object thisObject, string methodName)
0x30338  ret
```
