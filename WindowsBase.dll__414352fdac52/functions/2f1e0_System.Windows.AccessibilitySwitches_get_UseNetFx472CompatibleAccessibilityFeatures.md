# System.Windows.AccessibilitySwitches::get_UseNetFx472CompatibleAccessibilityFeatures

- ea: `0x2f1e0`
- end: `0x2f1f0`
- name: `System.Windows.AccessibilitySwitches::get_UseNetFx472CompatibleAccessibilityFeatures`
- size: `16`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x2f390`

## callees

- `0x2cb70`

## string_xrefs

- `0x2f1e0`: `Switch.UseLegacyAccessibilityFeatures.3`

## pseudocode

```c

```

## disassembly

```asm
0x2f1e0  ldstr    aSwitchUselegac_1// "Switch.UseLegacyAccessibilityFeatures.3"
0x2f1e5  ldsflda  int32 System.Windows.AccessibilitySwitches::_useLegacyAccessibilityFeatures3
0x2f1ea  call     bool System.LocalAppContext::GetCachedSwitchValue(string switchName, int32& switchValue)
0x2f1ef  ret
```
