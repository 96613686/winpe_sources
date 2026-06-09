# Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_Copy_16

- ea: `0xa390`
- end: `0xa3aa`
- name: `Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_Copy_16`
- size: `26`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x86e0`

## callees

- `0x9e20`

## string_xrefs

- `0xa395`: `Copy_16`

## pseudocode

```c

```

## disassembly

```asm
0xa390  call     class [mscorlib]System.Resources.ResourceManager Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ResourceManager()
0xa395  ldstr    aCopy16// "Copy_16"
0xa39a  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::resourceCulture
0xa39f  callvirt instance object [mscorlib]System.Resources.ResourceManager::GetObject(string, class [mscorlib]System.Globalization.CultureInfo)
0xa3a4  castclass [System.Drawing]System.Drawing.Icon
0xa3a9  ret
```
