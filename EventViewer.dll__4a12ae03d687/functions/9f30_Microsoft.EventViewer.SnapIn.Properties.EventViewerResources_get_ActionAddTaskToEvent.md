# Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ActionAddTaskToEvent

- ea: `0x9f30`
- end: `0x9f45`
- name: `Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ActionAddTaskToEvent`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x5d60`

## callees

- `0x9e20`

## string_xrefs

- `0x9f35`: `ActionAddTaskToEvent`

## pseudocode

```c

```

## disassembly

```asm
0x9f30  call     class [mscorlib]System.Resources.ResourceManager Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ResourceManager()
0x9f35  ldstr    aActionaddtaskt// "ActionAddTaskToEvent"
0x9f3a  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::resourceCulture
0x9f3f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x9f44  ret
```
