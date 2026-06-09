# System.Windows.Controls.FlowDocumentReader::ViewingModeEnabledChanged

- ea: `0x162e90`
- end: `0x162f10`
- name: `System.Windows.Controls.FlowDocumentReader::ViewingModeEnabledChanged`
- size: `128`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x13020`
- `0x38c40`
- `0xbcb80`
- `0x161b30`
- `0x161ba0`
- `0x161be0`
- `0x161c20`
- `0x162570`
- `0x162e90`

## string_xrefs

- `0x162ee9`: `FlowDocumentReaderViewingModeEnabledConflict`
- `0x162ec3`: `FlowDocumentReaderCannotDisableAllViewingModes`

## pseudocode

```c

```

## disassembly

```asm
0x162e90  ldarg.0
0x162e91  brfalse.s loc_162E9E
0x162e93  ldarg.0
0x162e94  isinst   System.Windows.Controls.FlowDocumentReader
0x162e99  ldnull
0x162e9a  cgt.un
0x162e9c  br.s     loc_162E9F
0x162e9e  ldc.i4.0
0x162e9f  call     void [WindowsBase]MS.Internal.Invariant::Assert(bool)
0x162ea4  ldarg.0
0x162ea5  castclass System.Windows.Controls.FlowDocumentReader
0x162eaa  stloc.0
0x162eab  ldloc.0
0x162eac  callvirt instance bool System.Windows.Controls.FlowDocumentReader::get_IsPageViewEnabled()
0x162eb1  brtrue.s loc_162ED3
0x162eb3  ldloc.0
0x162eb4  callvirt instance bool System.Windows.Controls.FlowDocumentReader::get_IsTwoPageViewEnabled()
0x162eb9  brtrue.s loc_162ED3
0x162ebb  ldloc.0
0x162ebc  callvirt instance bool System.Windows.Controls.FlowDocumentReader::get_IsScrollViewEnabled()
0x162ec1  brtrue.s loc_162ED3
0x162ec3  ldstr    aFlowdocumentre_5// "FlowDocumentReaderCannotDisableAllViewi"...
0x162ec8  call     string System.Windows.SR::Get(string id)
0x162ecd  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x162ed2  throw
0x162ed3  ldloc.0
0x162ed4  callvirt instance bool System.Windows.FrameworkElement::get_IsInitialized()
0x162ed9  brfalse.s loc_162EF9
0x162edb  ldloc.0
0x162edc  ldloc.0
0x162edd  callvirt instance valuetype System.Windows.Controls.FlowDocumentReaderViewingMode System.Windows.Controls.FlowDocumentReader::get_ViewingMode()
0x162ee2  callvirt instance bool System.Windows.Controls.FlowDocumentReader::CanSwitchToViewingMode(valuetype System.Windows.Controls.FlowDocumentReaderViewingMode mode)
0x162ee7  brtrue.s loc_162EF9
0x162ee9  ldstr    aFlowdocumentre_4// "FlowDocumentReaderViewingModeEnabledCon"...
0x162eee  call     string System.Windows.SR::Get(string id)
0x162ef3  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x162ef8  throw
0x162ef9  ldloc.0
0x162efa  call     class [PresentationCore]System.Windows.Automation.Peers.AutomationPeer [PresentationCore]System.Windows.Automation.Peers.UIElementAutomationPeer::FromElement(class [PresentationCore]System.Windows.UIElement)
0x162eff  isinst   System.Windows.Automation.Peers.FlowDocumentReaderAutomationPeer
0x162f04  stloc.1
0x162f05  ldloc.1
0x162f06  brfalse.s loc_162F0F
0x162f08  ldloc.1
0x162f09  ldarg.1
0x162f0a  callvirt instance void System.Windows.Automation.Peers.FlowDocumentReaderAutomationPeer::RaiseSupportedViewsChangedEvent(valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x162f0f  ret
```
