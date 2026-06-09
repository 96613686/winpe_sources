# System.Windows.FrameworkCompatibilityPreferences::SetIMECompositionTraceFromAppSettings

- ea: `0x8f00`
- end: `0x8f21`
- name: `System.Windows.FrameworkCompatibilityPreferences::SetIMECompositionTraceFromAppSettings`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x8920`

## string_xrefs

- `0x8f01`: `IMECompositionTraceTarget`
- `0x8f11`: `IMECompositionTraceFile`

## pseudocode

```c

```

## disassembly

```asm
0x8f00  ldarg.0
0x8f01  ldstr    aImecomposition// "IMECompositionTraceTarget"
0x8f06  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x8f0b  stsfld   string System.Windows.FrameworkCompatibilityPreferences::_IMECompositionTraceTarget
0x8f10  ldarg.0
0x8f11  ldstr    aImecomposition_0// "IMECompositionTraceFile"
0x8f16  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x8f1b  stsfld   string System.Windows.FrameworkCompatibilityPreferences::_IMECompositionTraceFile
0x8f20  ret
```
