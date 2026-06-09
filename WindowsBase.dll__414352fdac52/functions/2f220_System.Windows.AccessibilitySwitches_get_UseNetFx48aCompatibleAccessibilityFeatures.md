# System.Windows.AccessibilitySwitches::get_UseNetFx48aCompatibleAccessibilityFeatures

- ea: `0x2f220`
- end: `0x2f230`
- name: `System.Windows.AccessibilitySwitches::get_UseNetFx48aCompatibleAccessibilityFeatures`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x2cb70`

## string_xrefs

- `0x2f220`: `Switch.UseLegacyAccessibilityFeatures.5`

## pseudocode

```c

```

## disassembly

```asm
0x2f220  ldstr    aSwitchUselegac_4// "Switch.UseLegacyAccessibilityFeatures.5"
0x2f225  ldsflda  int32 System.Windows.AccessibilitySwitches::_useLegacyAccessibilityFeatures5
0x2f22a  call     bool System.LocalAppContext::GetCachedSwitchValue(string switchName, int32& switchValue)
0x2f22f  ret
```
