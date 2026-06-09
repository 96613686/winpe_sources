# System.Windows.Xps.Serialization.VisualSerializer::WriteCommonAttrs

- ea: `0x384e0`
- end: `0x38579`
- name: `System.Windows.Xps.Serialization.VisualSerializer::WriteCommonAttrs`
- size: `153`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x385c0`
- `0x38840`
- `0x38ea0`

## callees

- `0x36950`
- `0x384e0`

## string_xrefs

- `0x38561`: `FixedPage.NavigateUri`

## pseudocode

```c

```

## disassembly

```asm
0x384e0  ldarg.0
0x384e1  ldfld    string System.Windows.Xps.Serialization.VisualSerializer::_nameAttr
0x384e6  brfalse.s loc_38500
0x384e8  ldarg.0
0x384e9  ldstr    aName_0// "Name"
0x384ee  ldarg.0
0x384ef  ldfld    string System.Windows.Xps.Serialization.VisualSerializer::_nameAttr
0x384f4  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteAttr(string attribute, object val)
0x384f9  ldarg.0
0x384fa  ldnull
0x384fb  stfld    string System.Windows.Xps.Serialization.VisualSerializer::_nameAttr
0x38500  ldarg.0
0x38501  ldfld    class [PresentationCore]System.Windows.Media.Visual System.Windows.Xps.Serialization.VisualSerializer::_node
0x38506  brfalse.s loc_38552
0x38508  ldarg.1
0x38509  brfalse.s loc_3854B
0x3850b  ldarg.0
0x3850c  ldfld    class [PresentationCore]System.Windows.Media.Visual System.Windows.Xps.Serialization.VisualSerializer::_node
0x38511  call     string [PresentationCore]System.Windows.Automation.AutomationProperties::GetName(class [WindowsBase]System.Windows.DependencyObject)
0x38516  stloc.0
0x38517  ldloc.0
0x38518  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3851d  brtrue.s loc_3852B
0x3851f  ldarg.0
0x38520  ldstr    aAutomationprop// "AutomationProperties.Name"
0x38525  ldloc.0
0x38526  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteAttr(string attribute, object val)
0x3852b  ldarg.0
0x3852c  ldfld    class [PresentationCore]System.Windows.Media.Visual System.Windows.Xps.Serialization.VisualSerializer::_node
0x38531  call     string [PresentationCore]System.Windows.Automation.AutomationProperties::GetHelpText(class [WindowsBase]System.Windows.DependencyObject)
0x38536  stloc.1
0x38537  ldloc.1
0x38538  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3853d  brtrue.s loc_3854B
0x3853f  ldarg.0
0x38540  ldstr    aAutomationprop_0// "AutomationProperties.HelpText"
0x38545  ldloc.1
0x38546  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteAttr(string attribute, object val)
0x3854b  ldarg.0
0x3854c  ldnull
0x3854d  stfld    class [PresentationCore]System.Windows.Media.Visual System.Windows.Xps.Serialization.VisualSerializer::_node
0x38552  ldarg.0
0x38553  ldfld    class [System]System.Uri System.Windows.Xps.Serialization.VisualSerializer::_navigateUri
0x38558  ldnull
0x38559  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x3855e  brfalse.s loc_38578
0x38560  ldarg.0
0x38561  ldstr    aFixedpageNavig// "FixedPage.NavigateUri"
0x38566  ldarg.0
0x38567  ldfld    class [System]System.Uri System.Windows.Xps.Serialization.VisualSerializer::_navigateUri
0x3856c  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteAttr(string attribute, object val)
0x38571  ldarg.0
0x38572  ldnull
0x38573  stfld    class [System]System.Uri System.Windows.Xps.Serialization.VisualSerializer::_navigateUri
0x38578  ret
```
