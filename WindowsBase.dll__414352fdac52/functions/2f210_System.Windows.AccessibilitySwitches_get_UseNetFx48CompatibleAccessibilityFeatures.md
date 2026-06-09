# System.Windows.AccessibilitySwitches::get_UseNetFx48CompatibleAccessibilityFeatures

- ea: `0x2f210`
- end: `0x2f220`
- name: `System.Windows.AccessibilitySwitches::get_UseNetFx48CompatibleAccessibilityFeatures`
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

- `0x2f210`: `Switch.UseLegacyAccessibilityFeatures.4`

## pseudocode

```c

```

## disassembly

```asm
0x2f210  ldstr    aSwitchUselegac_3// "Switch.UseLegacyAccessibilityFeatures.4"
0x2f215  ldsflda  int32 System.Windows.AccessibilitySwitches::_useLegacyAccessibilityFeatures4
0x2f21a  call     bool System.LocalAppContext::GetCachedSwitchValue(string switchName, int32& switchValue)
0x2f21f  ret
```
