# Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ConnectingToRemoteComputerTitle

- ea: `0xa930`
- end: `0xa945`
- name: `Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ConnectingToRemoteComputerTitle`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x8d0`

## callees

- `0x9e20`

## string_xrefs

- `0xa935`: `ConnectingToRemoteComputerTitle`

## pseudocode

```c

```

## disassembly

```asm
0xa930  call     class [mscorlib]System.Resources.ResourceManager Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ResourceManager()
0xa935  ldstr    aConnectingtore// "ConnectingToRemoteComputerTitle"
0xa93a  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::resourceCulture
0xa93f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0xa944  ret
```
