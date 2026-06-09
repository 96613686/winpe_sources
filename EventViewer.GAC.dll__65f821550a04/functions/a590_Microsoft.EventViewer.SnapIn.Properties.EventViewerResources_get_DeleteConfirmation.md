# Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_DeleteConfirmation

- ea: `0xa590`
- end: `0xa5a5`
- name: `Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_DeleteConfirmation`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x38f0`

## callees

- `0x9e20`

## string_xrefs

- `0xa595`: `DeleteConfirmation`

## pseudocode

```c

```

## disassembly

```asm
0xa590  call     class [mscorlib]System.Resources.ResourceManager Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ResourceManager()
0xa595  ldstr    aDeleteconfirma// "DeleteConfirmation"
0xa59a  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::resourceCulture
0xa59f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0xa5a4  ret
```
