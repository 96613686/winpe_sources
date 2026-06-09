# System.Windows.AccessibilitySwitches::get_UseNetFx47CompatibleAccessibilityFeatures

- ea: `0x2f1c0`
- end: `0x2f1d0`
- name: `System.Windows.AccessibilitySwitches::get_UseNetFx47CompatibleAccessibilityFeatures`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x2cb70`

## string_xrefs

- `0x2f1c0`: `Switch.UseLegacyAccessibilityFeatures`

## pseudocode

```c

```

## disassembly

```asm
0x2f1c0  ldstr    aSwitchUselegac// "Switch.UseLegacyAccessibilityFeatures"
0x2f1c5  ldsflda  int32 System.Windows.AccessibilitySwitches::_useLegacyAccessibilityFeatures
0x2f1ca  call     bool System.LocalAppContext::GetCachedSwitchValue(string switchName, int32& switchValue)
0x2f1cf  ret
```
