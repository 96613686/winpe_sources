# Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_AttachATask32_16

- ea: `0xa790`
- end: `0xa7aa`
- name: `Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_AttachATask32_16`
- size: `26`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x86e0`

## callees

- `0x9e20`

## string_xrefs

- `0xa795`: `AttachATask32_16`

## pseudocode

```c

```

## disassembly

```asm
0xa790  call     class [mscorlib]System.Resources.ResourceManager Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ResourceManager()
0xa795  ldstr    aAttachatask321// "AttachATask32_16"
0xa79a  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::resourceCulture
0xa79f  callvirt instance object [mscorlib]System.Resources.ResourceManager::GetObject(string, class [mscorlib]System.Globalization.CultureInfo)
0xa7a4  castclass [System.Drawing]System.Drawing.Icon
0xa7a9  ret
```
