# Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ActionAddTaskDesc

- ea: `0x9f10`
- end: `0x9f25`
- name: `Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ActionAddTaskDesc`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x2d30`

## callees

- `0x9e20`

## string_xrefs

- `0x9f15`: `ActionAddTaskDesc`

## pseudocode

```c

```

## disassembly

```asm
0x9f10  call     class [mscorlib]System.Resources.ResourceManager Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ResourceManager()
0x9f15  ldstr    aActionaddtaskd// "ActionAddTaskDesc"
0x9f1a  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::resourceCulture
0x9f1f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x9f24  ret
```
