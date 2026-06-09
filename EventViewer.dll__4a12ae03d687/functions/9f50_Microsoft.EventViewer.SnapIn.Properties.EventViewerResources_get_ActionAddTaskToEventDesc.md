# Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ActionAddTaskToEventDesc

- ea: `0x9f50`
- end: `0x9f65`
- name: `Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ActionAddTaskToEventDesc`
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

- `0x9f55`: `ActionAddTaskToEventDesc`

## pseudocode

```c

```

## disassembly

```asm
0x9f50  call     class [mscorlib]System.Resources.ResourceManager Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ResourceManager()
0x9f55  ldstr    aActionaddtaskt_0// "ActionAddTaskToEventDesc"
0x9f5a  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::resourceCulture
0x9f5f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x9f64  ret
```
