# System.Windows.Automation.Peers.FlowDocumentReaderAutomationPeer::System.Windows.Automation.Provider.IMultipleViewProvider.GetViewName

- ea: `0xbcd30`
- end: `0xbcd78`
- name: `System.Windows.Automation.Peers.FlowDocumentReaderAutomationPeer::System.Windows.Automation.Provider.IMultipleViewProvider.GetViewName`
- size: `72`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x38c40`
- `0xbcd00`
- `0xbcd30`

## string_xrefs

- `0xbcd49`: `FlowDocumentReader_MultipleViewProvider_PageViewName`
- `0xbcd5a`: `FlowDocumentReader_MultipleViewProvider_TwoPageViewName`
- `0xbcd6b`: `FlowDocumentReader_MultipleViewProvider_ScrollViewName`

## pseudocode

```c

```

## disassembly

```asm
0xbcd30  ldsfld   string [mscorlib]System.String::Empty
0xbcd35  stloc.0
0xbcd36  ldarg.1
0xbcd37  ldc.i4.0
0xbcd38  blt.s    loc_BCD76
0xbcd3a  ldarg.1
0xbcd3b  ldc.i4.2
0xbcd3c  bgt.s    loc_BCD76
0xbcd3e  ldarg.0
0xbcd3f  ldarg.1
0xbcd40  call     instance valuetype System.Windows.Controls.FlowDocumentReaderViewingMode System.Windows.Automation.Peers.FlowDocumentReaderAutomationPeer::ConvertViewIdToMode(int32 viewId)
0xbcd45  stloc.1
0xbcd46  ldloc.1
0xbcd47  brtrue.s loc_BCD56
0xbcd49  ldstr    aFlowdocumentre_0// "FlowDocumentReader_MultipleViewProvider"...
0xbcd4e  call     string System.Windows.SR::Get(string id)
0xbcd53  stloc.0
0xbcd54  br.s     loc_BCD76
0xbcd56  ldloc.1
0xbcd57  ldc.i4.1
0xbcd58  bne.un.s loc_BCD67
0xbcd5a  ldstr    aFlowdocumentre_1// "FlowDocumentReader_MultipleViewProvider"...
0xbcd5f  call     string System.Windows.SR::Get(string id)
0xbcd64  stloc.0
0xbcd65  br.s     loc_BCD76
0xbcd67  ldloc.1
0xbcd68  ldc.i4.2
0xbcd69  bne.un.s loc_BCD76
0xbcd6b  ldstr    aFlowdocumentre_2// "FlowDocumentReader_MultipleViewProvider"...
0xbcd70  call     string System.Windows.SR::Get(string id)
0xbcd75  stloc.0
0xbcd76  ldloc.0
0xbcd77  ret
```
