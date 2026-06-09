# Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ActionOpenLogDesc

- ea: `0xa190`
- end: `0xa1a5`
- name: `Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ActionOpenLogDesc`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x29e0`

## callees

- `0x9e20`

## string_xrefs

- `0xa195`: `ActionOpenLogDesc`

## pseudocode

```c

```

## disassembly

```asm
0xa190  call     class [mscorlib]System.Resources.ResourceManager Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ResourceManager()
0xa195  ldstr    aActionopenlogd// "ActionOpenLogDesc"
0xa19a  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::resourceCulture
0xa19f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0xa1a4  ret
```
