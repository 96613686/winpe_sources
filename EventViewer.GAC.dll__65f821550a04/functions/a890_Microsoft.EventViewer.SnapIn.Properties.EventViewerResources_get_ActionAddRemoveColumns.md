# Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ActionAddRemoveColumns

- ea: `0xa890`
- end: `0xa8a5`
- name: `Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ActionAddRemoveColumns`
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

- `0xa895`: `ActionAddRemoveColumns`

## pseudocode

```c

```

## disassembly

```asm
0xa890  call     class [mscorlib]System.Resources.ResourceManager Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ResourceManager()
0xa895  ldstr    aActionaddremov// "ActionAddRemoveColumns"
0xa89a  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::resourceCulture
0xa89f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0xa8a4  ret
```
