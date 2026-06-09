# Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ActionSelEventsDeleteDesc

- ea: `0xa290`
- end: `0xa2a5`
- name: `Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ActionSelEventsDeleteDesc`
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

- `0xa295`: `ActionSelEventsDeleteDesc`

## pseudocode

```c

```

## disassembly

```asm
0xa290  call     class [mscorlib]System.Resources.ResourceManager Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ResourceManager()
0xa295  ldstr    aActionselevent_2// "ActionSelEventsDeleteDesc"
0xa29a  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::resourceCulture
0xa29f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0xa2a4  ret
```
