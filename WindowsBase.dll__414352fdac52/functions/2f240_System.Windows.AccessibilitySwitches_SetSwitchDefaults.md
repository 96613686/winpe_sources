# System.Windows.AccessibilitySwitches::SetSwitchDefaults

- ea: `0x2f240`
- end: `0x2f2d2`
- name: `System.Windows.AccessibilitySwitches::SetSwitchDefaults`
- size: `146`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x2c9d0`

## callees

- `0x2cbb0`
- `0x2f240`

## string_xrefs

- `0x2f259`: `Switch.UseLegacyAccessibilityFeatures`
- `0x2f26c`: `Switch.UseLegacyAccessibilityFeatures.2`
- `0x2f27f`: `Switch.UseLegacyAccessibilityFeatures.3`
- `0x2f2a8`: `Switch.UseLegacyAccessibilityFeatures.4`
- `0x2f2bb`: `Switch.UseLegacyAccessibilityFeatures.5`

## pseudocode

```c

```

## disassembly

```asm
0x2f240  ldsflda  int32 System.Windows.AccessibilitySwitches::s_DefaultsSet
0x2f245  ldc.i4.1
0x2f246  ldc.i4.0
0x2f247  call     int32 [mscorlib]System.Threading.Interlocked::CompareExchange(int32&, int32, int32)
0x2f24c  brtrue   loc_2F2D1
0x2f251  ldarg.0
0x2f252  ldc.i4   0x9EFC
0x2f257  bgt.s    loc_2F264
0x2f259  ldstr    aSwitchUselegac// "Switch.UseLegacyAccessibilityFeatures"
0x2f25e  ldc.i4.1
0x2f25f  call     void System.LocalAppContext::DefineSwitchDefault(string switchName, bool initialValue)
0x2f264  ldarg.0
0x2f265  ldc.i4   0x9EFD
0x2f26a  bgt.s    loc_2F277
0x2f26c  ldstr    aSwitchUselegac_0// "Switch.UseLegacyAccessibilityFeatures.2"
0x2f271  ldc.i4.1
0x2f272  call     void System.LocalAppContext::DefineSwitchDefault(string switchName, bool initialValue)
0x2f277  ldarg.0
0x2f278  ldc.i4   0x9EFE
0x2f27d  bgt.s    loc_2F2A0
0x2f27f  ldstr    aSwitchUselegac_1// "Switch.UseLegacyAccessibilityFeatures.3"
0x2f284  ldc.i4.1
0x2f285  call     void System.LocalAppContext::DefineSwitchDefault(string switchName, bool initialValue)
0x2f28a  ldstr    aSwitchUselegac_2// "Switch.UseLegacyToolTipDisplay"
0x2f28f  ldc.i4.1
0x2f290  call     void System.LocalAppContext::DefineSwitchDefault(string switchName, bool initialValue)
0x2f295  ldstr    aSwitchSystemWi_0// "Switch.System.Windows.Controls.ItemsCon"...
0x2f29a  ldc.i4.1
0x2f29b  call     void System.LocalAppContext::DefineSwitchDefault(string switchName, bool initialValue)
0x2f2a0  ldarg.0
0x2f2a1  ldc.i4   0x9F60
0x2f2a6  bgt.s    loc_2F2B3
0x2f2a8  ldstr    aSwitchUselegac_3// "Switch.UseLegacyAccessibilityFeatures.4"
0x2f2ad  ldc.i4.1
0x2f2ae  call     void System.LocalAppContext::DefineSwitchDefault(string switchName, bool initialValue)
0x2f2b3  ldarg.0
0x2f2b4  ldc.i4   0x9F60
0x2f2b9  bgt.s    loc_2F2D1
0x2f2bb  ldstr    aSwitchUselegac_4// "Switch.UseLegacyAccessibilityFeatures.5"
0x2f2c0  ldc.i4.1
0x2f2c1  call     void System.LocalAppContext::DefineSwitchDefault(string switchName, bool initialValue)
0x2f2c6  ldstr    aSwitchSystemWi_1// "Switch.System.Windows.Controls.OptOutOf"...
0x2f2cb  ldc.i4.1
0x2f2cc  call     void System.LocalAppContext::DefineSwitchDefault(string switchName, bool initialValue)
0x2f2d1  ret
```
