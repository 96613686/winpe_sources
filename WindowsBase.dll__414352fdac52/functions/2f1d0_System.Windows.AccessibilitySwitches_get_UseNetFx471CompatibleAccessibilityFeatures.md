# System.Windows.AccessibilitySwitches::get_UseNetFx471CompatibleAccessibilityFeatures

- ea: `0x2f1d0`
- end: `0x2f1e0`
- name: `System.Windows.AccessibilitySwitches::get_UseNetFx471CompatibleAccessibilityFeatures`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x2cb70`

## string_xrefs

- `0x2f1d0`: `Switch.UseLegacyAccessibilityFeatures.2`

## pseudocode

```c

```

## disassembly

```asm
0x2f1d0  ldstr    aSwitchUselegac_0// "Switch.UseLegacyAccessibilityFeatures.2"
0x2f1d5  ldsflda  int32 System.Windows.AccessibilitySwitches::_useLegacyAccessibilityFeatures2
0x2f1da  call     bool System.LocalAppContext::GetCachedSwitchValue(string switchName, int32& switchValue)
0x2f1df  ret
```
