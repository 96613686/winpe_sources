# Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_OpenLogFile_16

- ea: `0xa470`
- end: `0xa48a`
- name: `Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_OpenLogFile_16`
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

- `0xa475`: `OpenLogFile_16`

## pseudocode

```c

```

## disassembly

```asm
0xa470  call     class [mscorlib]System.Resources.ResourceManager Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ResourceManager()
0xa475  ldstr    aOpenlogfile16// "OpenLogFile_16"
0xa47a  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::resourceCulture
0xa47f  callvirt instance object [mscorlib]System.Resources.ResourceManager::GetObject(string, class [mscorlib]System.Globalization.CultureInfo)
0xa484  castclass [System.Drawing]System.Drawing.Icon
0xa489  ret
```
