# Microsoft.VisualStudio.Setup.CommonResources::get_VsixCannotUninstallOrphanedComponentsError

- ea: `0x3990`
- end: `0x39a5`
- name: `Microsoft.VisualStudio.Setup.CommonResources::get_VsixCannotUninstallOrphanedComponentsError`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x3380`

## string_xrefs

- `0x3995`: `VsixCannotUninstallOrphanedComponentsError`

## pseudocode

```c

```

## disassembly

```asm
0x3990  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.CommonResources::get_ResourceManager()
0x3995  ldstr    aVsixcannotunin// "VsixCannotUninstallOrphanedComponentsEr"...
0x399a  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.VisualStudio.Setup.CommonResources::resourceCulture
0x399f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x39a4  ret
```
