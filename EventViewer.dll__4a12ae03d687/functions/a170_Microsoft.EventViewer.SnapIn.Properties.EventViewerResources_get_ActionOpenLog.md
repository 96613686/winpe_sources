# Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ActionOpenLog

- ea: `0xa170`
- end: `0xa185`
- name: `Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ActionOpenLog`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x29e0`

## callees

- `0x9e20`

## string_xrefs

- `0xa175`: `ActionOpenLog`

## pseudocode

```c

```

## disassembly

```asm
0xa170  call     class [mscorlib]System.Resources.ResourceManager Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ResourceManager()
0xa175  ldstr    aActionopenlog// "ActionOpenLog"
0xa17a  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::resourceCulture
0xa17f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0xa184  ret
```
