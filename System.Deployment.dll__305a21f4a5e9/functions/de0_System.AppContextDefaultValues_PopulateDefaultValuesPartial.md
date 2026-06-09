# System.AppContextDefaultValues::PopulateDefaultValuesPartial

- ea: `0xde0`
- end: `0xe50`
- name: `System.AppContextDefaultValues::PopulateDefaultValuesPartial`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0xc30`

## callees

- `0xde0`
- `0xff0`

## string_xrefs

- `0xdf5`: `Switch.UseLegacyAccessibilityFeatures`
- `0xe08`: `Switch.UseLegacyAccessibilityFeatures.2`
- `0xe1b`: `Switch.UseLegacyAccessibilityFeatures.3`
- `0xe2e`: `Switch.UseLegacyAccessibilityFeatures.4`
- `0xe39`: `Switch.UseLegacyAccessibilityFeatures.5`

## pseudocode

```c

```

## disassembly

```asm
0xde0  ldarg.0
0xde1  ldstr    aNetframework// ".NETFramework"
0xde6  call     bool [mscorlib]System.String::op_Equality(string, string)
0xdeb  brfalse.s loc_E4F
0xded  ldarg.2
0xdee  ldc.i4   0x9EFC
0xdf3  bgt.s    loc_E00
0xdf5  ldstr    aSwitchUselegac// "Switch.UseLegacyAccessibilityFeatures"
0xdfa  ldc.i4.1
0xdfb  call     void System.LocalAppContext::DefineSwitchDefault(string switchName, bool initialValue)
0xe00  ldarg.2
0xe01  ldc.i4   0x9EFD
0xe06  bgt.s    loc_E13
0xe08  ldstr    aSwitchUselegac_0// "Switch.UseLegacyAccessibilityFeatures.2"
0xe0d  ldc.i4.1
0xe0e  call     void System.LocalAppContext::DefineSwitchDefault(string switchName, bool initialValue)
0xe13  ldarg.2
0xe14  ldc.i4   0x9EFE
0xe19  bgt.s    loc_E26
0xe1b  ldstr    aSwitchUselegac_1// "Switch.UseLegacyAccessibilityFeatures.3"
0xe20  ldc.i4.1
0xe21  call     void System.LocalAppContext::DefineSwitchDefault(string switchName, bool initialValue)
0xe26  ldarg.2
0xe27  ldc.i4   0x9F60
0xe2c  bgt.s    loc_E44
0xe2e  ldstr    aSwitchUselegac_2// "Switch.UseLegacyAccessibilityFeatures.4"
0xe33  ldc.i4.1
0xe34  call     void System.LocalAppContext::DefineSwitchDefault(string switchName, bool initialValue)
0xe39  ldstr    aSwitchUselegac_3// "Switch.UseLegacyAccessibilityFeatures.5"
0xe3e  ldc.i4.1
0xe3f  call     void System.LocalAppContext::DefineSwitchDefault(string switchName, bool initialValue)
0xe44  ldstr    aSwitchSystemWi// "Switch.System.Windows.Forms.UseLegacyTo"...
0xe49  ldc.i4.1
0xe4a  call     void System.LocalAppContext::DefineSwitchDefault(string switchName, bool initialValue)
0xe4f  ret
```
