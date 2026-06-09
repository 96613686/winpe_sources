# System.Windows.AccessibilitySwitches::VerifyDependencies

- ea: `0x2f390`
- end: `0x2f42a`
- name: `System.Windows.AccessibilitySwitches::VerifyDependencies`
- size: `154`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x2f2e0`

## callees

- `0x2c100`
- `0x2f1e0`
- `0x2f1f0`
- `0x2f200`
- `0x2f210`
- `0x2f230`
- `0x2f390`
- `0x2f430`

## string_xrefs

- `0x2f3ae`: `Switch.UseLegacyAccessibilityFeatures.3`
- `0x2f3e1`: `Switch.UseLegacyAccessibilityFeatures.3`
- `0x2f414`: `Switch.UseLegacyAccessibilityFeatures.5`
- `0x2f39f`: `AccessibilitySwitchDependencyNotSatisfied`
- `0x2f3d2`: `AccessibilitySwitchDependencyNotSatisfied`
- `0x2f405`: `AccessibilitySwitchDependencyNotSatisfied`

## pseudocode

```c

```

## disassembly

```asm
0x2f390  call     bool System.Windows.AccessibilitySwitches::get_UseLegacyToolTipDisplay()
0x2f395  brtrue.s loc_2F3C3
0x2f397  call     bool System.Windows.AccessibilitySwitches::get_UseNetFx472CompatibleAccessibilityFeatures()
0x2f39c  brfalse.s loc_2F3C3
0x2f39e  ldarg.0
0x2f39f  ldstr    aAccessibilitys// "AccessibilitySwitchDependencyNotSatisfi"...
0x2f3a4  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x2f3a9  ldstr    aSwitchUselegac_2// "Switch.UseLegacyToolTipDisplay"
0x2f3ae  ldstr    aSwitchUselegac_1// "Switch.UseLegacyAccessibilityFeatures.3"
0x2f3b3  ldc.i4.3
0x2f3b4  box      [mscorlib]System.Int32
0x2f3b9  call     string [mscorlib]System.String::Format(string, object, object, object)
0x2f3be  call     void System.Windows.AccessibilitySwitches::DispatchOnError(class System.Windows.Threading.Dispatcher dispatcher, string message)
0x2f3c3  call     bool System.Windows.AccessibilitySwitches::get_ItemsControlDoesNotSupportAutomation()
0x2f3c8  brtrue.s loc_2F3F6
0x2f3ca  call     bool System.Windows.AccessibilitySwitches::get_UseNetFx472CompatibleAccessibilityFeatures()
0x2f3cf  brfalse.s loc_2F3F6
0x2f3d1  ldarg.0
0x2f3d2  ldstr    aAccessibilitys// "AccessibilitySwitchDependencyNotSatisfi"...
0x2f3d7  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x2f3dc  ldstr    aSwitchSystemWi_0// "Switch.System.Windows.Controls.ItemsCon"...
0x2f3e1  ldstr    aSwitchUselegac_1// "Switch.UseLegacyAccessibilityFeatures.3"
0x2f3e6  ldc.i4.3
0x2f3e7  box      [mscorlib]System.Int32
0x2f3ec  call     string [mscorlib]System.String::Format(string, object, object, object)
0x2f3f1  call     void System.Windows.AccessibilitySwitches::DispatchOnError(class System.Windows.Threading.Dispatcher dispatcher, string message)
0x2f3f6  call     bool System.Windows.AccessibilitySwitches::get_OptOutOfGridColumnResizeUsingKeyboard()
0x2f3fb  brtrue.s loc_2F429
0x2f3fd  call     bool System.Windows.AccessibilitySwitches::get_UseNetFx48CompatibleAccessibilityFeatures()
0x2f402  brfalse.s loc_2F429
0x2f404  ldarg.0
0x2f405  ldstr    aAccessibilitys// "AccessibilitySwitchDependencyNotSatisfi"...
0x2f40a  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x2f40f  ldstr    aSwitchSystemWi_1// "Switch.System.Windows.Controls.OptOutOf"...
0x2f414  ldstr    aSwitchUselegac_4// "Switch.UseLegacyAccessibilityFeatures.5"
0x2f419  ldc.i4.5
0x2f41a  box      [mscorlib]System.Int32
0x2f41f  call     string [mscorlib]System.String::Format(string, object, object, object)
0x2f424  call     void System.Windows.AccessibilitySwitches::DispatchOnError(class System.Windows.Threading.Dispatcher dispatcher, string message)
0x2f429  ret
```
