# Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ActionOpenItem

- ea: `0xa810`
- end: `0xa825`
- name: `Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ActionOpenItem`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4cd0`

## callees

- `0x9e20`

## string_xrefs

- `0xa815`: `ActionOpenItem`

## pseudocode

```c

```

## disassembly

```asm
0xa810  call     class [mscorlib]System.Resources.ResourceManager Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ResourceManager()
0xa815  ldstr    aActionopenitem// "ActionOpenItem"
0xa81a  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::resourceCulture
0xa81f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0xa824  ret
```
