# Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ActionOpenItemDesc

- ea: `0xa830`
- end: `0xa845`
- name: `Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ActionOpenItemDesc`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4cd0`

## callees

- `0x9e20`

## string_xrefs

- `0xa835`: `ActionOpenItemDesc`

## pseudocode

```c

```

## disassembly

```asm
0xa830  call     class [mscorlib]System.Resources.ResourceManager Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ResourceManager()
0xa835  ldstr    aActionopenitem_0// "ActionOpenItemDesc"
0xa83a  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::resourceCulture
0xa83f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0xa844  ret
```
