# Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ActionAddTaskToView

- ea: `0x9f70`
- end: `0x9f85`
- name: `Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ActionAddTaskToView`
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

- `0x9f75`: `ActionAddTaskToView`

## pseudocode

```c

```

## disassembly

```asm
0x9f70  call     class [mscorlib]System.Resources.ResourceManager Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ResourceManager()
0x9f75  ldstr    aActionaddtaskt_1// "ActionAddTaskToView"
0x9f7a  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::resourceCulture
0x9f7f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x9f84  ret
```
