# Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ActionSelEventsDelete

- ea: `0xa270`
- end: `0xa285`
- name: `Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ActionSelEventsDelete`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x6220`

## callees

- `0x9e20`

## string_xrefs

- `0xa275`: `ActionSelEventsDelete`

## pseudocode

```c

```

## disassembly

```asm
0xa270  call     class [mscorlib]System.Resources.ResourceManager Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ResourceManager()
0xa275  ldstr    aActionselevent_1// "ActionSelEventsDelete"
0xa27a  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::resourceCulture
0xa27f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0xa284  ret
```
