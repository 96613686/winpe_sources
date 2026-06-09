# Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ActionAddTask

- ea: `0x9ef0`
- end: `0x9f05`
- name: `Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ActionAddTask`
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

- `0x9ef5`: `ActionAddTask`

## pseudocode

```c

```

## disassembly

```asm
0x9ef0  call     class [mscorlib]System.Resources.ResourceManager Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ResourceManager()
0x9ef5  ldstr    aActionaddtask// "ActionAddTask"
0x9efa  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::resourceCulture
0x9eff  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x9f04  ret
```
