# Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ActionAddTaskToViewDesc

- ea: `0x9f90`
- end: `0x9fa5`
- name: `Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ActionAddTaskToViewDesc`
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

- `0x9f95`: `ActionAddTaskToViewDesc`

## pseudocode

```c

```

## disassembly

```asm
0x9f90  call     class [mscorlib]System.Resources.ResourceManager Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ResourceManager()
0x9f95  ldstr    aActionaddtaskt_2// "ActionAddTaskToViewDesc"
0x9f9a  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::resourceCulture
0x9f9f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x9fa4  ret
```
