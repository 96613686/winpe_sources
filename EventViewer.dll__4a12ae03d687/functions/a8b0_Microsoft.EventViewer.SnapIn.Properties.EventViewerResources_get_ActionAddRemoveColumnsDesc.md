# Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ActionAddRemoveColumnsDesc

- ea: `0xa8b0`
- end: `0xa8c5`
- name: `Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ActionAddRemoveColumnsDesc`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x2ad0`

## callees

- `0x9e20`

## string_xrefs

- `0xa8b5`: `ActionAddRemoveColumnsDesc`

## pseudocode

```c

```

## disassembly

```asm
0xa8b0  call     class [mscorlib]System.Resources.ResourceManager Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ResourceManager()
0xa8b5  ldstr    aActionaddremov_0// "ActionAddRemoveColumnsDesc"
0xa8ba  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::resourceCulture
0xa8bf  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0xa8c4  ret
```
