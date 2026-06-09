# Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_CreateView_16

- ea: `0xa510`
- end: `0xa52a`
- name: `Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_CreateView_16`
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

- `0xa515`: `CreateView_16`

## pseudocode

```c

```

## disassembly

```asm
0xa510  call     class [mscorlib]System.Resources.ResourceManager Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ResourceManager()
0xa515  ldstr    aCreateview16// "CreateView_16"
0xa51a  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::resourceCulture
0xa51f  callvirt instance object [mscorlib]System.Resources.ResourceManager::GetObject(string, class [mscorlib]System.Globalization.CultureInfo)
0xa524  castclass [System.Drawing]System.Drawing.Icon
0xa529  ret
```
