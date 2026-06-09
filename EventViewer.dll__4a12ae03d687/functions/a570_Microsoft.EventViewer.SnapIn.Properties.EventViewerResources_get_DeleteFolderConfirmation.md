# Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_DeleteFolderConfirmation

- ea: `0xa570`
- end: `0xa585`
- name: `Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_DeleteFolderConfirmation`
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

- `0xa575`: `DeleteFolderConfirmation`

## pseudocode

```c

```

## disassembly

```asm
0xa570  call     class [mscorlib]System.Resources.ResourceManager Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ResourceManager()
0xa575  ldstr    aDeletefolderco// "DeleteFolderConfirmation"
0xa57a  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::resourceCulture
0xa57f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0xa584  ret
```
