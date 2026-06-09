# Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ViewerName

- ea: `0xa7b0`
- end: `0xa7c5`
- name: `Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ViewerName`
- size: `21`
- prototype: ``
- caller_count: `11`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x5f0`
- `0x7b0`
- `0x9e0`
- `0x1010`
- `0x13f0`
- `0x15c0`
- `0x38f0`
- `0x3cb0`
- `0x5560`
- `0x9120`
- `0x91b0`

## callees

- `0x9e20`

## pseudocode

```c

```

## disassembly

```asm
0xa7b0  call     class [mscorlib]System.Resources.ResourceManager Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ResourceManager()
0xa7b5  ldstr    aViewername// "ViewerName"
0xa7ba  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::resourceCulture
0xa7bf  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0xa7c4  ret
```
